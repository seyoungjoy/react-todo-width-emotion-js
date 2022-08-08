# Todo-list-app With emotion

## emotion.js 설치
```
$ npm install @emotion/react @emotion/styled
```

### Style Components
- 스타일을 설정해서 리액트 컴포넌트로 만들 수 있음.
- [styled-components](https://www.styled-components.com/)와 유사한 방법.

```jsx
import styled from '@emotion/styled'

const Button = styled.button`
  color: hotpink;
`

function App(){
    return(
        <div>
            <button></button>
        </div>
    )
}
```

### props를 기반한 스타일 컴포넌트 생성
```jsx
import styled from '@emotion/styled'

// 템플릿 리터럴로 표현할 때
const Button = styled.button`
    color:${props => (props.primary ? 'hotpink' : 'black')}
`

// object
const Container = style.div(props => ({
    display:'flex',
    flexDirection:props.col && 'column'
}))

function App(){
    return(
        <Container col>
            <Button>Block Button</Button>
            <Button primary>Hotpink Button</Button>
        </Container>
    )
}
```

### 컴포넌트 스타일링 
```jsx
const Basic = ({ className }) => <div className = {className}>Some text</div>

const Fancy = styled(Basic)`
  color:hotpink;
`
```

### 'withComponent'로 이미 사용했던 스타일을 그대로 들고올 수 있음.
```jsx
import styled from '@emotion/styled'

// section 태그의 스타일을 지정했음.
const Section = styled.section`
    backround:#333;
    color:#fff;
`

// 같은 스타일을 가진 aside 태그가 만들고 싶다? 이때 withComponent 사용
const Aside = Section.widthComponent('aside')



```

### Object Styles
```jsx
import styled from '@emotion/styled'

const H1 = styled.h1(
    {
        fontSize:20
    },
    props => ({ color:props.color })
)

function App(){
    return(
        <div>
            <H1 color={"red"}>hi</H1>
        </div>
    )
}
```

### 중첩 스타일 적용
```jsx
const H2 = styled.h2`
  fontSize: 30;
  & > strong {
    color:red;
  }
`

```

## react todo list
### React Children
```jsx
export default function Alert ({children}) {
  return (
    <AlertRoot>
      ...
      <AlertMessage>
        {children}
      </AlertMessage>
    </AlertRoot>
  )
}
```
https://fe-developers.kakaoent.com/2021/211022-react-children-tip/




## Trouble shooting
- [create-react-app 최신버전 설치 이슈](https://velog.io/@gygy/error-create-react-app-%EC%82%AD%EC%A0%9C-%ED%9B%84-%EC%B5%9C%EC%8B%A0%EB%B2%84%EC%A0%84%EC%9C%BC%EB%A1%9C-%EC%84%A4%EC%B9%98%EC%95%88%EB%90%A0%EB%95%8C-Need-to-install-the-following-packages-create-react-appOk-to-proceed-y)
```
npx create-react-app@latest my-app
```

## ?
- npx

## Reference
- [emotion](https://emotion.sh/docs/styled)
