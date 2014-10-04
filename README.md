# PolyForce
## Using Polymer components  with Visualforce


To run in your browser:

1. Install the unmanage polymer package from in your org from here  https://na17.salesforce.com/packaging/installPackage.apexp?p0=04to000000033gx

2. Create a new visualforce page and turn the follow attributes off 
   ```
      <apex:page showChat="false" showHeader="false" standardStylesheets="false" >
   ``` 
   
3.  Link Javascript CDN resources for Polymer.js and Polyfill.js and static resource called  mobile-UI-HTML which will help     
    querying Salesforce
   ```
    <apex:page showChat="false" showHeader="false" standardStylesheets="false" >
    <script src="//cdnjs.cloudflare.com/ajax/libs/polymer/0.3.3/polymer.js"></script> 
    <script src="//cdnjs.cloudflare.com/ajax/libs/polymer/0.3.3/platform.js"></script>
   ```
3.  Import data component to query salesforce imported from Salesforce Mobile UI Library   
    Now link Javascript CDN resource to Polymer.js and Polyfill.js and dist folder mobile-UI-HTML component to query salesforce 
   
   ```
    <link rel="import" href="{!URLFOR($Resource.MobileUIElements, 'dist/mobile-ui-elements.html')}"/>
    
   ```
##Start using charting component in Visualforce: 


1. Import charting component (installed through unmanaged package) on your page
   
   ```
      <link rel="import" href="/apex/force_ui_amchart"/>
   ```
2. Start using it 
   
   ```
   ##<b>Sample Donut Chart : </b><br/>
    <force-amchart charttype="donut" sobject="Opportunity" titlefield="Name" valuefield="Amount"       
    limitResults="50"></force-amchart>
   ```

##Supported Attributes : 
   
   ###We have built chart components that support four key attributes

   ```
   Charttype : (supported) donut, pie, pielengend, bar, bar_rotate, pyramid, barline
   sObject : (supported) salesforce standard object
   titlefield : Stirng (fieldname) (x-component)
   valuefield : String (fieldname) (y-component)
   limitResults: Limit the result (integer)
   orderby = DESC
   ```
##Visualforce Page for Pie Chart  : 
   
   ```
   <apex:page showChat="false" showHeader="false" standardStylesheets="false" >
    <script src="//cdnjs.cloudflare.com/ajax/libs/polymer/0.3.3/polymer.js"></script> 
    <script src="//cdnjs.cloudflare.com/ajax/libs/polymer/0.3.3/platform.js"></script>
    <link rel="import" href="{!URLFOR($Resource.MobileUIElements, 'dist/mobile-ui-elements.html')}"/>
    <link rel="import" href="/apex/force_ui_amchart"/>
  
    <!-- Using charting component after package installation --> 
    <b>Sample Donut Chart : </b><br/>
    <force-amchart charttype="donut" sobject="Opportunity" titlefield="Name" valuefield="Amount" 
    limitResults="50"></force-amchart>
   ```
###Hang tight for npm and bower package and upcoming components 

##Related Resource 
   1. How create Polymer Components in miunutes : http://www.oyecode.com/2014/07/google-polymer-create-your-first-custom.html
   2. Design Salesforce UI with drag and drop using Salesforce Polymer Pack for Mobile : Check out embedded video driven by 
      Akhilesh Gupta and Eugiene Oaksman in San Francisco HTML5 meetup at 
      http://www.oyecode.com/2014/07/how-to-use-google-polymer-with.html
   3. Salesforce Mobile UI/ Polymer Package official library - https://github.com/ForceDotComLabs/mobile-ui-elements
   4. What is Polymer : Presentation by Eric Bidelman 
   5. What is a Webcomponent : http://webdesign.tutsplus.com/articles/how-to-create-your-own-html-elements-with-web-components--cm
      s-21524
   6. Sharing Polymer Component : http://code.tutsplus.com/tutorials/sharing-polymer-components-part-2--cms-21497
   7. Interacting with Google Service with nothing but just HTML using Polymer : https://www.youtube.com/watch?v=eORqFaf_QzM
