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
ms.openlocfilehash: 303b8a566a730c5abd06d51fb7977174e19a6435
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370531"
---
# <a name="deleting-all-objects-in-a-cobject-collection"></a>CObject Koleksiyonundaki Tüm Nesneleri Silme

Bu makalede, koleksiyondaki tüm nesnelerin nasıl silinir (koleksiyon nesnesinin kendisini silmeden) açıklar.

`CObject`S (veya türetilen nesnelerin) koleksiyonundaki tüm nesneleri `CObject`silmek için, her nesneyi sırayla silmek için [koleksiyonun tüm üyelerine erişen](../mfc/accessing-all-members-of-a-collection.md) makalede açıklanan yineleme tekniklerinden birini kullanırsınız.

> [!CAUTION]
> Koleksiyondaki nesneler paylaşılabilir. Diğer bir deyişle, koleksiyon nesneye bir işaretçi tutar, ancak programın diğer bölümleri de aynı nesneye işaretçiler olabilir. Tüm parçalar nesneyi kullananı tamamlayana kadar paylaşılan bir nesneyi silmemeye dikkat etmelisiniz.

Bu makalede, aşağıdaki nesneler nasıl silinir gösterir:

- [Bir liste](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)

- [Bir dizi](#_core_to_delete_all_elements_in_an_array)

- [Bir harita](#_core_to_delete_all_elements_in_a_map)

#### <a name="to-delete-all-objects-in-a-list-of-pointers-to-cobject"></a><a name="_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject"></a>CObject işaretçileri listesindeki tüm nesneleri silmek için

1. Kullanın `GetHeadPosition` `GetNext` ve liste boyunca yineleyin.

1. Yinelemede karşılaşılan her nesneyi silmek için **silme** işlecinin kullanın.

1. Bu `RemoveAll` öğelerle ilişkili nesneler silindikten sonra tüm öğeleri listeden kaldırmak için işlevi arayın.

Aşağıdaki örnekte, nesnelerin bir listesinden tüm `CPerson` nesnelerin nasıl silinir gösterilmektedir. Listedeki her nesne, yığında `CPerson` başlangıçta ayrılan bir nesneye işaretçidir.

[!code-cpp[NVC_MFCCollections#17](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_1.cpp)]

Son işlev çağrısı, `RemoveAll`listeden tüm öğeleri kaldıran bir liste üye işlevidir. Üye işlev `RemoveAt` tek bir öğeyi kaldırır.

Bir öğenin nesnesini silme ve öğenin kendisini kaldırma arasındaki farka dikkat edin. Bir öğeyi listeden kaldırmak yalnızca listenin nesneye başvurularını kaldırır. Nesne hala bellekte var. Bir nesneyi sildiğinizde, nesne yok olur ve belleği geri alınır. Bu nedenle, öğenin nesnesi silindikten hemen sonra bir öğeyi kaldırmak önemlidir, böylece liste artık var olmayan nesnelere erişmeye çalışmaz.

#### <a name="to-delete-all-elements-in-an-array"></a><a name="_core_to_delete_all_elements_in_an_array"></a>Bir dizideki tüm öğeleri silmek için

1. Dizi `GetSize` boyunca yinelemek için dizin değerlerini kullanın.

1. Yinelemede karşılaşılan her öğeyi silmek için **silme** işlecikullanın.

1. Tüm `RemoveAll` öğeleri silindikten sonra diziden kaldırmak için işlevi arayın.

   Bir dizinin tüm öğelerini silme kodu aşağıdaki gibidir:

   [!code-cpp[NVC_MFCCollections#18](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_2.cpp)]

Yukarıdaki liste örneğinde olduğu gibi, bir dizideki tüm `RemoveAt` öğeleri kaldırmak veya tek bir öğeyi kaldırmak için arayabilirsiniz. `RemoveAll`

#### <a name="to-delete-all-elements-in-a-map"></a><a name="_core_to_delete_all_elements_in_a_map"></a>Haritadaki tüm öğeleri silmek için

1. `GetStartPosition` Dizide `GetNextAssoc` kullanmak ve yinelemek için.

1. Yinelemede karşılaşılan her harita öğesi için anahtarı ve/veya değeri silmek için **silme** işleğini kullanın.

1. Tüm `RemoveAll` öğeleri silindikten sonra haritadan kaldırmak için işlevi arayın.

   Koleksiyonun tüm öğelerini `CMap` silme kodu aşağıdaki gibidir. Eşlemedeki her öğe, anahtar olarak `CPerson` bir dize `CObject`ye ve değer olarak bir nesneye (türetilmiş) sahiptir.

   [!code-cpp[NVC_MFCCollections#19](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_3.cpp)]

Bir haritadaki tüm öğeleri kaldırmak `RemoveAll` `RemoveKey` veya belirtilen anahtarla tek bir öğeyi kaldırmak için arayabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Bir Koleksiyonun Tüm Üyelerine Erişme](../mfc/accessing-all-members-of-a-collection.md)
