---
title: /SECTION (EDITBIN)
ms.date: 11/04/2016
f1_keywords:
- /section
helpviewer_keywords:
- -SECTION editbin option
- SECTION editbin option
- alignment characters in sections
- /SECTION editbin option
ms.assetid: 4680ab4e-c984-4251-8241-93440cad7615
ms.openlocfilehash: 8bcc925b34118630c872a0147b93291626b7c19b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822437"
---
# <a name="section-editbin"></a>/SECTION (EDITBIN)

```
/SECTION:name[=newname][,attributes][alignment]
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek, nesne dosyası bölümü için derlenmiş ya da bağlı ayarlanan öznitelikleri geçersiz kılma, bir bölümün özniteliklerini değiştirir.

Sonra iki nokta üst üste ( **:** ), belirtin *adı* bölümü. Bölüm adı değiştirmek için izleyin *adı* eşittir işareti (=) ve bir *newname* bölümü için.

Veya bölümün `attributes`, virgül belirtin (**,**) bir veya daha fazla öznitelik karakterlerle devam eder. Bir öznitelik negatif yapılacak, ünlem işareti (!) karakteriyle koyun. Aşağıdaki karakterlerden bellek öznitelikleri belirtin:

|Öznitelik|Ayar|
|---------------|-------------|
|c|kod|
|d|Discardable|
|e|yürütülebilir|
|ı|başlatılmış veriler|
|K|önbelleğe alınan sanal bellek|
|m|bağlantıyı Kaldır|
|o|bağlantı bilgileri|
|p|sanal disk belleği|
|r|read|
|s|shared|
|u|başlatılmamış veri|
|w|write|

Denetime *hizalama*, bir karakter belirtmek **A** hizalama boyutu bayt cinsinden şu şekilde ayarlamak için aşağıdaki karakterlerden birini ve ardından:

|Karakter|Bayt hizalama boyutu|
|---------------|-----------------------------|
|1.|1.|
|2|2|
|4|4|
|8|8|
|p|16|
|t|32|
|s|64|
|x|Hizalama yok|

Belirtin `attributes` ve *hizalama* hiçbir boşluk içeren bir dize olarak karakter. Karakterler büyük/küçük harfe duyarlı değildir.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN Seçenekleri](editbin-options.md)
