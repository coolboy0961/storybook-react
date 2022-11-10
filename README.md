# storybook-react
ReactのプロジェクトにStorybookを導入したサンプル

## トラブルシュッティング

### Storybookの導入
`npx storybook init`
```
🔎 checking possible migrations..
🔎 found a 'eslintPlugin' migration:

╭──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╮
│                                                                                                                                      │
│   We've detected you are not using our eslint-plugin.                                                                                │
│                                                                                                                                      │
│   In order to have the best experience with Storybook and follow best practices, we advise you to install eslint-plugin-storybook.   │
│                                                                                                                                      │
│   More info: https://github.com/storybookjs/eslint-plugin-storybook#readme                                                           │
│                                                                                                                                      │
╰──────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯
? Do you want to run the 'eslintPlugin' migration on your project? › (y/N)
```
eslint-pluginは必須ではないので、いったん `N`を選択する

```
🔎 found a 'npm7' migration:

╭───────────────────────────────────────────────────────────────────────────────────────────────────╮
│                                                                                                   │
│   We've detected you are running npm 8.1.0                                                        │
│    which has peer dependency semantics which Storybook is incompatible with.                      │
│                                                                                                   │
│   In order to work with Storybook's package structure, you'll need to run `npm` with the          │
│   `--legacy-peer-deps=true` flag. We can generate an `.npmrc` which will do that automatically.   │
│                                                                                                   │
│   More info: https://github.com/storybookjs/storybook/issues/18298                                │
│                                                                                                   │
╰───────────────────────────────────────────────────────────────────────────────────────────────────╯
? Do you want to run the 'npm7' migration on your project? › (y/N)
```
npm7 migrationをやらないと、エラーになるので、`y`を選択する

Storybookのinitは無事完了する

`npm run storybook`でstorybookを起動すると、下記エラーが発生
```
ERROR in 
src/stories/Button.stories.tsx
  Line 1:26:   Delete `;`                                                                              prettier/prettier
  Line 2:1:    '@storybook/react' should be listed in the project's dependencies, not devDependencies  import/no-extraneous-dependencies
  Line 2:65:   Delete `;`                                                                              prettier/prettier
  Line 4:34:   Delete `;`                                                                              prettier/prettier
  Line 14:34:  Delete `;`                                                                              prettier/prettier
  Line 17:67:  Prop spreading is forbidden                                                             react/jsx-props-no-spreading
  Line 17:79:  Delete `;`                                                                              prettier/prettier
  Line 19:41:  Delete `;`                                                                              prettier/prettier
  Line 24:2:   Delete `;`                                                                              prettier/prettier
  Line 26:43:  Delete `;`                                                                              prettier/prettier
  Line 29:2:   Delete `;`                                                                              prettier/prettier
  Line 31:39:  Delete `;`                                                                              prettier/prettier
  Line 35:2:   Delete `;`                                                                              prettier/prettier
  Line 37:39:  Delete `;`                                                                              prettier/prettier
  Line 41:2:   Delete `;`                                                                              prettier/prettier

src/stories/Button.tsx
  Line 1:26:   Delete `;`                                                                                                                                               prettier/prettier
  Line 2:22:   Delete `;`                                                                                                                                               prettier/prettier
  Line 8:3:    propType "primary" is not required, but has no corresponding defaultProps declaration                                                                    react/require-default-props
  Line 8:20:   Delete `;`                                                                                                                                               prettier/prettier
  Line 12:3:   propType "backgroundColor" is not required, but has no corresponding defaultProps declaration                                                            react/require-default-props
  Line 12:27:  Delete `;`                                                                                                                                               prettier/prettier
  Line 16:3:   propType "size" is not required, but has no corresponding defaultProps declaration                                                                       react/require-default-props
  Line 16:38:  Delete `;`                                                                                                                                               prettier/prettier
  Line 20:16:  Delete `;`                                                                                                                                               prettier/prettier
  Line 24:3:   propType "onClick" is not required, but has no corresponding defaultProps declaration                                                                    react/require-default-props
  Line 24:23:  Delete `;`                                                                                                                                               prettier/prettier
  Line 30:1:   Prefer default export                                                                                                                                    import/prefer-default-export
  Line 37:23:  Replace `·?·'storybook-button--primary'·:·'storybook-button--secondary';` with `⏎····?·'storybook-button--primary'⏎····:·'storybook-button--secondary'`  prettier/prettier
  Line 41:79:  Replace `'·'` with `⏎········'·'⏎······`                                                                                                                 prettier/prettier
  Line 43:7:   Prop spreading is forbidden                                                                                                                              react/jsx-props-no-spreading
  Line 47:4:   Delete `;`                                                                                                                                               prettier/prettier
  Line 48:2:   Delete `;`                                                                                                                                               prettier/prettier

src/stories/Header.stories.tsx
  Line 1:26:   Delete `;`                                                                              prettier/prettier
  Line 2:1:    '@storybook/react' should be listed in the project's dependencies, not devDependencies  import/no-extraneous-dependencies
  Line 2:65:   Delete `;`                                                                              prettier/prettier
  Line 4:34:   Delete `;`                                                                              prettier/prettier
  Line 13:34:  Delete `;`                                                                              prettier/prettier
  Line 15:67:  Prop spreading is forbidden                                                             react/jsx-props-no-spreading
  Line 15:79:  Delete `;`                                                                              prettier/prettier
  Line 17:42:  Delete `;`                                                                              prettier/prettier
  Line 22:2:   Delete `;`                                                                              prettier/prettier
  Line 24:43:  Delete `;`                                                                              prettier/prettier
  Line 25:20:  Delete `;`                                                                              prettier/prettier

src/stories/Header.tsx
  Line 1:26:   Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 3:34:   Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 4:22:   Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 7:15:   Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 8:2:    Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 11:3:   propType "user" is not required, but has no corresponding defaultProps declaration                                                                                                                                               react/require-default-props
  Line 11:14:  Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 12:22:  Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 13:23:  Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 14:30:  Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 17:1:   Prefer default export                                                                                                                                                                                                            import/prefer-default-export
  Line 17:25:  Replace `·user,·onLogin,·onLogout,·onCreateAccount·` with `⏎··user,⏎··onLogin,⏎··onLogout,⏎··onCreateAccount,⏎`                                                                                                                  prettier/prettier
  Line 21:13:  Replace `·width="32"·height="32"·viewBox="0·0·32·32"·xmlns="http://www.w3.org/2000/svg"` with `⏎··········width="32"⏎··········height="32"⏎··········viewBox="0·0·32·32"⏎··········xmlns="http://www.w3.org/2000/svg"⏎········`  prettier/prettier
  Line 50:20:  Replace `·primary·size="small"·onClick={onCreateAccount}·label="Sign·up"` with `⏎··············primary⏎··············size="small"⏎··············onClick={onCreateAccount}⏎··············label="Sign·up"⏎···········`             prettier/prettier
  Line 56:2:   Delete `;`                                                                                                                                                                                                                       prettier/prettier

src/stories/Page.stories.tsx
  Line 1:26:   Delete `;`                                                                                        prettier/prettier
  Line 2:1:    '@storybook/react' should be listed in the project's dependencies, not devDependencies            import/no-extraneous-dependencies
  Line 2:65:   Delete `;`                                                                                        prettier/prettier
  Line 3:1:    '@storybook/testing-library' should be listed in the project's dependencies, not devDependencies  import/no-extraneous-dependencies
  Line 3:63:   Delete `;`                                                                                        prettier/prettier
  Line 4:30:   Delete `;`                                                                                        prettier/prettier
  Line 13:32:  Delete `;`                                                                                        prettier/prettier
  Line 15:63:  Prop spreading is forbidden                                                                       react/jsx-props-no-spreading
  Line 15:75:  Delete `;`                                                                                        prettier/prettier
  Line 17:43:  Delete `;`                                                                                        prettier/prettier
  Line 19:42:  Delete `;`                                                                                        prettier/prettier
  Line 23:39:  Delete `;`                                                                                        prettier/prettier
  Line 24:76:  Delete `;`                                                                                        prettier/prettier
  Line 25:37:  Delete `;`                                                                                        prettier/prettier
  Line 26:2:   Delete `;`                                                                                        prettier/prettier

src/stories/Page.tsx
  Line 1:26:   Delete `;`                                                                                                                                                                                                                                                                          prettier/prettier
  Line 3:34:   Delete `;`                                                                                                                                                                                                                                                                          prettier/prettier
  Line 4:20:   Delete `;`                                                                                                                                                                                                                                                                          prettier/prettier
  Line 7:15:   Delete `;`                                                                                                                                                                                                                                                                          prettier/prettier
  Line 8:2:    Delete `;`                                                                                                                                                                                                                                                                          prettier/prettier
  Line 10:1:   Prefer default export                                                                                                                                                                                                                                                               import/prefer-default-export
  Line 11:49:  Delete `;`                                                                                                                                                                                                                                                                          prettier/prettier
  Line 26:13:  Replace `·href="https://componentdriven.org"·target="_blank"·rel="noopener·noreferrer"` with `⏎············href="https://componentdriven.org"⏎············target="_blank"⏎············rel="noopener·noreferrer"⏎··········`                                                         prettier/prettier
  Line 32:78:  Replace `·page·states·without⏎··········needing·to·navigate·to·them·in·your·app.·Here·are·some·handy·patterns·for·managing·page⏎·········` with `⏎··········page·states·without·needing·to·navigate·to·them·in·your·app.·Here·are⏎··········some·handy·patterns·for·managing·page`  prettier/prettier
  Line 38:80:  Replace `·such·data·from·the⏎···········` with `⏎············such·data·from·the`                                                                                                                                                                                                    prettier/prettier
  Line 39:13:  `"` can be escaped with `&quot;`, `&ldquo;`, `&#34;`, `&rdquo;`                                                                                                                                                                                                                     react/no-unescaped-entities
  Line 39:18:  `"` can be escaped with `&quot;`, `&ldquo;`, `&#34;`, `&rdquo;`                                                                                                                                                                                                                     react/no-unescaped-entities
  Line 42:81:  Replace `·these·services·out⏎···········` with `⏎············these·services·out`                                                                                                                                                                                                    prettier/prettier
  Line 48:13:  Replace `·href="https://storybook.js.org/tutorials/"·target="_blank"·rel="noopener·noreferrer"` with `⏎············href="https://storybook.js.org/tutorials/"⏎············target="_blank"⏎············rel="noopener·noreferrer"⏎·········`                                         prettier/prettier
  Line 52:13:  Replace `·href="https://storybook.js.org/docs"·target="_blank"·rel="noopener·noreferrer"` with `⏎············href="https://storybook.js.org/docs"⏎············target="_blank"⏎············rel="noopener·noreferrer"⏎··········`                                                     prettier/prettier
  Line 58:79:  Insert `⏎·········`                                                                                                                                                                                                                                                                 prettier/prettier
  Line 59:15:  Replace `·width="10"·height="10"·viewBox="0·0·12·12"·xmlns="http://www.w3.org/2000/svg"` with `⏎············width="10"⏎············height="10"⏎············viewBox="0·0·12·12"⏎············xmlns="http://www.w3.org/2000/svg"⏎·······`                                           prettier/prettier
  Line 72:4:   Delete `;`                                                                                                                                                                                                                                                                          prettier/prettier
  Line 73:2:   Delete `;`                                                                                                                                                                                                                                                                          prettier/prettier

Search for the keywords to learn more about each error.
Child HtmlWebpackCompiler:
                          Asset      Size               Chunks  Chunk Names
    __child-HtmlWebpackPlugin_0  6.26 KiB  HtmlWebpackPlugin_0  HtmlWebpackPlugin_0
    Entrypoint HtmlWebpackPlugin_0 = __child-HtmlWebpackPlugin_0
    [./node_modules/html-webpack-plugin/lib/loader.js!./node_modules/@storybook/core-common/templates/index.ejs] 2.06 KiB {HtmlWebpackPlugin_0} [built]
WARN Force closed manager build
[ESLintError: 
src/stories/Button.stories.tsx
  Line 1:26:   Delete `;`                                                                              prettier/prettier
  Line 2:1:    '@storybook/react' should be listed in the project's dependencies, not devDependencies  import/no-extraneous-dependencies
  Line 2:65:   Delete `;`                                                                              prettier/prettier
  Line 4:34:   Delete `;`                                                                              prettier/prettier
  Line 14:34:  Delete `;`                                                                              prettier/prettier
  Line 17:67:  Prop spreading is forbidden                                                             react/jsx-props-no-spreading
  Line 17:79:  Delete `;`                                                                              prettier/prettier
  Line 19:41:  Delete `;`                                                                              prettier/prettier
  Line 24:2:   Delete `;`                                                                              prettier/prettier
  Line 26:43:  Delete `;`                                                                              prettier/prettier
  Line 29:2:   Delete `;`                                                                              prettier/prettier
  Line 31:39:  Delete `;`                                                                              prettier/prettier
  Line 35:2:   Delete `;`                                                                              prettier/prettier
  Line 37:39:  Delete `;`                                                                              prettier/prettier
  Line 41:2:   Delete `;`                                                                              prettier/prettier

src/stories/Button.tsx
  Line 1:26:   Delete `;`                                                                                                                                               prettier/prettier
  Line 2:22:   Delete `;`                                                                                                                                               prettier/prettier
  Line 8:3:    propType "primary" is not required, but has no corresponding defaultProps declaration                                                                    react/require-default-props
  Line 8:20:   Delete `;`                                                                                                                                               prettier/prettier
  Line 12:3:   propType "backgroundColor" is not required, but has no corresponding defaultProps declaration                                                            react/require-default-props
  Line 12:27:  Delete `;`                                                                                                                                               prettier/prettier
  Line 16:3:   propType "size" is not required, but has no corresponding defaultProps declaration                                                                       react/require-default-props
  Line 16:38:  Delete `;`                                                                                                                                               prettier/prettier
  Line 20:16:  Delete `;`                                                                                                                                               prettier/prettier
  Line 24:3:   propType "onClick" is not required, but has no corresponding defaultProps declaration                                                                    react/require-default-props
  Line 24:23:  Delete `;`                                                                                                                                               prettier/prettier
  Line 30:1:   Prefer default export                                                                                                                                    import/prefer-default-export
  Line 37:23:  Replace `·?·'storybook-button--primary'·:·'storybook-button--secondary';` with `⏎····?·'storybook-button--primary'⏎····:·'storybook-button--secondary'`  prettier/prettier
  Line 41:79:  Replace `'·'` with `⏎········'·'⏎······`                                                                                                                 prettier/prettier
  Line 43:7:   Prop spreading is forbidden                                                                                                                              react/jsx-props-no-spreading
  Line 47:4:   Delete `;`                                                                                                                                               prettier/prettier
  Line 48:2:   Delete `;`                                                                                                                                               prettier/prettier

src/stories/Header.stories.tsx
  Line 1:26:   Delete `;`                                                                              prettier/prettier
  Line 2:1:    '@storybook/react' should be listed in the project's dependencies, not devDependencies  import/no-extraneous-dependencies
  Line 2:65:   Delete `;`                                                                              prettier/prettier
  Line 4:34:   Delete `;`                                                                              prettier/prettier
  Line 13:34:  Delete `;`                                                                              prettier/prettier
  Line 15:67:  Prop spreading is forbidden                                                             react/jsx-props-no-spreading
  Line 15:79:  Delete `;`                                                                              prettier/prettier
  Line 17:42:  Delete `;`                                                                              prettier/prettier
  Line 22:2:   Delete `;`                                                                              prettier/prettier
  Line 24:43:  Delete `;`                                                                              prettier/prettier
  Line 25:20:  Delete `;`                                                                              prettier/prettier

src/stories/Header.tsx
  Line 1:26:   Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 3:34:   Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 4:22:   Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 7:15:   Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 8:2:    Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 11:3:   propType "user" is not required, but has no corresponding defaultProps declaration                                                                                                                                               react/require-default-props
  Line 11:14:  Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 12:22:  Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 13:23:  Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 14:30:  Delete `;`                                                                                                                                                                                                                       prettier/prettier
  Line 17:1:   Prefer default export                                                                                                                                                                                                            import/prefer-default-export
  Line 17:25:  Replace `·user,·onLogin,·onLogout,·onCreateAccount·` with `⏎··user,⏎··onLogin,⏎··onLogout,⏎··onCreateAccount,⏎`                                                                                                                  prettier/prettier
  Line 21:13:  Replace `·width="32"·height="32"·viewBox="0·0·32·32"·xmlns="http://www.w3.org/2000/svg"` with `⏎··········width="32"⏎··········height="32"⏎··········viewBox="0·0·32·32"⏎··········xmlns="http://www.w3.org/2000/svg"⏎········`  prettier/prettier
  Line 50:20:  Replace `·primary·size="small"·onClick={onCreateAccount}·label="Sign·up"` with `⏎··············primary⏎··············size="small"⏎··············onClick={onCreateAccount}⏎··············label="Sign·up"⏎···········`             prettier/prettier
  Line 56:2:   Delete `;`                                                                                                                                                                                                                       prettier/prettier

src/stories/Page.stories.tsx
  Line 1:26:   Delete `;`                                                                                        prettier/prettier
  Line 2:1:    '@storybook/react' should be listed in the project's dependencies, not devDependencies            import/no-extraneous-dependencies
  Line 2:65:   Delete `;`                                                                                        prettier/prettier
  Line 3:1:    '@storybook/testing-library' should be listed in the project's dependencies, not devDependencies  import/no-extraneous-dependencies
  Line 3:63:   Delete `;`                                                                                        prettier/prettier
  Line 4:30:   Delete `;`                                                                                        prettier/prettier
  Line 13:32:  Delete `;`                                                                                        prettier/prettier
  Line 15:63:  Prop spreading is forbidden                                                                       react/jsx-props-no-spreading
  Line 15:75:  Delete `;`                                                                                        prettier/prettier
  Line 17:43:  Delete `;`                                                                                        prettier/prettier
  Line 19:42:  Delete `;`                                                                                        prettier/prettier
  Line 23:39:  Delete `;`                                                                                        prettier/prettier
  Line 24:76:  Delete `;`                                                                                        prettier/prettier
  Line 25:37:  Delete `;`                                                                                        prettier/prettier
  Line 26:2:   Delete `;`                                                                                        prettier/prettier

src/stories/Page.tsx
  Line 1:26:   Delete `;`                                                                                                                                                                                                                                                                          prettier/prettier
  Line 3:34:   Delete `;`                                                                                                                                                                                                                                                                          prettier/prettier
  Line 4:20:   Delete `;`                                                                                                                                                                                                                                                                          prettier/prettier
  Line 7:15:   Delete `;`                                                                                                                                                                                                                                                                          prettier/prettier
  Line 8:2:    Delete `;`                                                                                                                                                                                                                                                                          prettier/prettier
  Line 10:1:   Prefer default export                                                                                                                                                                                                                                                               import/prefer-default-export
  Line 11:49:  Delete `;`                                                                                                                                                                                                                                                                          prettier/prettier
  Line 26:13:  Replace `·href="https://componentdriven.org"·target="_blank"·rel="noopener·noreferrer"` with `⏎············href="https://componentdriven.org"⏎············target="_blank"⏎············rel="noopener·noreferrer"⏎··········`                                                         prettier/prettier
  Line 32:78:  Replace `·page·states·without⏎··········needing·to·navigate·to·them·in·your·app.·Here·are·some·handy·patterns·for·managing·page⏎·········` with `⏎··········page·states·without·needing·to·navigate·to·them·in·your·app.·Here·are⏎··········some·handy·patterns·for·managing·page`  prettier/prettier
  Line 38:80:  Replace `·such·data·from·the⏎···········` with `⏎············such·data·from·the`                                                                                                                                                                                                    prettier/prettier
  Line 39:13:  `"` can be escaped with `&quot;`, `&ldquo;`, `&#34;`, `&rdquo;`                                                                                                                                                                                                                     react/no-unescaped-entities
  Line 39:18:  `"` can be escaped with `&quot;`, `&ldquo;`, `&#34;`, `&rdquo;`                                                                                                                                                                                                                     react/no-unescaped-entities
                                                   prettier/prettier  Line 32:78:  Replace `·page·states·without⏎··········needing·to·navigate·to·them·in·your·app.·Here·are·some·handy·patterns·for·managing·page⏎·········` with `⏎··········page·states·without·needing·to·navigate·to·them·in·your·app.·Here·are⏎··········some·handy·patterns·for·managing·page`  prettier/prettier········suc
  Line 38:80:  Replace `·such·data·from·the⏎···········` with `⏎············such·data·from·the`                                                                                                                                                                                                    prettier/prettier
  Line 39:13:  `"` can be escaped with `&quot;`, `&ldquo;`, `&#34;`, `&rdquo;`                                                                                                                                                                                                                     react/no-unescaped-entities
  Line 39:18:  `"` can be escaped with `&quot;`, `&ldquo;`, `&#34;`, `&rdquo;`                                                                                                                                                                                                                     react/no-unescaped-entities
  Line 42:81:  Replace `·these·services·out⏎···········` with `⏎············these·services·out`                                                                                                                                                                                                    prettier/prettier
  Line 48:13:  Replace `·href="https://storybook.js.org/tutorials/"·target="_blank"·rel="noopener·noreferrer"` with `⏎············href="https://storybook.js.org/tutorials/"⏎············target="_blank"⏎············rel="noopener·noreferrer"⏎·········`                                         prettier/prettier="_blank"
  Line 52:13:  Replace `·href="https://storybook.js.org/docs"·target="_blank"·rel="noopener·noreferrer"` with `⏎············href="https://storybook.js.org/docs"⏎············target="_blank"⏎············rel="noopener·noreferrer"⏎··········`                                                     prettier/prettier
  Line 58:79:  Insert `⏎·········`                                                                                                                                                                                                                                                                 prettier/prettier
  Line 59:15:  Replace `·width="10"·height="10"·viewBox="0·0·12·12"·xmlns="http://www.w3.org/2000/svg"` with `⏎············width="10"⏎············height="10"⏎············viewBox="0·0·12·12"⏎············xmlns="http://www.w3.org/2000/svg"⏎·······`                                           prettier/prettier       
  Line 72:4:   Delete `;`                                                                                                                                                                                                                                                                          prettier/prettier
  Line 73:2:   Delete `;`                                                                                                                                                                                                                                                                          prettier/prettier

Search for the keywords to learn more about each error.]

WARN Broken build, fix the error above.
WARN You may need to refresh the browser.

info => Loading presets
? Would you like to send crash reports to Storybook? › (Y/n)
```
`'@storybook/react' should be listed in the project's dependencies, not devDependencies`で検索したら、下記が出てきた。
https://stackoverflow.com/questions/70585870/eslint-error-storybook-react-should-be-listed-in-the-projects-dependencies
でいった対策を.eslintrcに入れたら、`'@storybook/react' should be listed in the project's dependencies, not devDependencies`エラーがなくなったが、
それ以外のエラーはまだ大量に出ている。

init時に提示されたeslint-plugin-storybookをインストールしていないからではないかと疑う
`npm install --save-dev eslint-plugin-storybook`

それでも変わらなかったので、npx storybook initをやり直して、ガイドに従ってeslint-plugin-storybookをインストールしてみる

それでも変わらなかったので、storybook react eslint errorで検索して、https://stackoverflow.com/questions/67550035/storybook-fails-on-eslint-errors-in-reactを見つける
それで、storybookのeslintチェックを外すように、`DISABLE_ESLINT_PLUGIN=true`をstorybook commandに入れると、
うまく起動できるようになった

起動したら、addon viewが表示されない

`storybook doesn't show addon`でhttps://github.com/storybookjs/storybook/issues/8383が出てきて、下記コマンドで解決
`localStorage.clear()`

### ビジュアルテストの導入
導入
```
npm install --save-dev @storybook/addon-storyshots
```
下記内容のstoryShots.test.tsファイルを作成
```
import initStoryshots from '@storybook/addon-storyshots';

initStoryshots();
```
`npm run test`を実行すると、全部のビジュアルテストが失敗する

エラー
```
TypeError: Cannot read properties of undefined (reading 'current')
```
React 18のみ発生する。

解決方法：
調査したURL
https://github.com/storybookjs/storybook/issues/18431
https://github.com/storybookjs/storybook/issues/19541

https://github.com/storybookjs/storybook/issues/19541
で、試しに
```
"overrides": {
  "react-test-renderer": "18.2.0"
}
```
を入れてみて、
1. add overrides setting in package.json
2. delete node_modules and package-lock.json
3. npm install
4. npm run test
をやると、
```
_interopRequireDefault is not a function
```
エラーが出ました。
ググってみると、下記記事を発見
https://stackoverflow.com/questions/66327197/how-to-fix-typeerror-interoprequiredefault-is-not-a-function-in-create-react-ap
1. add overrides setting in package.json
2. delete node_modules and package-lock.json
3. npm install
4. execute npx jest --clearCache
5. npm run test
で再度やると、うまくいった。