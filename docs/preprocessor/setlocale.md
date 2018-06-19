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
ms.openlocfilehash: 0cfabfa3c83fe2ff90a6f7dbe07d5205f7a6f9a9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847422"
---
# <a name="setlocale"></a>setlocale
(Ülke/bölge ve dil) joker karakter sabitleri ve dize değişmez değerleri çevirirken kullanılacak yerel tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#pragma setlocale( "[locale-string]" )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Geniş karakterler birden çok baytlı karakterleri dönüştürme algoritma bölgeye göre farklılık gösterebilir veya derleme yürütülebilir bir dosyanın çalıştırılacağı öğesinden farklı bir yerel olarak yer alabilir olduğundan bu pragma hedef yerel derleme zamanında belirtmek için bir yol sağlar. Başka bir garanti joker karakter dizelerini doğru biçimde depolanır.  
  
 Varsayılan *yerel ayar-dize* olan "".  
  
 "C" yerel değer olarak dizedeki her karakter eşlendiği bir `wchar_t` (kısa imzalanmamış). İçin geçerli olan diğer değerleri `setlocale` bulunan bu girdiler [dil dizeleri](../c-runtime-library/language-strings.md) listesi. Örneğin, size verebilir:  
  
```  
#pragma setlocale("dutch")  
```  
  
 Bir dil dize verme özelliği kod sayfası ve dil kimliği ile ilgili destek bilgisayarınızda bağlıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)