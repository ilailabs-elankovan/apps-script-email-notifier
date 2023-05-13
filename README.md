## HOW TO CREATE A FORM AUTOMATICALLY

```gs
function myfunction(){
  // Create new form title "New Form"
  var form = FormApp.create('New Form');
  
  // Add Checkbox Item
  var item = form.addCheckboxItem();
  item.setTitle('What condiments would you like on your hot dog?');
  item.setChoices([
          item.createChoice('Ketchup'),
          item.createChoice('Mustard'),
          item.createChoice('Relish')
      ]);
  
  // Add Multiple Choice Item
  form.addMultipleChoiceItem()
      .setTitle('Do you prefer cats or dogs?')
      .setChoiceValues(['Cats','Dogs'])
      .showOtherOption(true);

  // Add Page Break - "Next" Button
  form.addPageBreakItem()
      .setTitle('Getting to know you');
  
  // Add Date Item
  form.addDateItem()
      .setTitle('When were you born?');

  // Grid Item
  form.addGridItem()
      .setTitle('Rate your interests')
      .setRows(['Cars', 'Computers', 'Celebrities'])
      .setColumns(['Boring', 'So-so', 'Interesting']);

  Logger.log('Published URL: ' + form.getPublishedUrl());
  Logger.log('Editor URL: ' + form.getEditUrl());
}
```

## Reference 

[Tutorial Example](https://developers.google.com/apps-script/reference/forms)
