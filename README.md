
## Scalable URL Shortener


## Overview
URL shortening is used to create shorter aliases for long URLs. We call these shortened aliases “short links.” Users are redirected to the original URL when they hit these short links. Short links save much space when displayed, printed, messaged, or tweeted. Additionally, users are less likely to mistype shorter URLs.

For example, if we shorten the following URL through TinyURL:

```
https://babeljs.io/blog/2020/10/15/7.12.0#class-static-blocks-12079httpsgithubcombabelbabelpull12079-12143httpsgithubcombabelbabelpull12143
```

We would get:

```
https://tinyurl.com/y4ned4ep
```

The shortened URL is nearly one-fifth the size of the actual URL.

Some of the use cases for URL shortening is to optimise links shared across users, easy tracking of individual links and sometimes hiding the affiliated original URLs.

If you haven’t used tinyurl.com before, please try creating a new shortened URL and spend some time going through the various options their service offers. This will help you have a little context to the problem we solve through this project.

### Key points
- Create a group database `groupXDatabase`. You can clean the db you previously used and reuse that.
- This time each group should have a *single git branch*. Coordinate amongst yourselves by ensuring every next person pulls the code last pushed by a team mate. You branch will be checked as part of the demo. Branch name should follow the naming convention `project/urlShortnerGroupX`
- Follow the naming conventions exactly as instructed. The backend code will be integrated with the front-end application which means any mismatch in the expected request body will lead to failure in successful integration.

### Models
- Url Model
```
{ urlCode: { mandatory, unique, lowercase, trim }, longUrl: {mandatory, valid url}, shortUrl: {mandatory, unique} }
```

### POST /url/shorten
- Create a short URL for an original url received in the request body.

### GET /:urlCode
- Redirect to the original URL corresponding

## Caching strategy for faster response and minimizing db calls ( Redis )
- cached frequently used URLs for faster response and less db calls

## Response

### Successful Response structure
```yaml
{
  status: true,
  data: {

  }
}
```
### Error Response structure
```yaml
{
  status: false,
  message: ""
}
```
## Response samples

### Url shorten response
```yaml
{
  "data": {
    "longUrl": "http://www.abc.com/oneofthelongesturlseverseenbyhumans.com",
    "shortUrl": "http://localhost:3000/2WlQej2a",
    "urlCode": "2WlQej2a"
  } 
}

```

