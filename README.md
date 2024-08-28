# Testing Volto RSS Block
This repository aims to test [volto-rss-block](https://github.com/RedTurtle/volto-rss-block/) in Plone 6.

## Observations:
### Bugs
1. Content parsing occasionally fails for certain feeds (as shown in the figure below).
2. "Read more" button doesn't function properly as the links are empty ("#").
![screencapture-localhost-3000-test-2024-04-02-00_27_48](https://github.com/ziming-yuan/volto-rss-block-test/assets/104939482/554f1ad4-21f8-4085-8d32-1723f54b00a3)

## Testing Notes:
### Running
* Backend: `make build`, then `make start`
* Frontend: `make install`, then `yarn start`
* User name: admin
* Password: admin

### Installing Volto-RSS-Block
**Installaion sample frontend and backend**
1. Run `pipx run cookiecutter gh:collective/cookiecutter-plone-starter`
   
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
