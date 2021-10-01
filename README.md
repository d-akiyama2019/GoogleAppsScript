# GoogleAppsScript

```python
function third_backup(){
  //テンプレートオブジェクトの取得
  var templateid = "テンプレートオブジェクトのidを入れる"; // URLのそれっぽいところ
  var template = DriveApp.getFileById(templateid);

  //保存先フォルダオブジェクトの取得
  var destfolderid = "保存先フォルダのidを入れる"; // URLのそれっぽいところ
  var destfolder = DriveApp.getFolderById(destfolderid);

  //日付の取得
  var d = new Date();
  var s = Utilities.formatDate(d, "JST", "yyyyMMdd_HHmmss");

  //コピー作成
  var filename = s + "_" + template.getName();
  var newfile = template.makeCopy(filename, destfolder);

  //ファイルの共有設定（※権限付与はまた別途）
  newfile.setSharing(DriveApp.Access.PRIVATE, DriveApp.Permission.EDIT);
}
```
