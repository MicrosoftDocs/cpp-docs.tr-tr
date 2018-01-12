---
title: setlocale | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- setlocale_CPP
- vc-pragma.setlocale
dev_langs: C++
helpviewer_keywords:
- pragmas, setlocale
- setlocale pragma
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cf0cd4d6d77f4479d5a1cfd56f74f83c3980f38f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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