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
ms.openlocfilehash: 971ef08c5e79f851c502ea872c541517065797c5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372026"
---
# <a name="overloading-unary-operators"></a>Aşırı Yükleme Birli İşleçleri

Aşırı yüklenebilen birli işleçler şunlardır:

1. `!`([mantıksal Değİl](../cpp/logical-negation-operator-exclpt.md))

1. `&`([adresi-of](../cpp/address-of-operator-amp.md))

1. `~`([kişinin tamamlayıcısı](../cpp/one-s-complement-operator-tilde.md))

1. `*`([işaretçi dereference](../cpp/indirection-operator-star.md))

1. `+`([unary artı](../cpp/additive-operators-plus-and.md))

1. `-`([unary olumsuzlama](../cpp/additive-operators-plus-and.md))

1. `++`([artış](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))

1. `--`([kararname](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))

1. dönüştürme işleçleri

Postfix artış ve decrement işleçleri (`++` ve `--`) [artım ve decrement](../cpp/increment-and-decrement-operator-overloading-cpp.md)ayrı ayrı işlenir.

Dönüşüm işleçleri de ayrı bir konu üzerinde tartışılır; bkz. [Kullanıcı Tanımlı Tür Dönüşümleri.](../cpp/user-defined-type-conversions-cpp.md)

Aşağıdaki kurallar diğer tüm birli işleçler için doğrudur. Birli işleç işlevini statik olmayan bir üye olarak bildirmek için şu biçimde bildirmeniz gerekir:

> *ret tipi* **operatör** *op* **()**

*ret-type'ın* iade türü olduğu ve *op'un* önceki tabloda listelenen işleçlerden biri olduğu durumlarda.

Birli işleç işlevini genel bir işlev olarak bildirmek için şu biçimde bildirmeniz gerekir:

> *ret tipi* **operatör** *op* **(** *arg* **)**

*ret türü* ve *op* üye operatör işlevleri için açıklandığı ve *arg* hangi çalışması sınıf türü bir argüman dır.

> [!NOTE]
> Birli operatörlerin dönüş türleriyle ilgili bir kısıtlama yoktur. Örneğin, mantıksal NOT (`!`) integral değeri döndürmek için mantıklı, ancak bu zorlanmaz.

## <a name="see-also"></a>Ayrıca bkz.

[Operatör Aşırı Yükleme](../cpp/operator-overloading.md)
