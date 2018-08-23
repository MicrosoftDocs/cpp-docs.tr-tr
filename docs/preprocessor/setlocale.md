---
title: setlocale | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- setlocale_CPP
- vc-pragma.setlocale
dev_langs:
- C++
helpviewer_keywords:
- pragmas, setlocale
- setlocale pragma
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa6ba2bec5c862bb336d4b9bea0f47aad91fe0c1
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42464544"
---
# <a name="setlocale"></a>setlocale
Yerel (ülke/bölge ve dil) geniş karakter sabitleri ve dize değişmez değerleri çevirirken kullanılacak tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma setlocale( "[locale-string]" )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 
Geniş karakterler için çok baytlı karakterleri dönüştürme algoritması bölgeye göre değişiklik gösterebilir veya derleme yürütülebilir bir dosya çalıştıracağınız öğesinden farklı bir yerel ayar yer alabilir içerdiğinden, bu pragmayı derleme zamanında hedef yerel ayar belirtmek için bir yol sağlar. Başka bir garanti, geniş karakterli dizeler doğru biçimde depolanır.  
  
Varsayılan *yerel ayar dizesine* olan "".  
  
Değer olarak "C" yerel dizesindeki her karakterle eşleyen bir **wchar_t** (işaretsiz). İçin geçerli olan diğer değerleri `setlocale` bulunan bu girişler [dil dizeleri](../c-runtime-library/language-strings.md) listesi. Örneğin, size verebilir:  
  
```  
#pragma setlocale("dutch")  
```  
  
Bir dil dizesi oluşturabilme olanağı, kod sayfası ve dil kimliği desteği bilgisayarınızda bağlıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)