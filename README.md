# GraphQL apollo-client 이해

```
const client = new ApolloClient({
  uri: 'http://localhost:4000',
  cache: new InMemoryCache()
});
```

- client : GraphQL 서버로와 정보를 주고받을 ApolloClient 객체
- uri : GraphQL 서버의 주소
- cache : _InMemoryCache_ 를 통한 캐시 관리

> #### InMemoryCache
>
> - apollo client 는 gql 의 결과를 InMemoryCache 에 저장 --> 이를 통해 클라이언트는 불필요한 네트워크 요청 없이 동일한 데이터에 대해 요청 가능
> - 캐시는 응답 받은 데이터에 포함된 모든 식별 가능한 객체에 대해 고유한 ID 생성
> - 캐시는 개체를 ID별로 플랫 룩업 테이블에 저장
> - 들어오는 객체가 기존 객체와 동일한 ID로 저장될 때마다 해당 객체의 필드가 병합

### GraphQL Fragment

- 여러 쿼리에 사용될 수 있는, 재사용 가능한 필드셋
- 중복을 줄임으로써 전체 코드 간소화
