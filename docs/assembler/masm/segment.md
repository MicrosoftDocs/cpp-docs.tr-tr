---
title: SEGMENT | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- SEGMENT
dev_langs:
- C++
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 87c5f37d24ce8f8ae34bbc403fcf39515cd6cba2
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43686446"
---
# <a name="segment"></a>SEGMENT

Bir program segmenti tanımlayan *adı* segment özniteliklere sahip

## <a name="syntax"></a>Sözdizimi

> *adı* SEGMENT [[salt okunur]] [[*hizalama*]] [[*birleştirmek*]] [[*kullanın*]] [[*özellikleri*]] diğer adı (*dize*) [['*sınıfı*']]<br/>
> *Deyimleri*<br/>
> *adı* sona ERER

#### <a name="parameters"></a>Parametreler

*align*<br/>
Kesimin başlangıç adresi seçilebilir bellek adresleri aralığı. Hizalama türü aşağıdakilerden herhangi biri olabilir:

|Hizalama türü|Başlangıç adresi|
|----------------|----------------------|
|**BAYT**|Sonraki kullanılabilir bayt adresi.|
|**WORD**|Sonraki kullanılabilir word adresi (sözcük başına 2 bayt).|
|**DWORD**|Sonraki kullanılabilir çift sözcük adresi (çift sözcük başına 4 bayt).|
|**PARA**|Sonraki kullanılabilir paragraf adresi (paragraf başına 16 bayt).|
|**PAGE**|Sonraki kullanılabilir sayfa (sayfa başına 256 bayt) adresi.|
|**Hizalama**(*n*)|Sonraki kullanılabilir *n*th bayt adresi. Daha fazla bilgi için Açıklamalar bölümüne bakın.|

Bu parametre belirtilmezse, **PARA** varsayılan olarak kullanılır.

*Birleştirme*<br/>
**Genel**, **yığın**, **ortak**, **bellek**, **ADRESİNDEKİ**<em>adresi</em>, **Özel**

*Kullanın*<br/>
**USE16**, **USE32**, **DÜZ**

*Özellikleri*<br/>
**BİLGİ**, **okuma**, **yazma**, **yürütme**, **paylaşılan**, **NOPAGE**, **NOCACHE**, ve **AT**

Bunlar için COFF yalnızca desteklenir ve benzer adı COFF bölümü özelliklerini karşılık gelir (örneğin, **paylaşılan** için IMAGE_SCN_MEM_SHARED karşılık gelir). Okuma IMAGE_SCN_MEM_READ bayrağını ayarlar. Eski salt okunur bayrağı IMG_SCN_MEM_WRITE bayrağını temizleme bölümüne neden oldu. Varsa *özellikleri* , varsayılan özelliklerini kullanılmaz ve Programcı belirtilen bayraklar yalnızca yürürlükte olan ayarlanmıştır.

`ALIAS(` *dize* `)`<br/>
Bu dize, yayılan COFF nesne içinde bölüm adı olarak kullanılır.  Aynı dış ada farklı MASM segmentli ada sahip birden çok bölümü oluşturur.

İle desteklenmez **/OMF**.

*class*<br/>
Segment birleştirilmiş ve bunları nasıl birleştirilmiş dosyasında sıralı belirler. Normal değerler, `'DATA'`, `'CODE'`, `'CONST'` ve `'STACK'`

## <a name="remarks"></a>Açıklamalar

İçin `ALIGN(n)`, *n* 8192 1'den 2'in herhangi bir güç olabilir; ile desteklenmeyen **/OMF**.

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>