To reproduce:

1. run `yarn install`
2. run `yarn netlify dev -e`
3. Browse to http://localhost:9090/, which will redirect you to http://localhost:9090/us.html, and set the `nf_country` cookie to "`CA`" in JavaScript.
4. Browser to http://localhost:9090/ again.

**Expected behvior:** The user is 301 redirected to http://localhost:9090/canada.html as stipulated by the conditional redirection rule, thanks to the `nf_country` cookie being set to "`CA`".

**Observed behavior:** The user is 301 redirected to http://localhost/us.html, as though the `nf_country` cookie was ignored.

If you run `yarn netlify dev` instead of `yarn netlify dev -e`, the problem goes away.
