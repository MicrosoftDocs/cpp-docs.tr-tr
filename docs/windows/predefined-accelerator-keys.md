---
title: Hızlandırıcı tuşları (C++)
ms.date: 02/14/2019
helpviewer_keywords:
- accelerator keys
- keyboard shortcuts
- keyboard shortcuts [C++], predefined
- menus [C++], shortcut keys
- keyboard shortcuts [C++], menu association
ms.assetid: f234c5f2-4ec3-4c9e-834a-b5dd297625b9
ms.openlocfilehash: 6753545b711ff45f79b3140b30a2edbcea81c39c
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445405"
---
# <a name="accelerator-keys-c"></a>Hızlandırıcı tuşları (C++)

## <a name="predefined-accelerator-keys"></a>Önceden Tanımlanmış Hızlandırıcı Tuşları

Bir Windows uygulama projesinin parçası olabilecek bir dizi önceden tanımlanmış hızlandırıcı anahtarı vardır. Bu sanal anahtarların bazıları Windows ortamı içindir. Diğerleri tarayıcı veya Unicode uygulamalarını destekler. Herhangi bir hızlandırıcıda bu anahtarların herhangi birini kullanabilirsiniz.

|Anahtar|Açıklama|
|---------|-----------------|
|VK_ACCEPT|(IME) kabul et|
|VK_BROWSER_BACK|Pencerelerin Tarayıcı, **arka** anahtar|
|VK_BROWSER_FAVORITES|Pencerelerin Tarayıcı, **Sık Kullanılanlar** anahtarı|
|VK_BROWSER_FORWARD|Pencerelerin Tarayıcı, **iletme** anahtarı|
|VK_BROWSER_HOME|Pencerelerin Tarayıcı, **Başlangıç** ve **giriş** anahtarı|
|VK_BROWSER_REFRESH|Pencerelerin Tarayıcı, anahtarı **Yenile**|
|VK_BROWSER_SEARCH|Pencerelerin Tarayıcı, **arama** anahtarı|
|VK_BROWSER_STOP|Pencerelerin Tarayıcı, anahtarı **Durdur**|
|VK_CONVERT|(IME) Dönüştür|
|VK_FINAL|(IME) son modu|
|VK_HANGUEL|IME Hanguel modu (uyumluluk için korunur, VK_HANGUL kullanın)|
|VK_HANGUL|IME Hangul modu|
|VK_HANJA|IME Hanja modu|
|VK_JUNJA|IME Junja modu|
|VK_KANA|IME Kana modu|
|VK_KANJI|IME Kanji modu|
|VK_LAUNCH_APP1|Pencerelerin **Uygulama 1 anahtarını Başlat**|
|VK_LAUNCH_APP2|Pencerelerin **Uygulamayı Başlat 2** anahtarı|
|VK_LAUNCH_MAIL|Pencerelerin **Posta anahtarını Başlat**|
|VK_LAUNCH_MEDIA_SELECT|Pencerelerin **Medya anahtarını seçin**|
|VK_LCONTROL|**Sol CTRL** tuşu|
|VK_LMENU|**Sol menü** tuşu|
|VK_LSHIFT|**Sol SHIFT** tuşu|
|VK_MEDIA_NEXT_TRACK|Pencerelerin **Sonraki izleme** anahtarı|
|VK_MEDIA_PLAY_PAUSE|Pencerelerin **Medya anahtarını Oynat/Duraklat**|
|VK_MEDIA_PREV_TRACK|Pencerelerin **Önceki izleme** anahtarı|
|VK_MEDIA_STOP|Pencerelerin **Medya anahtarını durdur**|
|VK_MODECHANGE|(IME) modu değişiklik isteği|
|VK_NONCONVERT|(IME) dönüştürme olmayan|
|VK_OEM_1|Pencerelerin ABD standart klavyesi için **;:** anahtarı|
|VK_OEM_102|Pencerelerin RT 102 anahtar klavyesinde açılı ayraç tuşu ya da ters eğik çizgi tuşu|
|VK_OEM_2|Pencerelerin ABD standart klavyesi için **/?** anahtar|
|VK_OEM_3|Pencerelerin ABD standart klavyesi için **`~** anahtarı|
|VK_OEM_4|Pencerelerin ABD standart klavyesi için **[{** Key|
|VK_OEM_5|Pencerelerin ABD standart klavyesi için **\\&#124;**  anahtarı|
|VK_OEM_6|Pencerelerin ABD standart klavyesi için **]}** anahtarı|
|VK_OEM_7|Pencerelerin ABD standart klavyesi için, ' tek tırnak/çift tırnak ' anahtarı|
|VK_OEM_COMMA|Pencerelerin Herhangi bir ülke/bölge, **,** anahtar|
|VK_OEM_MINUS|Pencerelerin Herhangi bir ülke/bölge için **-** anahtarı|
|VK_OEM_PERIOD|Pencerelerin Herhangi bir ülke/bölge için, **.** anahtar|
|VK_OEM_PLUS|Pencerelerin Herhangi bir ülke/bölge için **+** anahtarı|
|VK_PACKET|Pencerelerin Unicode karakterleri klavye tuşları gibi geçirmek için kullanılır.|
|VK_RCONTROL|**Sağ CTRL** tuşu|
|VK_RMENU|**Sağ menü** tuşu|
|VK_RSHIFT|**Sağ SHIFT** tuşu|
|VK_SLEEP|**Bilgisayar uyku** anahtarı|
|VK_VOLUME_DOWN|Pencerelerin **Birim aşağı** tuşu|
|VK_VOLUME_MUTE|Pencerelerin **Birim sessiz** anahtar|
|VK_VOLUME_UP|Pencerelerin **Birim yukarı** anahtar|
|VK_XBUTTON1|Pencerelerin **X1** fare düğmesi|
|VK_XBUTTON2|Pencerelerin **X2** fare düğmesi|

## <a name="accelerator-key-association"></a>Hızlandırıcı tuş Ilişkilendirmesi

Birçok kez, bir menü öğesi ve klavye bileşiminin aynı program komutunu vermesini istiyorsunuz. Bu eylemi, menü öğesine ve uygulamanızın Hızlandırıcı tablosundaki bir girdiye aynı kaynak tanımlayıcısını (ID) atayarak yapabilirsiniz. Daha sonra hızlandırıcının adını göstermek için menü öğesinin başlığını düzenlersiniz. Menü öğeleri ve hızlandırıcı tuşları hakkında daha fazla bilgi için, bkz. [menü komutları](../windows/associating-a-menu-command-with-an-accelerator-key.md).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)<br/>