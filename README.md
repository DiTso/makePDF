# makePDF
Позволяет генерировать пдф из переданного html, массива $data либо строки из базы данных. При этом для шаблона используется заданный чанк.
Работает на базе mpdf - https://github.com/mpdf/mpdf (уже установлена в пакете, так что для тех, кто не дружит с composer проблем не будет).

# Немного примеров вызова
```[[makePDF? &html=`<html><body>hello world!</body></html>`]]```<br>
```[[makePDF? &page=`25`]]```<br>
```[[makePDF? &page=`test/test.html?print` &flag=`F` &custom_path=`assets/files/myfolder/`]]```<br>
```[[makePDF? &id=`5` &tpl=`chunkName`]]```<br>
```[[makePDF? &id=`10` &table=`mytable` &idField=`pid` &tpl=`chunkName`]]```<br><br>
```
$attachFiles = $modx->runSnippet("makePDF", array('action' => 'FormLister', 'data' => $pfd_data, 'tpl' => 'zajavkaReportTpl', 'folder_name' => 'zajavka'));
if (is_array($attachFiles)) {
    $FormLister->config->setConfig(array('attachFiles' => $attachFiles));
}
```

