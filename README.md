Download Link: https://assignmentchef.com/product/solved-comp-3512-assignment-3
<br>
<strong>COMP 3512 Assignment #3  </strong>




<table width="684">

 <tbody>

  <tr>

   <td width="126">USE CASE NAME:</td>

   <td width="558"><strong>Assignment 2 Functionality </strong></td>

  </tr>

  <tr>

   <td width="126">DESCRIPTION:</td>

   <td width="558">Expected base functionality</td>

  </tr>

  <tr>

   <td width="126">1.</td>

   <td width="558">Your system must have ALL the functionality from assignment 2.</td>

  </tr>

 </tbody>

</table>










<table width="684">

 <tbody>

  <tr>

   <td width="132">USE CASE NAME:</td>

   <td width="552"><strong>JSON Web Services </strong></td>

  </tr>

  <tr>

   <td width="132">DESCRIPTION:</td>

   <td width="552">Implement a simple JSON web service</td>

  </tr>

  <tr>

   <td width="132">1.</td>

   <td width="552">This web service will be a PHP page that simply echoes JSON instead of HTML. I have already provided you with the JSON file printRules.json. Your PHP page simply needs to read it into a string variable using the file_get_contents() function in PHP, set the HTTP Content-Type header to application/json (via the header() function in PHP), and then echo the string.</td>

  </tr>

  <tr>

   <td width="132">2.</td>

   <td width="552">Name your service print-services.php.</td>

  </tr>

 </tbody>

</table>




<table width="684">

 <tbody>

  <tr>

   <td width="132">USE CASE NAME:</td>

   <td width="552"><strong>View Favorites  </strong></td>

  </tr>

  <tr>

   <td width="132">DESCRIPTION:</td>

   <td width="552">Way to view and modify the contents of user’s favorites list.</td>

  </tr>

  <tr>

   <td width="132">1.</td>

   <td width="552">Initiated when user adds an item to the favorites list, or when user clicks any of the view favorites links/buttons.</td>

  </tr>

  <tr>

   <td width="132">2.</td>

   <td width="552">The system will display a listing of the contents of each of the two favorites list. For favorite posts, display small square image and post title; for favorite images, display small square image and image title. Allow the user to modify the favorites list’s contents (i.e., remove an individual item as well as way to quickly remove all items from the list).</td>

  </tr>

  <tr>

   <td width="132">3.</td>

   <td width="552">For the image favorites list, provide a button labeled “Print Favorites”. This button will display a modal dialog box (see Bootstrap documentation) that contains a form that allows the user to “order” prints of each image in the favorites (see <strong>Print Favorites Dialog</strong>).</td>

  </tr>

 </tbody>

</table>







<table width="684">

 <tbody>

  <tr>

   <td width="132">USE CASE NAME:</td>

   <td width="552"><strong>Print Favorites Dialog </strong></td>

  </tr>

  <tr>

   <td width="132">DESCRIPTION:</td>

   <td width="552">This dialog will use JavaScript and/or jQuery to dynamically calculate and display printing costs dynamically for each image in the favorites list based on user-specified options. It must retrieve the data used for the calculations from the printRules.json data retrieved asynchronously from print-services.php via JQuery. I will make modifications to this file when marking to verify your code is using the data retrieved from print-services.php.</td>

  </tr>

  <tr>

   <td width="132">1.</td>

   <td width="552">Initiated when user clicks Print Favorites button. This dynamically-generated form should appear in the Bootstrap modal dialog box displayed within the View Favorites form. The basic form structure with each image in the Favorites lists should be populated by PHP. The &lt;select&gt; lists and calculated values should all be populated by JavaScript/JQuery (JS/JQ). Thus, your page should initiate an AJAX request for print-services.php each time the modal dialog box is displayed.</td>

  </tr>

  <tr>

   <td width="132">2.</td>

   <td width="552">For each image in the cart, allow the user to select a print size (either 5”x7”, 8”x10”,11”x14”, or 12”x18”) a quantity, a stock and a frame. Defaults are: 5”x7”, 1, Matte, None.</td>

  </tr>

  <tr>

   <td width="132">3.</td>

   <td width="552">Display the possible sizes in a &lt;select&gt; list. This must be dynamically generated in JS/JQ from the sizes property in the data retrieved from your web service. Thus, when marking, if I change the name of one of the sizes in the printRules.json file, I should see that changed name in the dialog.</td>

  </tr>

  <tr>

   <td width="132">4</td>

   <td width="552">Display the cost for each image in the cart based on the above values. The base costs for the different sizes are provided in the sizes property in the data retrieved from your web service (for reference, they are $1.50, $2.50, $6.00, and $7.00).For instance, if the user selected 11”x14” and a quantity of 3, then the total for that image would be $18 ($6×3). However, the paper stock and frame selections will change these amounts (see next steps).</td>

  </tr>

  <tr>

   <td width="132">5</td>

   <td width="552">For each image in the cart, allow the user to select the paper stock in a &lt;select&gt; list. This must be dynamically generated in JS/JQ using the stock property in the data retrieved from your web service (either Matte, Glossy, or Canvas).The additional cost for the different paper stocks vary depending on the size and are defined by the costs property array in the data retrieved from your web service. For instance, for the Canvas paper stock, the extra costs are $4 (for 5×7), $4 (for 8×10), $8 (for 11×14), $8 (for 12×18).Thus, if the user selected 11”x14”, canvas stock, and quantity of 3, then total for that image would be $52 ([$6+$8]x3). However, the frame selected will change these amounts (see next item).</td>

  </tr>

 </tbody>

</table>




<table width="684">

 <tbody>

  <tr>

   <td width="132">6</td>

   <td width="552">For each image in the cart, allow the user to select a frame in a &lt;select&gt; list. This must be dynamically generated in JS/JQ using the frame property in the data retrieved from your web service.The additional cost for the frame varies depending on the frame type and print size and are defined by the costs property array in the data retrieved from your web service.For instance, the Expresso Walnut frame costs are $10 (for 5×7), $12 (for 8×10), $16 (for 11×14), $20 (for 12×18). Those costs are for each quantity.Thus, if the user selected 11”x14”, canvas stock, quantity of 3, and Expresso Walnut frame, then the total for that image would be $90 ([$6+$8+$16]x3).</td>

  </tr>

  <tr>

   <td width="132">7</td>

   <td width="552">For each image in the form, there should be a line total value displayed that is generated by JS/JQ. For instance, if the user had selected 11”x14”, canvas stock, quantity of 3, and Expresso Walnut frame for the first image in the favorites list, then the line total of $90 should be displayed at the end of the line.</td>

  </tr>

  <tr>

   <td width="132">8</td>

   <td width="552">Display a subtotal (the sum of each line total) and the shipping cost. The shipping cost varies depending upon the shipper and the amount of the order. This must be dynamically generated in JS/JQ using the shipping  and freeThresholds properties in the data retrieved from your web service.The shipping options defined by the web service are Standard and Express. Provide a radio button to let the user change the shipping option (the default should be Standard). As with everything else on the form, use the data in the JSON file (for instance, I may change the name of Express in the JSON file to ILOVECOMP3512 and I should see that in the form.The cost for shipping varies depending upon whether there are any frames and whether the total quantity of items is above a certain threshold. If there are no frames in the order, standard shipping is $5 and express shipping is $15 (that is a one-time cost regardless of the number). If there are frames and the total frame quantity is less than 10, standard shipping is $15 and express shipping is $25; for framed quantities equal to or above 10, standard shipping is $30 and express shipping is $45. The values for these rules are defined in the shipping  property in the data retrieved from your web service.If the total order before shipping is $100 or above, then standard shipping is free; if the total order is over $300, then express shipping is also free. The values for these rules are defined in the freeThresholds property in the data retrieved from your web service.</td>

  </tr>

  <tr>

   <td width="132">9</td>

   <td width="552">Add a grand total which is subtotal + shipping cost.</td>

  </tr>

  <tr>

   <td width="132">8</td>

   <td width="552">Add an Order button which submits the user print data via a request to order.php. See use case <strong>Submit and Display Order</strong>.</td>

  </tr>

  <tr>

   <td width="132"> </td>

   <td width="552">Remember: the display of all the prices should be dynamic. That is, when the user changes any of the &lt;select&gt; items or the shipping radio button, the prices should update immediately (see diagram … example below isn’t styled all that impressively, so try to make it look better).</td>

  </tr>

 </tbody>

</table>










<table width="684">

 <tbody>

  <tr>

   <td width="132">USE CASE NAME:</td>

   <td width="552"><strong>Submit and Display Order  </strong></td>

  </tr>

  <tr>

   <td width="132">DESCRIPTION:</td>

   <td width="552">Passes user input back to server and displays the result.</td>

  </tr>

  <tr>

   <td width="132">1.</td>

   <td width="552">Initiated when user clicks the order button in the Print Dialog form.</td>

  </tr>

  <tr>

   <td width="132">2.</td>

   <td width="552">The form must make a request to order.php. Your form must send the user’s form data via POST request. This means each user input element (the &lt;select&gt; lists and the quantity &lt;input&gt; element) needs a unique name. The resulting query for the example on the previous page might look like the following:size1=0&amp;paper1=0&amp;frame1=0&amp;qty1=1&amp;size2=2&amp;paper2=2&amp;frame2=2&amp;qty2=3&amp;ship=1Notice that I am using the id properties for the values selected by the user.</td>

  </tr>

  <tr>

   <td width="132">3.</td>

   <td width="552">Display the results received in the query string in some nicely formatted table (e.g., example below isn’t styled all that impressively, so try to make it look better).</td>

  </tr>

 </tbody>

</table>




<strong> </strong>

<table width="684">

 <tbody>

  <tr>

   <td width="132">USE CASE NAME:</td>

   <td width="552"><strong>Frame Preview  </strong></td>

  </tr>

  <tr>

   <td width="132">DESCRIPTION:</td>

   <td width="552">Show larger version of image with selected frame (<strong>only for group of three</strong>).</td>

  </tr>

  <tr>

   <td width="132">1.</td>

   <td width="552">When in the Print Favorites dialog, initiated when the user mouses over the thumbnail image in the form.</td>

  </tr>

  <tr>

   <td width="132">2.</td>

   <td width="552">Add JavaScript preview of the image when the user mouses over an image in the list. This preview should display the version from the small folder along with the title of the image in a nicely displayed &lt;div&gt; that is positioned at the location of the mouse pointer. When the mouse moves off the image, then the pop-over preview should disappear.What is different here (compared to the other image preview hover effects from assign 2), is that you will set the style.borderColor and borderWidth style properties of the image preview based on the color and border properties from the frame object in the JSON data retrieved from the web service (see below).</td>

  </tr>

 </tbody>

</table>

<strong> </strong>