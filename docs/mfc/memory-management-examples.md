---
title: 'Bellek Yönetimi: Örnekler'
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], memory allocation
- data structures [MFC]
- arrays [MFC], allocating resources
- objects [MFC], allocating memory
- data structures [MFC], allocating memory
- examples [MFC], memory allocation
- heap allocation [MFC], examples
- memory allocation [MFC], arrays
- MFC, memory management
- struct memory allocation [MFC]
- types [MFC], memory allocation
- memory allocation [MFC], objects
- memory allocation [MFC], examples
- arrays [MFC], memory management
- frame allocation [MFC]
- memory allocation [MFC], data structures
ms.assetid: f10240f8-b698-4c83-9288-97a54318930b
ms.openlocfilehash: 3a1e647175b7b5294e672efbf234e3ae2853e411
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367845"
---
# <a name="memory-management-examples"></a>Bellek Yönetimi: Örnekler

Bu makalede, MFC'nin üç farklı bellek ayırma türünher biri için çerçeve ayırmaları ve yığın ayırmaları nasıl gerçekleştirdiği açıklanmaktadır:

- [Bir dizi bayt](#_core_allocation_of_an_array_of_bytes)

- [Bir veri yapısı](#_core_allocation_of_a_data_structure)

- [Bir nesne](#_core_allocation_of_an_object)

## <a name="allocation-of-an-array-of-bytes"></a><a name="_core_allocation_of_an_array_of_bytes"></a>Bir Bayt Dizisinin Tahsisi

#### <a name="to-allocate-an-array-of-bytes-on-the-frame"></a>Çerçeveye bir dizi bayt ayırmak için

1. Diziyi aşağıdaki kodla gösterildiği şekilde tanımlayın. Dizi otomatik olarak silinir ve dizi değişkeni kapsamından çıktığında belleği geri alınır.

   [!code-cpp[NVC_MFC_Utilities#1](../mfc/codesnippet/cpp/memory-management-examples_1.cpp)]

#### <a name="to-allocate-an-array-of-bytes-or-any-primitive-data-type-on-the-heap"></a>Yığına bir dizi bayt (veya herhangi bir ilkel veri türü) ayırmak için

1. Bu örnekte gösterilen dizi sözdizimi ile **yeni** işleci kullanın:

   [!code-cpp[NVC_MFC_Utilities#2](../mfc/codesnippet/cpp/memory-management-examples_2.cpp)]

#### <a name="to-deallocate-the-arrays-from-the-heap"></a>Yığından dizileri dağıtmak için

1. **Silme** işleciaşağıdaki gibi kullanın:

   [!code-cpp[NVC_MFC_Utilities#3](../mfc/codesnippet/cpp/memory-management-examples_3.cpp)]

## <a name="allocation-of-a-data-structure"></a><a name="_core_allocation_of_a_data_structure"></a>Veri Yapısının Tahsisi

#### <a name="to-allocate-a-data-structure-on-the-frame"></a>Çerçeveüzerinde bir veri yapısı ayırmak için

1. Yapı değişkenini aşağıdaki gibi tanımlayın:

   [!code-cpp[NVC_MFC_Utilities#4](../mfc/codesnippet/cpp/memory-management-examples_4.cpp)]

   Yapının işgal ettiği bellek, kapsamı çıkarıldığında geri alınır.

#### <a name="to-allocate-data-structures-on-the-heap"></a>Yığınüzerinde veri yapıları ayırmak için

1. Aşağıdaki **new** örneklerde gösterildiği gibi, yığın üzerinde veri yapıları ayırmak ve bunları dağıtmak için **silme** yeni kullanın:

   [!code-cpp[NVC_MFC_Utilities#5](../mfc/codesnippet/cpp/memory-management-examples_5.cpp)]

## <a name="allocation-of-an-object"></a><a name="_core_allocation_of_an_object"></a>Nesnenin Tahsisi

#### <a name="to-allocate-an-object-on-the-frame"></a>Çerçeveye bir nesne ayırmak için

1. Nesneyi aşağıdaki gibi bildirin:

   [!code-cpp[NVC_MFC_Utilities#6](../mfc/codesnippet/cpp/memory-management-examples_6.cpp)]

   Nesne nin imha edicisi, nesne kapsamından çıktığında otomatik olarak çağrılır.

#### <a name="to-allocate-an-object-on-the-heap"></a>Yığına bir nesne ayırmak için

1. Yığındaki nesneleri ayırmak için nesneye işaretçi döndüren **yeni** işleci kullanın. Bunları **silmek** için silme işlecini kullanın.

   Aşağıdaki yığın ve çerçeve örnekleri, `CPerson` oluşturucunun hiçbir bağımsız değişken kabul etmediğini varsayar.

   [!code-cpp[NVC_MFC_Utilities#7](../mfc/codesnippet/cpp/memory-management-examples_7.cpp)]

   Oluşturucu için bağımsız değişken char için bir işaretçi ise, çerçeve ayırma için deyim: **char** `CPerson`

   [!code-cpp[NVC_MFC_Utilities#8](../mfc/codesnippet/cpp/memory-management-examples_8.cpp)]

   Yığın ayırma için deyim:

   [!code-cpp[NVC_MFC_Utilities#9](../mfc/codesnippet/cpp/memory-management-examples_9.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Yönetimi: Öbek Ayırma](../mfc/memory-management-heap-allocation.md)
