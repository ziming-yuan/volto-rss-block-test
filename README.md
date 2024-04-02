# Testing Volto RSS Block
This repository aims to test [volto-rss-block](https://github.com/RedTurtle/volto-rss-block/) in Plone 6.

## Testing Notes:
### Running
* Backend: `make build`, then `make start`
* Frontend: `make install`, then `yarn start`

### Installing Volto-RSS-Block
**Installation in frontend**
1. Run `yarn add volto-rss-block`.
2. Edit `package.json`:
   
   ```
   "addons": [
      "volto-rss-block"
    ],
   ```
4. Run `yarn add mrs-developer`.
5. Update `mrs.developer.json`:
   
   ```
   {
    "volto-rss-block": {
        "url": "https://github.com/RedTurtle/volto-rss-block/",
        "path": "src",
        "branch": "master"
    }
   }
   ```
6. Run `make develop` to install the addon in src/addons/.
7. Update `jsconfig.json`:
   
   ```
   {
    "compilerOptions": {
        "paths": {
            "volto-rss-block": [
                "addons/volto-rss-block/src"
            ]
        },
        "baseUrl": "src"
    }
   }  
   ```
9. Run `yarn install` and `yarn start`.
   
**Installation in backend**
1. Update `requirements.txt` to install the backend service available in PyPI that can be installed using pip:
   
   ```
      # List of add-ons that are needed.
      redturtle.rssservice
   ```
