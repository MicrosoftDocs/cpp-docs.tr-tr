---
title: 'Bellek Yönetimi: Örnekler | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 46e41ffab3f3f22bca1a9a721b4f2cdb03129d03
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391702"
---
# <a name="memory-management-examples"></a>Bellek Yönetimi: Örnekler

Bu makalede nasıl MFC çerçevesi ayırmaları ve yığın ayırmaları her üç tipik türleri bellek ayırmaları için gerçekleştirdiğini açıklar:

- [Bir bayt dizisi](#_core_allocation_of_an_array_of_bytes)

- [Bir veri yapısı](#_core_allocation_of_a_data_structure)

- [Bir nesne](#_core_allocation_of_an_object)

##  <a name="_core_allocation_of_an_array_of_bytes"></a> Bir bayt dizisi ayrılması

#### <a name="to-allocate-an-array-of-bytes-on-the-frame"></a>Çerçevesinde bir bayt dizisi için ayrılacak

1. Dizi, aşağıdaki kodda gösterildiği gibi tanımlayın. Dizi otomatik olarak silinir ve dizi değişkeni kapsamı çıktığında kendi bellek iadesi.

     [!code-cpp[NVC_MFC_Utilities#1](../mfc/codesnippet/cpp/memory-management-examples_1.cpp)]

#### <a name="to-allocate-an-array-of-bytes-or-any-primitive-data-type-on-the-heap"></a>Bayt dizisi (veya herhangi bir basit veri türü) yığında ayırmak için

1. Kullanım **yeni** işleci Bu örnekte gösterilen dizi söz dizimi ile:

     [!code-cpp[NVC_MFC_Utilities#2](../mfc/codesnippet/cpp/memory-management-examples_2.cpp)]

#### <a name="to-deallocate-the-arrays-from-the-heap"></a>Yığın dizilerden ayırması

1. Kullanım **Sil** işleci aşağıdaki gibi:

     [!code-cpp[NVC_MFC_Utilities#3](../mfc/codesnippet/cpp/memory-management-examples_3.cpp)]

##  <a name="_core_allocation_of_a_data_structure"></a> Ayırma, bir veri yapısı

#### <a name="to-allocate-a-data-structure-on-the-frame"></a>Çerçevenin bir veri yapısına ayırmak için

1. Yapı değişkeni aşağıdaki gibi tanımlayın:

     [!code-cpp[NVC_MFC_Utilities#4](../mfc/codesnippet/cpp/memory-management-examples_4.cpp)]

     Kapsamı çıktığında yapısı tarafından kapladığı belleği geri kazanılır.

#### <a name="to-allocate-data-structures-on-the-heap"></a>Veri yapıları yığında ayırmak için

1. Kullanım **yeni** yığında veri yapılarını ayrılacak ve **Sil** bunları, aşağıdaki örneklerde gösterildiği gibi serbest bırakmak:

     [!code-cpp[NVC_MFC_Utilities#5](../mfc/codesnippet/cpp/memory-management-examples_5.cpp)]

##  <a name="_core_allocation_of_an_object"></a> Bir nesnenin ayırma

#### <a name="to-allocate-an-object-on-the-frame"></a>Bir nesne çerçeve şirket ayrılamadı

1. Nesneyi şu şekilde bildirmek:

     [!code-cpp[NVC_MFC_Utilities#6](../mfc/codesnippet/cpp/memory-management-examples_6.cpp)]

     Nesnenin kapsamı çıktığında nesnenin yok Edicisi otomatik olarak çağrılır.

#### <a name="to-allocate-an-object-on-the-heap"></a>Yığındaki bir nesne ayrılamadı

1. Kullanım **yeni** yığını üzerindeki nesneler tahsis etmek için nesneye bir işaretçi döndürür, işleci. Kullanım **Sil** silmeyi işleci.

     Aşağıdaki yığın ve çerçeve örnekleri `CPerson` Oluşturucusu hiçbir bağımsız değişken alır.

     [!code-cpp[NVC_MFC_Utilities#7](../mfc/codesnippet/cpp/memory-management-examples_7.cpp)]

     Varsa bağımsız değişkeni için `CPerson` Oluşturucusu olan bir işaretçi **char**, çerçeve ayırma için deyim:

     [!code-cpp[NVC_MFC_Utilities#8](../mfc/codesnippet/cpp/memory-management-examples_8.cpp)]

     Yığın ayırma deyimidir:

     [!code-cpp[NVC_MFC_Utilities#9](../mfc/codesnippet/cpp/memory-management-examples_9.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Bellek Yönetimi: Öbek Ayırma](../mfc/memory-management-heap-allocation.md)

