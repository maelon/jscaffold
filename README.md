## A spa webpack scaffold with asynchronous modules loading

This tool just likes vue-cli, but with new feature: asynchronous modules loading templates.

### installation

```bash
npm install -g jscaffold
```

> be aware:
> node >= 4.0.0 required

### usage

* init

```bash
jscaffold init \<tempate-name\> \<project-name\>
```

`tempate-name`: now just webpack, more template coming soon
`project-name`: blank project name will create project in current directory, or will creat a named directory.

* list

```bash
jscaffold list 
```

This will list the templates available.

### workflow for example:

In a vue project with webpack, we use `require.ensure` to ___split code___ , our templates will build project into modules with a `vinfo.json`.

The `vinfo.json` describes builded version, builded date, and builded ___modules list width chunckhash___ for loading in browser.

The `index.html` in distribute directory will load the `vinfo.json` for ___loading modules list asynchronously in it in sequence___. This is the point.
