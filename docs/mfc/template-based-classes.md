---
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
ms.openlocfilehash: 29f5f815b62835aedbca1f79b797f826ea53d83b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370465"
---
# <a name="template-based-classes"></a>Şablona Dayalı Sınıflar

Bu makalede, MFC sürüm 3.0 ve sonraki sürümlerde tür güvenli şablon tabanlı toplama sınıfları açıklanmaktadır. Tür için güvenli koleksiyonlar oluşturmak için bu şablonları kullanmak daha uygundur ve şablonları temel almayan koleksiyon sınıflarını kullanmaktan daha etkili bir şekilde tür güvenliği sağlamaya yardımcı olur.

MFC şablon tabanlı koleksiyonlar iki kategorisini önceden tanımlar:

- [Basit dizi, liste ve harita sınıfları](#_core_using_simple_array.2c_.list.2c_.and_map_templates)

   `CArray`, `CList`, `CMap`

- [Yazılan işaretçilerin dizileri, listeleri ve haritaları](#_core_using_typed.2d.pointer_collection_templates)

   `CTypedPtrArray`, `CTypedPtrList`, `CTypedPtrMap`

Basit toplama sınıflarının tümü `CObject`sınıftan türetilmiştir, bu nedenle serileştirme, `CObject`dinamik oluşturma ve diğer özelliklerini devralır. Yazılan işaretçi toplama sınıfları, türetdiğiniz sınıfı belirtmenizi gerektirir — bu da MFC tarafından önceden tanımlanmış `CPtrList` `CPtrArray`olmayan işaretçi koleksiyonlarından biri olmalıdır, örneğin veya . Yeni koleksiyon sınıfınız belirtilen taban sınıftan devralır ve yeni sınıfın üye işlevleri, tür güvenliğini zorlamak için taban sınıf üyelerine kapsüllenmiş çağrılar kullanır.

C++ şablonları hakkında daha fazla bilgi için *C++ Dil*Referansı'ndaki [Şablonlar'a](../cpp/templates-cpp.md) bakın.

## <a name="using-simple-array-list-and-map-templates"></a><a name="_core_using_simple_array.2c_.list.2c_.and_map_templates"></a>Basit Dizi, Liste ve Harita Şablonlarını Kullanma

Basit koleksiyon şablonlarını kullanmak için, bu koleksiyonlarda ne tür veriler depolayabileceğinizi ve koleksiyon bildirimlerinizde hangi parametreleri kullanabileceğinizi bilmeniz gerekir.

### <a name="simple-array-and-list-usage"></a><a name="_core_simple_array_and_list_usage"></a>Basit Dizi ve Liste Kullanımı

Basit dizi ve liste sınıfları, [CArray](../mfc/reference/carray-class.md) ve [CList,](../mfc/reference/clist-class.md)iki parametre alır: *TYPE* ve `ARG_TYPE`. Bu sınıflar, *TYPE* parametresinde belirttiğiniz herhangi bir veri türünü depolayabilir:

- **Int,** **char**ve **float** gibi temel C++ veri türleri

- C++ yapıları ve sınıfları

- Tanımladığınız diğer türler

Kolaylık ve verimlilik için, işlev bağımsız değişkenlerinin türünü belirtmek için *ARG_TYPE* parametresini kullanabilirsiniz. Tipik olarak, *TYPE* parametresinde adını ARG_TYPE türe başvuru olarak belirtirsiniz. *TYPE* Örneğin:

[!code-cpp[NVC_MFCCollections#1](../mfc/codesnippet/cpp/template-based-classes_1.cpp)]

İlk örnek, `myArray` **int**s içeren bir dizi koleksiyonu bildirir. İkinci örnek, `myList`nesneleri depolayan `CPerson` bir liste koleksiyonu bildirir. Toplama sınıflarının belirli üye işlevleri, türü *ARG_TYPE* şablon parametresi tarafından belirtilen bağımsız değişkenleri alır. Örneğin, sınıfın `Add` `CArray` üye işlevi *ARG_TYPE* bir bağımsız değişken alır:

[!code-cpp[NVC_MFCCollections#2](../mfc/codesnippet/cpp/template-based-classes_2.cpp)]

### <a name="simple-map-usage"></a><a name="_core_simple_map_usage"></a>Basit Harita Kullanımı

Basit harita sınıfı, [CMap](../mfc/reference/cmap-class.md), dört parametre alır: *KEY*, *ARG_KEY*, *DEĞER*, ve *ARG_VALUE*. Dizi ve liste sınıfları gibi, harita sınıfları da herhangi bir veri türünü depolayabilir. Depoladıkları verileri dizileştiren ve sipariş eden dizilerin ve listelerin aksine, eşler eşanahtarları ve değerleri ilişkilendiriler: Değerin ilişkili anahtarını belirterek haritada depolanan bir değere erişirsiniz. *KEY* parametresi, haritada depolanan verilere erişmek için kullanılan anahtarların veri türünü belirtir. *KEY* türü bir yapı veya sınıf ise, *ARG_KEY* parametresi genellikle *KEY'de*belirtilen türe bir başvurudur. *DEĞER* parametresi, haritada depolanan maddelerin türünü belirtir. *ARG_VALUE* türü bir yapı veya sınıf ise, *ARG_VALUE* parametresi genellikle *VALUE'da*belirtilen türe yapılan bir başvurudur. Örneğin:

[!code-cpp[NVC_MFCCollections#3](../mfc/codesnippet/cpp/template-based-classes_3.cpp)]

İlk örnek `MY_STRUCT` değerleri depolar, **int** tuşlarıyla erişir ve erişilen `MY_STRUCT` öğeleri başvuruyla döndürür. İkinci örnek `CPerson` değerleri depolar, `CString` anahtarlarla eriştirilir ve erişilen öğelere başvuruları döndürür. Bu örnek, kişileri soyadına göre araştırdığınız basit bir adres defterini temsil edebilir.

*KEY* `CString` parametresi tür ve *KEY_TYPE* parametre türü `LPCSTR`olduğundan, tuşları `CString` tür öğeleri olarak haritada saklanır ama tür `SetAt` `LPCSTR`işaretçileri aracılığıyla gibi işlevlerde başvurulan . Örneğin:

[!code-cpp[NVC_MFCCollections#4](../mfc/codesnippet/cpp/template-based-classes_4.cpp)]

## <a name="using-typed-pointer-collection-templates"></a><a name="_core_using_typed.2d.pointer_collection_templates"></a>Yazılı İşaretçi Toplama Şablonlarını Kullanma

Yazılı işaretçi toplama şablonlarını kullanmak için, bu koleksiyonlarda ne tür veriler depolayabileceğinizi ve koleksiyon bildirimlerinizde hangi parametreleri kullanabileceğinizi bilmeniz gerekir.

### <a name="typed-pointer-array-and-list-usage"></a><a name="_core_typed.2d.pointer_array_and_list_usage"></a>Yazılı İşaretçi Dizi ve Liste Kullanımı

Yazılı işaretçi dizi ve liste sınıfları, [CTypedPtrArray](../mfc/reference/ctypedptrarray-class.md) ve [CTypedPtrList,](../mfc/reference/ctypedptrlist-class.md)iki parametre alır: *BASE_CLASS* ve *TYPE*. Bu sınıflar, *TYPE* parametresinde belirttiğiniz herhangi bir veri türünü depolayabilir. İşaretçileri depolayan şablonsuz koleksiyon sınıflarından birinden türetilmiştir; bu taban sınıfı *BASE_CLASS*olarak belirtirsiniz. Diziler için, `CObArray` ya `CPtrArray`kullanın ya da. Listeler için, `CObList` ya `CPtrList`kullanın veya.

Sonuç olarak, bir koleksiyonu temel alan `CObList`olarak beyan ettiğinizde, örneğin, yeni sınıf yalnızca taban sınıfının üyelerini devralmakla kalmıyor, aynı zamanda taban sınıf üyelerine çağrıları kapsülleyerek tür güvenliği sağlamaya yardımcı olan bir dizi ek tür güvenli üye işlevi ve işleçlerini de beyan eder. Bu kapsüllemeler gerekli tüm tür dönüştürme yönetir. Örneğin:

[!code-cpp[NVC_MFCCollections#5](../mfc/codesnippet/cpp/template-based-classes_5.cpp)]

İlk örnek, `myArray`'den `CObArray`türetilen bir yazılı işaretçi dizisi, bildirir. Dizi, işaretçileri nesnelere `CPerson` depolar `CPerson` ve döndürür (nereden türeyen `CObject`bir sınıf). `CObArray` Herhangi bir üye işlevi arayabilir veya yeni tür `GetAt` güvenli `ElementAt` ve işlevleri arayabilir veya tür-güvenli **[ ]** işleci kullanabilirsiniz.

İkinci örnek, `myList`'den `CPtrList`türetilen bir yazılı işaretçi listesi, bildirir. Liste işaretçileri nesnelere `MY_STRUCT` depolar ve döndürür. Dayalı bir `CPtrList` sınıf, işaretçileri türetilmiş olmayan `CObject`nesnelere depolamak için kullanılır. `CTypedPtrList`tip güvenli üye işlevleri bir `GetHead`dizi `GetTail` `RemoveHead`vardır: , , `RemoveTail`, `GetNext`, `GetPrev`, ve `GetAt`.

### <a name="typed-pointer-map-usage"></a><a name="_core_typed.2d.pointer_map_usage"></a>Yazılı-İşaretçi Eşharitası Kullanımı

Dakti-işaretçi sile, [CTypedPtrMap](../mfc/reference/ctypedptrmap-class.md), üç parametre alır: *BASE_CLASS*, *ANAHTAR*, ve *DEĞER*. *BASE_CLASS* parametresi, yeni sınıfı türetecek sınıfı `CMapPtrToWord`belirtir: `CMapPtrToPtr` `CMapStringToPtr`, `CMapWordToPtr` `CMapStringToOb`, , , ve benzeri. *KEY* içinde `CMap` *KEY* benzer : Bu aramalar için kullanılan anahtar türünü belirtir. *DEĞER,* *DEĞER'e* `CMap`benzer : Haritada depolanan nesnenin türünü belirtir. Örneğin:

[!code-cpp[NVC_MFCCollections#6](../mfc/codesnippet/cpp/template-based-classes_6.cpp)]

İlk örnek, dayalı bir `CMapPtrToPtr` haritadır `CString` — işaretçileriçin eşlenen anahtarları `MY_STRUCT`kullanır. Tür güvenli `Lookup` üye işlevini çağırarak depolanan bir işaretçiyi arayabilirsiniz. **[ ]** işleci, depolanan bir işaretçiyi aramak ve bulunamazsa eklemek için kullanabilirsiniz. Ve tür güvenli `GetNextAssoc` işlevini kullanarak haritayı yineleyebilirsiniz. Sınıfın diğer üye işlevlerini `CMapPtrToPtr`de arayabilirsiniz.

İkinci örnek, nesnelere `CMapStringToOb` depolanan işaretçileriçin `CMyObject` eşlenen dize anahtarlarını kullanan bir haritadır. Önceki paragrafta açıklanan aynı tür güvenli üyeleri kullanabilirsiniz veya sınıf `CMapStringToOb`üyelerini arayabilirsiniz.

> [!NOTE]
> *Değer* parametresi için bir işaretçi veya türe başvuru yerine bir **sınıf** veya **yapı** türü belirtirseniz, sınıf veya yapının bir kopya oluşturucusu olmalıdır.

Daha fazla bilgi için, [Tür Güvenli Toplama Nasıl Yapılır'a](../mfc/how-to-make-a-type-safe-collection.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar](../mfc/collections.md)
