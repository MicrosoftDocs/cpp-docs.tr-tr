---
title: Hızlandırma tuşları (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.accelerator
helpviewer_keywords:
- accelerator keys
- keyboard shortcuts
- keyboard shortcuts [C++], predefined
- menus [C++], shortcut keys
- keyboard shortcuts [C++], menu association
ms.assetid: f234c5f2-4ec3-4c9e-834a-b5dd297625b9
ms.openlocfilehash: 1e87d80b8995760eecda34334dab702480bd9669
ms.sourcegitcommit: 5beace7dcc6bf0e8b8cc96a930e7424f9daa05cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2019
ms.locfileid: "55232129"
---
# <a name="accelerator-keys-c"></a>Hızlandırma tuşları (C++)

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*.

## <a name="predefined-accelerator-keys"></a>Önceden Tanımlanmış Hızlandırıcı Tuşları

Bir Windows uygulaması projesi parçası olabilecek önceden tanımlanmış Hızlandırıcı tuşları vardır. Bu sanal anahtarları bazıları Windows ortamınız için değişir. Diğer destek tarayıcılar veya Unicode uygulamalar. Bu anahtarları bir Hızlandırıcı kullanabilirsiniz.

|Anahtar|Açıklama|
|---------|-----------------|
|VK_ACCEPT|IME kabul edin|
|VK_BROWSER_BACK|Windows: Tarayıcı arka anahtarı|
|VK_BROWSER_FAVORITES|Windows: Tarayıcı sık kullanılanları anahtarı|
|VK_BROWSER_FORWARD|Windows: Tarayıcı İleri anahtarı|
|VK_BROWSER_HOME|Windows: Tarayıcı başlangıç ve ana anahtarı|
|VK_BROWSER_REFRESH|Windows: Tarayıcı yenilemesi anahtarı|
|VK_BROWSER_SEARCH|Windows: Tarayıcı arama anahtarı|
|VK_BROWSER_STOP|Windows: Tarayıcı Durdur anahtarı|
|VK_CONVERT|IME dönüştürme|
|VK_FINAL|Son IME modu|
|VK_HANGUEL|IME Hanguel modu (uyumluluk için; tutulan VK_HANGUL kullanın)|
|VK_HANGUL|IME Hangul modu|
|VK_HANJA|IME Hanja modu|
|VK_JUNJA|IME Junja modu|
|VK_KANA|IME Kana modu|
|VK_KANJI|Kanji IME modu|
|VK_LAUNCH_APP1|Windows: Başlangıç uygulaması 1 anahtarı|
|VK_LAUNCH_APP2|Windows: Uygulama 2 anahtar Başlat|
|VK_LAUNCH_MAIL|Windows: Posta anahtar Başlat|
|VK_LAUNCH_MEDIA_SELECT|Windows: Ortam anahtarı seçin|
|VK_LCONTROL|Sola denetim anahtarı|
|VK_LMENU|Sol menü anahtarı|
|VK_LSHIFT|Sol SHIFT tuşunu|
|VK_MEDIA_NEXT_TRACK|Windows: Sonraki izleme anahtarı|
|VK_MEDIA_PLAY_PAUSE|Windows: Yürütme/duraklatma ortam anahtarı|
|VK_MEDIA_PREV_TRACK|Windows: Önceki izleme anahtarı|
|VK_MEDIA_STOP|Windows: Ortam anahtarı Durdur|
|VK_MODECHANGE|IME modu değişiklik isteği|
|VK_NONCONVERT|IME dönüştürme yok|
|VK_OEM_1|Windows: ABD Standart klavye için ';:' anahtarı|
|VK_OEM_102|Windows: Açılı ayraç anahtar veya ters eğik çizgi anahtarı RT 102 tuşlu klavye|
|VK_OEM_2|Windows: ABD Standart klavye için '/?' anahtar|
|VK_OEM_3|Windows: ABD Standart klavye için '' ~' anahtarı|
|VK_OEM_4|Windows: ABD Standart klavye için ' [{' anahtarı|
|VK_OEM_5|Windows: ABD Standart klavye için '\\&#124;' anahtarı|
|VK_OEM_6|Windows: ABD Standart klavye için ']}' anahtarı|
|VK_OEM_7|Windows: ABD Standart klavye için 'tek-teklif/çift tırnak' anahtarı|
|VK_OEM_COMMA|Windows: Tüm ülke/bölge için ',' anahtarı|
|VK_OEM_MINUS|Windows: Tüm ülke/bölge için '-' anahtarı|
|VK_OEM_PERIOD|Windows: Tüm ülke/bölge için '.' anahtarı|
|VK_OEM_PLUS|Windows: Tüm ülke/bölge için '+' anahtarı|
|VK_PACKET|Windows: Tuş vuruşları olmaları durumunda gibi Unicode karakterler geçirmek için kullanılır.|
|VK_RCONTROL|Doğru denetim anahtarı|
|VK_RMENU|Sağ menü anahtarı|
|VK_RSHIFT|Sağ SHIFT tuşunu|
|VK_SLEEP|Bilgisayar uyku anahtarı|
|VK_VOLUME_DOWN|Windows: Birim aşağı anahtarı|
|VK_VOLUME_MUTE|Windows: Birim sessiz anahtarı|
|VK_VOLUME_UP|Windows: Birim yukarı anahtarı|
|VK_XBUTTON1|Windows: X1 fare düğmesi|
|VK_XBUTTON2|Windows: X2 fare düğmesi|

## <a name="associating-an-accelerator-key-with-a-menu-item"></a>Hızlandırıcı Tuşunu Menü Öğesiyle İlişkilendirme

Çoğu zaman, bir menü öğesi ve aynı programı komutu vermek için bir tuş bileşimini istersiniz. Menü öğesi ve uygulamanızın Hızlandırıcı tablosunda bir giriş için aynı kaynak tanımlayıcısını (ID) atayarak bunu yapabilirsiniz. Hızlandırıcı adını göstermek için menü öğesinin resim yazısı Düzenle. Menü öğeleri ve kısayol tuşları hakkında daha fazla bilgi için bkz. [menü öğesi, bir Hızlandırıcı tuşuyla ilişkilendirme](../windows/associating-a-menu-command-with-an-accelerator-key.md).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)
