# GIT > IDE

In **VSCode** is pretty straight foward, but in another [[concepts_ide|IDE]], some tweaks are needed:
1. Having [[git]] configured with the name and email: 
	```shell
	git config --global user.name "Your Name"
	git config --global user.email "your.email@example.com" !! email configured in GitHub
	```
2. Set up credentials [[concepts_caching|caching]]:
	```shell
	git config --global credential.helper store
	```
3. Create a personal access token on GitHub (with it's expiration, scope)



