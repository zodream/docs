## HTML 

## 对标签的封装

`Zodream\Infrastructure\Support\Html;`

`Html::a($text, $href = '#', $option = array()): string;`

## 对表单的封装

`Zodream\Html\Form` 普通表单的封装

```phtml
<?= Form::open('./save')?>
    <?= Form::text($name, $value = null, $options = []) ?>

<?= Form::close()?>
```

`Zodream\Html\Dark\Form` 对模型表单的封装

```phtml
<?= Form::open(Model $model, './save')?>
    <?= Form::text($name) ?>

<?= Form::close('id')?>
```

## 独立部件的封装

`Zodream\Html\Page` 分页

```
$page = new Page(0);
echo $page->getLink(array $option = []): string
```

`Page->getLink()` 输出分页链接

