---
title: Aşırı Yükleme Birli İşleçleri
ms.date: 11/04/2016
helpviewer_keywords:
- unary operators [C++], plus
- increment operators [C++], overloaded
- unary operators [C++], minus
- operators [C++], unary
- redefinable unary operators [C++]
- unary operators [C++]
- pointer dereference operator overloading
- plus operator
ms.assetid: 7683ef08-42a4-4283-928f-d3dd4f3ab4c0
ms.openlocfilehash: a21c62549f02dddda951c79a06617671ccfe2526
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227224"
---
# <a name="overloading-unary-operators"></a>Aşırı Yükleme Birli İşleçleri

Aşırı yüklenebilen birli işleçler şunlardır:

1. `!`([MANTıKSAL değil](../cpp/logical-negation-operator-exclpt.md))

1. `&`([Adres-of](../cpp/address-of-operator-amp.md))

1. `~`([bir tane tamamlama](../cpp/one-s-complement-operator-tilde.md))

1. `*`([işaretçi başvurusu](../cpp/indirection-operator-star.md))

1. `+`([birli Plus](../cpp/additive-operators-plus-and.md))

1. `-`([birli olumsuzlama](../cpp/additive-operators-plus-and.md))

1. `++`([artış](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))

1. `--`([azaltma](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))

1. dönüştürme işleçleri

Sonek artırma ve azaltma işleçleri ( `++` ve `--` ), [artış ve azaltma ile](../cpp/increment-and-decrement-operator-overloading-cpp.md)ayrı olarak değerlendirilir.

Dönüştürme işleçleri de ayrı bir konuda ele alınmıştır; bkz. [Kullanıcı tanımlı tür dönüştürmeleri](../cpp/user-defined-type-conversions-cpp.md).

Aşağıdaki kurallar diğer tüm birli işleçler için doğrudur. Birli işleç işlevini statik olmayan bir üye olarak bildirmek için şu biçimde bildirmeniz gerekir:

> *ret türü* **`operator`** *op* **()**

Burada *ret-Type* dönüş türüdür ve *op* , yukarıdaki tabloda listelenen işleçlerden biridir.

Birli işleç işlevini genel bir işlev olarak bildirmek için şu biçimde bildirmeniz gerekir:

> *ret türü* **`operator`** *op* **(** *arg* **)**

Burada *ret-Type* ve *op* , Üye operatörü işlevleri için açıklanmış ve *arg* , üzerinde çalışacağı sınıf türünün bir bağımsız değişkenidir.

> [!NOTE]
> Birli operatörlerin dönüş türleriyle ilgili bir kısıtlama yoktur. Örneğin, mantıksal NOT ( `!` ) için bir tamsayı değeri döndürmesi mantıklı, ancak bu zorunlu değildir.

## <a name="see-also"></a>Ayrıca bkz.

[İşleç aşırı yüklemesi](../cpp/operator-overloading.md)
