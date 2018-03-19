---
title: SEGMENT | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- SEGMENT
dev_langs:
- C++
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 253c3b389bd0411e6b5096e914b6a844c8f40805
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2018
---
# <a name="segment"></a>SEGMENT
Adlı bir programı segmenti tanımlar *adı* segment özniteliklere sahip  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
   name SEGMENT [[READONLY]] [[align]] [[combine]] [[use]] [[characteristics]] ALIAS(string) [['class']]  
statements  
name ENDS  
```  
  
#### <a name="parameters"></a>Parametreler  
 *align*  
 Başlangıç adresi segmenti için seçilebilir bellek adresi aralığı. Hizalama türü aşağıdakilerden herhangi biri olabilir:  
  
|Türü hizalayın|Başlangıç adresi|  
|----------------|----------------------|  
|**BAYT**|Sonraki kullanılabilir bayt adresi.|  
|**WORD**|Sonraki kullanılabilir word adresi (word başına 2 bayt).|  
|**DWORD**|Sonraki kullanılabilir çift word adresi (çift sözcük başına 4 bayt).|  
|**PARA**|Sonraki kullanılabilir paragraf adresi (paragraf başına 16 bayt).|  
|**PAGE**|Sonraki kullanılabilir sayfa adresi (sayfa başına 256 bayt).|  
|**ALIGN**(*n*)|Sonraki kullanılabilir *n*th bayt adresi. Daha fazla bilgi için Açıklamalar bölümüne bakın.|  
  
 Bu parametre belirtilmezse, **PARA** varsayılan olarak kullanılır.  
  
 *combine*  
 **Ortak**, **yığın**, **ortak**, **bellek**, **ADRESİNDEKİ***adresi*, **özel**  
  
 *Kullanın*  
 **USE16**, **USE32**, **DÜZ**  
  
 `characteristics`  
 **BİLGİ**, **okuma**, **yazma**, **yürütme**, **paylaşılan**, **NOPAGE**, **NOCACHE**, ve **AT**  
  
 Bunlar için COFF yalnızca desteklenir ve benzer adı COFF bölüm özelliklerini karşılık (örneğin, **paylaşılan** için IMAGE_SCN_MEM_SHARED karşılık gelir). Okuma IMAGE_SCN_MEM_READ bayrağını ayarlar. Artık kullanılmayan salt okunur bayrağı IMG_SCN_MEM_WRITE bayrağını temizleme bölümüne neden oldu. Varsa `characteristics` , varsayılan özelliklerini kullanılmaz ve yalnızca Programcı tanımlı bayrak yürürlükte, ayarlanmıştır.  
  
 `ALIAS(` `string` `)`  
 Bu dize verilmiş COFF nesnesindeki bölüm adı olarak kullanılır.  Ayrı MASM segment adlarıyla aynı dış ada sahip birden çok bölüm oluşturur.  
  
 İle desteklenmez **/OMF**.  
  
 `class`  
 Nasıl kesimleri birleştirilmiş ve gerekir birleştirilmiş dosyasında sıralı belirler. Tipik değerlerdir, `'DATA'`, `'CODE'`, `'CONST'` ve `'STACK'`  
  
## <a name="remarks"></a>Açıklamalar  
 İçin `ALIGN(n)`, `n` 8192 1'den 2'in herhangi bir güç olabilir; desteklenmiyor **/OMF**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)