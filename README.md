# README

We want to have a habit of making programs which are  easy to understand, simple to maintain, and a piece of cake to extend and reuse in the future.

* rails new project_name
* rails s
* rails s -b $IP -p $PORT

* config/routes.rb
    * root "application#controller_name"
    * root "pages#home"



## controllers

* app/controllers/application_controller.rb
    * def controller_name
        * render plain : "hello world"
        * app/views/controller_name/function_name.html.erb

* app/controllers/controller_name_controller.rb
    * class ControllerName < ApplicationsController  ... end
        * def ... end


## Naming conventions 

* controller names are to be in snake_case
    * define the controller action
* for each controller name, create a folder of the same name under views
    * for each controller action, create a .html.erb in the corresponding directory under views 


## cute stuff

* you can have freedom in routes and have those point to a view of choice, not necessarily of the same route name
* you can edit the html scaffold in /views/layouts/application.html.erb


## Companies

controller name - companies_controller.rb

table name = companies table 
model name - company.rb
class definition Company


## migrations

* rails generate migration table_names
    * the table_name must be in plural form
    * /db/migrate/2018....rb
* def change ... end
    * create_table :table_name do |t| ... end
        * t.string :col_name    # 255 char limit
        * t.text :col_name      # for long texts 
* rails db:migrate
* rake db:migrate
    * /db/development.sqlite3
    * /db/schema.rb     # project database reference 
        * add this to git
    * /db/seeds.rb      # for seeding the db
* rails db:schema:load      # for migrating db to a different server
    * uses /db/schema.rb    # best practice


## comments 

* use # for single line
* use =begin ... =end  for multiline

## rails console
* rails console
    * exit
    * ModelName.all
    * m = ModelName.new()
        * there's a primary key 'id'. what's that for?  :)
        * new() doesn't save to the database
        * m.save    # saves the record to the database
    * [#<Company id: 1, prename: nil, company_name: nil, regtype: nil, streeta: nil, streetb: nil, streetc: nil, city: nil, region: nil, postcode: nil, country: nil>]
        * use the format to create new records from the console
        

## models
* /app/models/model_name.rb
    * model_name has to be the singular version of the table name
    * class ModelName < ApplicationRecord  ... end
    * rails console:  ModelName.all 
        *  SELECT  "companies".* FROM "companies" LIMIT ? 
        
