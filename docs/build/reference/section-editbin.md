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
ms.openlocfilehash: 23a7ab9efc96ec10f4ad14547b0c0a20f13ac014
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523311"
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

## <a name="see-also"></a>Ayrıca Bkz.

[EDITBIN Seçenekleri](../../build/reference/editbin-options.md)