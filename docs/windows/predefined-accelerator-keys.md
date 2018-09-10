---
title: Önceden tanımlanmış Hızlandırıcı tuşları (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.accelerator
dev_langs:
- C++
helpviewer_keywords:
- accelerator keys
- keyboard shortcuts
- keyboard shortcuts [C++], predefined
ms.assetid: f234c5f2-4ec3-4c9e-834a-b5dd297625b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5e6498e0b0722b5de28b5569c5f3565b0f033ea9
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315684"
---
# <a name="predefined-accelerator-keys-c"></a>Önceden tanımlanmış Hızlandırıcı tuşları (C++)

Bir Windows uygulaması projesi parçası olabilecek önceden tanımlanmış Hızlandırıcı tuşları vardır. Bu sanal anahtarları bazıları Windows ortamınız için değişir. Diğer destek tarayıcılar veya Unicode uygulamalar. Bu anahtarları bir Hızlandırıcı kullanabilirsiniz.

|Anahtar|Açıklama|
|---------|-----------------|
|VK_ACCEPT|IME kabul edin|
|VK_BROWSER_BACK|Windows: Tarayıcı geri anahtarı|
|VK_BROWSER_FAVORITES|Windows: Tarayıcı sık kullanılanları anahtarı|
|VK_BROWSER_FORWARD|Windows: Tarayıcı İleri anahtarı|
|VK_BROWSER_HOME|Windows: Tarayıcı başlangıç ve ana anahtarı|
|VK_BROWSER_REFRESH|Windows: Tarayıcı Yenile anahtarı|
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
|VK_LAUNCH_APP1|Windows: Başlangıç uygulama 1 anahtarı|
|VK_LAUNCH_APP2|Windows: Başlangıç uygulaması 2 anahtarı|
|VK_LAUNCH_MAIL|Windows: Başlangıç posta anahtarı|
|VK_LAUNCH_MEDIA_SELECT|Windows: Ortam anahtarı seçin|
|VK_LCONTROL|Sola denetim anahtarı|
|VK_LMENU|Sol menü anahtarı|
|VK_LSHIFT|Sol SHIFT tuşunu|
|VK_MEDIA_NEXT_TRACK|Windows: Sonraki izleme anahtarı|
|VK_MEDIA_PLAY_PAUSE|Windows: Yürütme/duraklatma ortam anahtarı|
|VK_MEDIA_PREV_TRACK|Windows: Önceki izleme anahtarı|
|VK_MEDIA_STOP|Windows: Stop ortam anahtarı|
|VK_MODECHANGE|IME modu değişiklik isteği|
|VK_NONCONVERT|IME dönüştürme yok|
|VK_OEM_1|Windows: ABD Standart klavye için ';:' anahtarı|
|VK_OEM_102|Windows: Ya da açılı ayraç veya ters eğik çizgi tuşuna RT 102 tuşlu klavye|
|VK_OEM_2|Windows: ABD Standart klavye için '/?' anahtar|
|VK_OEM_3|Windows: ABD Standart klavye için '' ~' anahtarı|
|VK_OEM_4|Windows: ABD Standart klavye için ' [{' anahtarı|
|VK_OEM_5|Windows: ABD Standart klavye için '\\&#124;' anahtarı|
|VK_OEM_6|Windows: ABD Standart klavye için ']}' anahtarı|
|VK_OEM_7|Windows: ABD Standart klavye için 'tek-teklif/çift tırnak' anahtarı|
|VK_OEM_COMMA|Windows: tüm ülke/bölge için ',' anahtarı|
|VK_OEM_MINUS|Windows: tüm ülke/bölge için '-' anahtarı|
|VK_OEM_PERIOD|Windows: tüm ülke/bölge için '.' anahtarı|
|VK_OEM_PLUS|Windows: tüm ülke/bölge için '+' anahtarı|
|VK_PACKET|Windows: tuş vuruşları değilmiş gibi Unicode karakterler geçirmek için kullanılır.|
|VK_RCONTROL|Doğru denetim anahtarı|
|VK_RMENU|Sağ menü anahtarı|
|VK_RSHIFT|Sağ SHIFT tuşunu|
|VK_SLEEP|Bilgisayar uyku anahtarı|
|VK_VOLUME_DOWN|Windows: Birim tuşunu|
|VK_VOLUME_MUTE|Windows: Birim sessiz anahtarı|
|VK_VOLUME_UP|Windows: Birim anahtarı|
|VK_XBUTTON1|Windows: Düğme X1 fare|
|VK_XBUTTON2|Windows: Düğme X2 fare|

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)  
[Kaynak Düzenleyicileri](../windows/resource-editors.md)