---
title: "Bellek Yönetimi: Örnekler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bc937e64a09ecedb127524de384d48860da5764f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="memory-management-examples"></a>Bellek Yönetimi: Örnekler
Bu makalede nasıl MFC çerçeve ayırma ve yığın ayırmaları her bellek ayırmaları tipik üç tür için gerçekleştirdiği açıklanmıştır:  
  
-   [Bir bayt dizisi](#_core_allocation_of_an_array_of_bytes)  
  
-   [Bir veri yapısı](#_core_allocation_of_a_data_structure)  
  
-   [Bir nesne](#_core_allocation_of_an_object)  
  
##  <a name="_core_allocation_of_an_array_of_bytes"></a>Bir bayt dizisi ayırma  
  
#### <a name="to-allocate-an-array-of-bytes-on-the-frame"></a>Çerçevede bir bayt dizisi ayırmak için  
  
1.  Dizi aşağıdaki kodda gösterildiği gibi tanımlayın. Dizi otomatik olarak silinir ve dizi değişkeni kapsamı çıktığında kendi bellek iadesi.  
  
     [!code-cpp[NVC_MFC_Utilities#1](../mfc/codesnippet/cpp/memory-management-examples_1.cpp)]  
  
#### <a name="to-allocate-an-array-of-bytes-or-any-primitive-data-type-on-the-heap"></a>Öbek üzerinde (veya herhangi bir temel veri türü) bayt dizisi ayırmak için  
  
1.  Kullanım **yeni** işleci Bu örnekte gösterilen dizi sözdizimi ile:  
  
     [!code-cpp[NVC_MFC_Utilities#2](../mfc/codesnippet/cpp/memory-management-examples_2.cpp)]  
  
#### <a name="to-deallocate-the-arrays-from-the-heap"></a>Diziler öbek de serbest bırakma için  
  
1.  Kullanım **silmek** şekilde işleci:  
  
     [!code-cpp[NVC_MFC_Utilities#3](../mfc/codesnippet/cpp/memory-management-examples_3.cpp)]  
  
##  <a name="_core_allocation_of_a_data_structure"></a>Ayırma, bir veri yapısı  
  
#### <a name="to-allocate-a-data-structure-on-the-frame"></a>Bir veri yapısı çerçevesinde ayırmak için  
  
1.  Yapı değişkeni aşağıdaki gibi tanımlayın:  
  
     [!code-cpp[NVC_MFC_Utilities#4](../mfc/codesnippet/cpp/memory-management-examples_4.cpp)]  
  
     Kapsamı çıktığında yapısı tarafından kapladığı bellek iadesi.  
  
#### <a name="to-allocate-data-structures-on-the-heap"></a>Veri yapıları yığında ayırmak için  
  
1.  Kullanım **yeni** veri yapılarını yığında ayırmak için ve **silmek** tarafından aşağıdaki örneklerde gösterildiği gibi bunları kaldırmak için:  
  
     [!code-cpp[NVC_MFC_Utilities#5](../mfc/codesnippet/cpp/memory-management-examples_5.cpp)]  
  
##  <a name="_core_allocation_of_an_object"></a>Bir nesnenin ayırma  
  
#### <a name="to-allocate-an-object-on-the-frame"></a>Çerçeve nesne ayrılamadı  
  
1.  Nesnesi şu şekilde bildirin:  
  
     [!code-cpp[NVC_MFC_Utilities#6](../mfc/codesnippet/cpp/memory-management-examples_6.cpp)]  
  
     Nesne kapsamı çıktığında yıkıcı nesne için otomatik olarak çağrılır.  
  
#### <a name="to-allocate-an-object-on-the-heap"></a>Yığında bir nesne ayrılamadı  
  
1.  Kullanım **yeni** öbek nesnelerde ayırmak için bir işaretçi nesnesine döndüren, işleci. Kullanım **silmek** silmeyi işleci.  
  
     Aşağıdaki öbek ve çerçeve örnekleri `CPerson` oluşturucu bağımsız değişkeni alır.  
  
     [!code-cpp[NVC_MFC_Utilities#7](../mfc/codesnippet/cpp/memory-management-examples_7.cpp)]  
  
     Varsa bağımsız değişkeni için `CPerson` Oluşturucusu bir işaretçidir `char`, çerçeve ayırma ifadesi:  
  
     [!code-cpp[NVC_MFC_Utilities#8](../mfc/codesnippet/cpp/memory-management-examples_8.cpp)]  
  
     Yığın ayırma ifadesidir:  
  
     [!code-cpp[NVC_MFC_Utilities#9](../mfc/codesnippet/cpp/memory-management-examples_9.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek Yönetimi: Öbek Ayırma](../mfc/memory-management-heap-allocation.md)

