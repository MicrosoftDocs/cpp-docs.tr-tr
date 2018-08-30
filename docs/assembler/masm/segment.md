---
title: SEGMENT | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: f5defce11b611f23b67e5e44ac1b9d406f73c0ae
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210425"
---
# <a name="segment"></a>SEGMENT
Bir program segmenti tanımlayan *adı* segment özniteliklere sahip  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
   name SEGMENT [[READONLY]] [[align]] [[combine]] [[use]] [[characteristics]] ALIAS(string) [['class']]  
statements  
name ENDS  
```  
  
#### <a name="parameters"></a>Parametreler  
 *align*  
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
  
 *Birleştirme*  
 **Genel**, **yığın**, **ortak**, **bellek**, **ADRESİNDEKİ**<em>adresi</em>, **Özel**  
  
 *Kullanın*  
 **USE16**, **USE32**, **DÜZ**  
  
 `characteristics`  
 **BİLGİ**, **okuma**, **yazma**, **yürütme**, **paylaşılan**, **NOPAGE**, **NOCACHE**, ve **AT**  
  
 Bunlar için COFF yalnızca desteklenir ve benzer adı COFF bölümü özelliklerini karşılık gelir (örneğin, **paylaşılan** için IMAGE_SCN_MEM_SHARED karşılık gelir). Okuma IMAGE_SCN_MEM_READ bayrağını ayarlar. Eski salt okunur bayrağı IMG_SCN_MEM_WRITE bayrağını temizleme bölümüne neden oldu. Varsa `characteristics` , varsayılan özelliklerini kullanılmaz ve Programcı belirtilen bayraklar yalnızca yürürlükte olan ayarlanmıştır.  
  
 `ALIAS(` `string` `)`  
 Bu dize, yayılan COFF nesne içinde bölüm adı olarak kullanılır.  Aynı dış ada farklı MASM segmentli ada sahip birden çok bölümü oluşturur.  
  
 İle desteklenmez **/OMF**.  
  
 `class`  
 Segment birleştirilmiş ve bunları nasıl birleştirilmiş dosyasında sıralı belirler. Normal değerler, `'DATA'`, `'CODE'`, `'CONST'` ve `'STACK'`  
  
## <a name="remarks"></a>Açıklamalar  
 İçin `ALIGN(n)`, `n` 8192 1'den 2'in herhangi bir güç olabilir; ile desteklenmeyen **/OMF**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)