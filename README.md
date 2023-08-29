Clone this repo, then to produce an artifact and a build info to publish it to artifactory

```
 jf gradlec --repo-resolve=myproj-gradle-dev-virtual --repo-deploy=myproj-gradle-dev-virtual --uses-plugin=false --deploy-maven-desc=true --deploy-ivy-desc=true
```

Then build and publish the artifact and link everything to a build 

```
jf gradle clean build artifactoryPublish  --build-name=my-kts-demo --build-number=1 --project=myproj  
```

and finally publish the buildinfo 

```
jf rt bp my-kts-demo 1 --project=myproj 
```