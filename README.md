
<html lang="zh-CN"><head>
        <meta http-equiv="content-type" content="text/html; charset=gb2312">
        <meta charset="utf-8">
        <title>接口Api</title>
        <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
        <meta http-equiv="X-UA-Compatible" content="IE=edge,Chrome=1">
        <meta name="renderer" content="webkit">
        <link href="./bootstrap.css" type="text/css" rel="stylesheet">
        <link href="./font-awesome.css?20180823" type="text/css" rel="stylesheet">
        <link href="./style.css?20180823" type="text/css" rel="stylesheet">  
         </head>

<body class="fixed-sidebar full-height-layout gray-bg">
    <div class="pace pace-inactive">
        <div class="pace-progress" data-progress-text="100%" data-progress="99" style="transform: translate3d(100%, 0px, 0px);">
            <div class="pace-progress-inner">
            </div>
        </div>
        <div class="pace-activity">
        </div>
    </div>
    <div id="wrapper"> 
        <div id="page-wrapper" class="gray-bg">
            <div class="row border-bottom">
    
</div>
            <div class="row wrapper wrapper-content">
                <div class="row">
                    <div class="col-lg-12">
                        <div class="panel panel-default">
                            

                                                        <div class="panel-body">
                                <div class="col-md-12">
                                    <div class="row">
                                        
                                    </div>
                                </div>
                            </div>
                            
                            
                            
                            
                            <div class="panel-heading">
                                <div class="panel-title">
                                    <em class="fa fa-list">
                                    </em>
                                    接口开发文档&nbsp;&nbsp;（编码：UTF-8）
                                </div>
                            </div>
                            <div class="panel-body">
                                <div class="col-md-12">
                                    <div class="row">
                                        <h1>支付接口</h1>
                                        <p>支付接口参数【请求方式：GET或POST均可】【如遇问题可尝试用html表单提交参数】</p>
                                        <table class="table table-bordered">
                                            <thead>
                                                <tr>
                                                    <th>参数名称</th>
                                                    <th>参数含义</th>
                                                    <th>必填</th>
                                                    <th>说明</th>
                                                </tr>
                                            </thead>
                                            <tbody>
                                                <tr>
                                                    <td>fxid</td>
                                                    <td>商户id</td>
                                                    <td>是</td>
                                                    <td>唯一号，由蓝夜支付提供</td>
                                                </tr>
                                                <tr>
                                                    <td>fxddh</td>
                                                    <td>商户订单号</td>
                                                    <td>是</td>
                                                    <td>仅允许字母或数字类型,不超过22个字符，不要有中文</td>
                                                </tr>
                                                <tr>
                                                    <td>fxdesc</td>
                                                    <td>商品名称</td>
                                                    <td>是</td>
                                                    <td>utf-8编码</td>
                                                </tr>
                                                <tr>
                                                    <td>fxfee</td>
                                                    <td>支付金额</td>
                                                    <td>是</td>
                                                    <td>请求的价格(单位：元) 可以0.01元</td>
                                                </tr>
                                                <tr>
                                                    <td>fxnotifyurl</td>
                                                    <td>异步通知地址</td>
                                                    <td>是</td>
                                                    <td>异步接收支付结果通知的回调地址，通知url必须为外网可访问的url，不能携带参数。</td>
                                                </tr>
                                                <tr>
                                                    <td>fxbackurl</td>
                                                    <td>同步通知地址</td>
                                                    <td>是</td>
                                                    <td>支付成功后跳转到的地址，不参与签名。</td>
                                                </tr>
                                                <tr>
                                                    <td>fxpay</td>
                                                    <td>请求类型
                                                        【支付宝手机网站H5：zfbwap2】                                                    </td>
                                                    <td>是</td>
                                                    <td>请求支付的接口类型。</td>
                                                </tr>
                                                <tr>
                                                    <td>fxnotifystyle</td>
                                                    <td>异步数据类型</td>
                                                    <td>否</td>
                                                    <td>异步返回数据的类型，默认1 返回数据为表单数据（Content-Type: multipart/form-data），2 返回post json数据。</td>
                                                </tr>
                                                <tr>
                                                    <td>fxattch</td>
                                                    <td>附加信息</td>
                                                    <td>否</td>
                                                    <td>原样返回，utf-8编码</td>
                                                </tr>
                                                <tr>
                                                    <td>fxsmstyle</td>
                                                    <td>扫码模式</td>
                                                    <td>否</td>
                                                    <td>用于扫码模式（sm），仅带sm接口可用，默认0返回扫码图片，为1则返回扫码跳转地址。</td>
                                                </tr>
                                                <tr>
                                                    <td>fxbankcode</td>
                                                    <td>银行类型</td>
                                                    <td>否</td>
                                                    <td>用于网银直连模式，请求的银行编号，参考<a href="#yh">银行附录</a>,仅网银接口可用。</td>
                                                </tr>
                                                <tr>
                                                    <td>fxfs</td>
                                                    <td>反扫付款码数字</td>
                                                    <td>否</td>
                                                    <td>用于用户被扫，用户的付款码数字,仅反扫接口可用。</td>
                                                </tr>
                                                <tr>
                                                    <td>fxuserid</td>
                                                    <td>快捷模式绑定商户id</td>
                                                    <td>否</td>
                                                    <td>用于识别用户绑卡信息，仅快捷接口可用。</td>
                                                </tr>
                                                <tr>
                                                    <td>fxsign</td>
                                                    <td>签名【md5(商务号+商户订单号+支付金额+异步通知地址+商户秘钥)】</td>
                                                    <td>是</td>
                                                    <td>通过签名算法计算得出的签名值。</td>
                                                </tr>
                                                <tr>
                                                    <td>fxip</td>
                                                    <td>支付用户IP地址</td>
                                                    <td>是</td>
                                                    <td>用户支付时设备的IP地址</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                        
                                        <p>支付申请示例（请用脚本语言模拟如下提交方式）</p>
                                        <table class="table table-bordered">
                                            <thead>
                                                <tr>
                                                    <td><pre>&lt;form id="Form1" name="Form1" method="post" action="http://localhost/Pay"&gt;
    &lt;input type="hidden" name="fxid" value='2017100'/&gt;
    &lt;input type="hidden" name="fxddh" value='1531392180374'/&gt;
    &lt;input type="hidden" name="fxdesc" value='test'/&gt;
    &lt;input type="hidden" name="fxfee" value='10'/&gt;
    &lt;input type="hidden" name="fxattch" value='mytest'/&gt;
    &lt;input type="hidden" name="fxnotifyurl" value='http://localhost/notifyUrl.php'/&gt;
    &lt;input type="hidden" name="fxbackurl" value='http://localhost/backUrl.php'/&gt;
    &lt;input type="hidden" name="fxpay" value='wxsm'/&gt;
    &lt;input type="hidden" name="fxip" value='126.155.2.36'/&gt;
    &lt;input type="hidden" name="fxsign" value='3990af9dbffc4e0ac6d307aee9b034d8'/&gt;
&lt;/form&gt;
</pre>
                                                    </td>
                                                </tr>
                                            </thead>
                                        </table>

                                        <p>支付接口返回【数据格式：json】</p>
                                        <table class="table table-bordered">
                                            <thead>
                                                <tr>
                                                    <th>参数</th>
                                                    <th>参数含义</th>
                                                    <th>必须</th>
                                                    <th>说明</th>
                                                </tr>
                                            </thead>
                                            <tbody>
                                                <tr>
                                                    <td>status</td>
                                                    <td>状态</td>
                                                    <td>是</td>
                                                    <td>状态【1代表正常】【0代表错误】</td>
                                                </tr>
                                                <tr>
                                                    <td>payurl</td>
                                                    <td>支付链接</td>
                                                    <td>是</td>
                                                    <td>正常状态下返回支付跳转路径，跳转到该路径即可支付</td>
                                                </tr>
                                                <tr>
                                                    <td>error</td>
                                                    <td>错误信息</td>
                                                    <td>是</td>
                                                    <td>错误状态下返回错误信息utf-8编码数据</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                        
                                        <p>支付申请返回示例</p>
                                        <table class="table table-bordered">
                                            <thead>
                                                <tr>
                                                    <td><pre>{
    "status":1,
    "payurl":"https://localhost/Index/Index/qrcode?url=weixin%3A%2F%2Fwxpay%2Fbizpayurl%3Fpr%3D1qznay9&amp;w=150&amp;k=a7f356ce6e0bd96cde2e404b9b272ad4"
}
                                                    </pre>
                                                    </td>
                                                </tr>
                                            </thead>
                                        </table>

                                        <p>同步（GET）/异步（POST）【数据格式：默认 表单数组（Content-Type: multipart/form-data）（java请用request.getInputStream获取参数）】</p>
                                        <p>返回参数【成功失败均返回数据，请判断订单状态，请以异步数据为准】</p>
                                        <table class="table table-bordered">
                                            <thead>
                                                <tr>
                                                    <th>参数</th>
                                                    <th>参数含义</th>
                                                    <th>必须</th>
                                                    <th>说明</th>
                                                </tr>
                                            </thead>
                                            <tbody>
                                                <tr>
                                                    <td>fxid</td>
                                                    <td>商户ID</td>
                                                    <td>是</td>
                                                    <td>商户ID，由蓝夜支付提供</td>
                                                </tr>
                                                <tr>
                                                    <td>fxddh</td>
                                                    <td>商户订单号</td>
                                                    <td>是</td>
                                                    <td>平台返回商户提交的订单号</td>
                                                </tr>
                                                <tr>
                                                    <td>fxorder</td>
                                                    <td>平台订单号</td>
                                                    <td>是</td>
                                                    <td>平台内部生成的订单号</td>
                                                </tr>
                                                <tr>
                                                    <td>fxdesc</td>
                                                    <td>商品名称</td>
                                                    <td>是</td>
                                                    <td>utf-8编码</td>
                                                </tr>
                                                <tr>
                                                    <td>fxfee</td>
                                                    <td>支付金额</td>
                                                    <td>是</td>
                                                    <td>支付的价格(单位：元)</td>
                                                </tr>
                                                <tr>
                                                    <td>fxattch</td>
                                                    <td>附加信息</td>
                                                    <td>是</td>
                                                    <td>原样返回，utf-8编码</td>
                                                </tr>
                                                <tr>
                                                    <td>fxstatus</td>
                                                    <td>订单状态</td>
                                                    <td>是</td>
                                                    <td>【1代表支付成功】</td>
                                                </tr>
                                                <tr>
                                                    <td>fxtime</td>
                                                    <td>支付时间</td>
                                                    <td>是</td>
                                                    <td>支付成功时的时间，unix时间戳。</td>
                                                </tr>
                                                <tr>
                                                    <td>fxsign</td>
                                                    <td>签名【md5(订单状态+商务号+商户订单号+支付金额+商户秘钥)】</td>
                                                    <td>是</td>
                                                    <td>通过签名算法计算得出的签名值。</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                        <p><font color="red">【商户接收数据后需要返回success代表通知成功】</font></p>

                                        <p>订单查询【提交参数GET或POST均可】</p>
                                        <table class="table table-bordered">
                                            <thead>
                                                <tr>
                                                    <th>参数</th>
                                                    <th>参数含义</th>
                                                    <th>必须</th>
                                                    <th>说明</th>
                                                </tr>
                                            </thead>
                                            <tbody>
                                                <tr>
                                                    <td>fxid</td>
                                                    <td>商户ID</td>
                                                    <td>是</td>
                                                    <td>唯一号，由蓝夜支付提供</td>
                                                </tr>
                                                <tr>
                                                    <td>fxddh</td>
                                                    <td>商户订单号</td>
                                                    <td>是</td>
                                                    <td>平台返回商户提交的订单号</td>
                                                </tr>
                                                <tr>
                                                    <td>fxaction</td>
                                                    <td>商户查询动作</td>
                                                    <td>是</td>
                                                    <td>商户查询动作，这里填写【orderquery】</td>
                                                </tr>
                                                <tr>
                                                    <td>fxsign</td>
                                                    <td>签名【md5(商务号+商户订单号+商户查询动作+商户秘钥)】</td>
                                                    <td>是</td>
                                                    <td>通过签名算法计算得出的签名值。</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                        <p>订单查询返回【数据格式：json】</p>
                                        <table class="table table-bordered">
                                            <thead>
                                                <tr>
                                                    <th>参数</th>
                                                    <th>参数含义</th>
                                                    <th>必须</th>
                                                    <th>说明</th>
                                                </tr>
                                            </thead>
                                            <tbody>
                                                <tr>
                                                    <td>fxid</td>
                                                    <td>商户ID</td>
                                                    <td>是</td>
                                                    <td>唯一号，由蓝夜支付提供</td>
                                                </tr>
                                                <tr>
                                                    <td>fxstatus</td>
                                                    <td>状态</td>
                                                    <td>是</td>
                                                    <td>支付状态【1正常支付】【0支付异常】</td>
                                                </tr>
                                                <tr>
                                                    <td>fxddh</td>
                                                    <td>商户订单号</td>
                                                    <td>是</td>
                                                    <td>平台返回商户提交的订单号</td>
                                                </tr>
                                                <tr>
                                                    <td>fxorder</td>
                                                    <td>平台订单号</td>
                                                    <td>是</td>
                                                    <td>平台内部生成的订单号</td>
                                                </tr>
                                                <tr>
                                                    <td>fxdesc</td>
                                                    <td>商品名称</td>
                                                    <td>是</td>
                                                    <td>utf-8编码</td>
                                                </tr>
                                                <tr>
                                                    <td>fxfee</td>
                                                    <td>支付金额</td>
                                                    <td>是</td>
                                                    <td>支付的价格(单位：元)</td>
                                                </tr>
                                                <tr>
                                                    <td>fxattch</td>
                                                    <td>附加信息</td>
                                                    <td>是</td>
                                                    <td>原样返回，utf-8编码</td>
                                                </tr>
                                                <tr>
                                                    <td>fxtime</td>
                                                    <td>支付时间</td>
                                                    <td>是</td>
                                                    <td>支付成功时的时间，unix时间戳。</td>
                                                </tr>
                                                <tr>
                                                    <td>fxsign</td>
                                                    <td>签名【md5(订单状态+商务号+商户订单号+支付金额+商户秘钥)】</td>
                                                    <td>是</td>
                                                    <td>通过签名算法计算得出的签名值。</td>
                                                </tr>
                                                <tr>
                                                    <td>error</td>
                                                    <td>错误信息</td>
                                                    <td>是</td>
                                                    <td>错误状态下返回错误信息utf-8编码数据</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                        <p id="yh">银行附录</p>
                                        <table class="table table-bordered">
                                            <thead>
                                                <tr>
                                                    <th>银行名称</th>
                                                    <th>银行编号</th>
                                                </tr>
                                            </thead>
                                            <tbody>
                                                <tr>
                                                    <td>中国银行</td>
                                                    <td>BOC</td>
                                                </tr><tr>
                                                    <td>中国工商银行</td>
                                                    <td>ICBC</td>
                                                </tr><tr>
                                                    <td>中国建设银行</td>
                                                    <td>CCB</td>
                                                </tr><tr>
                                                    <td>中国农业银行</td>
                                                    <td>ABC</td>
                                                </tr><tr>
                                                    <td>中国邮政银行</td>
                                                    <td>PSBC</td>
                                                </tr><tr>
                                                    <td>交通银行</td>
                                                    <td>BCM</td>
                                                </tr><tr>
                                                    <td>招商银行</td>
                                                    <td>CMB</td>
                                                </tr><tr>
                                                    <td>光大银行</td>
                                                    <td>CEB</td>
                                                </tr><tr>
                                                    <td>兴业银行</td>
                                                    <td>CIB</td>
                                                </tr><tr>
                                                    <td>华夏银行</td>
                                                    <td>HXB</td>
                                                </tr><tr>
                                                    <td>广发银行</td>
                                                    <td>GDB</td>
                                                </tr><tr>
                                                    <td>浦发银行</td>
                                                    <td>SPDB</td>
                                                </tr><tr>
                                                    <td>平安银行</td>
                                                    <td>SZPAB</td>
                                                </tr><tr>
                                                    <td>中国民生银行</td>
                                                    <td>CMBC</td>
                                                </tr>                                            </tbody>
                                        </table>
                                    </div>
                                </div>
                            </div>                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script src="/Public/plugin/clipboard.js"></script> 
    <script>
        $(document).ready(function () {
            $('.paysubmit').on('click', function () {
                $('.imgediv').css({'display': 'none'});
                var pay = $('.jkstyle option:selected').val();

                if (typeof (pay) == 'undefined' || pay == '') {
                    layer.alert('请选择支付方式');
                    return false;
                }

                var index = layer.load();
                $.post('', {'pay': pay, 'times': Math.random()}, function (data) {
                    layer.close(index);
                    if (data['status'] == 1) {
                        if (pay.indexOf('sm') != -1) {
                            $('.imgewm').html('<p><img src="' + data['data'][0] + '"/></p><p>扫码支付，<a href="javascript:location.reload();">已付款</a></p>');
                            $('.imgediv').css({'display': 'block'});
                        } else {
                            location.href = data['data'][0];
                        }
                    } else {
                        layer.alert(data['data']);
                    }
                });
            });

            var targetText = $("#target").text();
            var clipboard = new Clipboard('#copy_btn');
            clipboard.on('success', function (e) {
                alert("复制成功");
                e.clearSelection();
            });
            
            $('#copy_show').click(function(){
                var status=$(this).attr('status');
                if(status=='1'){
                    $(this).text('隐藏');
                    $(this).attr('status',2);
                    $('.miyaocon').text($('#copy_btn').attr('data-clipboard-text'));
                }else{
                    $(this).text('查看');
                    $(this).attr('status',1);
                    $('.miyaocon').text('******');
                }
            });

            $('#reset_btn').click(function () {
                var idname = "resetkeydiv";
                var content = '<div style="margin:25px 20px 10px 20px;">' +
                        '<table border="0"><tbody>' +
                        '<tr><td align="center"><b>支付密码：</b></td>' +
                        '<td>' +
                        '<input type="password" id="paypass" value="" style="margin:0px 10px;width:150px;padding:5px 5px;color:#555;"/>' +
                        '</td>' +
                        '<td align="center" colspan="2">' +
                        '<input type="button" value="重置秘钥" id="savesubmit"/>' +
                        '<input type="hidden" value="idName" id="closediv" />' +
                        '</td></tr>' +
                        '</tbody></table>' +
                        '<div id="showsaveinfo"></div>' +
                        '<div id="explain">' +
                        '<b style="color:#000;">重置秘钥后所有之前的对接信息将失效。</b>' +
                        '</div></div>';
                layer.open({
                    id: 'resetkeydiv',
                    type: 1,
                    title: '重置秘钥',
                    content: content,
                    area: ['400px', '150px'],
                    btn: []
                });
            });
            $('#savesubmit').live('click', function () {
                $('#showsaveinfo').html('');
                var paypass = $('#paypass').val();
                var index = layer.load();
                $.post('/home/resetkey.html', {'paypass': paypass, 'times': Math.random()}, function (data) {
                    layer.close(index);
                    if (data.status == '0') {
                        layer.msg(data['data']);
                    } else {
                        layer.closeAll();
                        layer.msg('秘钥重置成功');
                        $("#copy_btn").attr('data-clipboard-text',data['data'][0]);
                        if($('#copy_show').attr('status')=='2') $('.miyaocon').text(data['data'][0]);
                    }
                });
            });
        });
    </script>

        <div style="display:none"> dsfghjkojkjk123 dsfghjkojkjk147</div>
 

</body></html>
