---
title: İkili işleçler | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2018
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
ms.openlocfilehash: 6c5ad5997657ce9f8a61383a2cd7e685f0a28751
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036559"
---
# <a name="binary-operators"></a>İkili İşleçler

Aşağıdaki tablo, aşırı yüklenebilir işleçler listesini gösterir.

## <a name="redefinable-binary-operators"></a>Yeniden Tanımlanabilir İkili İşleçler

|İşleç|Ad|
|--------------|----------|
|**,**|Virgül|
|**\!=**|Eşitsizlik|
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
|**->&#42;**|İşaretçi-üye seçimi|
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
|**^**|Dışlamalı OR|
|**^=**|Özel VEYA/atama|
|**&#124;**|Bit düzeyinde kapsamalı OR|
|**&#124;=**|Bit düzeyinde kapsamlı VEYA/atama|
|**&#124;&#124;**|Mantıksal VEYA|

İkili işleç işlevini statik olmayan bir üye olarak bildirmek için şu biçimde bildirmeniz gerekir:

> *ret-type* **işleci** *op* **(** *arg* **)**

Burada *ret-type* dönüş türü *op* yukarıdaki tabloda listelenen işleçlerden biridir ve *arg* herhangi bir türde bir bağımsız değişken.

İkili bir işleç işlevini genel bir işlev olarak bildirmek için şu biçimde bildirmeniz gerekir:

> *ret-type* **işleci** *op* **(** _arg1_**,** _arg2_ **)**

Burada *ret-type* ve *op* üye işleci işlevleri için tanımlanmıştır ve *arg1* ve *arg2* bağımsız değişkenler. Bağımsız değişkenlerden en az biri sınıf türünde olmalıdır.

> [!NOTE]
> İkili işleçlerin dönüş türlerinde herhangi bir sınırlama yoktur; ancak, kullanıcı tanımlı ikili işleçlerin çoğu bir sınıf türü veya sınıf türü başvurusu döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)