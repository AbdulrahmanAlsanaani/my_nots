# For Search
## [main resource](https://www.infoq.com/articles/ruby-open-classes-monkeypatching/)
- duck typing
- adapters
- Singleton Classes
## How to safely use Open Classes
- alias
  ```
  class Gateway
    def process(document)
      p "gateway processed document: #{document}"
    end
  end

  Gateway.new.process("hello world") 

    <!-- => gateway processed document: hello world -->

  class Gateway
    alias old_process process
    def process(document)
      p "do something else"
      old_process(document)
    end
  end

  Gateway.new.process("hello world") 

  => do something else
  => gateway processed document: hello world
  ```
- alias_method_chain
- Close on an unbound method
  ```
  class Test
    def test
      :original
    end
  end
  um = Test.instance_method(:test)
  class Test
    def test
      :modified
    end
  end
  t = Test.new
  t.test            #=> :modified
  um.bind(t).call   #=> :original
  ```
  [read more](https://ruby-doc.org/core-2.7.1/UnboundMethod.html)

- Extend a module that redefines the method and uses super
- write expiation
