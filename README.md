# How To Create a LiveChat Agent App

LiveChat makes it easy to get up and running with an agent app, the central platform for customer support. For customers, this means the convenience of having a live representative just one-click away through an easy-to-use messaging system. For business owners, this means a centralized service for managing many support agents, with rich analytics to see how customers are interacting with your website.

Consider this your first step in an exciting journey through the LiveChat ecosystem. From setting up your first LiveChat agent app to creating a custom app and monetizing your creation, this guide will introduce you to everything you need to know to get started on the platform, creating meaningful customer experiences with proven results for your business.

## Getting Started

Setting up a LiveChat app requires developers to create an account with LiveChat, as well as a Developer Console account using their LiveChat login details. Navigate to the LiveChat account sign page and enter your name and details to get started with a new account.

From there, we are prompted to install LiveChat via WooCommerce, Google Tag Manager, WordPress, and Shopify, among numerous other 3rd-party plugins. For this guide, we will be using Google’s Firebase platform to get up and running fairly quickly with a basic application and will install LiveChat manually, but feel free to use whatever option fits your needs.

Photo #1

Using Firebase also requires a Firebase account, which developers can sign up for on the Firebase website. Once signed in, select the option to create a new project. Enter a descriptive name for your application and press the submit button. Firebase will then walk you through the setup process, asking if you want to use Google Analytics with your new app.

For simplicity’s sake, we won’t be using analytics in this demonstration. Upon clicking continue, Firebase returns us to their Project Overview page, where we can integrate the service with our application.

Photo #2

Next, we need to create a local directory to house our new application. Switching to the terminal on our local machine, we can navigate to the root directory and use the command `mkdir your-directory-name` to create a new directory. Then, use `cd your-directory-name` to navigate inside of the directory and get started building a basic application.

The Firebase command line tools can be immensely helpful when building out any Firebase application, and we can use the command `curl -sL firebase.tools | bash` to install them on our local machine. This installs the Firebase Command Line Interface (CLI) on our system globally, so we shouldn’t have to worry about installing them again for future projects.

From there, we can use the terminal command `firebase login` to log in to our Firebase account on the command line. After clicking the link returned by Firebase and entering your password when prompted, Firebase should return a “Success!” message that includes the email address for your Firebase account.

Returning to the Firebase console in our browser, we can navigate to our application and select the “web” option to add Firebase to our web app. Enter an app nickname relevant to your project, select “Also set up Firebase hosting for this app,” and click the button to proceed with the registration process.

Next, we need to navigate to the directory of our app on our local machine and run the terminal command `firebase init` to initialize our new application with Firebase. From there, we should be prompted to select which Firebase CLI features you want to use for this project. Use the arrow keys to navigate to Firebase’s “Hosting” option, selecting the option with the space bar and pressing “enter” to submit.

Photo #3

You should then be asked to connect your application’s local directory with its associated project on Firebase. For our purposes, we’ll select the “Use an existing project” option and choose the project we set up earlier. Next, we’ll be prompted to choose an internal directory for our static files and select a central index file to serve as the focal center of our project.

For this demonstration, we’ll use the default options to keep our static files in a directory titled “public” and configure our project as a single-page application with a central `index.html` file as the origin. Selecting the “public” and “yes” options, Firebase should respond by creating a `firebase.json` file in your local directory, as well as a `public` folder containing a single `index.html` file.

Photo #4

Now we can use the terminal command `firebase deploy` to launch our application. Navigate to the URL returned from Firebase to see what we have so far. While still far away from anything close to a finished application, it’s immensely helpful to know that everything is running smoothly with Firebase at this stage.

Photo #5

## Installing a LiveChat Agent App

Remember earlier when we were prompted to install LiveChat? Now that we have a basic application, we can return to the installation page and grab the code needed to integrate LiveChat with our project. Selecting the option to manually install LiveChat, we can copy and paste the provided `<script>` tag into our application.

For complex multi-page applications, this means pasting the provided JavaScript in each page of our project, but because our app currently only has one page at `index.html`, we should be safe simply pasting it there beneath the preexisting HTML. Open the file in your favorite text editor and paste the provided code just above the closing `</body>` tag.

Now we can redeploy our application by entering `firebase deploy` in our terminal. Refreshing our application in the browser, we should see a small chat icon displayed in the lower right corner, with options to write and submit a question to a live support agent.

Photo #6

LiveChat provides a variety of customer service options by default, which can be accessed from your LiveChat dashboard. Support agents can see how many customers are currently viewing the webpage, where those potential customers are based, and numerous details about their browser, operating system, and which pages of your site they have visited.

Agents can also view and respond to customer messages, as well as create tickets to manage those responses. LiveChat also offers a robust Reports system that allows agents to track goals and sales facilitated through LiveChat, with rich metrics to help support agents learn from their customers’ behavior.

While these features are all available from the dashboard of each LiveChat account, we can explore even more options available through LiveChat’s Developer Console. There, developers can create custom apps to manage e-commerce payments, share files from Google Drive, display real-time language translations, and more thanks to the ease and flexibility of LiveChat SDK. Next, we’ll show you how to get up and running with the LiveChat API to start building custom applications tailor-made for the needs of your clients.

## Creating Apps and Widgets in LiveChat’s Developer Console

LiveChat’s Developer Console makes it easy to build incredible apps and widgets, which can be a great addition to the service’s many default features. LiveChat provides a variety of ideas to get developers started, as well as sample apps to show what’s possible with the API. Navigate to your Developer Console to get started creating your first widget.

For now, click on the “Apps” option in the sidebar, where you’ll find the option to create your very first LiveChat application. Select the “Create” option, give your app a descriptive name, and choose the template that best corresponds with your intentions as a developer.

For this demonstration, we’ll be building a custom widget for our support agents to share links with unique text and images suited to customers’ needs. Select the “Agent App Widget” option from the dropdown menu and click “Continue” to proceed.

Photo #7

Now that we’ve created our Agent App Widget, we need to modify the app to actually do something. Inside of the Agent App Widget menu, click the “Edit widget” button to begin making changes to the widget. Here, we can change the Widget Source URL to the URL of the larger application where our plugin is embedded. Copy the Firebase URL and paste in place of the default URL.

Next, we need to navigate to the menu’s “Building Blocks” option to add an App Authorization building block to our application. Because we’re working primarily on the front-end, we want to select the option for “JavaScript app,” pressing “Continue” to navigate forward through the building block process. We want to copy and paste our Firebase URL into the Redirect URI whitelist, pressing the “Add” and “Save changes” buttons to confirm our Redirect URI change.

To update and modify any chat data, we need to include each of the `chats.conversation` options in our access scope. In the section labeled “App scopes and API access,” select all three of the `chats.conversation` options (`chats.conversation--all:rw`, `chats.conversation--my:rw` and `chats.conversation--access:rw`), adding them each to your app and selecting “Save changes.” Before navigating away, be sure to copy the Client Id from this page, which will be needed to ensure our data is passed through the Agent Chat API in a secure manner.

Now it’s time to install our LiveChat app for use in our broader Firebase application. Navigate to the “Display details” section of our menu, where you can enter a short description of your application and provide an image to be used as an icon for the broader app. After saving these changes, select “Private installation” from the menu and click “Install app” to bring the widget to your Firebase application.

Returning to our support agent dashboard, we can now navigate to the current chat, where we’ll find the option to select our newly-created app. Find its icon at the top of the right sidebar to navigate to the link we provided in our widget. While for now it provides a link to our original Firebase application in a smaller window, we will soon replace this link with a custom widget.

Photo #8
 
Ultimately, our custom widget will generate a form for support agents to create rich title cards for customers. To do that, we first need to walk our agent through an authentication process to ensure that they’re logged in. We can use LiveChat’s “Sign in with LiveChat” feature to get up and running with a simple authentication button in a relatively short number of steps.

“Sign in with LiveChat” is installed as part of LiveChat’s Software Development Kit (SDK) library, which we can install with Node Package Manager (NPM) or via Content Delivery Network (CDN) hosting. Because our Firebase project is a small, single-page application, we’ll use CDN, copying the provided `<script>` tag and pasting it inside of the `<head>` tag of each HTML file we want to feature a “Sign in with LiveChat” button. In our case, we’ll create a new HTML file called `second-page.html`, pasting the `<script>` tag inside of the new document’s `<head>` tag.

Photo #9

Next, we need to include the button itself, as well as the “Sign in with LiveChat” button container. Copy and paste the provided `<div>` tag inside the `<body>` of your code. Once you’ve finished, wrap the `<div>` tag in the provided `<a>` tag, which uses JavaScript DOM manipulation to open a pop up window with each click from a user.

Photo #10

Now we need to give our button the correct functionality. Following the next step in the documentation, we need to initialize the SDK in our Firebase application. We can copy and paste the provided `<script>` tag into the `<body>` of our code.

We can now use JavaScript DOM manipulation to hide our “Sign in with LiveChat” button and replace it with the LiveChat widget form. Be sure to replace `"<your_client_id>"` with the client id unique to your app, which can be found in the Authorization section of your Developers Console. Also, don’t forget to set your `access_token` variable to the incoming `data.access_token` from LiveChat.

Photo #11

With our authorization correctly set up, we want to use the Agent Chat API’s web reference to send data submitted through our widget back to the LiveChat API. To do this, we need to create another `<script>` tag, grabbing values submitted to the LiveChat form and assigning them to keys within our `payload` object.

We can then make a POST request to our API that includes our `payload` data. For this example, we’ll be using the Axios library, but feel free to use another HTTP client if you prefer. To use the CDN hosted version of Axios, we will include its `<script>` tag inside of the `<head>` of our file.

More details on POST request endpoints are available in the Web API Methods documentation.

Photo #12

Now we need to use our client id to determine which user will receive our response, and stylize the response for our chat window. Moving to the Agent App SDK documentation, we find two ways to include the Agent App SDK in our project: Node Package Manager (NPM) or Universal Model Definition (UMD) build.

Since we’re building a relatively simple, single-page Firebase application, we can copy the UMD option and paste it inside of the `<head>` tag in our `second-page.html` file.

Photo #13

Additionally, we also need to create a function that listens for changes to our widget and updates the `chat_id` to reflect the input data. We can use the `.createDetailsWidget()` method provided by the Agent App SDK, passing the widget in as a parameter and modifying the `”customer_profile”` in accordance with our data.

Photo #14

Now we can create a simple HTML form for our support agents to interact with. Using the HTML `<form>` element, we can build out a series of `<input>` elements to correspond with the values used earlier in our payload and a button to handle each `<input>` on submit. Be sure to add a `“livechat-widget-form"` id to the `<form>` element and a default style of `“display:none”`, so we can toggle our form’s visibility after the support agent has been authenticated.

Photo #15

Returning to our terminal, we can use `firebase deploy` to redeploy our Firebase application and see our form in action. Navigate to the URL in your browser, where you should now see the HTML form we created earlier.

To make this `second-page.html` form show up in our widget, we need to return to the Developer Console, select “Agent App Widget,” and change the “Widget Content URL” to the URL of our form. For our example, this would be our Firebase URL plus `second-page.html`.

Photo #16

Support agents should now be able to use the widget to send a stylized link to customers with the submission form. While it doesn’t have any validation or styling, this example shows the basic components of each LiveChat widget. For more on LiveChat’s design system, be sure to check out the full documentation.

## Monetizing Your Apps

In addition to creating your own custom apps and widgets, you can also monetize these components directly within the LiveChat ecosystem. Apps are bought and sold through the LiveChat Marketplace, which can be found in the LiveChat agent menu and is accessible to anyone with a LiveChat account. With apps from MailChimp, Shopify, Slack, and many others, the LiveChat Marketplace already offers countless solutions to problems that support agents face every day.

While you can rely on preexisting applications in the LiveChat Marketplace, it’s also important to understand how to submit your own apps to be considered for monetization. To start the submission process, navigate to the Developer Console, select the app you wish to monetize, and within its “Building Blocks” menu option, choose the “App Monetization” option and click “Get started.”

Photo #17

Here we’re presented with a variety of choices about how to price our app. We can choose a price, billing cycle, and type of payment for our application, as well as whether or not we want to offer a free trial before developers are asked to purchase the app. Setting the billing cycle to “Just once” removes the option to offer a free trial, while setting it to “Monthly” allows us to offer a free trial.

To publish your app in the LiveChat Marketplace, scroll down to the bottom of the menu and select the “Publish on Marketplace” option. There, we can fill out the remaining details necessary to submit our app to the LiveChat review team. Once submitted, a representative from LiveChat will review your app to ensure that it complies with our standards.

LiveChat encourages developers to test their apps before this submission, and to provide thorough documentation and tutorials for others looking to use their application. The company provides its own design system to help developers match the look and feel of a native LiveChat application, but the design system isn’t required as part of the LiveChat review process.

It’s worth noting that LiveChat takes a small percentage of earnings made through its app sales. App creators earn 80 percent of the revenue for every application sold, while LiveChat earns 20 percent of the income made from each purchase. This allows LiveChat to continue to provide outstanding customer service to each of its clients while 
