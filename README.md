# Strapi Plugin Location

This plugin allows users to create location inputs and store latitude and longitude values as geometry types in a PostGIS database. It also provides functionality to filter items based on their location.

## Caution 🖐⚠️

This plugin requires a PostgreSQL database with the PostGIS extension enabled (can be used on that database plugin will enable it for you if it can). Make sure you have a compatible database set up before using this plugin. For development I used postgis docker image from here: https://registry.hub.docker.com/r/postgis/postgis/

## 🙉 What does the plugin do for you?

- ✅ Provides a custom location input field for latitude and longitude values
- ✅ Handles storage of location values as geometry types in a PostGIS database
- ✅ Allows filtering of items based on their location
- ✅ Enables searching for items with the same location or within a specified range

## 🧑‍💻 Installation

1. Install the package with your preferred package manager using one of the commands bellow:

```
npm i @notum-cz/strapi-plugin-location
```
```
yarn add @notum-cz/strapi-plugin-location
```
2. Create or modify file `config/plugins.js` and include the following code snippet:

```
module.exports = ({ env }) => ({
	"location-plugin": {
		enabled:  true,
	},
});
```

## ⚙️ Usage
 - To use a custom input field for latitude and longitude go to the Content-type-builder of your application –> select a desired content-type -> click add another field -> select Cutstom tab -> name the field and hit the save button.
 - To search or filter items based on their location use url parameter `location` in the following formats.

For example for a content-type named *Restaurant* with a field *coords* containing the coordinates the url with the location query would be:

`localhost:1337/api/restaurants?$location[coords]=49.200949303006055,16.623833585841673,5000`

This will return a list of restaurants within 5000m of the point specified by the coordinates. **Replace the collection name *restaurant* and the field name *coords* with the name of your collection name and the field containing the coordinates**. The last number (5000) is range and is not required.
Also this format is supported:

`localhost:1337/api/restaurants?$location[coords][lat]=49.200949303006055&$location[coords][lng]=16.623833585841673`

## 🛣️ Road map
- ✨ Add a leaflet map to display the location
## 🐛 Bugs

We manage bugs through [GitHub Issues](https://github.com/notum-cz/strapi-plugin-location/issues). <br>
If you're interested in helping us, you would be a rock  ⭐.

## 🧔 Authors

The main star: **Dominik Míček** https://github.com/Ballonek <br>
Maintainer: **Ondřej Mikulčík** https://github.com/omikulcik <br>
Project owner: **Ondřej Janošík** <br>

Wanna be here? Open an issue (and solve it), PR or share improvement idea and you will become a listed contributor.

## 🚀 Created with passion by [Notum Technologies](https://notum.cz/en)

- Official STRAPI partner and Czech based custom development agency.
- We're passionate about sharing our expertise with the open source community, which is why we developed this plugin. 🖤

## 🎯 [How can Notum help you with your STRAPI project?](https://notum.cz/en/strapi/)

✔️ We offer valuable assistance in developing custom STRAPI, web, and mobile apps to fulfill your requirements and goals.. <br>
✔️ With a track record of 100+ projects, our open communication and exceptional project management skills provide us with the necessary tools to get your project across the finish line.<br>
📅 To initiate a discussion about your Strapi project, feel free to reach out to us via email at sales@notum.cz. We're here to assist you!