# Credit-Card-App
This Angular app features a credit card form with real-time validation and input masking. Users can enter details like name, card number, expiration date, and security code, with dynamic error messages for invalid inputs. The app uses reactive forms, custom validators, and a live preview of card details as the form is filled out.
<h1>Credit Card Form Application</h1>

![Card Preview](public/Credit%20card%20preview.png)


<h2>1. App Component</h2>
<p>
  The <strong>AppComponent</strong> acts as the root component, importing essential modules and components like 
  <code>RouterOutlet</code>, <code>ReactiveFormsModule</code>, <code>CardFormComponent</code>, and the 
  <code>NgxMaskDirective</code>. It renders the <code>&lt;app-card-form&gt;</code> component within the container.
</p>

<h2>2. Input Component</h2>
<p>
  This component is responsible for rendering form inputs with labels and validation error messages. 
  It takes in two <code>@Input()</code> properties: <strong>control</strong> (which binds to a <code>FormControl</code>) and 
  <strong>label</strong>.
  Validation errors are handled via the <code>showErrors()</code> method, which checks if the input has been touched and 
  contains errors, displaying the appropriate error messages for <strong>required</strong>, <strong>minlength</strong>, 
  <strong>maxlength</strong>, and <strong>pattern</strong> validation rules.
</p>

<h2>3. Card Form Component</h2>
<p>
  The <strong>CardFormComponent</strong> is the main form handling component, encapsulating the form fields like Name, Card 
  Number, Expiration, and Security Code. It uses the <code>ReactiveFormsModule</code> to handle form state and validation. 
  Each field in the form is bound to its own <code>FormControl</code> with specific validators:
</p>
<ul>
  <li><strong>Name:</strong> required, minLength(3), maxLength(30)</li>
  <li><strong>Card Number:</strong> required, minLength(16), maxLength(16)</li>
  <li><strong>Expiration:</strong> required, custom validation using <code>DateFormControl</code>, pattern for MM/YY format</li>
  <li><strong>Security Code:</strong> required, pattern for a 3-digit numeric code</li>
</ul>
<p>
  The form includes two buttons:
</p>
<ul>
  <li><strong>Submit:</strong> Enabled only if the form is valid, it logs the form submission to the console.</li>
  <li><strong>Reset:</strong> Resets all form controls to null values.</li>
</ul>

<h2>4. Card Component</h2>
<p>
  The <strong>CardComponent</strong> is responsible for displaying the visual representation of the credit card details. 
  The input values from the <code>cardForm</code> fields (name, card number, expiration) are passed to it using 
  <code>@Input()</code> bindings.
</p>

<h2>5. DateFormControl</h2>
<p>
  This is a custom form control extending Angular's <code>FormControl</code> class to handle formatting for the expiration 
  date. It includes:
</p>
<ul>
  <li>Automatic insertion of a forward slash (<strong>/</strong>) after the second character for MM/YY format.</li>
  <li>Prevents invalid characters and restricts input to a maximum of 5 characters.</li>
</ul>

<h2>Key Features:</h2>
<ul>
  <li><strong>Reactive Forms with Validation:</strong> The project uses Angular’s reactive forms, allowing powerful form 
      validation and dynamic input handling.</li>
  <li><strong>Masked Input:</strong> The <code>NgxMaskDirective</code> is integrated to ensure proper formatting for inputs 
      like card number and expiration.</li>
  <li><strong>Custom Form Control:</strong> The <code>DateFormControl</code> demonstrates how to extend 
      <code>FormControl</code> for specific input behaviors like formatting a date string.</li>
  <li><strong>Dynamic Input Handling:</strong> The form is flexible, with the card information dynamically updated in the 
      preview component as users fill out the form.</li>
  <li><strong>Error Handling:</strong> Validation errors are displayed inline, with specific error messages based on the type 
      of validation failure.</li>
</ul>
