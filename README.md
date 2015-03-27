# dynamicSelect
Dynamically edit select objects with jquery

##Initialize

###Pre-populated select

####Html

    <select id="theSelect" name="theSelect">
        <option value="value1">html1</option>
        <option value="value2">html2</option>
        <option value="value3">html3</option>
    </select>

####Javascript

    $("#theSelect").dynamicSelect();
    
    
###Empty select

####Html

    <select id="theSelect" name="theSelect"></select>


####Javascript

    options = [
        {
            value: "value1",
            label: "html1"
        },
        {
            value: "value2",
            label: "html2"
        },
        {
            value: "value3",
            label: "html3"
        }
    ];
    $("#theSelect").dynamicSelect(options);
