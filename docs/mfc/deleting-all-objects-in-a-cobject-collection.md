---
title: CObject Koleksiyonundaki Tüm Nesneleri Silme
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], deleting in collections
- objects in CObject collections, deleting
- CObject class [MFC], deleting in collection
- collection classes [MFC], deleting all objects
- CObject class collection
- objects in CObject collections
- collection classes [MFC], shared objects
ms.assetid: 81d2c1d5-a0a5-46e1-8ab9-82b45cf7afd2
ms.openlocfilehash: 5aac324b6af50db019c2a4b55b26a612cc081894
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225078"
---
# <a name="deleting-all-objects-in-a-cobject-collection"></a>CObject Koleksiyonundaki Tüm Nesneleri Silme

Bu makalede, bir koleksiyondaki tüm nesnelerin nasıl silineceği açıklanmaktadır (koleksiyon nesnesinin kendisi silinmeksizin).

Bir `CObject` s (veya öğesinden türetilmiş nesneler) koleksiyonundaki tüm nesneleri silmek için `CObject` , her bir nesneyi sırayla silmek üzere [bir koleksiyonun tüm üyelerine erişme](accessing-all-members-of-a-collection.md) makalesinde açıklanan yineleme tekniklerinden birini kullanırsınız.

> [!CAUTION]
> Koleksiyonlardaki nesneler paylaşılabilir. Diğer bir deyişle, koleksiyon nesneye bir işaretçi tutar, ancak programın diğer bölümlerinde aynı nesneye işaretçiler de olabilir. Tüm parçalar nesnesini kullanarak bitene kadar paylaşılan bir nesneyi silmemeye dikkat etmeniz gerekir.

Bu makalede, içindeki nesnelerin nasıl silineceği gösterilmektedir:

- [Bir liste](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)

- [Bir dizi](#_core_to_delete_all_elements_in_an_array)

- [Eşleme](#_core_to_delete_all_elements_in_a_map)

#### <a name="to-delete-all-objects-in-a-list-of-pointers-to-cobject"></a><a name="_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject"></a>CObject işaretçilerinden oluşan bir listedeki tüm nesneleri silmek için

1. `GetHeadPosition`, Ve kullanarak `GetNext` Listeyi yinelemek için kullanın.

1. **`delete`** Yineleme içinde karşılaşılan her nesneyi silmek için işlecini kullanın.

1. `RemoveAll`Bu öğelerle ilişkili nesneler silindikten sonra tüm öğeleri listeden kaldırmak için işlevi çağırın.

Aşağıdaki örnek bir nesne listesinden tüm nesnelerin nasıl silineceğini gösterir `CPerson` . Listedeki her bir nesne, `CPerson` Başlangıçta yığında ayrılmış bir nesne işaretçisidir.

[!code-cpp[NVC_MFCCollections#17](codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_1.cpp)]

Son işlev çağrısı, `RemoveAll` listedeki tüm öğeleri kaldıran bir liste üyesi işlevidir. Üye işlevi `RemoveAt` tek bir öğeyi kaldırır.

Bir öğenin nesnesini silme ve öğenin kendisini kaldırma arasındaki farka dikkat edin. Bir öğenin listeden kaldırılması yalnızca listenin nesnesine ait başvurusunu kaldırır. Nesne bellekte hala var. Bir nesneyi sildiğinizde, mevcut olmaya erer ve belleği geri kazanılır. Bu nedenle, listenin artık mevcut olmayan nesnelere erişmeyi deneyememesi için öğenin nesnesi silindikten hemen sonra bir öğeyi kaldırmak önemlidir.

#### <a name="to-delete-all-elements-in-an-array"></a><a name="_core_to_delete_all_elements_in_an_array"></a>Bir dizideki tüm öğeleri silmek için

1. `GetSize`Dizi boyunca yinelemek için ve tamsayı dizin değerlerini kullanın.

1. **`delete`** Yineleme içinde karşılaşılan her öğeyi silmek için işlecini kullanın.

1. `RemoveAll`Silinmeden sonra dizideki tüm öğeleri kaldırmak için işlevi çağırın.

   Bir dizinin tüm öğelerini silme kodu aşağıdaki gibidir:

   [!code-cpp[NVC_MFCCollections#18](codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_2.cpp)]

Yukarıdaki liste örneğinde olduğu gibi, `RemoveAll` bir dizideki tüm öğeleri kaldırmak veya `RemoveAt` tek bir öğeyi kaldırmak için öğesini çağırabilirsiniz.

#### <a name="to-delete-all-elements-in-a-map"></a><a name="_core_to_delete_all_elements_in_a_map"></a>Bir haritadaki tüm öğeleri silmek için

1. `GetStartPosition` `GetNextAssoc` Dizi boyunca yinelemek için ve kullanın.

1. **`delete`** Yineleme içinde karşılaşılan her harita öğesi için anahtarı ve/veya değeri silmek için işlecini kullanın.

1. `RemoveAll`Silindikten sonra haritadan tüm öğeleri kaldırmak için işlevi çağırın.

   Bir koleksiyonun tüm öğelerini silme kodu aşağıdaki gibidir `CMap` . Eşlemedeki her öğe, anahtar olarak bir dize ve `CPerson` değer olarak bir nesnesi (öğesinden türetilmiş `CObject` ) içerir.

   [!code-cpp[NVC_MFCCollections#19](codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_3.cpp)]

`RemoveAll`Bir haritadaki tüm öğeleri kaldırmak veya `RemoveKey` belirtilen anahtarla tek bir öğeyi kaldırmak için öğesini çağırabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Bir koleksiyonun tüm üyelerine erişme](accessing-all-members-of-a-collection.md)
