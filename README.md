# Anime Character Lookup

## Table of Contents

1. [Introduction](#introduction)
2. [Features](#features)
3. [Technologies Used](#technologies-used)
5. [API Integration](#api-integration)
7. [Installation](#installation)
8. [Contributing](#contributing)
9. [License](#license)

## Introduction

This project is an open-source React application designed to provide information about anime characters. It serves as a learning tool for working with APIs and using TypeScript with React (TSX). Users can search for their favorite anime characters and get detailed information, including their names (both in English and native Japanese), descriptions, images, and the anime they are featured in.

## Features

- Search for anime characters by name
- Display character's full name and native name
- Show character description
- Display character image
- Show the anime from which the character comes
- Responsive and user-friendly interface

## Technologies Used

- **React**: A JavaScript library for building user interfaces.
- **TypeScript**: A typed superset of JavaScript that compiles to plain JavaScript.
- **GraphQL**: A query language for your API, used here to fetch data from the AniList API.
- **AniList API**: A GraphQL-based API to retrieve anime and manga information.


## API Integration

### Querying the API

The project queries the AniList API to fetch data about anime characters. Here is the GraphQL query used:

```graphql
query {
    Character(search: "characterName") {
        name {
            full
            native
        }
        description(asHtml: true)
        image {
            large
        }
        media {
            nodes {
                title {
                    romaji
                }
            }
        }
    }
}
```

### What the Query Returns

The query returns the following data about the character:

- **name**: An object containing:
  - `full`: The full name of the character.
  - `native`: The native (Japanese) name of the character.
- **description**: A description of the character in HTML format.
- **image**: An object containing:
  - `large`: A URL to the large-sized image of the character.
- **media**: An object containing:
  - `nodes`: An array of media (anime/manga) objects, each containing:
    - `title`: An object containing:
      - `romaji`: The romaji (Latin alphabet) title of the media.

## Usage

1. **Search**: Type the name of the anime character you are looking for in the search bar.
2. **Submit**: Press the search button or hit Enter.
3. **View Results**: The application will display the character's name, native name, description, image, and the anime they appear in.

## Installation

To run this project locally, follow these steps:

```sh
  git clone https://github.com/sebilune/character-lookup.git
  cd character-lookup
  npm i
  npm run dev
```
## Contributing

Contributions are welcome! To contribute to this project, please fork the repository and create a pull request with your changes. Ensure that your code adheres to the existing style and conventions and that all tests pass.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
