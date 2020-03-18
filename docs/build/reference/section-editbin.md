---
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
ms.openlocfilehash: 770e1d1c1cf288a7fe68f5bd076791d43f5b8572
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438919"
---
# <a name="section-editbin"></a>/SECTION (EDITBIN)

```
/SECTION:name[=newname][,attributes][alignment]
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, bir bölümün özniteliklerini değiştirir, bu, bölümün nesne dosyası derlendiğinde veya bağlandığında ayarlanan öznitelikleri geçersiz kılar.

İki nokta üst üste ( **:** ) sonra, bölümün *adını* belirtin. Bölüm adını değiştirmek için *adı* eşittir işareti (=) ve bölüm için bir *YeniAd* kullanın.

Bölümün `attributes`ayarlamak veya değiştirmek için, bir virgül ( **,** ) ve ardından bir veya daha fazla öznitelik karakteri belirtin. Bir özniteliğe bir öznitelik eklemek için, karakterinin önüne bir ünlem işareti (!) getirin. Aşağıdaki karakterler bellek özniteliklerini belirtir:

|Öznitelik|Ayar|
|---------------|-------------|
|c|kod|
|d|discardable|
|e|yürütülür|
|ı|başlatılan veriler|
|Ek|önbelleğe alınmış sanal bellek|
|m|bağlantıyı kaldır|
|o|bağlantı bilgisi|
|p|disk belleğine alınmış sanal bellek|
|r|read|
|s|shared|
|u|başlatılmamış veriler|
|w|write|

*Hizalamayı*denetlemek için, aşağıdaki karakterlerden birini izleyen karakteri belirterek, şöyle **bir** hizalama boyutunu aşağıda gösterildiği gibi ayarlayın:

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

Boşluk olmayan bir dize olarak `attributes` ve *Hizalama* karakterlerini belirtin. Karakterler büyük/küçük harfe duyarlı değildir.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN Seçenekleri](editbin-options.md)
