---
title: İkili işleçler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- member-selection operators [C++]
- operators [C++], binary
- binary operators [C++]
ms.assetid: c0e7fbff-bc87-4708-8333-504ac09ee83e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b930c548ea411beb03255d694f2423903053288
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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