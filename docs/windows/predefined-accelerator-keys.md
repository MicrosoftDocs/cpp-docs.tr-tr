---
title: Hızlandırma tuşları (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.accelerator
helpviewer_keywords:
- accelerator keys
- keyboard shortcuts
- keyboard shortcuts [C++], predefined
- menus [C++], shortcut keys
- keyboard shortcuts [C++], menu association
ms.assetid: f234c5f2-4ec3-4c9e-834a-b5dd297625b9
ms.openlocfilehash: 99867f146ca80d8b48c9be9deb59044207b33af1
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210503"
---
# <a name="accelerator-keys-c"></a>Hızlandırma tuşları (C++)

## <a name="predefined-accelerator-keys"></a>Önceden Tanımlanmış Hızlandırıcı Tuşları

Bir Windows uygulaması projesi parçası olabilecek önceden tanımlanmış Hızlandırıcı tuşları vardır. Bu sanal anahtarları bazıları Windows ortamınız için değişir. Diğerleri, tarayıcı veya Unicode uygulamaları destekler. Bu anahtarları bir Hızlandırıcı kullanabilirsiniz.

|Anahtar|Açıklama|
|---------|-----------------|
|VK_ACCEPT|(IME) kabul edin|
|VK_BROWSER_BACK|(Windows) Tarayıcı **geri** anahtarı|
|VK_BROWSER_FAVORITES|(Windows) Tarayıcı **Sık Kullanılanlar** anahtarı|
|VK_BROWSER_FORWARD|(Windows) Tarayıcı **İleri** anahtarı|
|VK_BROWSER_HOME|(Windows) Tarayıcı **Başlat** ve **giriş** anahtarı|
|VK_BROWSER_REFRESH|(Windows) Tarayıcı **Yenile** anahtarı|
|VK_BROWSER_SEARCH|(Windows) Tarayıcı **arama** anahtarı|
|VK_BROWSER_STOP|(Windows) Tarayıcı **Durdur** anahtarı|
|VK_CONVERT|(IME) dönüştürme|
|VK_FINAL|(IME) son modu|
|VK_HANGUEL|(IME) Hanguel modu (VK_HANGUL kullanmak için Uyumluluk saklanır,)|
|VK_HANGUL|(IME) Hangul modu|
|VK_HANJA|(IME) Hanja modu|
|VK_JUNJA|(IME) Junja modu|
|VK_KANA|(IME) Kana modu|
|VK_KANJI|(IME) Kanji modu|
|VK_LAUNCH_APP1|(Windows) **Başlangıç uygulaması 1** anahtarı|
|VK_LAUNCH_APP2|(Windows) **Başlat uygulama 2** anahtarı|
|VK_LAUNCH_MAIL|(Windows) **Posta Başlat** anahtarı|
|VK_LAUNCH_MEDIA_SELECT|(Windows) **Medya Seç** anahtarı|
|VK_LCONTROL|**Sol Ctrl** anahtarı|
|VK_LMENU|**Sol menü** anahtarı|
|VK_LSHIFT|**Sol Shift** anahtarı|
|VK_MEDIA_NEXT_TRACK|(Windows) **Sonraki parçaya** anahtarı|
|VK_MEDIA_PLAY_PAUSE|(Windows) **Play/duraklatma medya** anahtarı|
|VK_MEDIA_PREV_TRACK|(Windows) **Önceki izleme** anahtarı|
|VK_MEDIA_STOP|(Windows) **Durdur medya** anahtarı|
|VK_MODECHANGE|(IME) modunda değişiklik isteği|
|VK_NONCONVERT|(IME) dönüştürme yok|
|VK_OEM_1|(Windows) ABD Standart klavye için **;:** anahtarı|
|VK_OEM_102|(Windows) Açılı ayraç anahtar veya ters eğik çizgi anahtarı RT 102 tuşlu klavye|
|VK_OEM_2|(Windows) ABD Standart klavye için **/?** anahtar|
|VK_OEM_3|(Windows) ABD Standart klavye için **`~** anahtarı|
|VK_OEM_4|(Windows) ABD Standart klavye için **[{** anahtarı|
|VK_OEM_5|(Windows) ABD Standart klavye için **\\ &#124;** anahtarı|
|VK_OEM_6|(Windows) ABD Standart klavye için **]}** anahtarı|
|VK_OEM_7|(Windows) ABD Standart klavye için 'tek-teklif/çift tırnak' anahtarı|
|VK_OEM_COMMA|(Windows) Tüm ülke/bölge için **,** anahtarı|
|VK_OEM_MINUS|(Windows) Tüm ülke/bölge için **-** anahtarı|
|VK_OEM_PERIOD|(Windows) Tüm ülke/bölge için **.** anahtar|
|VK_OEM_PLUS|(Windows) Tüm ülke/bölge için **+** anahtarı|
|VK_PACKET|(Windows) Unicode karakterler tuş vuruşları iseler olarak geçirmek için kullanılır.|
|VK_RCONTROL|**Sağ Ctrl** anahtarı|
|VK_RMENU|**Sağ menü** anahtarı|
|VK_RSHIFT|**Sağ Shift** anahtarı|
|VK_SLEEP|**Bilgisayar uyku modunda** anahtarı|
|VK_VOLUME_DOWN|(Windows) **Birim aşağı** anahtarı|
|VK_VOLUME_MUTE|(Windows) **Birim sessiz** anahtarı|
|VK_VOLUME_UP|(Windows) **Birim yukarı** anahtarı|
|VK_XBUTTON1|(Windows) **X1** fare düğmesi|
|VK_XBUTTON2|(Windows) **X2** fare düğmesi|

## <a name="accelerator-key-association"></a>Hızlandırıcı anahtar ilişkilendirmesi

Çoğu zaman, bir menü öğesi ve aynı programı komutu vermek için bir tuş bileşimini istersiniz. Menü öğesi ve uygulamanızın Hızlandırıcı tablosunda bir giriş için aynı kaynak tanımlayıcısını (ID) atayarak, bu eylemi gerçekleştirin. Hızlandırıcı adını göstermek için menü öğesinin resim yazısı Düzenle. Menü öğeleri ve kısayol tuşları hakkında daha fazla bilgi için bkz. [menü komutları](../windows/associating-a-menu-command-with-an-accelerator-key.md).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)<br/>