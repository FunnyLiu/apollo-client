
# 源码分析

## 文件结构

``` bash
/Users/liufang/openSource/FunnyLiu/apollo-client
├── CHANGELOG.md
├── COLLABORATORS.md
├── CONTRIBUTING.md
├── LICENSE
├── README.md
├── ROADMAP.md
├── codemods
|  ├── ac2-to-ac3
|  |  ├── README.md
|  |  ├── examples
|  |  |  ├── client-and-cache.ts
|  |  |  ├── link-packages.js
|  |  |  └── react-packages.tsx
|  |  ├── imports.js
|  |  └── package.json
|  └── misc
|     └── mockLinkRejection.ts
├── config
|  ├── entryPoints.js
|  ├── helpers.ts
|  ├── jest.config.js
|  ├── prepareDist.js
|  ├── processInvariants.ts
|  ├── resolveModuleIds.ts
|  ├── rewriteSourceMaps.ts
|  ├── rollup.config.js
|  ├── tsconfig.json
|  └── version.js
├── docs
|  ├── README.md
|  ├── gatsby-config.js
|  ├── package-lock.json
|  ├── package.json
|  ├── shared
|  |  ├── apollo-provider.mdx
|  |  ├── mutation-options.mdx
|  |  ├── mutation-result.mdx
|  |  ├── query-options.mdx
|  |  ├── query-result.mdx
|  |  ├── subscription-options.mdx
|  |  └── subscription-result.mdx
|  ├── source
|  |  ├── api
|  |  |  ├── cache
|  |  |  |  └── InMemoryCache.mdx
|  |  |  ├── core
|  |  |  |  ├── ApolloClient.mdx
|  |  |  |  └── ObservableQuery.mdx
|  |  |  ├── link
|  |  |  |  ├── apollo-link-batch-http.mdx
|  |  |  |  ├── apollo-link-context.md
|  |  |  |  ├── apollo-link-dedup.md
|  |  |  |  ├── apollo-link-error.md
|  |  |  |  ├── apollo-link-rest.md
|  |  |  |  ├── apollo-link-retry.md
|  |  |  |  ├── apollo-link-schema.md
|  |  |  |  ├── apollo-link-ws.md
|  |  |  |  ├── introduction.md
|  |  |  |  └── persisted-queries.md
|  |  |  └── react
|  |  |     ├── components.mdx
|  |  |     ├── hoc.mdx
|  |  |     ├── hooks.mdx
|  |  |     ├── ssr.md
|  |  |     └── testing.md
|  |  ├── assets
|  |  |  ├── client-diagrams
|  |  |  |  ├── 1-overview.png
|  |  |  |  ├── 2-map.png
|  |  |  |  ├── 3-minimize.png
|  |  |  |  └── 4-normalize.png
|  |  |  ├── client-mocking
|  |  |  |  ├── cli-clientcheck.png
|  |  |  |  ├── devtools-clientstate.png
|  |  |  |  ├── vscode-autocomplete.png
|  |  |  |  ├── vscode-errors.png
|  |  |  |  └── vscode-typeinfo.png
|  |  |  ├── client-schema.png
|  |  |  ├── devtools
|  |  |  |  ├── apollo-client-devtools
|  |  |  |  |  ├── apollo-devtools-graphiql.png
|  |  |  |  |  ├── apollo-devtools-queries.png
|  |  |  |  |  └── apollo-devtools-store.png
|  |  |  |  ├── devtools.png
|  |  |  |  ├── mutation-init.png
|  |  |  |  ├── mutation-result-data.png
|  |  |  |  ├── mutation-result.png
|  |  |  |  ├── query-init-data.png
|  |  |  |  ├── query-init.png
|  |  |  |  └── query-result.png
|  |  |  └── link
|  |  |     ├── concepts-intro-1.png
|  |  |     ├── concepts-intro-2.png
|  |  |     └── error-request-flow.png
|  |  ├── caching
|  |  |  ├── advanced-topics.mdx
|  |  |  ├── cache-configuration.md
|  |  |  ├── cache-field-behavior.md
|  |  |  ├── cache-interaction.md
|  |  |  └── garbage-collection.mdx
|  |  ├── data
|  |  |  ├── error-handling.mdx
|  |  |  ├── fragments.md
|  |  |  ├── mutations.mdx
|  |  |  ├── queries.mdx
|  |  |  └── subscriptions.mdx
|  |  ├── development-testing
|  |  |  ├── client-schema-mocking.mdx
|  |  |  ├── developer-tooling.md
|  |  |  ├── static-typing.md
|  |  |  └── testing.mdx
|  |  ├── get-started.mdx
|  |  ├── img
|  |  |  ├── client-schema.png
|  |  |  └── githunt.png
|  |  ├── index.mdx
|  |  ├── integrations
|  |  |  ├── integrations.md
|  |  |  ├── react-native.md
|  |  |  └── webpack.md
|  |  ├── local-state
|  |  |  ├── client-side-schema.mdx
|  |  |  ├── local-resolvers.mdx
|  |  |  ├── local-state-management.mdx
|  |  |  ├── managing-state-with-field-policies.mdx
|  |  |  └── reactive-variables.mdx
|  |  ├── logo
|  |  |  ├── favicon.png
|  |  |  ├── icon-apollo-white-200x200.png
|  |  |  ├── large.png
|  |  |  ├── logo-apollo-space.svg
|  |  |  └── square.png
|  |  ├── migrating
|  |  |  ├── apollo-client-3-migration.mdx
|  |  |  └── hooks-migration.md
|  |  ├── networking
|  |  |  ├── advanced-http-networking.md
|  |  |  ├── authentication.mdx
|  |  |  └── basic-http-networking.md
|  |  ├── pagination
|  |  |  ├── core-api.mdx
|  |  |  ├── cursor-based.mdx
|  |  |  ├── key-args.mdx
|  |  |  ├── offset-based.mdx
|  |  |  └── overview.mdx
|  |  ├── performance
|  |  |  ├── babel.md
|  |  |  ├── optimistic-ui.mdx
|  |  |  ├── performance.mdx
|  |  |  └── server-side-rendering.mdx
|  |  ├── template.md
|  |  └── why-apollo.mdx
|  └── static
|     └── _redirects
├── examples
|  └── bundling
|     ├── README.md
|     ├── bundlesize.sh
|     ├── no-tree-shaking
|     |  ├── rollup-ac2
|     |  |  ├── README.md
|     |  |  ├── package-lock.json
|     |  |  ├── package.json
|     |  |  ├── public
|     |  |  |  ├── favicon.ico
|     |  |  |  ├── index.html
|     |  |  |  └── js
|     |  |  ├── rollup.config.js
|     |  |  └── src
|     |  |     ├── App.js
|     |  |     └── index.js
|     |  ├── rollup-ac3
|     |  |  ├── README.md
|     |  |  ├── package-lock.json
|     |  |  ├── package.json
|     |  |  ├── public
|     |  |  |  ├── favicon.ico
|     |  |  |  ├── index.html
|     |  |  |  └── js
|     |  |  ├── rollup.config.js
|     |  |  └── src
|     |  |     ├── App.js
|     |  |     └── index.js
|     |  └── rollup-ac3-no-react
|     |     ├── README.md
|     |     ├── package-lock.json
|     |     ├── package.json
|     |     ├── public
|     |     |  ├── favicon.ico
|     |     |  ├── index.html
|     |     |  └── js
|     |     ├── rollup.config.js
|     |     └── src
|     |        └── index.js
|     └── tree-shaking
|        ├── rollup-ac2
|        |  ├── README.md
|        |  ├── package-lock.json
|        |  ├── package.json
|        |  ├── public
|        |  |  ├── favicon.ico
|        |  |  ├── index.html
|        |  |  └── js
|        |  ├── rollup.config.js
|        |  └── src
|        |     ├── App.js
|        |     └── index.js
|        ├── rollup-ac3
|        |  ├── README.md
|        |  ├── package-lock.json
|        |  ├── package.json
|        |  ├── public
|        |  |  ├── favicon.ico
|        |  |  ├── index.html
|        |  |  └── js
|        |  ├── rollup.config.js
|        |  └── src
|        |     ├── App.js
|        |     └── index.js
|        ├── rollup-ac3-no-react
|        |  ├── README.md
|        |  ├── package-lock.json
|        |  ├── package.json
|        |  ├── public
|        |  |  ├── favicon.ico
|        |  |  ├── index.html
|        |  |  └── js
|        |  ├── rollup.config.js
|        |  └── src
|        |     └── index.js
|        └── webpack-ac3
|           ├── README.md
|           ├── package-lock.json
|           ├── package.json
|           ├── public
|           |  ├── favicon.ico
|           |  └── index.html
|           └── src
|              ├── App.js
|              └── index.js
├── netlify.toml
├── package-lock.json
├── package.json
├── renovate.json
├── src
|  ├── __tests__
|  |  ├── ApolloClient.ts
|  |  ├── __snapshots__
|  |  |  ├── ApolloClient.ts.snap
|  |  |  ├── client.ts.snap
|  |  |  ├── exports.ts.snap
|  |  |  ├── graphqlSubscriptions.ts.snap
|  |  |  └── mutationResults.ts.snap
|  |  ├── client.ts
|  |  ├── exports.ts
|  |  ├── fetchMore.ts
|  |  ├── graphqlSubscriptions.ts
|  |  ├── local-state
|  |  |  ├── __snapshots__
|  |  |  |  └── general.ts.snap
|  |  |  ├── export.ts
|  |  |  ├── general.ts
|  |  |  ├── resolvers.ts
|  |  |  └── subscriptions.ts
|  |  ├── mutationResults.ts
|  |  ├── optimistic.ts
|  |  └── subscribeToMore.ts
|  ├── cache
|  |  ├── core
|  |  |  ├── __tests__
|  |  |  |  └── cache.ts
|  |  |  ├── cache.ts
|  |  |  └── types
|  |  |     ├── Cache.ts
|  |  |     ├── DataProxy.ts
|  |  |     └── common.ts
|  |  ├── index.ts
|  |  └── inmemory
|  |     ├── __tests__
|  |     |  ├── __snapshots__
|  |     |  |  ├── cache.ts.snap
|  |     |  |  ├── entityStore.ts.snap
|  |     |  |  ├── fragmentMatcher.ts.snap
|  |     |  |  ├── policies.ts.snap
|  |     |  |  └── writeToStore.ts.snap
|  |     |  ├── cache.ts
|  |     |  ├── diffAgainstStore.ts
|  |     |  ├── entityStore.ts
|  |     |  ├── fragmentMatcher.ts
|  |     |  ├── helpers.ts
|  |     |  ├── optimistic.ts
|  |     |  ├── policies.ts
|  |     |  ├── readFromStore.ts
|  |     |  ├── recordingCache.ts
|  |     |  ├── roundtrip.ts
|  |     |  └── writeToStore.ts
|  |     ├── entityStore.ts
|  |     ├── fixPolyfills.native.ts
|  |     ├── fixPolyfills.ts
|  |     ├── helpers.ts
|  |     ├── inMemoryCache.ts
|  |     ├── policies.ts
|  |     ├── reactiveVars.ts
|  |     ├── readFromStore.ts
|  |     ├── types.ts
|  |     └── writeToStore.ts
|  ├── config
|  |  └── jest
|  |     └── setup.ts
|  ├── core
|  |  ├── ApolloClient.ts
|  |  ├── LocalState.ts
|  |  ├── ObservableQuery.ts
|  |  ├── QueryInfo.ts
|  |  ├── QueryManager.ts
|  |  ├── Reobserver.ts
|  |  ├── __tests__
|  |  |  ├── LocalState.ts
|  |  |  ├── ObservableQuery.ts
|  |  |  ├── QueryManager
|  |  |  |  ├── index.ts
|  |  |  |  ├── links.ts
|  |  |  |  ├── multiple-results.ts
|  |  |  |  └── recycler.ts
|  |  |  └── fetchPolicies.ts
|  |  ├── index.ts
|  |  ├── networkStatus.ts
|  |  ├── types.ts
|  |  └── watchQueryOptions.ts
|  ├── errors
|  |  ├── __tests__
|  |  |  └── ApolloError.ts
|  |  └── index.ts
|  ├── index.ts
|  ├── link
|  |  ├── batch
|  |  |  ├── __tests__
|  |  |  |  └── batchLink.ts
|  |  |  ├── batchLink.ts
|  |  |  ├── batching.ts
|  |  |  └── index.ts
|  |  ├── batch-http
|  |  |  ├── __tests__
|  |  |  |  └── batchHttpLink.ts
|  |  |  ├── batchHttpLink.ts
|  |  |  └── index.ts
|  |  ├── context
|  |  |  ├── __tests__
|  |  |  |  └── index.ts
|  |  |  └── index.ts
|  |  ├── core
|  |  |  ├── ApolloLink.ts
|  |  |  ├── __tests__
|  |  |  |  └── ApolloLink.ts
|  |  |  ├── concat.ts
|  |  |  ├── empty.ts
|  |  |  ├── execute.ts
|  |  |  ├── from.ts
|  |  |  ├── index.ts
|  |  |  ├── split.ts
|  |  |  └── types.ts
|  |  ├── error
|  |  |  ├── __tests__
|  |  |  |  └── index.ts
|  |  |  └── index.ts
|  |  ├── http
|  |  |  ├── HttpLink.ts
|  |  |  ├── __tests__
|  |  |  |  ├── HttpLink.ts
|  |  |  |  ├── checkFetcher.ts
|  |  |  |  ├── parseAndCheckHttpResponse.ts
|  |  |  |  ├── selectHttpOptionsAndBody.ts
|  |  |  |  ├── selectURI.ts
|  |  |  |  └── serializeFetchParameter.ts
|  |  |  ├── checkFetcher.ts
|  |  |  ├── createHttpLink.ts
|  |  |  ├── createSignalIfSupported.ts
|  |  |  ├── index.ts
|  |  |  ├── parseAndCheckHttpResponse.ts
|  |  |  ├── rewriteURIForGET.ts
|  |  |  ├── selectHttpOptionsAndBody.ts
|  |  |  ├── selectURI.ts
|  |  |  └── serializeFetchParameter.ts
|  |  ├── persisted-queries
|  |  |  ├── __tests__
|  |  |  |  ├── index.ts
|  |  |  |  └── react.tsx
|  |  |  └── index.ts
|  |  ├── retry
|  |  |  ├── __tests__
|  |  |  |  ├── delayFunction.ts
|  |  |  |  ├── retryFunction.ts
|  |  |  |  └── retryLink.ts
|  |  |  ├── delayFunction.ts
|  |  |  ├── index.ts
|  |  |  ├── retryFunction.ts
|  |  |  └── retryLink.ts
|  |  ├── schema
|  |  |  ├── __tests__
|  |  |  |  └── schemaLink.ts
|  |  |  └── index.ts
|  |  ├── utils
|  |  |  ├── __tests__
|  |  |  |  ├── fromError.ts
|  |  |  |  ├── fromPromise.ts
|  |  |  |  ├── toPromise.ts
|  |  |  |  └── validateOperation.ts
|  |  |  ├── createOperation.ts
|  |  |  ├── fromError.ts
|  |  |  ├── fromPromise.ts
|  |  |  ├── index.ts
|  |  |  ├── throwServerError.ts
|  |  |  ├── toPromise.ts
|  |  |  ├── transformOperation.ts
|  |  |  └── validateOperation.ts
|  |  └── ws
|  |     ├── __tests__
|  |     |  └── webSocketLink.ts
|  |     └── index.ts
|  ├── react
|  |  ├── components
|  |  |  ├── Mutation.tsx
|  |  |  ├── Query.tsx
|  |  |  ├── Subscription.tsx
|  |  |  ├── __tests__
|  |  |  |  ├── client
|  |  |  |  |  ├── Mutation.test.tsx
|  |  |  |  |  ├── Query.test.tsx
|  |  |  |  |  ├── Subscription.test.tsx
|  |  |  |  |  └── __snapshots__
|  |  |  |  |     └── Query.test.tsx.snap
|  |  |  |  └── ssr
|  |  |  |     ├── getDataFromTree.test.tsx
|  |  |  |     └── server.test.tsx
|  |  |  ├── index.ts
|  |  |  └── types.ts
|  |  ├── context
|  |  |  ├── ApolloConsumer.tsx
|  |  |  ├── ApolloContext.ts
|  |  |  ├── ApolloProvider.tsx
|  |  |  ├── __tests__
|  |  |  |  ├── ApolloConsumer.test.tsx
|  |  |  |  └── ApolloProvider.test.tsx
|  |  |  └── index.ts
|  |  ├── data
|  |  |  ├── MutationData.ts
|  |  |  ├── OperationData.ts
|  |  |  ├── QueryData.ts
|  |  |  ├── SubscriptionData.ts
|  |  |  └── index.ts
|  |  ├── hoc
|  |  |  ├── __tests__
|  |  |  |  ├── client-option.test.tsx
|  |  |  |  ├── fragments.test.tsx
|  |  |  |  ├── mutations
|  |  |  |  |  ├── index.test.tsx
|  |  |  |  |  ├── lifecycle.test.tsx
|  |  |  |  |  ├── queries.test.tsx
|  |  |  |  |  └── recycled-queries.test.tsx
|  |  |  |  ├── queries
|  |  |  |  |  ├── __snapshots__
|  |  |  |  |  |  └── lifecycle.test.tsx.snap
|  |  |  |  |  ├── api.test.tsx
|  |  |  |  |  ├── errors.test.tsx
|  |  |  |  |  ├── index.test.tsx
|  |  |  |  |  ├── lifecycle.test.tsx
|  |  |  |  |  ├── loading.test.tsx
|  |  |  |  |  ├── observableQuery.test.tsx
|  |  |  |  |  ├── polling.test.tsx
|  |  |  |  |  ├── reducer.test.tsx
|  |  |  |  |  ├── skip.test.tsx
|  |  |  |  |  └── updateQuery.test.tsx
|  |  |  |  ├── shared-operations.test.tsx
|  |  |  |  ├── ssr
|  |  |  |  |  ├── getDataFromTree.test.tsx
|  |  |  |  |  └── server.test.tsx
|  |  |  |  ├── statics.test.tsx
|  |  |  |  └── subscriptions
|  |  |  |     └── subscriptions.test.tsx
|  |  |  ├── graphql.tsx
|  |  |  ├── hoc-utils.tsx
|  |  |  ├── index.ts
|  |  |  ├── mutation-hoc.tsx
|  |  |  ├── query-hoc.tsx
|  |  |  ├── subscription-hoc.tsx
|  |  |  ├── types.ts
|  |  |  └── withApollo.tsx
|  |  ├── hooks
|  |  |  ├── __tests__
|  |  |  |  ├── useApolloClient.test.tsx
|  |  |  |  ├── useLazyQuery.test.tsx
|  |  |  |  ├── useMutation.test.tsx
|  |  |  |  ├── useQuery.test.tsx
|  |  |  |  ├── useReactiveVar.test.tsx
|  |  |  |  └── useSubscription.test.tsx
|  |  |  ├── index.ts
|  |  |  ├── useApolloClient.ts
|  |  |  ├── useLazyQuery.ts
|  |  |  ├── useMutation.ts
|  |  |  ├── useQuery.ts
|  |  |  ├── useReactiveVar.ts
|  |  |  ├── useSubscription.ts
|  |  |  └── utils
|  |  |     ├── useBaseQuery.ts
|  |  |     └── useDeepMemo.ts
|  |  ├── index.ts
|  |  ├── parser
|  |  |  ├── __tests__
|  |  |  |  └── parser.test.ts
|  |  |  └── index.ts
|  |  ├── ssr
|  |  |  ├── RenderPromises.ts
|  |  |  ├── __tests__
|  |  |  |  ├── useLazyQuery.test.tsx
|  |  |  |  └── useQuery.test.tsx
|  |  |  ├── getDataFromTree.ts
|  |  |  ├── index.ts
|  |  |  └── renderToStringWithData.ts
|  |  └── types
|  |     └── types.ts
|  ├── testing
|  |  └── index.ts
|  ├── utilities
|  |  ├── common
|  |  |  ├── __tests__
|  |  |  |  ├── cloneDeep.ts
|  |  |  |  ├── compact.ts
|  |  |  |  ├── environment.ts
|  |  |  |  ├── maybeDeepFeeze.ts
|  |  |  |  └── mergeDeep.ts
|  |  |  ├── arrays.ts
|  |  |  ├── canUse.ts
|  |  |  ├── cloneDeep.ts
|  |  |  ├── compact.ts
|  |  |  ├── environment.ts
|  |  |  ├── errorHandling.ts
|  |  |  ├── filterInPlace.ts
|  |  |  ├── maybeDeepFreeze.ts
|  |  |  └── mergeDeep.ts
|  |  ├── graphql
|  |  |  ├── __tests__
|  |  |  |  ├── directives.ts
|  |  |  |  ├── fragments.ts
|  |  |  |  ├── getFromAST.ts
|  |  |  |  ├── storeUtils.ts
|  |  |  |  └── transform.ts
|  |  |  ├── directives.ts
|  |  |  ├── fragments.ts
|  |  |  ├── getFromAST.ts
|  |  |  ├── storeUtils.ts
|  |  |  └── transform.ts
|  |  ├── index.ts
|  |  ├── observables
|  |  |  ├── Concast.ts
|  |  |  ├── Observable.ts
|  |  |  ├── asyncMap.ts
|  |  |  └── iteration.ts
|  |  ├── policies
|  |  |  ├── __tests__
|  |  |  |  └── relayStylePagination.test.ts
|  |  |  └── pagination.ts
|  |  └── testing
|  |     ├── __tests__
|  |     |  └── stripSymbols.ts
|  |     ├── index.ts
|  |     ├── itAsync.ts
|  |     ├── mocking
|  |     |  ├── MockedProvider.tsx
|  |     |  ├── __tests__
|  |     |  |  ├── MockedProvider.test.tsx
|  |     |  |  ├── __snapshots__
|  |     |  |  |  └── MockedProvider.test.tsx.snap
|  |     |  |  └── mockSubscriptionLink.test.tsx
|  |     |  ├── mockClient.ts
|  |     |  ├── mockFetch.ts
|  |     |  ├── mockLink.ts
|  |     |  ├── mockQueryManager.ts
|  |     |  ├── mockSubscriptionLink.ts
|  |     |  └── mockWatchQuery.ts
|  |     ├── observableToPromise.ts
|  |     ├── stripSymbols.ts
|  |     ├── subscribeAndCount.ts
|  |     └── wrap.ts
|  └── version.ts
└── tsconfig.json

directory: 142 file: 443

ignored

```

## 外部模块依赖

![img](./outer.svg)

## 内部模块依赖

![img](./inner.svg)
  