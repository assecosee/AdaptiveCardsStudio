![Visual Studio Marketplace Downloads](https://img.shields.io/visual-studio-marketplace/d/asseco.assecoadaptivecardsstudiobeta)
![Visual Studio Marketplace Version](https://img.shields.io/visual-studio-marketplace/v/asseco.assecoadaptivecardsstudiobeta)

![AC Studio ](https://madewithcards.blob.core.windows.net/uploads/29bb3d02-2158-40b8-8420-4dd1f15da34c-acstudio.png)

## Features

With AdaptiveCards Studio you can author cards directly in Visual Studio Code. The Extension automatically detects all Adaptive Cards in your working space and lets you easily edit the card template and sample data.

## Extension Settings

To use the Extension you must configure it first!

This extension contributes the following settings:

-   `acstudio.defaultHostConfig`  : The HostConfig to be used when rendering cards
-   `acstudio.cardTemplatesSupportedLanguages`  : The list of the enabled languages for writting card templates (JSON and YAML are currently supported)

Alpha and experimental:
-   `acstudio.cmsAccessToken`  : (ALPHA) Access Token for the CMS used
-   `acstudio.cmsAccessUrl`  : (ALPHA) URL To the CMS
-   `acstudio.cmsFolder`  : (ALPHA) The Folder where to store temporary files for CMS

## Usage

Open the Adaptive Cards Panel and select a card.... thats all you have to do :)

## Snippets

The Extension comes with various snippets to make authoring cards even easier. Just press ctrl+space anywhere in the AdaptiveCard Json

Snippets for Adaptive Cards Elements:
-   `ac-txt`  : TextBlock with minimum properties
-   `ac-txtfull`  : TextBlock with all properties
-   `ac-col3`  : Columnset with 3 columns
-   `ac-col2`  : Columnset with 2 columns
-   `ac-fctset`  : Factset
-   `ac-ctr`  : Container
-   `ac-img`  : Image

Snippets for Adaptive Card Samples:
-   `ac-empty`  : A new, blank AdaptiveCard
-   `ac-activityUpdate`  : Adaptive Cards Activity Update Sample
-   `ac-expenseReport`  : Adaptive Cards Expense Report Sample
-   `ac-inputForm`  : Adaptive Cards Input Form Sample


## SampleData

When editing templates its a tremendous help to have sample data available. The Extension lets you create and store sample data for your templates easily.

## CMS Usage

The CMS interoperability is in alpha preview, to connect the extension to your self hosted CMS set the config values above to your URL and access token. The only way to get an access token right now is using developer tools in your browser and inspecting the calls when logged in to your CMS. This is an alpha proof of concept and will have a proper login mechanism soon.

## YAML IntelliSense and linting

YAML IntelliSense and linting for Adaptive Cards schema is not provided by the AdaptiveCards Studio extension nor by Visual Studio Code. In order to enable these features you have to install YAML extension for Visual Studio Code by Red Hat.

After the extension is installed, you need to configure the extension. To do this go to `File -> Preferences -> Settings` to open the settings page and search for `yaml`.

Open the settings for the YAML extension and search for `Yaml: Schemas` and click `Edit in settings.json`.

The `settings.json` file will open. you need to search again for the `yaml.schemas` object. If it doesn´t exist yet, you will have to create it.

This property represents a key-value, where the key is the absolute path to the schema file on our system and the value is a glob expression that specifies the files that the schema will be applied.

If we want to apply AdaptiveCards schema file to all YAML files in VS code our configuration would look like this:
```json
"yaml.schemas": {
  "http://adaptivecards.io/schemas/adaptive-card.json": ".yaml",
},
```

Note that this schema will be applied to all YAML files. We could change value for this schema to `.card.yaml` so that this schema is applied only to files that are ending with `.card.yaml`.