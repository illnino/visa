1. 当rails中"/assets/defaults.js" not found
> 
    It's most likely because the reference to  
    javascript_include_tag :defaults  
    is still in the application layout. That reference should be changed to  
    javascript_include_tag "application"
        
    http://stackoverflow.com/questions/6359860/rails-3-1rc4-defaults-js-not-found
    

2. Add user_id

```ruby
rails g migration add_user_id_to_travel user_id:integer
```  
	谨记加上user_id:integer 否则就算migrate都不能为table加上新column
       
    
3. inherted_resources

```ruby  
config.app_generators.scaffold_controller = :scaffold_controller
```

4. devise, cancan, rolify gem cant be grouped together

```ruby  
    group :auth do
    	gem 'devise'
    	gem 'cancan'
    	gem 'rolify'
    end
```
    it will fail