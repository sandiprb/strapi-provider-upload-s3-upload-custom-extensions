# strapi-provider-upload-aws-s3-custom-extensions

## Configurations

This is a fork of official [strapi s3 upload](https://www.npmjs.com/package/strapi-provider-upload-aws-s3)

This package allows you to restrict file upload to s3 from Strapi media library with certain extensions restrictions. Just add `allowedExtensions` array to your upload provide config


**Example**

`./config/plugins.js`

```js
module.exports = ({ env }) => ({
  // ...
  upload: {
    // update provider name
    provider: 'aws-s3-custom-extensions',
    providerOptions: {
      accessKeyId: env('AWS_ACCESS_KEY_ID'),
      secretAccessKey: env('AWS_ACCESS_SECRET'),
      region: env('AWS_REGION'),
      // add allowedExtensions array
      allowedExtensions: ['.png', '.jpg', '.webp'],
      params: {
        Bucket: env('AWS_BUCKET'),
      },
    },
  },
  // ...
});
```
