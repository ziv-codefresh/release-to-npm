README:

The release-tonpm can be used to publish images to npm. 
The below pipeline configuration demonstrates simple usage:

  deploy_to_npm:
  
    title: Publishing To Npm 
    image: codefresh/relae-to-npm:latest
    commands:    
      - USER=${{USER}} EMAIL=${{EMAIL} PASSWORD=${{PASSWORD} npm run ci-publish     
    when: 
      branch: 
        only: [ master ]


Parameter Reference:

USER- user name of npm account
EMAIL- email of npm account 
PASSWORD - password for nmp account 



 
  Login into your project's NPM registry

  npm login --registry <registry url>
  npm login --registry http://registry.npmjs.org

  Copy the token
  The login step added a line to your ~/.npmrc file looking something like this

  //registry.npmjs.org/:_authToken=00000000-0000-0000-0000-000000000000

  Grab the auth token value 00000000-0000-0000-0000-000000000000 (older NPM proxies or registries like sinopia might have an older different token string format)

  Set the token as CI environment variable
  Go to your CI project settings and add a new variable NPM_TOKEN with the value you have just copied
