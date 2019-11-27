---
title: İşaretçiler (C++)
ms.date: 11/19/2019
description: Microsoft C++'taki ham işaretçiler ve akıllı işaretçiler hakkında.
helpviewer_keywords:
- pointers (C++)
ms.assetid: 595387c5-8e58-4670-848f-344c7caf985e
ms.openlocfilehash: 21dcc55048e9e378f370f25254e1910b05e49d69
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246417"
---
# <a name="pointers-c"></a>İşaretçiler (C++)

İşaretçi, bir nesnenin bellek adresini depolayan bir değişkendir. İşaretçiler hem C hem de üç ana amaç C++ için kapsamlı olarak kullanılır:

- yığında yeni nesneler ayırmak için
- işlevleri diğer işlevlere geçirmek için
- diziler veya diğer veri yapılarında öğeleri yinelemek için.

C stili programlamada, *ham işaretçiler* tüm bu senaryolar için kullanılır. Ancak ham işaretçiler birçok ciddi programlama hatasının kaynağıdır. Bu nedenle, önemli bir performans avantajı sağladığı durumlar haricinde kullanımları kesinlikle önerilmez ve hangi işaretçinin nesneyi silmekten sorumlu olan *işaretçi* olduğu konusunda hiçbir belirsizlik yoktur. Modern C++ , nesneleri ayırmaya yönelik *akıllı işaretçiler* , veri yapılarına geçiş için *yineleyiciler* ve işlevleri geçirmek için *lambda ifadeleri* sağlar. Ham işaretçiler yerine bu dil ve kitaplık tesislerini kullanarak, programınızı daha güvenli hale getirir, hata ayıklama ve daha kolay anlaşılır ve bakım yapmanız gerekir. Daha fazla bilgi için bkz. [akıllı işaretçiler](smart-pointers-modern-cpp.md), [yineleyiciler](../standard-library/iterators.md)ve [lambda ifadeleri](lambda-expressions-in-cpp.md) .

## <a name="in-this-section"></a>Bu bölümde

- [Ham işaretçiler](raw-pointers.md)
- [Const ve volatile işaretçileri](const-and-volatile-pointers.md)
- [New ve delete işleçleri](new-and-delete-operators.md)
- [Akıllı işaretçiler](smart-pointers-modern-cpp.md)
- [Nasıl yapılır: unique_ptr örnekleri oluşturma ve kullanma](how-to-create-and-use-unique-ptr-instances.md)
- [Nasıl yapılır: shared_ptr örnekleri oluşturma ve kullanma](how-to-create-and-use-shared-ptr-instances.md)
- [Nasıl yapılır: weak_ptr örnekleri oluşturma ve kullanma](how-to-create-and-use-weak-ptr-instances.md)
- [Nasıl yapılır: CComPtr ve CComQIPtr örnekleri oluşturma ve kullanma](how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md)

## <a name="see-also"></a>Ayrıca bkz.

[Yineleyiciler](../standard-library/iterators.md)</br>
[Lambda ifadeleri](lambda-expressions-in-cpp.md)
