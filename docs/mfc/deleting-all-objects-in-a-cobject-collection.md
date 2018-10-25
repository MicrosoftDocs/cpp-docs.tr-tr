---
title: CObject koleksiyonundaki tüm nesneleri silme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], deleting in collections
- objects in CObject collections, deleting
- CObject class [MFC], deleting in collection
- collection classes [MFC], deleting all objects
- CObject class collection
- objects in CObject collections
- collection classes [MFC], shared objects
ms.assetid: 81d2c1d5-a0a5-46e1-8ab9-82b45cf7afd2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 986bc24c57f8692bfdd98194b9e58c9cee6817f6
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067195"
---
# <a name="deleting-all-objects-in-a-cobject-collection"></a>CObject Koleksiyonundaki Tüm Nesneleri Silme

Bu makalede (koleksiyon nesnesinin kendisini silmeden) koleksiyonundaki tüm nesneleri silme işlemini açıklar.

Koleksiyonundaki tüm nesneleri silmek için `CObject`s (veya türetilen nesnelerin `CObject`), makalesinde açıklanan yineleme tekniklerden birini kullanın [bir koleksiyonun tüm üyelerine erişme](../mfc/accessing-all-members-of-a-collection.md) her bir nesnenin silmek için kapatın.

> [!CAUTION]
>  Koleksiyonlarında nesneler paylaşılabilir. Diğer bir deyişle, koleksiyon nesnesine bir işaretçi tutar ancak programın diğer bölümlerini de aynı nesneye bir işaretçi olabilir. Nesnesini kullanarak tüm bölümleri tamamlanana kadar paylaşılan bir nesne silmemeyi dikkatli olmanız gerekir.

Bu makalede, nesneleri silme işlemini göstermektedir:

- [Bir liste](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)

- [Bir dizi](#_core_to_delete_all_elements_in_an_array)

- [Bir eşleme](#_core_to_delete_all_elements_in_a_map)

#### <a name="_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject"></a>  CObject işaretçiler listesindeki tüm nesneleri silme

1. Kullanım `GetHeadPosition` ve `GetNext` listede gezinmek için.

1. Kullanım **Sil** yinelemede karşılaştığından her nesneyi silmek için işleci.

1. Çağrı `RemoveAll` öğelerle ilişkili nesneler silindikten sonra listeden tüm öğeleri kaldırmak için işlevi.

Aşağıdaki örnek bir listeden tüm nesneleri silme gösterir `CPerson` nesneleri. Listedeki her bir nesne işaretçisidir bir `CPerson` yığın üzerinde ayrılan nesne.

[!code-cpp[NVC_MFCCollections#17](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_1.cpp)]

Son işlev çağrısı `RemoveAll`, listeden tüm öğeleri kaldırır listesi üye işlevi olmasıdır. Üye işlevi `RemoveAt` tek bir öğeyi kaldırır.

Bir öğenin nesneyi silmek ve öğe kaldırıldığında arasındaki farka dikkat edin. Listeden bir öğe kaldırıldığında, yalnızca nesne listenin başvuruyu kaldırır. Nesne bellekte hala mevcut. Bir nesne sildiğinizde, mevcut olmaktan çıkar ve onun belleğini geri kazanılır. Bu nedenle, liste artık mevcut nesnelere erişmek denememesi hemen öğenin nesne silindikten sonra bir öğe kaldırmak önemlidir.

#### <a name="_core_to_delete_all_elements_in_an_array"></a>  Bir dizideki tüm öğeler silinecek

1. Kullanım `GetSize` ve dizi aracılığıyla yineleme yapmak için tamsayı dizin değerleri.

1. Kullanım **Sil** işleci yinelemede karşılaştığından her öğe silinemedi.

1. Çağrı `RemoveAll` silindikten sonra diziden tüm öğeleri kaldırmak için işlevi.

   Bir dizinin tüm öğeleri silmek için kod aşağıdaki gibidir:

   [!code-cpp[NVC_MFCCollections#18](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_2.cpp)]

Liste örneği yukarıdaki çağırabilirsiniz gibi `RemoveAll` bir dizideki tüm öğeleri kaldırmak için veya `RemoveAt` tek bir öğe kaldırmak için.

#### <a name="_core_to_delete_all_elements_in_a_map"></a> Bir eşlem içindeki tüm öğeleri silmek için

1. Kullanım `GetStartPosition` ve `GetNextAssoc` dizi aracılığıyla yineleme yapmak için.

1. Kullanım **Sil** işleci yinelemede karşılaştığından anahtarı ve/veya her harita öğesinin değeri silinemedi.

1. Çağrı `RemoveAll` silindikten sonra tüm öğeleri eşlemden kaldırmak için işlevi.

   Tüm öğeleri silmek için kod bir `CMap` koleksiyon aşağıdaki gibidir. Haritadaki her öğe olan anahtar bir dize ve `CPerson` nesne (türetilen `CObject`) değeri.

   [!code-cpp[NVC_MFCCollections#19](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_3.cpp)]

Çağırabilirsiniz `RemoveAll` eşlemedeki tüm öğeleri kaldırmak için veya `RemoveKey` belirtilen anahtarı içeren tek bir öğe kaldırmak için.

## <a name="see-also"></a>Ayrıca Bkz.

[Bir Koleksiyonun Tüm Üyelerine Erişme](../mfc/accessing-all-members-of-a-collection.md)

