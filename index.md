WSO2 Identity Server is 100% Open Source!. We maintain product source code under two GitHub organizations: wso2 and wso2-extensions. These two GitHub organizations carry code related to all WSO2 products, with hundreds of repositories. Sometimes it's hard to find, which jar file comes from which repo. If you would like to contribute to the product, please check this git repo explorer (rEx).

<img src="./image.png" width="640">


### Initial Setup

**Step:1** This relies on Docker, so make sure you have Docker running in your local environment.

**Step:2** Copy rex.sh to a directory where you want to maintain Identity Server git repositories. Alway better to keep this readonly. 
```markdown
wget https://github.com/prabath/wso2is-repo-explorer/raw/master/rex.sh
chmod +x rex.sh
```
### Updates

There are three components need to be updated. The rex.sh - will have minimal updates. Any changes to the core of the tool would require updating the Docker image. The indexes will get updated every four hours.

The tool will detect all the updates and will automatically install them.

### Usage 

Clone all Identity Server related repositories. This is not a required step to run other commands.

```markdown
./rex.sh clone
```
List out all Identity Server related repositories. You can do this, even without cloning all repos.

```markdown
./rex.sh list
```
Update all Identity Server related repositories. If there are any new repos, those will be cloned. 

```markdown
./rex.sh update
```

Find the git repo(s), by the given name. You can do this, even without cloning all repos. The -j option will narrow down the search results for the given jar file name (without version)

```markdown
./rex.sh find org.wso2.carbon.identity.authenticator.mutualssl

./rex.sh find -c org.wso2.carbon.identity.authenticator.mutualssl

./rex.sh find OAuth2TokenValidator

./rex.sh find OAuth2TokenValidator.java

./rex.sh find samlsso
```

Update metadata related to all Identity Server repos. It's better to do an update at least weekly, to find the most up-to-date search results. 

```markdown
./rex.sh update-index
```

List the git repo(s), along with all the corresponding updates since IS 5.2.0.

```markdown
./rex.sh updates
```

List the git repo(s), along with all the updates since IS 5.2.0 for the given Jar file.

```markdown
./rex.sh updates -c  org.wso2.carbon.identity.recovery.ui
```

List the updates along with all the components since IS 5.2.0 for the given repo.

```markdown
./rex.sh updates -r carbon-identity-framework
```
List the updates by all the product versions.

```markdown
./rex.sh updates -p
```
List the updates by the given product version.

```markdown
./rex.sh updates -p IS_5.2.0
```
### Source Code

We welcome contribution from the community. Please check the source code at https://github.com/prabath/wso2is-repo-explorer

