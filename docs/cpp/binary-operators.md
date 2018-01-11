---
title: "İkili işleçler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- member-selection operators [C++]
- operators [C++], binary
- binary operators [C++]
ms.assetid: c0e7fbff-bc87-4708-8333-504ac09ee83e
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 15c52d48359210a21b23caa72afee7e2a3bcd8cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="binary-operators"></a>İkili İşleçler
Aşağıdaki tablo, aşırı yüklenebilir işleçler listesini gösterir.  
  
### <a name="redefinable-binary-operators"></a>Yeniden Tanımlanabilir İkili İşleçler  
  
|İşleç|Ad|  
|--------------|----------|  
|**,**|Virgül|  
|`!=`|Eşitsizlik|  
|`%`|Mod|  
|`%=`|Mod/atama|  
|**&**|Bit düzeyinde AND|  
|**&&**|Mantıksal VE|  
|**&=**|Bit düzeyinde VE/atama|  
|**\***|Çarpma|  
|**\*=**|Çarpma/atama|  
|**+**|Toplama|  
|`+=`|Toplama/atama|  
|**-**|Çıkarma|  
|**-=**|Çıkarma/atama|  
|**->**|Üye seçimi|  
|**->\***|İşaretçi-üye seçimi|  
|**/**|Bölme|  
|`/=`|Bölme/atama|  
|**<**|Küçüktür|  
|**<<**|Sola kaydırma|  
|**<<=**|Sola kaydırma/atama|  
|**<=**|Küçüktür veya eşittir|  
|**=**|Atama|  
|`==`|Eşitlik|  
|**>**|Büyüktür|  
|**>=**|Büyüktür veya eşittir|  
|**>>**|Sağa kaydırma|  
|**>>=**|Sağa kaydırma/atama|  
|**^**|Dışlayan OR|  
|`^=`|Özel VEYA/atama|  
|**&#124;**|Bit düzeyinde kapsamalı OR|  
|`&#124;=`|Bit düzeyinde kapsamlı VEYA/atama|  
|`&#124;&#124;`|Mantıksal VEYA|  
  
 İkili işleç işlevini statik olmayan bir üye olarak bildirmek için şu biçimde bildirmeniz gerekir:  
  
 *ret türü* **işleci**`op`**(** `arg` **)**  
  
 Burada *ret türü* dönüş türü `op` yukarıdaki tabloda listelenen işleçleri biridir ve `arg` herhangi bir türde bir bağımsız değişken.  
  
 İkili bir işleç işlevini genel bir işlev olarak bildirmek için şu biçimde bildirmeniz gerekir:  
  
 *ret türü* **işleci**`op`**(** `arg1` **,** `arg2` **)**  
  
 Burada *ret türü* ve `op` üye işleci işlevleri için açıklanan ve `arg1` ve `arg2` bağımsız değişkenler. Bağımsız değişkenlerden en az biri sınıf türünde olmalıdır.  
  
> [!NOTE]
>  İkili işleçlerin dönüş türlerinde herhangi bir sınırlama yoktur; ancak, kullanıcı tanımlı ikili işleçlerin çoğu bir sınıf türü veya sınıf türü başvurusu döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)