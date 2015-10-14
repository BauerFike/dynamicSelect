# dynamicSelect
Dynamically edit select objects with jquery

This plugin binds a select with a cached version of it which can be used to dynamically re-render its options.
Each option is internally stored as an object which can make use of the following properties:

*   label: (String)The text which goes between `<option>` tags.
*   value: (String)The value of the `<option>`.
*   classHtml: (String)The html class value.
*   idHtml: (String)The html id value.
*   disabled: (Boolean)1 to disable the `<option>`.
*   visible: (Boolean)Set to 0 to not render the `<option>`.
*   selected: (Boolean)Set to 1 to render this `<option>` as selected.

#####Example of an option object

        {
            value: "value1",
            label: "html1",
            classHtml: "selectClass",
            idHtml: "selectId",
            disabled: 0,
            visible: 1,
            selected: 0
        }

##Initialize

###Pre-populated select
Binding the plug-in to a select containing a list of options will authomatically cache them and generate the list of option objects for future use.

####Html

    <select id="theSelect" name="theSelect">
        <option value="value1">html1</option>
        <option value="value2">html2</option>
        <option value="value3">html3</option>
    </select>

####Javascript

    $("#theSelect").dynamicSelect();
    
    
###Empty select
It's also possible to initialize the plug-in by directly passing the list of options.

####Html

    <select id="theSelect" name="theSelect"></select>


####Javascript
By passing an array of values, the plugin will automatically generate a list of options with those values set both as value and label.

    $("#theSelect").dynamicSelect(["html1","html2","html3"]);
    
To set more fields on each option an array of objects can be passed instead.

    options = [
        {
            value: "value1",
            label: "html1",
            disabled: 1
        },
        {
            value: "value2",
            label: "html2",
            selected: 1
        },
        {
            value: "value3",
            label: "html3",
            visible: 0
        }
    ];
    $("#theSelect").dynamicSelect(options);


##Options

###updateOptions
Update a property of one or more options.

####Code examples:
Set the option with label "html3" as visible:

	$("#theSelect").dynamicSelect("updateOptions",{"label":"html3"},{"visible":1});
	
More values for the property selector can be passed with an array.

Set the options with values "value2" and "value3" as disabled:

	$("#theSelect").dynamicSelect("updateOptions",{"value":["value2","value3"]},{"disabled":1});
	
Use the selector "all" to edit every option.

Enable every option:

	$("#theSelect").dynamicSelect("updateOptions","all",{"disabled":0});
