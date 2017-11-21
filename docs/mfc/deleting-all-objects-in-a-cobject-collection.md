---
title: "CObject koleksiyonundaki tüm nesneleri silme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- objects [MFC], deleting in collections
- objects in CObject collections, deleting
- CObject class [MFC], deleting in collection
- collection classes [MFC], deleting all objects
- CObject class collection
- objects in CObject collections
- collection classes [MFC], shared objects
ms.assetid: 81d2c1d5-a0a5-46e1-8ab9-82b45cf7afd2
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8065af989f220f5954b851149c1b7c7a814a7d1f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="deleting-all-objects-in-a-cobject-collection"></a>CObject Koleksiyonundaki Tüm Nesneleri Silme
Bu makalede (koleksiyon nesnesi silmeden) koleksiyonundaki tüm nesneleri silme açıklanmaktadır.  
  
 Bir koleksiyondaki tüm nesneleri silmek için `CObject`s (veya türetilmiş nesnelerin `CObject`), makalesinde açıklanan yineleme teknikleri birini kullanmanız [bir koleksiyonun tüm üyelerine erişme](../mfc/accessing-all-members-of-a-collection.md) her nesneyi silmek için kapatın.  
  
> [!CAUTION]
>  Koleksiyonlarında nesneler paylaşılabilir. Diğer bir deyişle, koleksiyon nesnesi için bir işaretçi tutar, ancak program diğer bölümleriyle aynı nesne işaretçileri da sahip olabilirsiniz. Tüm bölümleri nesnesini kullanarak bitinceye kadar paylaşılan bir nesne silmemeye olması gerekir.  
  
 Bu makalede nesneleri Sil gösterilmektedir:  
  
-   [Bir liste](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)  
  
-   [Bir dizi](#_core_to_delete_all_elements_in_an_array)  
  
-   [Bir eşleme](#_core_to_delete_all_elements_in_a_map)  
  
#### <a name="_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject"></a>CObject işaretçiler listesindeki tüm nesneleri silmek için  
  
1.  Kullanım `GetHeadPosition` ve `GetNext` eşlemeleri yinelemek için.  
  
2.  Kullanım **silmek** yinelemede karşılaştı her nesneyi silmek için işleci.  
  
3.  Çağrı `RemoveAll` işlevi bu öğelerle ilişkili nesneler silindikten sonra tüm öğeleri listeden kaldırın.  
  
 Aşağıdaki örnek, tüm nesneleri listesinden silmek gösterilmiştir `CPerson` nesneleri. Listedeki her nesneyi gösteren bir işaretçidir bir `CPerson` yığında ayrılan nesne.  
  
 [!code-cpp[NVC_MFCCollections#17](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_1.cpp)]  
  
 Son işlev çağrısı `RemoveAll`, listeden tüm öğeleri kaldırır bir liste üyesi işlevdir. Üye işlevini `RemoveAt` tek bir öğeyi kaldırır.  
  
 Bir öğenin nesne silme ve öğe kaldırıldığında arasındaki fark. Yalnızca listeden bir öğe kaldırıldığında nesnesine listenin başvuru kaldırır. Nesne hala bellekte mevcut. Bir nesne sildiğinizde, mevcut işlemiyorsa ve kendi bellek iadesi. Bu nedenle, böylece artık mevcut nesnelere erişmek listenin denemez öğenin nesne hemen silindikten sonra bir öğeyi kaldırmak önemlidir.  
  
#### <a name="_core_to_delete_all_elements_in_an_array"></a>Bir dizinin tüm öğeleri silmek için  
  
1.  Kullanım `GetSize` ve dizi boyunca yinelemek için tamsayı dizini değerleri.  
  
2.  Kullanım **silmek** yinelemede karşılaştı her öğe silmek için işleci.  
  
3.  Çağrı `RemoveAll` silindikten sonra diziden tüm öğeleri kaldırmak için işlevi.  
  
     Bir dizinin tüm öğeleri silmek için kod aşağıdaki gibidir:  
  
     [!code-cpp[NVC_MFCCollections#18](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_2.cpp)]  
  
 Liste örneği yukarıdaki arayabileceğiniz gibi `RemoveAll` bir dizideki tüm öğeleri kaldırmak için veya `RemoveAt` tek bir öğe kaldırmak için.  
  
#### <a name="_core_to_delete_all_elements_in_a_map"></a>Bir eşlemindeki tüm öğeleri silmek için  
  
1.  Kullanım `GetStartPosition` ve `GetNextAssoc` dizi boyunca yinelemek için.  
  
2.  Kullanım **silmek** yinelemede karşılaştı anahtarı ve/veya her harita öğesinin değeri silmek için işleci.  
  
3.  Çağrı `RemoveAll` silindikten sonra eşlemesinden tüm öğeleri kaldırmak için işlevi.  
  
     Tüm öğeleri silmek için kod bir `CMap` koleksiyonu aşağıdaki gibidir. Anahtar olarak bir dize eşlemesindeki her öğeye sahip ve bir `CPerson` nesne (türetilmiş `CObject`) değeri.  
  
     [!code-cpp[NVC_MFCCollections#19](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_3.cpp)]  
  
 Çağırabilirsiniz `RemoveAll` haritada tüm öğeleri kaldırmak için veya `RemoveKey` tek bir öğe belirtilen anahtara sahip kaldırmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir koleksiyonun tüm üyelerine erişme](../mfc/accessing-all-members-of-a-collection.md)

