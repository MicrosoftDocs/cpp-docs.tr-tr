---
description: Daha fazla bilgi edinin:/SECTION (EDITBIN)
title: /SECTION (EDITBIN)
ms.date: 11/04/2016
f1_keywords:
- /section_editbin
helpviewer_keywords:
- -SECTION editbin option
- SECTION editbin option
- alignment characters in sections
- /SECTION editbin option
ms.assetid: 4680ab4e-c984-4251-8241-93440cad7615
ms.openlocfilehash: 51d1305ca4f3e0e8222ae9408b44563a4c480d57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224874"
---
# <a name="section-editbin"></a>/SECTION (EDITBIN)

```
/SECTION:name[=newname][,attributes][alignment]
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, bir bölümün özniteliklerini değiştirir, bu, bölümün nesne dosyası derlendiğinde veya bağlandığında ayarlanan öznitelikleri geçersiz kılar.

İki nokta üst üste ( **:** ) sonra, bölümün *adını* belirtin. Bölüm adını değiştirmek için *adı* eşittir işareti (=) ve bölüm için bir *YeniAd* kullanın.

Bölümü ayarlamak veya değiştirmek için, bir `attributes` virgül (**,**) ve ardından bir veya daha fazla öznitelik karakteri belirtin. Bir özniteliğe bir öznitelik eklemek için, karakterinin önüne bir ünlem işareti (!) getirin. Aşağıdaki karakterler bellek özniteliklerini belirtir:

|Öznitelik|Ayar|
|---------------|-------------|
|c|kod|
|d|discardable|
|e|yürütülür|
|ı|başlatılan veriler|
|k|önbelleğe alınmış sanal bellek|
|m|bağlantıyı kaldır|
|o|bağlantı bilgisi|
|p|disk belleğine alınmış sanal bellek|
|r|read|
|s|shared|
|u|başlatılmamış veriler|
|w|write|

*Hizalamayı* denetlemek için, aşağıdaki karakterlerden birini izleyen karakteri belirterek, şöyle **bir** hizalama boyutunu aşağıda gösterildiği gibi ayarlayın:

|Karakter|Bayt cinsinden hizalama boyutu|
|---------------|-----------------------------|
|1|1|
|2|2|
|4|4|
|8|8|
|p|16|
|t|32|
|s|64|
|x|hizalama yok|

Boşluk `attributes` olmayan bir dize olarak ve *Hizalama* karakterlerini belirtin. Karakterler büyük/küçük harfe duyarlı değildir.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN seçenekleri](editbin-options.md)
