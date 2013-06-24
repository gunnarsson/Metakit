Metakit - Reusable Custom WordPress Meta Boxes
====================================

Metakit is a fork of a project by: [tammyhart](http://github.com/tammyhart)


Latest Updates
-------------

- Fixed the "manage" link bug
- Image and file upload buttons now use the new 3.5 media uploader!


### Fields Included

* Text Input (types: text,tel, email, url, number)
* Textarea
* WYSIWYG Editor
* Single checkbox
* Select and [Chosen](http://harvesthq.github.com/chosen/) select with support for "multiple"
* Radio group
* Checkbox group
* Taxonomy Select box and Checkboxes
* Post select with support for "multiple" and [Chosen](http://harvesthq.github.com/chosen/)
* Post Checkboxes
* jQuery UI Date input
* jQuery UI Slider
* Farbtastic color chooser
* Post Drag and Drop Sort
* Image upload/select
* File upload/select
* Sortable Repeatable area with ability to use any of the above mentioned fields (with caution and reason)

### Notes

Not all fields are covered in the included example, but they are in the [Wiki](https://github.com/tammyhart/Reusable-Custom-WordPress-Meta-Boxes/wiki)


Usage
-----

These files are written from the perspecitve of being used in a theme. 

1. Add the metaboxes directory in your theme or plugin.
2. Include metaboxes/meta_box.php in your functions.php.
4. Use the class to create and add meta boxes to any post type (see Examples section below or the [Wiki](https://github.com/tammyhart/Reusable-Custom-WordPress-Meta-Boxes/wiki)
)


Examples
--------

### Create an array that contains the field data (full examples of each filed type found in inc/sample.php)

	$prefix = 'sample_';
	
	$fields = array(
		array( // Text Input
			'label'	=> 'Text Input', // <label>
			'desc'	=> 'A description for the field.', // description
			'id'	=> $prefix.'text', // field id and name
			'type'	=> 'text' // type of field
		),
		array( // Textarea
			'label'	=> 'Textarea', // <label>
			'desc'	=> 'A description for the field.', // description
			'id'	=> $prefix.'textarea', // field id and name
			'type'	=> 'textarea' // type of field
		)
	);

### Instantiate the class with all required variables

	/**
	 * Instantiate the class with all variables to create a meta box
	 * var $id string meta box id
	 * var $title string title
	 * var $fields array fields
	 * var $page string|array post type to add meta box to
	 * var $js bool including javascript or not
	 */
	$sample_box = new custom_add_meta_box( 'sample_box', 'Sample Box', $fields, 'post', true );
