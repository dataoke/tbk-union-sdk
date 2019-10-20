**淘宝联盟SDK**

淘宝联盟SDK

PHP =>7.0

`composer require yumufeng/tbk-union-sdk`

如果是在swoole 扩展下使用，支持协程并发，需要在编译swoole扩展的时候开启，系统会自动判断是否采用swoole

```./configure --enable-openssl```

## 使用

```php
<?php


$config = [
    'appkey' => '',
    'secretKey' => '',
    'session' => '',//授权接口（sc类的接口）需要带上
    'sandbox' => false,
];

$client = new \TaobaoUnionSdk\TbkFatory($config);

$result = $client->tools->createTpwd([
    'text' => '【小树苗】儿童牙膏无氟可吞咽牙膏',
    'url' => 'https://uland.taobao.com/coupon/edetail?e=O60EAyHyKIpt3vqbdXnGlivNjFRkusPB5djj77wlO1yRouJg2hy9lJ7clY2Hw1o40khhwrZzASf9g1RlPpGU2hmFTDIT3kLkWOGP4KauORrEQlnWllxAq7Da9SMviYqQfo0s4juXT4zk4UQqwowTnTclmaPT%2FN8Oi5zCOSkadsc%3D&af=1&pid=mm_29563340_122900348_29874650260',
    'logo' => 'http://imgproxy.18cap.cn/imgextra/i3/1060894880/*o1*c*n01n8*p*b*g41lv5*jdeej6r_!!1060894880.jpg_400x400.jpg'
]);


if ($result == false) {
    var_dump($client->getError());
}

echo json_encode($result);

```

## 说明文档

| 接口名称  | 对应方法  |
| --------   | ---- |
| taobao.tbk.content.get( 淘宝客-推广者-图文内容输出 )        |    \$app->content->get()  |
| taobao.tbk.content.effect.get( 淘宝客-推广者-图文内容效果数据 )    |    \$app->content->effect()  |
| taobao.tbk.coupon.get (阿里妈妈推广券信息查询)   |    \$app->coupon->get()  |
| taobao.tbk.dg.newuser.order.get(淘宝客-推广者-新用户订单明细查询)    |    \$app->dg->newuser_order_get()  |
| taobao.tbk.dg.newuser.order.sum(淘宝客-推广者-拉新活动对应数据查询) |    \$app->dg->newuser_order_sum()  |
| taobao.tbk.dg.optimus.material( 淘宝客-推广者-物料精选 )  |    \$app->dg->material_optimus()  |
| taobao.tbk.dg.material.optional( 淘宝客-推广者-物料搜索)   |    \$app->dg->material_optional()  |
| taobao.tbk.item.recommend.get (淘宝客商品关联推荐查询)        |    \$app->item->recommend()  |
| taobao.tbk.item.info.get (淘宝客商品详情（简版）)        |    \$app->item->get()  |
| taobao.tbk.item.click.extract (链接解析api)    |    \$app->item->extractClick()  |
| taobao.tbk.item.word.get(淘宝客-推广者-商品出词)   |    \$app->item->word()  |
| taobao.tbk.shop.recommend.get(淘宝客店铺关联推荐查询)  |    \$app->shop->recommend()  |
| taobao.tbk.shop.get (淘宝客店铺查询)        |    \$app->shop->get()  |
| taobao.tbk.ju.tqg.get (淘抢购api)    |    \$app->ju->tqg()  |
| taobao.tbk.tpwd.create (淘宝客淘口令)     |    \$app->tools->createTpwd()  |


## 支持

- 淘宝客私域参考：https://open.taobao.com/api.htm?docId=37988&docType=2&scopeId=14474
- 淘宝客API： https://open.taobao.com/api.htm?docId=24517&docType=2
## License

MIT
