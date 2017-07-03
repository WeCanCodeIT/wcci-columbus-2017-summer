# Reviews Site, Full Stack

## Overview

Return to your reviews site from the [previous exercise](../reviews-site) (or create another).

We're going to add categories to reviews. Each category will have one or more reviews (a one to many relationship). Each review will be assigned to one category (a many to one relationship).

Also, we're going to JPA-enable your site so that it writes/reads from an H2 database.


## Tasks

Feel free to use appropriate class names other than `Review` and `Category`, but these instructions will refer to `Review` and `Category`.

- Add the following dependencies to `build.gradle` (or use [Spring Initializr](https://start.spring.io/) to create a new `build.gradle`)
	- [ ] JPA (spring-boot-starter-data-jpa)
	- [ ] H2
- Create a `Category` class that:
	- [ ] is a JPA entity.
	- [ ] contains an instance variable referencing the `Review`s it contains.
	- [ ] configures an appropriate JPA relationship to its reviews.
- Update the `Review` class such that:
	- [ ] it is a JPA entity.
	- [ ] configures a JPA relationship to its associated category.
	- [ ] allows for a description/content/body longer than 255 characters.
- Update your view (templates/html/css) such that:
	- [ ] there is a page that lists review categories, each of which links to the (details) page for a specific category.
	- [ ] there is a page that lists the reviews for a chosen category, each of which links to the (details) page for a specific review.
	- [ ] each review detail page has a link to the page for its category.

### Stretch Tasks

#### Tags

- [ ] Create a `Tag` entity.
- [ ] Update `Review` so that it can have tags associated with it. (One review, many tags.)
- [ ] Display tags on the review details page.
- [ ] Create a page that displays links to all of the reviews associated with a given tag.

##### Stretchier

- [ ] Style your tags list template as a *tag cloud*, making tags which appear more often larger and/or bolder and those that appear less often smaller and/or lower weight.
- [ ] Allow creation and deletion of tags from a review using `<form>` and `<button>` elements along with the appropriate controller method(s).

### Tips

#### Mapping out URLs, Model attributes, view template names, etc

It is good practice to map things out and think them through, using plural and singular names appropriately, or you'll likely be well confused.

Your names, etc will be different, but hopefully this helps with some of the confusion I've seen around naming and what is in the model for a specific view. I'll append model and view to names to help clarify, though we usually wouldn't do this in the wild.

|Page Intent	|URL (mapped via @RequestMapping)	|Model Attribute	|Description of model attribute|View Template name|View will display|
|-----------|--------------------------------		|---------------|------------------------------|------------------|--------------------|
|Categories List|/categories				|"categoriesModel"	|
