CWD=$(shell pwd)

NODE=$(CWD)/node_modules


NPM_PACKAGES_JS = \
	$(NODE)/jquery/dist/jquery \
	$(NODE)/bootstrap/dist/js/bootstrap \
	$(NODE)/vue/dist/vue

NPM_PACKAGES_CSS = \
	$(NODE)/bootstrap/dist/css/bootstrap \
	$(NODE)/bootstrap/dist/css/bootstrap-theme

npm:
	npm install

dev: npm clean
	for PKGE in $(NPM_PACKAGES_JS); do \
		ln -sv $$PKGE.js $$PKGE.link.js ; \
	done
	for PKGE in $(NPM_PACKAGES_CSS); do \
		ln -sv $$PKGE.css $$PKGE.link.css ; \
	done

prod: npm clean
	for PKGE in $(NPM_PACKAGES_JS); do \
		ln -sv $$PKGE.min.js $$PKGE.link.js ; \
	done
	for PKGE in $(NPM_PACKAGES_CSS); do \
		ln -sv $$PKGE.min.css $$PKGE.link.css ; \
	done

clean:
	for PKGE in $(NPM_PACKAGES_JS); do \
		$(RM) -v $$PKGE.link.js; \
	done
	for PKGE in $(NPM_PACKAGES_CSS); do \
		$(RM) -v $$PKGE.link.css ; \
	done

fclean: clean
	$(RM) -Rfv $(NODE)

re: fclean npm