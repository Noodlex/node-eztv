eztv
========
EZTV API module for Node.js

[![Build Status](https://travis-ci.org/moesalih/node-eztv.svg?branch=master)](https://travis-ci.org/moesalih/node-eztv)
[![NPM version](https://badge.fury.io/js/eztv.svg)](http://badge.fury.io/js/eztv)
[![Dependency Status](https://img.shields.io/david/moesalih/node-eztv.svg)](https://david-dm.org/moesalih/node-eztv)
[![npm](https://img.shields.io/npm/dm/eztv.svg?maxAge=2592000)]()

### Install
```bash
npm install eztv --save
```

### Usage
```js
import eztv from 'eztv';

const [firstShow] = await eztv.getShows({ query: 'big bang' });
console.log(firstShow);
```

### Methods
#### `getShows(options, callback)`

Returns a list of shows.

`options`: An optional options object. Currently supports:

- `query`: Show title to search for. If this option is ommited, all shows are returned.

`callback`: A function that takes two parameters:

- `error`: Error object or null.
- `results`: Array of shows. 

Each result is an object:

```json
{
  "id": 23,
  "slug": "the-big-bang-theory",
  "status": "break",
  "title": "The Big Bang Theory",
  "url": "/shows/23/the-big-bang-theory/"
}
```

#### `getShowEpisodes(showId, callback)`

Returns a list of episodes for a given show.

`showId`: The show ID.

`callback`: A function that takes two parameters:

- `error`: Error object or null.
- `results`: Array of episodes.

**Returns:**

```json
{
  "episodes": [...],
  "id": 23,
  "title": "The Big Bang Theory"
}
```

Each episode is an object:

```json
{
  "episodeNumber": 17,
  "episodeNumber2": null,
  "extra": "HDTV x264-LOL",
  "id": 52823,
  "magnet": "magnet:?xt=urn:btih:64DZYZWMUAVLIWJUXGDI...",
  "proper": false,
  "repack": false,
  "seasonNumber": 7,
  "show": "The Big Bang Theory",
  "title": "The Big Bang Theory S07E17 HDTV x264-LOL",
  "torrentURL": "http://piratebaytorrents.info/9715961...",
  "url": "/ep/52823/the-big-bang-theory-s07e17-hdtv-x264-lol/"
}
```
