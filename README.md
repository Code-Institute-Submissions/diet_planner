# diet_planner
# Aleksandra Kula - Diet Planner

Code Institute, Data Centric Development 2019/2020

# Project purpose

Promote good eating and sharing great recipes with others by providing easy to use cookbook where good recipes can be found easily as well as edited where necessary. Website lets not only to view a single recipe but also to set a plan for the whole week, print it out and prepare a shopping list that makes preparations more convenient. 

As a developer purposes of creating this website is to learn how to implement interactive frontend on top of backend written in Python and how to manage data persistance with MongoDB.

## Demo 

Live demo can be found here: https://best-diet-planner.herokuapp.com/

![](screenshots/diet_planner_screen.png)

## Wireframes
Wireframes are available [here](https://github.com/OlaQla/diet_planner/tree/master/diet_plan_wireframes)

## UX 
- In my design of user experience I chose to use intense colors to attracts intense emotions. Green connotes eco-friendliness, healthy. Red and yellow are the chief food colors, evoking the tastebuds and stimulating the appetite. Both red and yellow are also effective at grabbing attention. 

    - ![#5cb85c](https://placehold.it/15/5cb85c/000000?text=+) `#5cb85c`
    - ![#f0ad4e](https://placehold.it/15/f0ad4e/000000?text=+) `#f0ad4e`
    - ![#5bc0de](https://placehold.it/15/5bc0de/000000?text=+) `#5bc0de`
    - ![#d9534f](https://placehold.it/15/d9534f/000000?text=+) `#d9534f`

## Pages role and functionality: 

### Home

It is a default and landing page with purpose of welcoming user and providing navigation to other functionality. 

### CookBook

Page listing all available dishes with pictures and basic information about a dish. Allows to search for recipes by names and allows user to navigate to a page that allows to create a new recipe. By clicking on any of existing recipes browser is navigated to a recipe detailed view with full recipe, list of ingredients and an option to futher edit existing recipe. From details view recipes can be edited or deleted. In add / edit recipe page by clicking on existing recipe photo or placeholder image user can select other from a list of photos available in applications s3 bucket to uplaod and select a photo.

### Diet plan

Along with the cookbook it's the core functionality of the application. Diet plan page contains a carousel with each carousel item being one day in a week containing one empty field for each dish category. By clicking one of the fields user is presented a popup allowing to browse for recipes by either scrolling through the list or by using provided search for searching by a substring in recipe title. To refine search user can use provided tags to add / remove tags used for refining search results. Once user is happy with weekly dish selection application provides and option to prepare a printed version of combined recipes list with required ingredients and how to prepare the disher for the whole week. This page also provides an option to prepare weekly shopping list based on user selections. Presented list contains aggregated list of ingredients summing them up as long as used units are the same. 

### Ingredients manager

Page that allows user to Add / Edit / Update / Delete ingredients. 

### Category manager

Page that allows user to Add / Edit / Update / Delete dish categories. 

## Functionality left to implement

The biggest missing functionality I have identified is user authentication. At the moment content can be corrupted by not careful or malicious users, there is also no way to create private content, which would require having implemented authentication as well as restructuring the data for encapsulation purposes.  

 ## Flask API documentation
|Route|Parameters|Http Method|Rendered template|Reads from DB|Writes to DB| Reads from S3|Writes to S3|Description|
---|---|---|---|---|---|---|---|---|
/favicon.ico|N/A|GET|N/A|NO|NO|NO|NO|Loads favicon from static content| 
/diet_planner|N/A|GET|main.html|NO|NO|NO|NO|Renders main application page| 
/get_categories|N/A|GET|get_categories.html|YES|NO|NO|NO|Renders page showing all available dish categories| 
/delete_category|category_id|GET|N/A|NO|YES|NO|NO|Deletes selected dish category|
/edit_category|category_id|GET|edit_category.html|YES|YES|NO|NO|Renders page allowing to enter updated category data|
/update_category|category_id|POST|N/A|NO|YES|NO|NO|Updates dish category with posted data|
/add_category|N/A|GET|add_category.html|NO|NO|NO|NO|Renders page allowing to ender new category data| 
/insert_category|N/A|POST|N/A|NO|YES|NO|NO|Creates new category in database from posted data| 
/get_ingredients|N/A|GET|get_ingredients.html|YES|NO|NO|NO|Renders page with all known ingredients| 
/delete_ingredient|ingredient_id|GET|N/A|NO|YES|NO|NO|Deletes selected ingredient| 
/edit_ingredient|ingredient_id|GET|edit_ingredient.html|NO|YES|NO|NO| Renders page allowing to edit data of an existing ingredient| 
/update_ingredient| ingredient_id|POST|N/A|NO|YES|NO|NO|Updates selected ingredient with posted data| 
/add_ingredient|N/A|GET|add_ingredient.html|NO|NO|NO|NO|Renders page allowing user to enter data of a new ingredient| 
/insert_ingredient|N/A|POST|N/A|NO|YES|NO|NO|Created new ingredient in database from posted data| 
/get_recipes|N/A|GET|get_recipes.html|YES|NO|NO|NO|Renders page showing all available recipes| 
/add_recipe|N/A|GET|add_recipe.html|YES|NO|NO|NO|Renders page allowing user to input data for a new recipe| 
/insert_recipe|N/A|POST|N/A|NO|YES|NO|NO|Inserts new recipe into a database from posted data| 
/view_recipe|recipe_id|GET|view_recipe.html|YES|NO|NO|NO|Renders a page showing details of existing recipe| 
/delete_recipe|recipe_id|GET|N/A|NO|YES|NO|NO|Deletes selected recipe from database| 
/edit_recipe|recipe_id|GET|add_recipe.html|YES|YES|NO|NO|Renders a version of add_recipe page that loads existing recipe data and allows for editing the data| 
/add_image|N/A|POST|N/A|NO|NO|NO|YES|Uploads new image to s3 bucket|
/update_recipe|recipe_id|POST|N/A|NO|YES|NO|NO|Updates selected recipe with posted data| 
/diet_plan|N/A|GET|diet_plan.html|YES|NO|NO|NO|Renders a page allowing for creating a weekly diet plan, create a printable version with details of selected dishes and to create an aggregated view of weekly shopping necessary| 
/images|N/A|GET|N/A|NO|NO|YES|NO|Get all images available in s3 bucket| 
 




## Technologies

1. HTML 5
- Document structure definition
2. Bootstrap
-  Pages elements layout, element styling and interactive componenst
3. CSS3 
- tuning bootstrap styles and layouts
4. JavaScrit/jQuery
- Interactive elements implementation, data loading and preprocessing
5. Python
- backend handlers: loading, saving and processing data
6. Jinja templates
- templating engine for backend web page composition
7. Mongodb
- data persistance
9. Flask
- web application structure
10. Heroku
- Application hosted on Heroku
11. Git 
- Code Version Control
11. Amazon S3
- image persistance and delivery
10. Am I Responsive
- Testing responsiveness of the website
11. Balsamiq Mockups 
- Creating wireframes

   
## Testing 

### Automated Testing

The following validation services were used to check the validity of the code:

  - W3C Markup Validation Service was used to validate HTML.

  - W3C CSS validation was used to validate CSS.

  - JSHint was used to validate JavaScript.

### Manual Testing

- Website was tested manually using multiple browsers.
- Each html file was tested in multiple screen resolution and in mobile device modes, available in browsers developer tools. 
- All links have been manually tested to ensure that they are pointing to the correct destination. 
- Checked if all alt attributes are add on any img tag on website and if it describes what’s on it. Screen readers for the blind and visually impaired will read out this text and therefore make image accessible.

Browsers used for testing: 

| Browser name        |
| ------------- |
| Google Chrome |
| Microsoft Edge |
| Opera |
| Mozilla Firefox |


Virtual devices used for responsiveness testing: 

| Device name    |
| ------------- |
| Galaxy S5 |
| Pixel 2 |
| iPhone 5/SE |
| iPad |
| iPad Pro |


## Deployment / Hosting

This site is hosted using free tier of Heroku. It has CI/CD configured to deploy directly from the master branch hosted on Github so the deployed site will update automatically upon new commits to the master branch. For the purpose of deploying application three files were created Procfile containing instruction for dyno to start application, runtime.txt containing version of python to run in virtual machine and requirements.txt listing dependencies that need to be installed alongside application to make it start and run as intended.  

Deployment process involved:

- Create Git repository on GitHub
- Create deployment configuration files: Procfile, runtime.txt, requirements.txt
- Create database in cloud hosted MongoDB
- Create bucket in free tier of AWS S3
- Create application in Heroku
- Put S3 and MongoDB keys in environment variables in Heroku application
- Point heroku application to Github repository master branch
- Commit code and code updates to Git repository on GitHub
- Ensure application works on Heroku 

## Credits

### Content 
Content was manually created using own resources

### Media
The pictures were downloaded from: 
- pixabay.com, 
- pixels.com,
- unsplash.com,

** Purpose of this project is educational **