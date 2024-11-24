# PHP App ① レビュー

## 全般

### 以下のaタグのリンクを押下した際にedit.phpの$_GETにどんな値が格納されるか説明してください。

```html
<a href="edit.php?todo_id=123&todo_content=焼肉">更新</a>
```
$_GETのtodo_idとtodo_contentというキーに、それぞれ123、焼肉が格納される。

### 以下のフォームの送信ボタンを押下した際にstore.phpの$_POSTにどんな値が格納されるか説明してください。

```html
<form action="store.php" method="post">
    <input type="text" name="id" value="123">
		<textarea　name="content">焼肉</textarea>
    <button type="submit">送信</button>
</form>
```
$_POSTにidがキー、123がバリューとなる連想配列として格納され、contentというキーに焼肉が格納される。

### `require_once()` は何のために記述しているか説明してください。

PHPで外部ファイルを読み込むときに記述している。

### `savePostedData($post)`は何をしているか説明してください。

記述なし。

### `header('location: ./index.php')`は何をしているか説明してください。

PHPのheader関数を用いてリダイレクト先を指定している。
「Location: 遷移先のURL」という形で指定する。

### `getRefererPath()`は何をしているか説明してください。
記述なし。

### `connectPdo()` の返り値は何か、またこの記述は何をするための記述か説明してください。
返り値はPODオブジェクト。
PDOという定義済みのクラスをインスタンス化している。

### `try catch`とは何か説明してください。
例外処理を実装する際に使用する。
try内に例外が発生する可能性がある処理を書き、例外が発生した際に、catch内の処理が実行される。

### Pdoクラスをインスタンス化する際に`try catch`が必要な理由を説明してください。
例外処理を行わないと例外が発生するたびにアプリケーションがクラッシュしてしまうため、
例外が発生した場合も正しく動くように対処する必要があるから。

## 新規作成

### `createTodoData($post)`は何をしているか説明してください。
createTodoDataにpostされたデータを渡している。

## 一覧

### `getTodoList()`の返り値について説明してください。
登録したデータをデータベースから全権取得する、getAllRecords関数。

### `<?= ?>`は何の省略形か説明してください。
echoの省略形。
<td><?= $todo['id']; ?></td> は
<td><?php echo $todo['id']; ?></td> と同じ意味。

## 更新

### `getSelectedTodo($_GET['id'])`の返り値は何か、またなぜ`$_GET['id']` を引数に渡すのか説明してください。

### `updateTodoData($post)`は何をしているか説明してください。

## 削除

### `deleteTodoData($id)`は何をしているか説明してください。

### `deleted_at`を現在時刻で更新すると一覧画面からToDoが非表示になる理由を説明してください。

### 今回のように実際のデータを削除せずに非表示にすることで削除されたように扱うことを〇〇削除というか。

### 実際にデータを削除することを〇〇削除というか。

### 前問のそれぞれの削除のメリット・デメリットについて説明してください。
