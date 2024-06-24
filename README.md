# vue-display-cards ![CI](https://github.com/display-labs/vue-display-cards/actions/workflows/ci.yml/badge.svg) ![npm](https://img.shields.io/npm/v/vue-display-cards) ![license](https://img.shields.io/npm/l/vue-display-cards) ![downloads](https://img.shields.io/npm/dm/vue-display-cards)

Various modern card components for Vue.
Designed to be production-ready with minimal setup. Provide your content and you're good to go.

## Live demo
https://display-labs.github.io/vue-display-cards

## npm
https://www.npmjs.com/package/vue-display-cards

## Installation and usage example
Minified and gzipped bundle size: 48kb.
```bash
$ npm install --save vue-display-cards
```

```javascript
import { ProfileCard } from 'vue-display-cards';

export default {
  components: { ProfileCard },
  template: `<ProfileCard
    hover-effect
    link='https://github.com/display-labs'
    cover-image='https://i.imgur.com/vRAtM3i.jpg'
    avatar='https://i.imgur.com/XJxqvsU.jpg'
    full-name='Sarah Chen'
    role='Senior Frontend Engineer'
  />`
}
```

## Development
### Getting started
After cloning the repo, run the following commands to start the development server with hot reload:

```shell
$ npm install
$ npm run dev
```

### Running tests
The project includes comprehensive test coverage. To run the test suite:

```shell
$ npm test
```

### Contributing
We welcome all contributions. You can enhance existing cards or introduce completely new card types.

## Card types
All cards support these additional props:

- `custom-class` to apply additional CSS classes
- `hover-effect` (boolean) to enable animation on hover
- Other props are passed to the root element for custom event handlers

### Profile cards
Cards for displaying user profiles or team members.

| attribute    | type        | description                                                                                             |
|--------------|-------------|---------------------------------------------------------------------------------------------------------|
| link         | string/null | optional URL for card navigation                                                                        |
| cover-image  | string      | URL for the header background image                                                                     |
| avatar       | string      | URL for the profile avatar image                                                                        |
| full-name    | string      | person's full name                                                                                      |
| role         | string      | person's job role                                                                                       |
| metrics      | array/null  | optional array with 'label' and 'value' for card footer                                                 |

![Profile card](https://i.imgur.com/2QMNcjY.png)

### Product showcase cards
Cards for e-commerce product displays.

| attribute    | type    	| description                                                   |
|-------------|-----------------|---------------------------------------------------------------|
| images      | array   	| array of product image URLs                                   |
| price       | string  	| displayed price in top-left corner                            |
| product-name| string  	| product title                                                 |
| description | string  	| brief product description                                     |
| rating      | number 	| product rating (0-5) - upcoming feature                       |
| action-url  | string  	| URL for primary action button                 			|
| button-label| string/null     | optional button text				        	|

![Product card](https://i.imgur.com/qDCMzwV.png)

### Content cards with tags
Cards for content with categorization tags.

| attribute   | type        | description                                                                                                           |
|-------------|-------------|-----------------------------------------------------------------------------------------------------------------------|
| link        | string/null | optional navigation URL                                                                                               |
| thumbnail   | string      | URL for content thumbnail and background                                                                              |
| title       | string      | content title                                                                                                         |
| description | string      | brief content summary                                                                                                 |
| tags        | array/null  | array of strings displayed as pill tags                                                                               |

![Content card](https://i.imgur.com/SyakUBF.png)

### Flip cards
Cards with front and back sides that flip on hover. Accepts any Vue components.

This card uses a different structure with nested components:

  ```javascript
    <FlipCard>
        <FlipCardBack>
			  Back side content
		  </FlipCardBack>
		  <FlipCardFront>
			  Front side content
		  </FlipCardFront>
	</FlipCard>
  ```

Check the demo for working examples.

### Recipe display cards
Cards for food recipes with preparation details.

| attribute   | type         | description                                                            |
|-------------|--------------|------------------------------------------------------------------------|
| link        | string/null  | optional navigation URL                                                |
| image       | string       | URL for recipe image                                                   |
| title       | string       | recipe name                                                            |
| duration    | string       | preparation time                                                       |
| servings    | string       | portion size information                                               |

![Recipe card](https://i.imgur.com/PfE6Cf0.png)

### Article header cards
Cards for news articles and blog posts.

| attribute | type        | description                                               |
|-----------|-------------|-----------------------------------------------------------|
| link      | string/null | optional article URL                                      |
| image     | string      | URL for background image                                  |
| author    | string      | article author name                                       |
| date      | string      | publication date                                          |
| categories| array       | optional array of category tags                           |

![Article card](https://i.imgur.com/3fZKPyS.png)

### Finance cards
Cards for displaying financial data with charts.

| attribute         | type              | description                                                                      |
|-------------------|-------------------|----------------------------------------------------------------------------------|
| asset-name        | string            | Financial asset name                                                             |
| current-price     | string            | Current price (formatted by consumer)                                            |
| icon              | any               | Asset icon component                                                             |
| symbol            | string            | Trading symbol                                                                   |
| change            | string            | Price change percentage                                                          |
| direction         | number(-1, 0, 1)  | Trend direction indicator                                                        |
| chart-color       | string            | Chart line color                                                                 |
| chart-data        | array\[number\]   | Array of numerical values for chart                                              |

![Finance card](http://i.imgur.com/7yGpFnw.png)

### Payment method cards
Cards representing credit/debit cards with flip animation.

| attribute         | type           | description                                                                                                                                                      |
|-------------------|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| background        | string         | CSS background value. Default background used if not provided                                                                                                    |
| pattern           | string/null    | Background pattern option: "worldMap", "geometric", or "wave". Null for no pattern                                                                               |
| provider-icon     | string/component| Payment provider icon - URL or Vue component                                                                                                                     |
| card-number       | string         | Payment card number                                                                                                                                              |
| expiry            | string         | Card expiration date                                                                                                                                             |
| cardholder        | string         | Cardholder name                                                                                                                                                  |
| security-code     | string         | Security code displayed on card back                                                                                                                             |

![Payment cards](http://i.imgur.com/0Nb9K1B.png)
