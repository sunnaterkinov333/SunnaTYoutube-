
<?php 
ob_start();
error_reporting(0);

define('SunnaTYotube',"6074674133:AAHeiPQdVnfGvDDWl8XBFMKbNtk5N80a1eA");
$Admin = "5208050021";
$vipkanal = "SunnaT Youtube"; /*@SunnaYT_bot*/
$Visacard = "4151680022735987";
$Visacard = "4151680022735987";

function bot($method,$datas=[]){
    $url = "https://api.telegram.org/bot".DasturchiNet."/".$method;
    $ch = curl_init();
    curl_setopt($ch,CURLOPT_URL,$url);
    curl_setopt($ch,CURLOPT_RETURNTRANSFER,true);
    curl_setopt($ch,CURLOPT_POSTFIELDS,$datas);
    $res = curl_exec($ch);
    if(curl_error($ch)){
        var_dump(curl_error($ch));
    }else{
        return json_decode($res);
    }
}

///Avto Webhook!
$a=file_get_contents("https://api.telegram.org/bot".Islombek."/setwebhook?url=".$_SERVER['SERVER_NAME']."".$_SERVER['SCRIPT_NAME']);
echo $a;
//

$DasturchiNet = json_decode(file_get_contents('php://input'));
$message = $DasturchiNet->message;
$cid = $message->chat->id;
$name = $message->chat->first_name;
$tx = $message->text;
$Islombek = file_get_contents("Islombek/$cid.Ixtiyor");
$m_saved = file_get_contents("Islombek/inew.txt");
$m_save = file_get_contents("Islombek/id.txt");
$mid = $message->message_id;
$type = $message->chat->type;
$text = $message->text;
$uid= $message->from->id;
$name = $message->from->first_name;
$name = $message->from->first_name;
$name = $message->from->first_name;
$familya = $message->from->last_name;
$bio = $message->from->about;
$username = $message->from->username;
$chat_id = $message->chat->id;
$reply = $message->reply_to_message->text;
$nameru = "<a href='tg://user?id=$uid'>$name</a>";

$rpl = json_encode([
            'resize_keyboard'=>false,
            'force_reply'=>true,
            'selective'=>true
        ]);


//inline uchun metodlar
$data = $DasturchiNet->callback_query->data;
$qid = $DasturchiNet->callback_query->id;
$cid2 = $DasturchiNet->callback_query->message->chat->id;
$mid2 = $DasturchiNet->callback_query->message->message_id;
$callfrid = $DasturchiNet->callback_query->from->id;
$callname = $DasturchiNet->callback_query->from->first_name;
$calluser = $DasturchiNet->callback_query->from->username;
$surname = $DasturchiNet->callback_query->from->last_name;
$about = $DasturchiNet->callback_query->from->about;
$nameuz = "<a href='tg://user?id=$callfrid'>$callname $surname</a>";
mkdir("Ixtiyor");

if($text == "/start"){
bot('Sendmessage',[
'chat_id'=>$cid,
'text'=>"<b>📋 Quyidagilardan birini tanlang:</b>",
'parse_mode'=>'html',
'reply_markup'=>json_encode([
'inline_keyboard'=>[
[['text'=>"➕Vipga Obuna Boʻlish",'callback_data'=>"oplata"]],
]
]),
]);
  }


if($data == "menyu"){
        bot('editMessageText',[
        'chat_id'=>$cid2,
        'message_id'=>$mid2,
        'text'=>"*📋Quyidagilardan birini tanlang:*",
'parse_mode'=>"Markdown",
        'reply_markup'=>json_encode([
'inline_keyboard'=>[
[['text'=>"➕Vipga Obuna Boʻlish",'callback_data'=>"oplata"]],
]
]),
]);
}

if($data == "oplata"){
        bot('editMessageText',[
        'chat_id'=>$cid2,
        'message_id'=>$mid2,
        'text'=>"⏱ <b>Yuklanmoqda...</b>",
       'parse_mode'=>'html',
]);
       bot('editMessageText',[
      'chat_id'=>$cid2,
     'message_id'=>$mid2 + 1,
'text'=>"⏱ <b>Yuklanmoqda...</b>",
       'parse_mode'=>'html',
]);
     bot('editMessageText',[
        'chat_id'=>$cid2,
       'message_id'=>$mid2,
        'text'=>"*🤝 Obunani faollashtirish uchun quyidagi hamyonlarning biriga kerakli mablag'ni kiritishingiz kerak!*",
'parse_mode'=>"Markdown",
        'reply_markup'=>json_encode([
        'inline_keyboard'=>[
[['text'=>"💳 Visa",'callback_data'=>"Visa"],['text'=>"💳 Visa",'callback_data'=>"Visa"]],
[['text'=>"◀️ Orqaga",'callback_data'=>"menyu"]],
]
])
]);
}



if($data == "orqa"){
        bot('editMessageText',[
        'chat_id'=>$cid2,
        'message_id'=>$mid2,
        'text'=>"*🤝 Obunani faollashtirish uchun quyidagi hamyonlarning biriga kerakli mablag'ni kiritishingiz kerak!*",
'parse_mode'=>"Markdown",
        'reply_markup'=>json_encode([
        'inline_keyboard'=>[
[['text'=>"💳 Visa",'callback_data'=>"Visa"],['text'=>"💳 Visa",'callback_data'=>"Visa"]],
[['text'=>"◀️ Orqaga",'callback_data'=>"menyu"]],
]
])
]);
}

if($data == "Visa"){
	bot('editMessageText',[
	'chat_id'=>$cid2,
	'message_id'=>$mid2,
	'text'=>"<b>📋 To'lov tizimi:</b> CLICK

<b>💳 Hamyon ( yoki karta ):</b> <code>$humo</code>
<b>💵 1 oylik obuna narxi:</b> <u>50000 so'm</u>


<b>Qo'shimcha:</b> Almashuvingiz muvaffaqiyatli bajarilishi uchun quyidagi harakatlarni amalga oshiring: 
1) Istalgan pul miqdorini tepadagi Hamyonga tashlang
2) «✅ To'lov qildim» tugmasini bosing; 
3) Qancha pul miqdoni yuborganingizni kiriting;
4) Toʻlov haqidagi suratni botga yuboring;
5) Operator tomonidan almashuv tasdiqlanishini kuting.",
'parse_mode'=>"html",
'reply_markup'=>json_encode([
'inline_keyboard'=>[
[['text'=>"✅ To'lov qildim",'callback_data'=>"money"]],
[['text'=>"◀️ Orqaga",'callback_data'=>"orqa"]],
]
])
]);
}

if($data == "Visa"){
	bot('editMessageText',[
	'chat_id'=>$cid2,
	'message_id'=>$mid2,
	'text'=>"<b>📋 To'lov tizimi:</b> Visa

<b>💳 Hamyon ( yoki karta ):</b> <code>$uzcard</code>
<b>📝 Izoh:</b> <code>$cid2</code>
<b>💵 1 oylik obuna narxi:</b> <u>50000 so'm</u>


<b>Qo'shimcha:</b> Almashuvingiz muvaffaqiyatli bajarilishi uchun quyidagi harakatlarni amalga oshiring: 
1) Istalgan pul miqdorini tepadagi Hamyonga tashlang
2) «✅ To'lov qildim» tugmasini bosing; 
3) Qancha pul miqdoni yuborganingizni kiriting;
4) Toʻlov haqidagi suratni botga yuboring;
5) Operator tomonidan almashuv tasdiqlanishini kuting.",
'parse_mode'=>"html",
'reply_markup'=>json_encode([
'inline_keyboard'=>[
[['text'=>"✅ To'lov qildim",'callback_data'=>"money"]],
[['text'=>"◀️ Orqaga",'callback_data'=>"orqa"]],
]
])
]);
}


if($data == "money"){
	bot('DeleteMessage',[
	'chat_id'=>$cid2,
	'message_id'=>$mid2,
	]);
	bot('SendMessage',[
	'chat_id'=>$cid2,
	'text'=>"<b>To'lov miqdorini kiriting:</b>",
	'parse_mode'=>'html',
'reply_markup'=>$back,
	]);
	file_put_contents("Islombek/$cid2.Islombek",'oplata');
}

if($Islombek == "oplata"){
if(is_numeric($text)=="true"){
	file_put_contents("Islombek/inew.txt",$text);
	file_put_contents("Islombek/id.txt",$cid);
	bot('SendMessage',[
	'chat_id'=>$cid,
	'text'=>"<b>To'lovingizni chek yoki skreenshotini shu yerga yuboring:</b>",
	'parse_mode'=>'html',
	]);
	file_put_contents("Islombek/$cid.Ixtiyor",'rasm');
}else{
bot('SendMessage',[
	'chat_id'=>$cid,
	'text'=>"<b>Qiymat qabul qilinmadi, qayta urinib ko'ring:</b>",
	'parse_mode'=>'html',
]);
}
}

if($Islombek == "rasm"){
$photo = $message->photo;
$file = $photo[count($photo)-1]->file_id;
bot('sendMessage',[
'chat_id'=>$cid,
'text'=>"*Hisobni to'ldirganingiz haqida ma'lumot asosiy adminga yuborildi. Agar to'lovni amalga oshirganingiz haqida ma'lumot mavjud bo'lsa, Sizga rasmiy silka beriladi.*",
'parse_mode'=>'MarkDown',
'reply_markup'=>$main_menu
]);
unlink("Islombek/$cid.Islombek");
    bot('sendPhoto',[
        'chat_id'=>$Admin,
        'photo'=>$file,
        'caption'=>"📄 <b>Foydalanuvchidan check:

👮‍♂️ Foydalanuvchi:</b> <a href='https://t.me/$username'>$name</a>
🔎 <b>iD raqami:</b> $fid
💵 <b>To'lov miqdori:</b> $m_saved",
'disable_web_page_preview'=>true,
'parse_mode'=>'html',
'reply_markup'=>json_encode([
'inline_keyboard'=>[
[['text'=>"✅ Qabul qilindi",'callback_data'=>"on"],['text'=>"❌ Qabul qilinmadi",'callback_data'=>"off"]],
]
])
]);
}

if($data == "on"){
	bot('deleteMessage',[
	'chat_id'=>$cid2,
	'message_id'=>$mid2,
	]);
	bot('SendMessage',[
	'chat_id'=>$m_save,
	'text'=>"<b>Foydalanuvchi $m_saved so'm ga to'ldirish bo'yicha yuborgan so'rovingiz qabul qilindi.
Sizning kanalga qoʻshilish silkangiz: https://https://t.me/SunnatYoutube</b>",
	'parse_mode'=>'html',
	]);
		bot('SendMessage',[
	'chat_id'=>$Admin,
	'text'=>"<b>Foydalanuvchi hisobini $m_saved so'm ga to'ldirish bo'yicha yuborgan so'rovi qabul qilindi.</b>",
	'parse_mode'=>'html',
	]);
	unlink("Islombek/id.txt");
	unlink("Islombek/inew.txt");
}

if($data == "off"){
	bot('deleteMessage',[
	'chat_id'=>$cid2,
	'message_id'=>$mid2,
	]);
	bot('SendMessage',[
	'chat_id'=>$m_save,
	'text'=>"<b>Hisobingizni $m_saved so'm ga to'ldirish bo'yicha yuborgan so'rovingiz qabul qilinmadi!</b>",
	'parse_mode'=>'html',
	]);
		bot('SendMessage',[
	'chat_id'=>$Admin,
	'text'=>"<b>Foydalanuvchi hisobini $m_saved $valyuta ga to'ldirish bo'yicha yuborgan so'rovi qabul qilinmadi!</b>",
	'parse_mode'=>'html',
	]);
	unlink("Islombek/id.txt");
	unlink("Islombek/inew.txt");
}



?>
