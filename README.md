
# 源码分析

## 文件结构

``` bash
/Users/liufang/openSource/FunnyLiu/apollo-client
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
├── src
|  ├── cache
|  |  ├── core
|  |  |  ├── cache.ts
|  |  |  └── types
|  |  |     ├── Cache.ts
|  |  |     ├── DataProxy.ts
|  |  |     └── common.ts
|  |  ├── index.ts
|  |  └── inmemory
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
|  |  |  └── index.ts
|  |  ├── retry
|  |  |  ├── delayFunction.ts
|  |  |  ├── index.ts
|  |  |  ├── retryFunction.ts
|  |  |  └── retryLink.ts
|  |  ├── schema
|  |  |  └── index.ts
|  |  ├── utils
|  |  |  ├── createOperation.ts
|  |  |  ├── fromError.ts
|  |  |  ├── fromPromise.ts
|  |  |  ├── index.ts
|  |  |  ├── throwServerError.ts
|  |  |  ├── toPromise.ts
|  |  |  ├── transformOperation.ts
|  |  |  └── validateOperation.ts
|  |  └── ws
|  |     └── index.ts
|  ├── react
|  |  ├── components
|  |  |  ├── Mutation.tsx
|  |  |  ├── Query.tsx
|  |  |  ├── Subscription.tsx
|  |  |  ├── index.ts
|  |  |  └── types.ts
|  |  ├── context
|  |  |  ├── ApolloConsumer.tsx
|  |  |  ├── ApolloContext.ts
|  |  |  ├── ApolloProvider.tsx
|  |  |  └── index.ts
|  |  ├── data
|  |  |  ├── MutationData.ts
|  |  |  ├── OperationData.ts
|  |  |  ├── QueryData.ts
|  |  |  ├── SubscriptionData.ts
|  |  |  └── index.ts
|  |  ├── hoc
|  |  |  ├── graphql.tsx
|  |  |  ├── hoc-utils.tsx
|  |  |  ├── index.ts
|  |  |  ├── mutation-hoc.tsx
|  |  |  ├── query-hoc.tsx
|  |  |  ├── subscription-hoc.tsx
|  |  |  ├── types.ts
|  |  |  └── withApollo.tsx
|  |  ├── hooks
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
|  |  |  └── index.ts
|  |  ├── ssr
|  |  |  ├── RenderPromises.ts
|  |  |  ├── getDataFromTree.ts
|  |  |  ├── index.ts
|  |  |  └── renderToStringWithData.ts
|  |  └── types
|  |     └── types.ts
|  ├── testing
|  |  └── index.ts
|  ├── utilities
|  |  ├── common
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



# <a href="https://www.apollographql.com/"><img src="https://user-images.githubusercontent.com/841294/53402609-b97a2180-39ba-11e9-8100-812bab86357c.png" height="100" alt="Apollo Client"></a>

## Apollo Client

[![npm version](https://badge.fury.io/js/%40apollo%2Fclient.svg)](https://badge.fury.io/js/%40apollo%2Fclient)
[![Build Status](https://circleci.com/gh/apollographql/apollo-client.svg?style=svg)](https://circleci.com/gh/apollographql/apollo-client)
[![Join the community on Spectrum](https://withspectrum.github.io/badge/badge.svg)](https://spectrum.chat/apollo)

Apollo Client is a fully-featured caching GraphQL client with integrations for React, Angular, and more. It allows you to easily build UI components that fetch data via GraphQL.

## Documentation

All Apollo Client documentation, including React integration articles and helpful recipes, can be found at: <br/>
[https://www.apollographql.com/docs/react/](https://www.apollographql.com/docs/react/)

The Apollo Client API reference can be found at: <br/>
[https://www.apollographql.com/docs/react/api/apollo-client/](https://www.apollographql.com/docs/react/api/apollo-client/)

## Maintainers

- [@benjamn](https://github.com/benjamn) (Apollo)
- [@hwillson](https://github.com/hwillson) (Apollo)
