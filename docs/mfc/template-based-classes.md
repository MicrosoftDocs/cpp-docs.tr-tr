---
description: 'Hakkında daha fazla bilgi edinin: Template-Based sınıfları'
title: Şablona Dayalı Sınıflar
ms.date: 11/04/2016
helpviewer_keywords:
- type-safe collections
- CTypedPtrList class [MFC], template-based classes
- arrays [MFC], classes
- arrays [MFC], pointers
- typed pointers, collections of
- arrays [MFC], template-based
- CArray class [MFC], template-based classes
- simple template-based collections
- simple array collection classes [MFC]
- typed pointers
- collections, typed-pointer
- CList class [MFC], template-based classes
- collection classes [MFC], template-based
- CTypedPtrMap class [MFC], template-based classes
- pointers, collections of typed
- CTypedPtrArray class [MFC], template-based classes
- MFC collection classes [MFC], template-based
- template-based collection classes [MFC]
- simple list collection classes [MFC]
ms.assetid: c69fc95b-c8f6-4a99-abed-517c9898ef0c
ms.openlocfilehash: 87b03c649bfb6acf401c3ee78e6db07c1185dff5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216320"
---
# <a name="template-based-classes"></a>Şablona Dayalı Sınıflar

Bu makalede, MFC sürüm 3,0 ve sonrasında tür kullanımı uyumlu şablon tabanlı koleksiyon sınıfları açıklanmaktadır. Tür kullanımı uyumlu Koleksiyonlar oluşturmak için bu şablonları kullanmak daha uygundur ve şablon tabanlı olmayan koleksiyon sınıflarını kullanmaktan daha etkili bir şekilde tür güvenliği sağlamaya yardımcı olur.

MFC, şablon tabanlı koleksiyonların iki kategorisini önceden tanımlar:

- [Basit dizi, liste ve eşleme sınıfları](#_core_using_simple_array.2c_.list.2c_.and_map_templates)

   `CArray`, `CList`, `CMap`

- [Yazılan işaretçilerin dizileri, listeleri ve eşlemeleri](#_core_using_typed.2d.pointer_collection_templates)

   `CTypedPtrArray`, `CTypedPtrList`, `CTypedPtrMap`

Basit koleksiyon sınıflarının hepsi sınıfından türetilir `CObject` , bu nedenle serileştirme, dinamik oluşturma ve diğer özelliklerini alırlar `CObject` . Türü belirtilmiş işaretçi koleksiyon sınıfları, veya gibi MFC tarafından önceden tanımlanmış şablon olmayan işaretçi koleksiyonlarından biri olması gereken içinden türettiğiniz sınıfı belirtmenizi gerektirir `CPtrList` `CPtrArray` . Yeni koleksiyon sınıfınız belirtilen temel sınıftan devralınır ve yeni sınıfın üye işlevleri tür güvenliğini zorlamak için taban sınıf üyelerine kapsüllenmiş çağrılar kullanır.

C++ şablonları hakkında daha fazla bilgi için bkz. *C++ dil başvurusu* içindeki [Şablonlar](../cpp/templates-cpp.md) .

## <a name="using-simple-array-list-and-map-templates"></a><a name="_core_using_simple_array.2c_.list.2c_.and_map_templates"></a> Basit dizi, liste ve eşleme şablonları kullanma

Basit koleksiyon şablonlarını kullanmak için, bu koleksiyonlara ne tür verileri depolayabileceğinizi ve koleksiyon bildirimlerinizde kullanılacak parametreleri bilmeniz gerekir.

### <a name="simple-array-and-list-usage"></a><a name="_core_simple_array_and_list_usage"></a> Basit dizi ve liste kullanımı

Basit dizi ve liste sınıfları, [CArray](../mfc/reference/carray-class.md) ve [CList](../mfc/reference/clist-class.md), Iki parametre alır: *tür* ve `ARG_TYPE` . Bu sınıflar, *tür* parametresinde belirttiğiniz herhangi bir veri türünü depolayabilirler:

- , Ve gibi temel C++ veri türleri **`int`** **`char`****`float`**

- C++ yapıları ve sınıfları

- Tanımladığınız diğer türler

Kullanışlı ve verimlilik için, işlev bağımsız değişkenlerinin türünü belirtmek üzere *ARG_TYPE* parametresini kullanabilirsiniz. Genellikle, *tür* parametresinde adlandırdığınız türe başvuru olarak *ARG_TYPE* belirtirsiniz. Örneğin:

[!code-cpp[NVC_MFCCollections#1](../mfc/codesnippet/cpp/template-based-classes_1.cpp)]

İlk örnek, öğeleri içeren bir dizi koleksiyonu bildirir `myArray` **`int`** . İkinci örnek, nesneleri depolayan bir liste koleksiyonunu bildirir `myList` `CPerson` . Koleksiyon sınıflarının belirli üye işlevleri, türü *ARG_TYPE* şablon parametresiyle belirtilen bağımsız değişkenleri alır. Örneğin, `Add` sınıfının üye işlevi `CArray` bir *ARG_TYPE* bağımsız değişkeni alır:

[!code-cpp[NVC_MFCCollections#2](../mfc/codesnippet/cpp/template-based-classes_2.cpp)]

### <a name="simple-map-usage"></a><a name="_core_simple_map_usage"></a> Basit eşleme kullanımı

Basit eşleme sınıfı olan [CMap](../mfc/reference/cmap-class.md), dört parametre alır: *anahtar*, *ARG_KEY*, *değer* ve *ARG_VALUE*. Dizi ve liste sınıfları gibi, eşleme sınıfları herhangi bir veri türünü de saklayabilir. Depotıkları verileri dizin ve sipariş eden diziler ve listelerden farklı olarak, haritalar anahtarları ve değerleri ilişkilendirir: değerin ilişkili anahtarını belirterek haritada depolanan bir değere erişirsiniz. *Anahtar* parametresi, haritada depolanan verilere erişmek için kullanılan anahtarların veri türünü belirtir. *Anahtar* türü bir yapı veya sınıf ise, *ARG_KEY* parametresi genellikle *anahtarda* belirtilen türe bir başvurudur. *Value* parametresi, haritada depolanan öğelerin türünü belirtir. *ARG_VALUE* türü bir yapı veya sınıf ise, *ARG_VALUE* parametresi genellikle *değer*'de belirtilen türe bir başvurudur. Örneğin:

[!code-cpp[NVC_MFCCollections#3](../mfc/codesnippet/cpp/template-based-classes_3.cpp)]

İlk örnek, `MY_STRUCT` değerleri depolar, anahtarlara göre erişir **`int`** ve erişilen `MY_STRUCT` öğeleri başvuruya göre döndürür. İkinci örnek değerleri depolar `CPerson` , anahtarlara göre erişir `CString` ve erişilen öğelere başvurular döndürür. Bu örnek, son ada göre kişileri aramak için bir basit adres defterini temsil edebilir.

*Anahtar* parametresi türü `CString` ve *key_type* parametresi türünde olduğu için `LPCSTR` , anahtarlar haritada tür öğeleri olarak saklanır, `CString` ancak `SetAt` tür işaretçileri aracılığıyla gibi işlevlerde başvurulur `LPCSTR` . Örneğin:

[!code-cpp[NVC_MFCCollections#4](../mfc/codesnippet/cpp/template-based-classes_4.cpp)]

## <a name="using-typed-pointer-collection-templates"></a><a name="_core_using_typed.2d.pointer_collection_templates"></a> Typed-Pointer koleksiyonu şablonlarını kullanma

Yazılan işaretçi koleksiyonu şablonlarını kullanmak için, bu koleksiyonlarda depoladığınız veri türlerini ve koleksiyon bildirimlerinde hangi parametreleri kullanacağınızı bilmeniz gerekir.

### <a name="typed-pointer-array-and-list-usage"></a><a name="_core_typed.2d.pointer_array_and_list_usage"></a> Typed-Pointer dizi ve liste kullanımı

Yazılan işaretçi dizisi ve liste sınıfları, [CTypedPtrArray](../mfc/reference/ctypedptrarray-class.md) ve [CTypedPtrList](../mfc/reference/ctypedptrlist-class.md), iki parametre alır: *BASE_CLASS* ve *türü*. Bu sınıflar, *tür* parametresinde belirttiğiniz herhangi bir veri türünü saklayabilir. Bunlar, işaretçileri depolayan şablon olmayan koleksiyon sınıflarından birinden türetilir; Bu temel sınıfı *BASE_CLASS* belirlersiniz. Diziler için ya da kullanın `CObArray` `CPtrArray` . Listeler için ya da kullanın `CObList` `CPtrList` .

Aslında, temelinde bir koleksiyon bildirdiğinizde, `CObList` Yeni sınıf yalnızca temel sınıfının üyelerini devralmadığınızda, ancak temel sınıf üyelerine yapılan çağrıları kapsülleyerek tür güvenliği sağlamaya yardımcı olan ek türdeki güvenli üye işlevleri ve işleçleri de bildirir. Bu encapsulations tüm gerekli tür dönüşümünü yönetir. Örneğin:

[!code-cpp[NVC_MFCCollections#5](../mfc/codesnippet/cpp/template-based-classes_5.cpp)]

İlk örnek, öğesinden türetilmiş bir tür işaretçisi dizisi bildirir `myArray` `CObArray` . Dizi, nesnelere işaretçiler depolar ve döndürür `CPerson` (burada sınıfından `CPerson` türetilmiş bir sınıftır `CObject` ). Herhangi bir `CObArray` üye işlevi çağırabilir veya yeni tür-güvenli `GetAt` ve işlevleri çağırabilir ya da tür kullanımı `ElementAt` güvenli **[]** işlecini kullanabilirsiniz.

İkinci örnek, öğesinden türetilmiş, türü belirlenmiş işaretçi listesini bildirir `myList` `CPtrList` . Liste, nesnelere işaretçiler depolar ve döndürür `MY_STRUCT` . Temel bir sınıf `CPtrList` , öğesinden türetilmeyen nesnelere işaretçiler depolamak için kullanılır `CObject` . `CTypedPtrList` ,,,,,, ve türünde sayıda güvenli üye işlevi vardır:,,, `GetHead` `GetTail` ,, `RemoveHead` `RemoveTail` `GetNext` `GetPrev` ve `GetAt` .

### <a name="typed-pointer-map-usage"></a><a name="_core_typed.2d.pointer_map_usage"></a> Eşleme kullanımını Typed-Pointer

Yazılan işaretçi eşleme sınıfı, [CTypedPtrMap](../mfc/reference/ctypedptrmap-class.md), üç parametre alır: *BASE_CLASS*, *anahtar* ve *değer*. *BASE_CLASS* parametresi, yeni sınıfın türettikleri sınıfı belirtir: `CMapPtrToWord` , `CMapPtrToPtr` ,, `CMapStringToPtr` `CMapWordToPtr` ,, vb `CMapStringToOb` . *Anahtar* , içindeki *anahtara* benzerdir `CMap` : aramalar için kullanılan anahtarın türünü belirtir. *Değer* , içindeki *değere* benzerdir `CMap` : haritada depolanan nesne türünü belirtir. Örneğin:

[!code-cpp[NVC_MFCCollections#6](../mfc/codesnippet/cpp/template-based-classes_6.cpp)]

İlk örnek,, `CMapPtrToPtr` `CString` işaretçilerle eşleştirilmiş anahtarları kullanır `MY_STRUCT` . Bir tür kullanımı uyumlu üye işlevini çağırarak, saklı bir işaretçi arayabilirsiniz `Lookup` . Saklı bir işaretçi aramak ve bulunamazsa eklemek için **[]** işlecini kullanabilirsiniz. Aynı şekilde, tür kullanımı uyumlu işlevini kullanarak eşlemeyi yineleyebilirsiniz `GetNextAssoc` . Ayrıca, sınıfının diğer üye işlevlerini çağırabilirsiniz `CMapPtrToPtr` .

İkinci örnek, temel alınarak kullanılan bir haritadır, `CMapStringToOb` nesneleri saklı işaretçilerle eşleştirilmiş dize anahtarlarını kullanır `CMyObject` . Önceki paragrafta açıklanan tür açısından güvenli üyeleri kullanabilir veya sınıfının üyelerini çağırabilirsiniz `CMapStringToOb` .

> [!NOTE]
> **`class`** **`struct`** *Değer* parametresi için bir işaretçi veya tür başvurusu yerine bir veya türü belirtirseniz, sınıf veya yapının bir kopya Oluşturucusu olması gerekir.

Daha fazla bilgi için bkz. [Type-Safe koleksiyonu oluşturma](../mfc/how-to-make-a-type-safe-collection.md).

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar](../mfc/collections.md)
