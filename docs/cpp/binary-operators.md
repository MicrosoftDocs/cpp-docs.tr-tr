---
description: 'Daha fazla bilgi edinin: Ikili Işleçler'
title: İkili İşleçler
ms.date: 06/14/2018
helpviewer_keywords:
- member-selection operators [C++]
- operators [C++], binary
- binary operators [C++]
ms.assetid: c0e7fbff-bc87-4708-8333-504ac09ee83e
ms.openlocfilehash: cfb897a3df7cdb3d76f7af82f694e1cf09284cc7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229606"
---
# <a name="binary-operators"></a>İkili İşleçler

Aşağıdaki tablo, aşırı yüklenebilir işleçler listesini gösterir.

## <a name="redefinable-binary-operators"></a>Yeniden Tanımlanabilir İkili İşleçler

|Operatör|Ad|
|--------------|----------|
|**,**|Virgül|
|**!=**|Eşitsizlik|
|**%**|Mod|
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
|**/**|Bölüm|
|**/=**|Bölme/atama|
|**<**|Küçüktür|
|**<<**|Sola kaydırma|
|**<<=**|Sola kaydırma/atama|
|**<=**|Küçük veya eşittir|
|**=**|Atama|
|**==**|Eşitlik|
|**>**|Büyüktür|
|**>=**|Büyük veya eşittir|
|**>>**|Sağa kaydırma|
|**>>=**|Sağa kaydırma/atama|
|**^**|Dışlamalı veya|
|**^=**|Özel VEYA/atama|
|**&#124;**|Bit düzeyinde kapsamalı OR|
|**&#124;=**|Bit düzeyinde kapsamlı VEYA/atama|
|**&#124;&#124;**|Mantıksal EĞER|

İkili işleç işlevini statik olmayan bir üye olarak bildirmek için şu biçimde bildirmeniz gerekir:

> *ret türü* **`operator`** *op* **(** *arg* **)**

Burada *ret-Type* dönüş türü, *op* , yukarıdaki tabloda listelenen işleçlerden *biridir ve bağımsız değişken herhangi* bir türde bağımsız değişkendir.

İkili bir işleç işlevini genel bir işlev olarak bildirmek için şu biçimde bildirmeniz gerekir:

> *ret türü* **`operator`** *op* **(** _arg1_**,** _arg2_ **)**

Burada *ret-Type* ve *op* , Üye operatörü işlevleri ve *arg1* ve *arg2* bağımsız değişkenleri için açıklanmıştır. Bağımsız değişkenlerden en az biri sınıf türünde olmalıdır.

> [!NOTE]
> İkili işleçlerin dönüş türlerinde herhangi bir sınırlama yoktur; ancak, kullanıcı tanımlı ikili işleçlerin çoğu bir sınıf türü veya sınıf türü başvurusu döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[İşleç aşırı yüklemesi](../cpp/operator-overloading.md)
