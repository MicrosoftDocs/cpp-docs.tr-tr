---
title: İşaretçiler (C++)
ms.date: 11/19/2019
description: Microsoft C++'daki ham işaretçiler ve akıllı işaretçiler hakkında.
helpviewer_keywords:
- pointers (C++)
ms.assetid: 595387c5-8e58-4670-848f-344c7caf985e
ms.openlocfilehash: 485cee667fa288bff76fdeac7c9f229355c276d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371910"
---
# <a name="pointers-c"></a>İşaretçiler (C++)

İşaretçi, bir nesnenin bellek adresini depolayan bir değişkendir. İşaretçiler hem C hem de C++'da üç ana amaç için yaygın olarak kullanılır:

- yığınüzerinde yeni nesneler ayırmak için,
- işlevleri diğer işlevlere aktarmak için
- diziler veya diğer veri yapıları öğeleri üzerinde tekrarlayın.

C stili programlamada, *ham işaretçiler* tüm bu senaryolar için kullanılır. Ancak, ham işaretçiler birçok ciddi programlama hatalarının kaynağıdır. Bu nedenle, önemli bir performans avantajı sağladıkları ve nesnenin silinmekten sorumlu olan *işaretçisi* sahibi olduğu konusunda belirsizlik olmadığı durumlar dışında kullanımları şiddetle önerilmez. Modern C++, nesneleri ayırmak için *akıllı işaretçiler,* veri yapılarında geçiş için *yineleyiciler* ve geçen işlevler için *lambda ifadeleri* sağlar. Ham işaretçiler yerine bu dil ve kitaplık olanaklarını kullanarak, programınızı daha güvenli, hata ayıklama nın daha kolay ve anlaşılması ve bakımı daha kolay hale getirirsiniz. Daha fazla bilgi için [Akıllı işaretçiler,](smart-pointers-modern-cpp.md) [Yineleyiciler](../standard-library/iterators.md)ve [Lambda ifadelerine](lambda-expressions-in-cpp.md) bakın.

## <a name="in-this-section"></a>Bu bölümde

- [Ham işaretçiler](raw-pointers.md)
- [Const ve uçucu işaretçiler](const-and-volatile-pointers.md)
- [yeni ve silme işleçleri](new-and-delete-operators.md)
- [Akıllı işaretçiler](smart-pointers-modern-cpp.md)
- [Nasıl kullanılır: unique_ptr örnekleri oluşturma ve kullanma](how-to-create-and-use-unique-ptr-instances.md)
- [Nasıl kullanılır: shared_ptr örnekleri oluşturma ve kullanma](how-to-create-and-use-shared-ptr-instances.md)
- [Nasıl kullanılır: weak_ptr örnekleri oluşturma ve kullanma](how-to-create-and-use-weak-ptr-instances.md)
- [Nasıl kullanılır: CComPtr ve CComQIPtr örneklerini oluşturma ve kullanma](how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md)

## <a name="see-also"></a>Ayrıca bkz.

[Yineleyiciler](../standard-library/iterators.md)</br>
[Lambda ifadeleri](lambda-expressions-in-cpp.md)
