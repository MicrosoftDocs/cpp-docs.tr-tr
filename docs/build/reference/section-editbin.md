---
title: -SECTION (EDITBIN) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /section
dev_langs:
- C++
helpviewer_keywords:
- -SECTION editbin option
- SECTION editbin option
- alignment characters in sections
- /SECTION editbin option
ms.assetid: 4680ab4e-c984-4251-8241-93440cad7615
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e29e258b4fb661cfa06e057704bba983ad924f34
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378359"
---
# <a name="section-editbin"></a>/SECTION (EDITBIN)
```  
/SECTION:name[=newname][,attributes][alignment]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenek bölümü için nesne dosyası derlenmiş ya da bağlantılı ayarlanan öznitelikleri geçersiz kılma bir bölüm özniteliklerini değiştirir.  
  
 İki nokta üst üste sonra ( **:** ), belirtin *adı* bölümünün. Bölüm adı değiştirmek için izleyin *adı* eşittir işareti (=) ve bir *newname* bölümü için.  
  
 Ayarlamak veya bölümün değiştirmek için `attributes`, virgül belirtin (**,**) bir veya daha fazla öznitelikleri karakterle devam etmelidir. Bir öznitelik negate için kendi ünlem işareti (!) karakteriyle koyun. Şu karakterleri bellek öznitelikleri belirtin:  
  
|Öznitelik|Ayar|  
|---------------|-------------|  
|c|kod|  
|d|Discardable|  
|e|yürütülebilir dosya|  
|ı|başlatılmış veri|  
|K|önbelleğe alınan sanal bellek|  
|m|bağlantıyı Kaldır|  
|o|bağlantı bilgileri|  
|P|sanal disk belleği|  
|R|read|  
|s|shared|  
|u|Başlatılmamış verileri|  
|w|write|  
  
 Denetim için *hizalama*, karakteri belirtin **A** hizalama boyutunu bayt cinsinden şu şekilde ayarlamak için şu karakterlerden birini kullanarak ve ardından:  
  
|Karakter|Hizalama boyutunu bayt cinsinden|  
|---------------|-----------------------------|  
|1.|1.|  
|2|2|  
|4|4|  
|8|8|  
|P|16|  
|t|32|  
|s|64|  
|x|Hizalama yok|  
  
 Belirtin `attributes` ve *hizalama* karakter hiçbir boşluk içeren bir dize olarak. Karakterleri büyük küçük harfe duyarlı değildir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EDITBIN Seçenekleri](../../build/reference/editbin-options.md)