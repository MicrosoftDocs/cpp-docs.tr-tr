---
title: Şablona dayalı sınıflar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b972d4552a8e41ca0dcea4ef57d48ef161ea35b9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069236"
---
# <a name="template-based-classes"></a>Şablona Dayalı Sınıflar

Bu makalede, MFC sürüm 3.0 ve sonraki tür kullanımı uyumlu şablon tabanlı koleksiyon sınıflarını açıklar. Tür kullanımı uyumlu koleksiyonlar oluşturmak için bu şablonları kullanarak daha kolaydır ve tür güvenliği şablonlarına dayalı koleksiyon sınıfları kullanmaktan daha etkili bir şekilde sağlanır.

MFC, şablona dayalı koleksiyonlar iki kategorisi önceden belirler:

- [Basit dizi, liste ve eşleme sınıfları](#_core_using_simple_array.2c_.list.2c_.and_map_templates)

   `CArray`, `CList`, `CMap`

- [Diziler, listeler ve eşlemeler yazılan işaretçiler](#_core_using_typed.2d.pointer_collection_templates)

   `CTypedPtrArray`, `CTypedPtrList`, `CTypedPtrMap`

Basit koleksiyon sınıfları tüm sınıfından türetilen `CObject`, serileştirme, dinamik oluşturma ve diğer özelliklerini devralır `CObject`. İşaretçi türü belirlenmiş koleksiyon sınıfları, türetilen sınıf belirtmenizi gerektirir — MFC tarafından gibi önceden tanımlanmış sınıflarındaki işaretçi koleksiyonlardan biri olmalıdır `CPtrList` veya `CPtrArray`. Yeni koleksiyon sınıfınıza belirtilen temel sınıfından devralır ve tür güvenliği zorlamak için temel sınıf üyelerinin kapsüllenmiş çağrıları yeni sınıfın üye işlevleri kullanın.

C++ şablonları hakkında daha fazla bilgi için bkz. [şablonları](../cpp/templates-cpp.md) içinde *C++ dil başvurusu*.

##  <a name="_core_using_simple_array.2c_.list.2c_.and_map_templates"></a> Basit dizi, liste ve eşleme şablonları kullanma

Basit koleksiyon şablonlarını kullanmak için ne tür veriler bu koleksiyonlarında depolayabilir ve koleksiyon bildirimlerinizde kullanılacak parametreleri bilmeniz gerekir.

###  <a name="_core_simple_array_and_list_usage"></a> Basit dizi ve kullanımı Listele

Liste sınıfları ve Basit dizi [CArray](../mfc/reference/carray-class.md) ve [CList](../mfc/reference/clist-class.md), iki parametre alır: *türü* ve `ARG_TYPE`. Bu sınıfların belirttiğiniz herhangi bir veri türü depolayabilirsiniz *türü* parametresi:

- Gibi temel bir C++ veri türleri **int**, **char**, ve **float**

- C++ yapılar ve sınıflar

- Tanımladığınız diğer türler

Kolaylık ve verimlilik için kullanabileceğiniz *ARG_TYPE* parametresinin türü işlev bağımsız değişkenleri belirtin. Genellikle, belirttiğiniz *ARG_TYPE* adlı içinde türüne başvuru olarak *türü* parametresi. Örneğin:

[!code-cpp[NVC_MFCCollections#1](../mfc/codesnippet/cpp/template-based-classes_1.cpp)]

İlk örnek, bir dizi koleksiyon bildirir `myArray`, içeren **int**s. İkinci örnek bir liste koleksiyonu bildirir `myList`, depolayan `CPerson` nesneleri. Belirli bir koleksiyon sınıflarının üye işlevleri tarafından belirtilen türü bir bağımsız değişken almaz *ARG_TYPE* şablon parametresi. Örneğin, `Add` sınıfının üye işlevinde `CArray` götüren bir *ARG_TYPE* bağımsız değişkeni:

[!code-cpp[NVC_MFCCollections#2](../mfc/codesnippet/cpp/template-based-classes_2.cpp)]

###  <a name="_core_simple_map_usage"></a> Basit eşleme kullanımı

Basit bir eşlem sınıfı, [CMap](../mfc/reference/cmap-class.md), dört parametre alır: *anahtarı*, *ARG_KEY*, *değer*, ve *ARG_VALUE*. Dizi ve liste sınıflar gibi herhangi bir veri türü eşleme sınıfları depolayabilirsiniz. , Diziler ve dizin ve bunlar depolamak verileri sıralayabilir, listeler, haritalar anahtarları ve değerleri ilişkilendirin: değer ilişkili anahtar belirterek bir eşlem içinde depolan bir değer erişim. *Anahtar* parametresi eşlemesinde depolanan verilere erişmek için kullanılan anahtarları veri türünü belirtir. Varsa türünü *anahtarı* yapısı veya sınıf *ARG_KEY* parametresi, genellikle belirtilen türe başvuru *anahtar*. *Değer* parametresi eşlemesinde depolanan öğelerin türünü belirtir. Varsa türünü *ARG_VALUE* yapısı veya sınıf *ARG_VALUE* parametresi, genellikle belirtilen türe başvuru *değer*. Örneğin:

[!code-cpp[NVC_MFCCollections#3](../mfc/codesnippet/cpp/template-based-classes_3.cpp)]

İlk örnek depoları `MY_STRUCT` değerlerini, bunlara erişen **int** anahtarları ve erişilen döndürür `MY_STRUCT` başvuruya göre öğeleri. İkinci örnek depoları `CPerson` değerlerini, bunlara erişen `CString` anahtarları ve başvurular erişilen öğeleri döndürür. Bu örnek, bir basit adres defteri kişileri soyadına göre arayın, temsil edebilir.

Çünkü *anahtarı* parametre türüdür `CString` ve *KEY_TYPE* parametre türüdür `LPCSTR`, anahtarları, öğe türü eşlemde depolanır `CString` içinde başvurulmuş ancak gibi işlevler `SetAt` işaretçiler aracılığıyla `LPCSTR`. Örneğin:

[!code-cpp[NVC_MFCCollections#4](../mfc/codesnippet/cpp/template-based-classes_4.cpp)]

##  <a name="_core_using_typed.2d.pointer_collection_templates"></a> Yazılan işaretçi toplama şablonlarını kullanma

Yazılan işaretçi toplama şablonlarını kullanmak için koleksiyon bildirimlerinde kullanılacak parametreleri hangi tür verileri bu koleksiyonlarında depolayabilir ve bilmeniz gerekir.

###  <a name="_core_typed.2d.pointer_array_and_list_usage"></a> İşaretçi türü belirlenmiş dizi ve kullanımı Listele

Liste sınıfları ve işaretçi türü belirlenmiş dizi [CTypedPtrArray](../mfc/reference/ctypedptrarray-class.md) ve [CTypedPtrList](../mfc/reference/ctypedptrlist-class.md), iki parametre alır: *$base_class* ve *türü*. Bu sınıfların belirttiğiniz herhangi bir veri türü depolayabilirsiniz *türü* parametresi. İşaretçileri depolar sınıflarındaki koleksiyon sınıflarının birinden, türetilmiş; Bu temel sınıfta belirttiğiniz *$base_class*. Diziler için kullanın `CObArray` veya `CPtrArray`. Listeler için kullanın `CObList` veya `CPtrList`.

Aslında, temel alan bir koleksiyon bildirdiğinizde söyleyin `CObList`, yeni bir sınıf yalnızca temel sınıfının üyelerini devralır, ancak bunu Ayrıca birkaç ek tür kullanımı uyumlu üye işlevler ve işleçler kapsülleyerek tür güvenliğini sağlamaya yardımcı bildirir temel sınıf üyelerinin çağrıları. Bu encapsulations tüm gerekli tür dönüştürme yönetin. Örneğin:

[!code-cpp[NVC_MFCCollections#5](../mfc/codesnippet/cpp/template-based-classes_5.cpp)]

İlk örnek, bir işaretçi türü belirlenmiş dizi bildirir `myArray`, türetilmiş `CObArray`. Dizi depolar ve işaretçileri döndürür `CPerson` nesneleri (burada `CPerson` öğesinden türetilmiş bir sınıf `CObject`). Tüm çağırabilirsiniz `CObArray` üye işlevini veya yeni tür kullanımı uyumlu çağırabilir `GetAt` ve `ElementAt` işlev veya tür kullanımı uyumlu kullanın **[]** işleci.

İkinci örnekte yazılan işaretçi listesini bildirir `myList`, türetilmiş `CPtrList`. Liste depolar ve işaretçileri döndürür `MY_STRUCT` nesneleri. Bir sınıfı temel alan `CPtrList` türetilmemiş nesnelerine işaretçiler depolamak için kullanılan `CObject`. `CTypedPtrList` tür kullanımı uyumlu üye işlevleri vardır: `GetHead`, `GetTail`, `RemoveHead`, `RemoveTail`, `GetNext`, `GetPrev`, ve `GetAt`.

###  <a name="_core_typed.2d.pointer_map_usage"></a> Yazılan işaretçi eşleme kullanımı

Yazılan işaretçi eşlem sınıfı [CTypedPtrMap](../mfc/reference/ctypedptrmap-class.md), üç parametre alır: *$base_class*, *anahtarı*, ve *değer*. *$Base_class* parametresi, yeni bir sınıf türetmek sınıf belirtir: `CMapPtrToWord`, `CMapPtrToPtr`, `CMapStringToPtr`, `CMapWordToPtr`, `CMapStringToOb`ve benzeri. *ANAHTAR* için benzer *anahtarı* içinde `CMap`: aramalar için kullanılan anahtar türünü belirtir. *DEĞER* için benzer *değer* içinde `CMap`: eşlem içinde depolan bir nesne türünü belirtir. Örneğin:

[!code-cpp[NVC_MFCCollections#6](../mfc/codesnippet/cpp/template-based-classes_6.cpp)]

Temel bir harita ilk örnektir `CMapPtrToPtr` — kullandığı `CString` işaretçileri eşlenen anahtarları `MY_STRUCT`. Tür açısından güvenli çağırarak depolanan bir işaretçi bakabilirsiniz `Lookup` üye işlevi. Kullanabileceğiniz **[]** depolanmış bir işaretçiyle aramak ve eklemek değilse işlecini bulunamadı. Ve tür kullanımı uyumlu kullanarak haritada yineleyebilirsiniz `GetNextAssoc` işlevi. Diğer üye işlevlerini sınıfı ayrıca, çağırabilirsiniz `CMapPtrToPtr`.

Temel bir harita ikinci örnektir `CMapStringToOb` — saklı işaretçileri eşlenen dize anahtarları kullanan `CMyObject` nesneleri. Önceki paragrafta açıklanan aynı tür kullanımı uyumlu üyeleri kullanabilir veya sınıfının üyelerini çağırabilirsiniz `CMapStringToOb`.

> [!NOTE]
>  Belirtirseniz bir **sınıfı** veya **yapı** yazın *değer* parametresi yerine bir işaretçi veya başvuru türü, sınıf veya yapı için bir kopya oluşturucusu olmalıdır.

Daha fazla bilgi için [tür kullanımı uyumlu koleksiyon yapma](../mfc/how-to-make-a-type-safe-collection.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Koleksiyonlar](../mfc/collections.md)

