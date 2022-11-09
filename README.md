
To see the issue is occurring, run:  

```
npm i
npm run package
```

Then check to see if the output bundle includes the `node_gyp_bins` directory and the python3 sym link:

```
find ./out/test-darwin-x64/test.app/Contents -type l | grep node_gyp_bins
#==> ./out/test-darwin-x64/test.app/Contents/Resources/app/node_modules/node-mac-permissions/build/node_gyp_bins/python3
```

If this `python3` symlink is present in the bundle, the app will not pass gatekeeper.