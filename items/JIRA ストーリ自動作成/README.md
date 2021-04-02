MacOS上でJIRAからボタンでストーリ作成　　issue 作成したので、
ちょこちょこ詰まったとこを中心にメモります。

## 実現すること
- Mac上でJIRAより、issue=ストーリ作成ができること　ConfuluenceからJIRA課題を起票する。


## 動作環境について

- macOS Mojave 
- FireFox　　Chromeだとできないおそらく社内設定のため


１．さっそくJIRAConfuluenceより作成ボタンおす。
２．｛｝と入力しその間に以下を入力。
３．お終い。

テスト方法
ボタンを押す。反応しない場合は、htmlがおかしいため削除しつつ最低限の実装しつつたしかめながら行う。

```terminal:JIRA

<div style="margin-top:1.0rem; margin-bottom:2.0rem;">
  <a id="create-jira" class="create-jira external-link"
      style="margin:0;" href="#" rel="nofollow" target="_blank">
    <button id="request-btn-group"
        class="aui-button aui-button-primary">ストーリ作成ボタン！</button></a>
</div>
<script type="text/javascript">
(function() {
  // url
  // [準備] > [URL] の手順で取得した URL を設定します。
  var baseUrl = 'http://XXXXXXXXXX/CreateIssueDetails!init.jspa';

  // project・・変数を自分で確認し設定すること仮XXXX
  var project = '?pid=XXXX';

  // issue・・変数を自分で確認し設定すること仮XXXX
  var issue = '&issuetype=XXXX';

  // priority
  var priority = '&priority=3';

  // duedate
  // この例では起票日から7日後をデフォルトの期限としています。
   //  var duedate = '&duedate=';
    // var dt = new Date();
    // dt.setDate(dt.getDate() + 7);
    // duedate += (dt.getFullYear() + '/' + (dt.getMonth() + 1) + '/' + dt.getDate());

  // desc
  // 改行コードも encodeURIComponent で囲えばデフォルト値に含めることができます。★★★
  //var desc = '&description=' +'メモ' + encodeURIComponent('T/O') ;
//  var desc = '&description=' + encodeURIComponent('改行の文字コードは\nです');

var desc = '&description=' + encodeURIComponent('＜ユーザストーリ＞ \n【その仕事のユーザー】として、\n【そのタスクの内容】したい\n なぜなら、【そのタスクをする理由】からだ\n');

  // summary
  // 要約はわざと空にしてあります。
  // 要約を空にしておくことで、課題作成時に入力不足エラーが発生し、
  // すでに入力された他の値をテンプレートとして利用できます。
  var summary = '&summary=';

  // assignee
  // デフォルトの担当者を設定したい場合は、encodeURIComponent でユーザーIDを囲って指定。
  var assignee = '&assignee='+encodeURIComponent('admin');;

  // reporter
  // Confluence を使用していて、ユーザーが JIRA と一元管理されている場合のみ使用可能。
  var username = $('#user-menu-link').data('username');
  var reporter = '&reporter=' + encodeURIComponent(username);

  // link
  $('.create-jira').attr('href', baseUrl + project + issue + priority + summary + assignee + reporter + desc);
})();
</script>
```

### 以上（執筆３０分）
