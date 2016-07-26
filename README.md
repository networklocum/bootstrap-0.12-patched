Regular bootstrap 0.12 (latest IE8 compatible) with patch from [angular-ui/0.13](https://github.com/angular-ui/bootstrap/commit/a5a82d9be7dc0bd1cfd510bacf9aa411c6efe1bc) (ie9+)  to allow vetoable close events for modal, and typeahead-no-results variable binding

Steps I did:

````
git clone https://github.com/angular-ui/bootstrap.git
cd bootstrap && git checkout 0.12.1
git cherry-pick a5a82d9be7dc0bd1cfd510bacf9aa411c6efe1bc
git cherry-pick 647cdd931c1eecb8c0de6e260363ae76c8f542e6
npm install && grunt
cd dist/
```

Then, I extracted the content of `dist/` into a new git repo, I C/P the official `package.json` and updated the field `main`.

I pushed and ran `npm install --save networklocum/bootstrap-0.12-patched` into bart

### Use

(you can refer to the official documentation at (https://angular-ui.github.io/bootstrap/) )

```javascript
// in your modal's controller
$scope.$on("modal.closing", (event) => {
    if(true) event.preventDefault()
})
```
