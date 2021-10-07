# TypeScript With React

Use TS template with

```
npx create-react-app app --template typescript
```

Sample React component

```js
interface Props {
    title: string
    color?: string
}

const Header = (props: Props) => {
    return(
        <header>
            <h1>{props.title}</h1>
        </header>
    )
}

export default Header;
```
