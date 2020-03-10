# TypeScriptチュートリアル

参考リンク
https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html

## TypeScriptのインストール

yarnを使用した

```
$ yarn global add typescript
```

## サンプルコードの作成

`greeter.ts` という名前で `Hello, World!` 的なプログラムの作成

```TypeScript:greeter.ts
function greeter(person: string) {
    return "Hello, " + person;
}

let user = "Jane User";

document.body.textContent = greeter(user);
```

## コンパイル

以下のコマンドでコンパイルしてjsファイルが生成される

```
$ tsc greeter.ts
```

型を宣言することで、変数に予期せぬ値が入ったときにエラーを検知できる
(例えば `user` に `123` というintの数値をいれるとコンパイル時にエラーになる)

## クラス

TypeScriptでは他のオブジェクト指向言語のようにInterfaceやClassが定義できる

```TypeScript
interface Person {
    firstName: string;
    lastName: string;
}

function greeter(person: Person) {
    return "Hello, " + person.firstName + " " + person.lastName;
}

let user = { firstName: "Jane", lastName: "User" };

document.body.textContent = greeter(user);
```

```TypeScript
class Student {
    fullName: string;
    constructor(public firstName: string, public middleInitial: string, public lastName: string) {
        this.fullName = firstName + " " + middleInitial + " " + lastName;
    }
}

interface Person {
    firstName: string;
    lastName: string;
}

function greeter(person: Person) {
    return "Hello, " + person.firstName + " " + person.lastName;
}

let user = new Student("Jane", "M.", "User");

document.body.textContent = greeter(user);
```

## Webアプリ作成


```HTML
<!DOCTYPE html>
<html>
    <head><title>TypeScript Greeter</title></head>
    <body>
        <script src="greeter.js"></script>
    </body>
</html>
```
