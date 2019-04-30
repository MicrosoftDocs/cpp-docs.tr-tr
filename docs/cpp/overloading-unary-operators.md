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
ms.openlocfilehash: 802380bad59534e8402020142e394b3948032476
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62377237"
---
# <a name="overloading-unary-operators"></a>Aşırı Yükleme Birli İşleçleri

Aşırı yüklenebilen birli işleçler şunlardır:

1. `!` ([mantıksal değil](../cpp/logical-negation-operator-exclpt.md))

1. `&` ([adres](../cpp/address-of-operator-amp.md))

1. `~` ([birinin tamamlayıcısı](../cpp/one-s-complement-operator-tilde.md))

1. `*` ([işaretçiye](../cpp/indirection-operator-star.md))

1. `+` ([birli artı](../cpp/additive-operators-plus-and.md))

1. `-` ([tekli olumsuzlama](../cpp/additive-operators-plus-and.md))

1. `++` ([artışı](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))

1. `--` ([azaltma](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))

9. dönüştürme işleçleri

Sonek artırma ve azaltma işleçleri (`++` ve `--`) içinde ayrı ayrı değerlendirilir [artırmak ve azaltma](../cpp/increment-and-decrement-operator-overloading-cpp.md).

Dönüştürme işleçleri de ayrı bir konuda ele alınmıştır; bkz: [kullanıcı tanımlı tür dönüşümleri](../cpp/user-defined-type-conversions-cpp.md).

Aşağıdaki kurallar diğer tüm birli işleçler için doğrudur. Birli işleç işlevini statik olmayan bir üye olarak bildirmek için şu biçimde bildirmeniz gerekir:

> *ret-type* **işleci** *op* **)**

Burada *ret-type* dönüş türü ve *op* yukarıdaki tabloda listelenen işleçlerden.

Birli işleç işlevini genel bir işlev olarak bildirmek için şu biçimde bildirmeniz gerekir:

> *ret-type* **işleci** *op* **(** *arg* **)**

Burada *ret-type* ve *op* üye işleci işlevleri için tanımlanmıştır ve *arg* üzerinde çalışacağı sınıf türünün bir bağımsız değişken.

> [!NOTE]
>  Birli operatörlerin dönüş türleriyle ilgili bir kısıtlama yoktur. Örneğin, mantıksal değil için mantıklıdır (`!`) bir tamsayı değeri, ancak bu döndürülecek zorlanmaz.

## <a name="see-also"></a>Ayrıca bkz.

[İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)