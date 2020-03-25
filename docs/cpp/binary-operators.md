---
title: İkili İşleçler
ms.date: 06/14/2018
helpviewer_keywords:
- member-selection operators [C++]
- operators [C++], binary
- binary operators [C++]
ms.assetid: c0e7fbff-bc87-4708-8333-504ac09ee83e
ms.openlocfilehash: 030ae71fec7a0d1572804f30d09f6f9b2749e436
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181310"
---
# <a name="binary-operators"></a>İkili İşleçler

Aşağıdaki tablo, aşırı yüklenebilir işleçler listesini gösterir.

## <a name="redefinable-binary-operators"></a>Yeniden Tanımlanabilir İkili İşleçler

|İşleç|Ad|
|--------------|----------|
|**,**|Virgül|
|**!=**|Eşitsizlik|
|**%**|Modulus|
|**%=**|Mod/atama|
|**&**|Bit düzeyinde AND|
|**&&**|Mantıksal VE|
|**&=**|Bit düzeyinde VE/atama|
|**&#42;**|Çarpma|
|**&#42;=**|Çarpma/atama|
|**+**|Toplama|
|**+=**|Toplama/atama|
|**-**|Çıkarma|
|**-=**|Çıkarma/atama|
|**->**|Üye seçimi|
|**->&#42;**|Üye işaretçisi seçimi|
|**/**|Bölme|
|**/=**|Bölme/atama|
|**<**|Küçüktür|
|**<<**|Sola kaydırma|
|**<<=**|Sola kaydırma/atama|
|**<=**|Küçüktür veya eşittir|
|**=**|Atama|
|**==**|Eşitlik|
|**>**|Büyüktür|
|**>=**|Büyüktür veya eşittir|
|**>>**|Sağa kaydırma|
|**>>=**|Sağa kaydırma/atama|
|**^**|Dışlamalı veya|
|**^=**|Özel VEYA/atama|
|**&#124;**|Bit düzeyinde kapsamalı OR|
|**&#124;=**|Bit düzeyinde kapsamlı VEYA/atama|
|**&#124;&#124;**|Mantıksal VEYA|

İkili işleç işlevini statik olmayan bir üye olarak bildirmek için şu biçimde bildirmeniz gerekir:

> *ret türü* **işleç işleci** *op* **(** *arg* **)**

Burada *ret-Type* dönüş türü, *op* , yukarıdaki tabloda listelenen işleçlerden *biridir ve bağımsız değişken herhangi* bir türde bağımsız değişkendir.

İkili bir işleç işlevini genel bir işlev olarak bildirmek için şu biçimde bildirmeniz gerekir:

> *ret türü* **işleç işleci** *op* **(** _arg1_ **,** _arg2_ **)**

Burada *ret-Type* ve *op* , Üye operatörü işlevleri ve *arg1* ve *arg2* bağımsız değişkenleri için açıklanmıştır. Bağımsız değişkenlerden en az biri sınıf türünde olmalıdır.

> [!NOTE]
> İkili işleçlerin dönüş türlerinde herhangi bir sınırlama yoktur; ancak, kullanıcı tanımlı ikili işleçlerin çoğu bir sınıf türü veya sınıf türü başvurusu döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)
