.PHONY: css
css:
	mkdir -p bundle
	postcss --watch --use autoprefixer --use postcss-import css/app.css --output bundle/app.css

.PHONY: server
server:
	browser-sync start --server --files='index.html,test.html,bundle/app.css,build/app.js,js/app.js'
.PHONY: js
js:
	webpack --watch --progress js/app.jsx build/app.js --module-bind "js=babel" --module-bind "jsx=babel"
.PHONY: all
all:
	(make css & make js & make server & wait)

.PHONY: clean
clean:
	rm -r bundle