```sh
alias repourl="git config --get remote.origin.url | sed 's/:/\//' | sed 's/git@/https:\/\//' | sed 's/\.git//' | sed 's/https\//https:/'"
```

Będąc w gitowym repo ten alias skonwertuje Ci adres remote’a na url i możesz łatwo otworzyć repo z cli.
Na jego podstawie możesz otwierać dowolne repozytorium w przeglądarce.
Wrzuć to w bashrc/zshrc, sklonuj repozytoria i zapomnij o ręcznym przeklikiwaniu się przez GitLaba podczas gdy właśnie wchodzi deployment, który wywali CFC do góry nogami.

```sh
alias repourl="git config --get remote.origin.url | sed 's/:/\//' | sed 's/git@/https:\/\//' | sed 's/\.git//' | sed 's/https\//https:/'"
#GITLAB
repo() {
	open -a "Google Chrome" `repourl`
}
repoci() {
	open -a "Google Chrome" `repourl`/pipelines
}
repomrs() {
	open -a "Google Chrome" `repourl`/merge_requests
}
repovars() {
	open -a "Google Chrome" `repourl`/-/settings/ci_cd
}
repohooks() {
	open -a "Google Chrome" `repourl`/hooks
}
```
