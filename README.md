Regular bootstrap 0.12 (latest IE8 compatible) with patch from [angular-ui/0.13](https://github.com/angular-ui/bootstrap/commit/a5a82d9be7dc0bd1cfd510bacf9aa411c6efe1bc) (ie9+)  to allow vetoable close events for modal

Steps I did:

````
git clone https://github.com/angular-ui/bootstrap.git
cd bootstrap && git checkout 0.12.1
git cherry-pick a5a82d9be7dc0bd1cfd510bacf9aa411c6efe1bc
npm install && grunt
cd dist/
```

Then, I extracted the content of `dist/` into a new git repo, I C/P the official `package.json` and updated the field `main`.

I pushed and ran `npm install --save networklocum/bootstrap-0.12-patched` into bart
