---
description: 'Daha fazla bilgi edinin: bellek yönetimi: örnekler'
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
ms.openlocfilehash: dcd7ba9ce5fee0af932766494f0a7afd64684e77
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222300"
---
# <a name="memory-management-examples"></a>Bellek Yönetimi: Örnekler

Bu makalede, MFC 'nin üç tipik bellek ayırma türü için çerçeve ayırmaları ve yığın ayırmaları nasıl gerçekleştirdiği açıklanmaktadır:

- [Bayt dizisi](#_core_allocation_of_an_array_of_bytes)

- [Veri yapısı](#_core_allocation_of_a_data_structure)

- [Bir nesne](#_core_allocation_of_an_object)

## <a name="allocation-of-an-array-of-bytes"></a><a name="_core_allocation_of_an_array_of_bytes"></a> Bayt dizisinin ayrılması

#### <a name="to-allocate-an-array-of-bytes-on-the-frame"></a>Çerçevede bir bayt dizisi ayırmak için

1. Diziyi aşağıdaki kodla gösterildiği gibi tanımlayın. Dizi değişkeni kapsamından çıktığında dizi otomatik olarak silinir ve bellek geri kazanılır.

   [!code-cpp[NVC_MFC_Utilities#1](codesnippet/cpp/memory-management-examples_1.cpp)]

#### <a name="to-allocate-an-array-of-bytes-or-any-primitive-data-type-on-the-heap"></a>Yığında bir bayt dizisi (veya herhangi bir ilkel veri türü) ayırmak için

1. **`new`** Bu örnekte gösterilen dizi sözdizimi ile işlecini kullanın:

   [!code-cpp[NVC_MFC_Utilities#2](codesnippet/cpp/memory-management-examples_2.cpp)]

#### <a name="to-deallocate-the-arrays-from-the-heap"></a>Dizileri yığından serbest bırakmak için

1. **`delete`** İşlecini aşağıdaki gibi kullanın:

   [!code-cpp[NVC_MFC_Utilities#3](codesnippet/cpp/memory-management-examples_3.cpp)]

## <a name="allocation-of-a-data-structure"></a><a name="_core_allocation_of_a_data_structure"></a> Veri yapısını ayırma

#### <a name="to-allocate-a-data-structure-on-the-frame"></a>Çerçevede bir veri yapısı ayırmak için

1. Yapı değişkenini aşağıdaki gibi tanımlayın:

   [!code-cpp[NVC_MFC_Utilities#4](codesnippet/cpp/memory-management-examples_4.cpp)]

   Yapının kapladığı bellek, kapsamından çıktığında geri kazanılır.

#### <a name="to-allocate-data-structures-on-the-heap"></a>Yığın üzerinde veri yapıları ayırmak için

1. **`new`** **`delete`** Aşağıdaki örneklerde gösterildiği gibi, yığın üzerinde veri yapıları ayırmak ve onları serbest bırakmak için kullanın:

   [!code-cpp[NVC_MFC_Utilities#5](codesnippet/cpp/memory-management-examples_5.cpp)]

## <a name="allocation-of-an-object"></a><a name="_core_allocation_of_an_object"></a> Bir nesnenin ayrılması

#### <a name="to-allocate-an-object-on-the-frame"></a>Çerçevede bir nesne ayırmak için

1. Nesneyi aşağıdaki gibi bildirin:

   [!code-cpp[NVC_MFC_Utilities#6](codesnippet/cpp/memory-management-examples_6.cpp)]

   Nesne kapsamından çıktığında nesnenin yıkıcısı otomatik olarak çağrılır.

#### <a name="to-allocate-an-object-on-the-heap"></a>Yığın üzerinde bir nesne ayırmak için

1. **`new`** Yığın üzerinde nesneleri ayırmak için nesnesine bir işaretçi döndüren işlecini kullanın. İşleci kullanarak **`delete`** bunları silin.

   Aşağıdaki yığın ve çerçeve örnekleri, `CPerson` oluşturucunun bağımsız değişken aldığını varsayar.

   [!code-cpp[NVC_MFC_Utilities#7](codesnippet/cpp/memory-management-examples_7.cpp)]

   Oluşturucunun bağımsız değişkeni `CPerson` öğesine işaretçisiyse **`char`** , çerçeve ayırma için olan ifade şu şekilde olur:

   [!code-cpp[NVC_MFC_Utilities#8](codesnippet/cpp/memory-management-examples_8.cpp)]

   Yığın ayırma için olan ifade:

   [!code-cpp[NVC_MFC_Utilities#9](codesnippet/cpp/memory-management-examples_9.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Bellek yönetimi: yığın ayırma](memory-management-heap-allocation.md)
