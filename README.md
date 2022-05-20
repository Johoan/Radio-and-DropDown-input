# Radio-and-DropDown-input
# text fields are all very well, but we'd really like to give our users different ways to interact with us and answer our questions. Multiple choice inputs like # checkboxes, radio buttons, and dropdown menus are very useful for this.

# Each of these inputs has, of course, a  click  event, but that's not really what we want. What we'd really like is an event that triggers when the user changes their choice — the  change  event. 

# Practice — with checkboxes!
# In this new app, we are going to show the user's choices in real time in the sidebar. Let's start with the checkboxes. Head to CodePen Exercise P2CH1c and follow the instructions below.

 # Add an event listener to the "Sports" checkbox (with id sports-checkbox) that listens for the change event and captures the $event object.

# Now we need to work out if the checkbox is checked or not (seeing as the change event is emitted at every change). To do this, we need the $event.target.checked property (a boolean that returns true if the box is checked, false if not). Let's use that now to add or remove the text-secondary class that grays out the corresponding # <li> element in the sidebar. In your new event listener, set up an if…else statement which checks the $event.target.checked property. If it is true, remove the text-# # secondary class. If it is false, add the text-secondary class.

# Hint: The <ul> element has id hobbies-result. You can use its children property to access its various <li> elements.

# Add similar event listeners to the other two checkboxes which gray out their corresponding <li> elements.
  
  
 # While radio buttons and dropdown menus have a very similar function — they allow the user to pick one option out of many — we handle them slightly differently in # JavaScript, mainly because radio buttons are separate elements while a <select> element is one single element.

Let's start with the radio buttons. We're going to use a new DOM method here to gain access to all of our radio buttons. Add this line:  const radioButtons = document.getElementsByName('transport-method');Remember, to group radio buttons together we give them the same name attribute.

Now we're going to iterate over our radio buttons, assigning each of them a listener which will set the text in the sidebar to the selected value. Remember that radioButtons is an HTMLCollection and not an Array: this means we sadly cannot use funky Array tricks for iteration. Using a simple for loop, add event listeners to each radio button that set the transportResult text content to the emitted value, stored in the $event.target.value property.

Once that's working, let's set up the dropdown menu. Add a change event listener to the <select> element, capture the $event object, and use the $event.target.value property to set the corresponding text in the sidebar.

One last thing: as it stands, when the user loads the page, there is no text in musicResult, despite the fact that Rock is chosen by default. Let's leverage the <select> element's value property (as opposed to the event's value property) to give musicResult the right default text. Set the text content of musicResult to the value of the <select> element.
  
  Form inputs can emit some very interesting and useful events.  So far, we have been using the  change  event, but here are a few other examples:

input  — similar to the  change  event, the  input  event is emitted every time the user changes the input in a text field, and the  $event.target.value  property contains the current content of the text field

focus  /  blur  — when a user clicks or tabs to a form control and it becomes the active control, its  focus  event is emitted; when a user clicks or tabs away from a form control and it is no longer the active control, its  blur  event is emitted
