---
title: "Şablona dayalı sınıflar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2beb417bdedab6196ff6d27a387c4b61f083c4ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="template-based-classes"></a>Şablona Dayalı Sınıflar
Bu makalede sürüm 3.0 ve sonraki MFC'de tür kullanımı uyumlu şablona dayalı koleksiyon sınıfları açıklanmaktadır. Tür kullanımı uyumlu koleksiyonlar oluşturmak için bu şablonları kullanarak daha kolaydır ve tür güvenliği şablonlar temelinde değil koleksiyon sınıfları kullanmaktan daha verimli bir şekilde sağlanır.  
  
 MFC şablona dayalı koleksiyonlar iki kategorisi önceden belirler:  
  
-   [Basit dizi, liste ve eşleme sınıfları](#_core_using_simple_array.2c_.list.2c_.and_map_templates)  
  
     `CArray`, `CList`, `CMap`  
  
-   [Diziler, listeler ve haritaları yazılan işaretçiler](#_core_using_typed.2d.pointer_collection_templates)  
  
     `CTypedPtrArray`, `CTypedPtrList`, `CTypedPtrMap`  
  
 Basit koleksiyon sınıfları tüm sınıfından türetilen `CObject`, serileştirme, dinamik oluşturma ve diğer özelliklerini devralır `CObject`. Yazılan işaretçi koleksiyon sınıfları, türetilen sınıf belirtmenizi gerektirir —, şunlardan biri olmalıdır MFC tarafından gibi önceden tanımlanmış şablon Olmayandan işaretçi koleksiyonları `CPtrList` veya `CPtrArray`. Yeni koleksiyon sınıfınızın belirtilen taban sınıfından devralıyor ve tür güvenliği zorlamak için kapsüllenmiş çağrıları taban sınıf üyelerine yeni sınıfın üye işlevleri kullanın.  
  
 C++ şablonları hakkında daha fazla bilgi için bkz: [şablonları](../cpp/templates-cpp.md) içinde *C++ dil başvurusu*.  
  
##  <a name="_core_using_simple_array.2c_.list.2c_.and_map_templates"></a>Basit dizi, liste ve eşleme şablonları kullanma  
 Basit bir koleksiyonun şablonları kullanmak için ne tür veriler bu koleksiyonları depolayabilir ve koleksiyon bildirimlerinizde kullanmak üzere hangi parametreleri bilmeniz gerekir.  
  
###  <a name="_core_simple_array_and_list_usage"></a>Basit dizi ve liste kullanımı  
 Liste sınıfları ve Basit dizi [CArray](../mfc/reference/carray-class.md) ve [CList](../mfc/reference/clist-class.md), iki parametre alır: *türü* ve `ARG_TYPE`. Bu sınıfları, belirttiğiniz herhangi bir veri türü depolayabilir *türü* parametre:  
  
-   Temel bir C++ veri türleri, aşağıdaki gibi `int`, `char`, ve **float**  
  
-   C++ yapılar ve sınıflar  
  
-   Tanımladığınız diğer türleri  
  
 Kolaylık sağlamak ve verimlilik için kullanabileceğiniz `ARG_TYPE` parametre türü işlev bağımsız değişkenleri belirtin. Genellikle, belirttiğiniz `ARG_TYPE` adlı içinde türüne bir başvuru olarak *türü* parametresi. Örneğin:  
  
 [!code-cpp[NVC_MFCCollections#1](../mfc/codesnippet/cpp/template-based-classes_1.cpp)]  
  
 İlk örnek, bir dizi koleksiyonu bildirir `myArray`, içeren `int`s. Liste koleksiyonu ikinci örnek bildirir `myList`, depolar `CPerson` nesneleri. Koleksiyon sınıflarının belirli üye işlevleri, türü tarafından belirtilen bağımsız değişkenler almayan `ARG_TYPE` şablon parametresi. Örneğin, **Ekle** sınıfının üye işlevini `CArray` geçen bir `ARG_TYPE` bağımsız değişkeni:  
  
 [!code-cpp[NVC_MFCCollections#2](../mfc/codesnippet/cpp/template-based-classes_2.cpp)]  
  
###  <a name="_core_simple_map_usage"></a>Basit harita kullanımı  
 Basit harita sınıfı [CMap](../mfc/reference/cmap-class.md), dört parametre alır: *anahtar*, `ARG_KEY`, *değeri*, ve `ARG_VALUE`. Dizi ve liste sınıfları gibi herhangi bir veri türü eşleme sınıfları depolayabilirsiniz. Diziler ve dizin ve depoladıkları veri sipariş, listeler, aksine eşlemeleri anahtarları ve değerleri ilişkilendirmek: değerinin ilişkili anahtar belirterek bir eşlemesinde depolanan bir değer erişim. *Anahtar* Parametre eşlemesinde depolanan verilere erişmek için kullanılan anahtarları veri türünü belirtir. Varsa türünü *anahtar* yapısı ya da sınıfı, `ARG_KEY` parametredir genellikle belirtilen türüne bir başvuru *anahtar*. *Değeri* Parametre eşlemesinde depolanan öğeler türünü belirtir. Varsa türünü `ARG_VALUE` yapısı ya da sınıfı, `ARG_VALUE` parametredir genellikle belirtilen türüne bir başvuru *değeri*. Örneğin:  
  
 [!code-cpp[NVC_MFCCollections#3](../mfc/codesnippet/cpp/template-based-classes_3.cpp)]  
  
 İlk örnek depoları `MY_STRUCT` değerlerini, bunlara erişen `int` anahtarları ve erişilen döndürür `MY_STRUCT` başvuruya göre öğeleri. İkinci örnek depoları `CPerson` değerlerini, bunlara erişen `CString` anahtarları ve erişilen öğelere başvurular döndürür. Bu örnek, bir basit adres defteri kişileri son adına göre aramak, temsil edebilir.  
  
 Çünkü *anahtar* parametredir türü `CString` ve *KEY_TYPE* parametredir türü `LPCSTR`, anahtarları eşlemesinde türü öğeleri olarak depolanır `CString` içinde başvuruyor ancak gibi işlevleri `SetAt` türü işaretçileri aracılığıyla `LPCSTR`. Örneğin:  
  
 [!code-cpp[NVC_MFCCollections#4](../mfc/codesnippet/cpp/template-based-classes_4.cpp)]  
  
##  <a name="_core_using_typed.2d.pointer_collection_templates"></a>Yazılan işaretçi koleksiyonu şablonlarını kullanma  
 Yazılan işaretçi koleksiyonu şablonları kullanmak için hangi veri türlerini bu koleksiyonları depolayabilir ve koleksiyon bildirimlerinizde kullanmak üzere hangi parametreleri bilmeniz gerekir.  
  
###  <a name="_core_typed.2d.pointer_array_and_list_usage"></a>Yazılan işaretçi dizi ve liste kullanımı  
 Liste sınıfları ve yazılan işaretçi dizi [CTypedPtrArray](../mfc/reference/ctypedptrarray-class.md) ve [CTypedPtrList](../mfc/reference/ctypedptrlist-class.md), iki parametre alır: `BASE_CLASS` ve *türü*. Bu sınıfları, belirttiğiniz herhangi bir veri türü depolayabilir *türü* parametresi. Bunlar işaretçileri depolar şablon Olmayandan koleksiyon sınıflarının birinden türetilen; Bu taban sınıf içinde belirttiğiniz `BASE_CLASS`. Diziler için kullanın ya da `CObArray` veya `CPtrArray`. Listeler için kullanın ya da `CObList` veya `CPtrList`.  
  
 Aslında, temel alan bir koleksiyon bildirirken söyleyin `CObList`, yeni sınıfın yalnızca devralınabilir. taban sınıfı üyeleri devralır, ancak bu da ek tür kullanımı uyumlu üye sayısı işlevleri ve tür güvenliği kapsülleyerek sağlamaya yardımcı işleçleri bildirir taban sınıf üyelerine çağırır. Bu encapsulations tüm gerekli tür dönüştürme yönetin. Örneğin:  
  
 [!code-cpp[NVC_MFCCollections#5](../mfc/codesnippet/cpp/template-based-classes_5.cpp)]  
  
 İlk örnek bir yazılan işaretçi dizi tanımlarken `myArray`, türetilmiş `CObArray`. Dizi depolar ve işaretçiler döndürür `CPerson` nesneleri (burada `CPerson` öğesinden türetilmiş bir sınıf `CObject`). Herhangi bir çağrı `CObArray` üye işlevini veya yeni tür kullanımı uyumlu çağırabilir `GetAt` ve `ElementAt` işlevleri veya tür kullanımı uyumlu kullanın **[]** işleci.  
  
 İkinci örnekte yazılan işaretçi listesini bildirir `myList`, türetilmiş `CPtrList`. Liste depolar ve işaretçiler döndürür `MY_STRUCT` nesneleri. Bir sınıfın temel alarak `CPtrList` öğesinden türetilmemiş nesnelerine işaretçiler depolamak için kullanılan `CObject`. `CTypedPtrList`tür kullanımı uyumlu üye işlevleri sayısı: `GetHead`, `GetTail`, `RemoveHead`, `RemoveTail`, `GetNext`, `GetPrev`, ve `GetAt`.  
  
###  <a name="_core_typed.2d.pointer_map_usage"></a>Yazılan işaretçi Haritası kullanım  
 Yazılan işaretçi harita sınıfı [CTypedPtrMap](../mfc/reference/ctypedptrmap-class.md), üç parametre alır: `BASE_CLASS`, *anahtar*, ve *değeri*. `BASE_CLASS` Parametresi, yeni sınıf Türetmenin sınıfı belirtir: `CMapPtrToWord`, `CMapPtrToPtr`, `CMapStringToPtr`, `CMapWordToPtr`, `CMapStringToOb`ve benzeri. *ANAHTAR* için benzer *anahtar* içinde `CMap`: aramalar için kullanılan anahtar türünü belirtir. *DEĞER* için benzer *değeri* içinde `CMap`: eşlemesinde depolanan nesne türünü belirtir. Örneğin:  
  
 [!code-cpp[NVC_MFCCollections#6](../mfc/codesnippet/cpp/template-based-classes_6.cpp)]  
  
 İlk örnek dayalı bir eşleme olduğundan **CMapPtrToPt**r — kullandığı `CString` işaretçileri eşlenmiş anahtarları `MY_STRUCT`. Tür kullanımı uyumlu çağırarak depolanan bir işaretçi bakabilirsiniz `Lookup` üye işlevi. Kullanabileceğiniz **[]** depolanan bir işaretçi arayın ve bunu ekleyin değilse bulunan için işleci. Ve tür kullanımı uyumlu kullanarak harita yineleyebilirsiniz `GetNextAssoc` işlevi. Diğer üye sınıfı işlevleri çağırabilir `CMapPtrToPtr`.  
  
 İkinci örneğe göre bir eşleme olduğundan **CMapStringToO**b — saklı işaretçiler eşlenmiş dize anahtarları kullanan `CMyObject` nesneleri. Önceki paragrafta açıklanan aynı tür kullanımı uyumlu üyeleri kullanabilir ya da sınıfı üyeleri çağırabilirsiniz `CMapStringToOb`.  
  
> [!NOTE]
>  Belirtirseniz bir **sınıfı** veya `struct` yazın *değeri* parametresi yerine bir işaretçi veya başvuru türü, sınıf veya yapı için kopya Oluşturucu olması gerekir.  
  
 Daha fazla bilgi için bkz: [tür kullanımı uyumlu koleksiyon yapma](../mfc/how-to-make-a-type-safe-collection.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koleksiyonlar](../mfc/collections.md)

