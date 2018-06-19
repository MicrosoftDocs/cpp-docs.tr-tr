---
title: 'Nasıl yapılır: tür kullanımı uyumlu koleksiyon yapma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- type-safe collections [MFC]
- serializing collection-class elements [MFC]
- collection classes [MFC], type safety
- SerializeElements function [MFC]
- collection classes [MFC], template-based
- serialization [MFC], collection classes
- collection classes [MFC], deriving from nontemplate
ms.assetid: 7230b2db-4283-4083-b098-eb231bf5b89e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bcd1fbce9e6dda649da8fe2e53fc7dc70db1da33
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354445"
---
# <a name="how-to-make-a-type-safe-collection"></a>Nasıl yapılır: Tür Kullanımı Uyumlu Koleksiyon Yapma
Bu makalede, kendi veri türleri için tür kullanımı uyumlu koleksiyonlar nasıl oluşturulacağı açıklanmaktadır. Konular şunlardır:  
  
-   [Şablona dayalı sınıflar için tür güvenliği kullanma](#_core_using_template.2d.based_classes_for_type_safety)  
  
-   [Yardımcı işlevleri uygulama](#_core_implementing_helper_functions)  
  
-   [Şablon Olmayandan koleksiyon sınıfları kullanma](#_core_using_nontemplate_collection_classes)  
  
 Microsoft Foundation Class Kitaplığı C++ şablonlar temelinde önceden tanımlanmış tür kullanımı uyumlu koleksiyonlar sağlar. Şablonları olduklarından bu sınıflarının tür güvenliği ve tür atama ve bu amaç için bir şablon Olmayandan sınıfı kullanarak söz konusu diğer ek iş olmadan kullanım kolaylığı sağlamaya yardımcı. MFC örnek [TOPLAMAK](../visual-cpp-samples.md) şablona dayalı koleksiyon sınıfları bir MFC uygulamasında kullanımını gösterir. Genel olarak, bu sınıfları yeni Koleksiyonlar kod yazmak istediğiniz zaman kullanın.  
  
##  <a name="_core_using_template.2d.based_classes_for_type_safety"></a> Şablona dayalı sınıflar için tür güvenliği kullanma  
  
#### <a name="to-use-template-based-classes"></a>Şablona dayalı sınıflar kullanmak için  
  
1.  Koleksiyon sınıfı türünde bir değişken bildirin. Örneğin:  
  
     [!code-cpp[NVC_MFCCollections#7](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_1.cpp)]  
  
2.  Üye işlevlerini koleksiyon nesnesinin çağırın. Örneğin:  
  
     [!code-cpp[NVC_MFCCollections#8](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_2.cpp)]  
  
3.  Gerekirse, uygulama [yardımcı işlevleri](../mfc/reference/collection-class-helpers.md) ve [SerializeElements](../mfc/reference/collection-class-helpers.md#serializeelements). Bu işlevler uygulama hakkında daha fazla bilgi için bkz: [uygulama yardımcı işlevleri](#_core_implementing_helper_functions).  
  
 Bu örnek, tamsayı listesi bildirimi gösterir. Adım 1'de ilk parametre listesi öğeleri olarak depolanan veriler türüdür. İkinci parametre nasıl verileri için geçirilen ve koleksiyon sınıfının üye işlevleri gibi döndürülen belirtir **Ekle** ve `GetAt`.  
  
##  <a name="_core_implementing_helper_functions"></a> Yardımcı işlevleri uygulama  
 Şablona dayalı koleksiyon sınıfları `CArray`, `CList`, ve `CMap` türetilen koleksiyonu sınıfınız için gerektiği gibi özelleştirebileceğiniz beş genel yardımcı işlevleri kullanın. Bu yardımcı işlevleri hakkında daha fazla bilgi için bkz: [koleksiyon sınıfı Yardımcıları](../mfc/reference/collection-class-helpers.md) içinde *MFC başvurusu*. Seri hale getirme fonksiyonunun uygulanması şablona dayalı koleksiyon sınıfları birçok kullanım için gereklidir.  
  
###  <a name="_core_serializing_elements"></a> Öğelerini serileştirme  
 `CArray`, `CList`, Ve `CMap` sınıfları çağrısı `SerializeElements` koleksiyon öğeleri depolamak veya bunları arşivden okuyun.  
  
 Varsayılan uygulaması `SerializeElements` yardımcı işlevini arşive nesnelerden Bitsel yazma mu veya bit mi nesneleri depolanmış bağlı olarak bu nesnelere arşivden okuma veya arşivden alınamıyor. Geçersiz kılma `SerializeElements` bu eylemi uygun değilse.  
  
 Koleksiyonunuz türetilmiş nesneleri depoluyorsa `CObject` ve kullandığınız `IMPLEMENT_SERIAL` makrosu koleksiyon öğesi sınıfı uygulamasında gerçekleştirebileceğiniz, yerleşik seri hale getirme işlevselliğinden `CArchive` ve `CObject`:  
  
 [!code-cpp[NVC_MFCCollections#9](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_3.cpp)]  
  
 Aşırı yüklenmiş ekleme işleçlerini `CArchive` çağrısı `CObject::Serialize` (veya bu işlevi bir geçersiz kılma) her **CPerson** nesnesi.  
  
##  <a name="_core_using_nontemplate_collection_classes"></a> Şablon Olmayandan koleksiyon sınıfları kullanma  
 MFC koleksiyon sınıfları MFC sürüm 1.0 ile sunulan de destekler. Bu sınıfların şablonlar temelinde değil. Desteklenen türlerden biri verileri içerecek şekilde kullanılabilmesi için `CObject*`, **UINT**, `DWORD`, ve `CString`. Bu önceden tanımlanmış koleksiyonları kullanabilirsiniz (gibi `CObList`) türetilen nesne koleksiyonları tutmak için `CObject`. MFC ayrıca ilkel türler gibi tutmak için önceden tanımlanmış diğer koleksiyonları sağlar **UINT** ve void işaretçileri (`void`*). Genel olarak, ancak genellikle daha belirli bir sınıf ve türevleri nesnelerin tutmak için kendi tür kullanımı uyumlu koleksiyonlar tanımlamak yararlıdır. Bunun yapılması koleksiyon sınıflarının değil şablonlar temelinde şablona dayalı sınıflar kullanmaktan daha fazla iş olduğuna dikkat edin.  
  
 Şablon Olmayandan koleksiyonlarla tür kullanımı uyumlu koleksiyonlar oluşturmanın iki yolu vardır:  
  
1.  Şablon Olmayandan koleksiyonları gerekirse tür atama ile kullanın. Bu daha kolay bir yaklaşımdır.  
  
2.  Öğesinden türetilen ve şablon Olmayandan tür kullanımı uyumlu koleksiyon genişletebilirsiniz.  
  
#### <a name="to-use-the-nontemplate-collections-with-type-casting"></a>Şablon Olmayandan koleksiyonları tür atama ile kullanmak için  
  
1.  Şablon Olmayandan sınıflarından gibi kullandığınız `CWordArray`, doğrudan.  
  
     Örneğin, oluşturabileceğiniz bir `CWordArray` ve herhangi bir 32 bit değeri ekleyin, sonra bunları almak. Yapmak için başka bir şey yoktur. Yalnızca önceden tanımlanmış işlevini kullanın.  
  
     Önceden tanımlanmış bir koleksiyon gibi kullanabilir `CObList`, türetilmiş herhangi bir nesne tutmak için `CObject`. A `CObList` koleksiyonu işaretçileri tutmak için tanımlanmış `CObject`. Listeden bir nesne aldığınızda, bu yana uygun türde sonucu cast gerekebilir `CObList` işlevleri dönmek için işaretçiler `CObject`. Örneğin, depolama, `CPerson` nesnelerini bir `CObList` koleksiyonu, elinizde bir işaretçi olarak alınan öğe dönüştürmek bir `CPerson` nesnesi. Aşağıdaki örnek kullanan bir `CObList` tutmak için koleksiyon `CPerson` nesneler:  
  
     [!code-cpp[NVC_MFCCollections#10](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_4.cpp)]  
  
     Önceden tanımlanmış koleksiyon türü kullanarak ve gerektiğinde atama bu tekniği çoğu, koleksiyon gereksinimlerinize için yeterli olabilir. Daha fazla işlevsellik ya da daha fazla tür güvenliği gerekirse, şablona dayalı bir sınıf kullanma veya bir sonraki yordamı izleyin.  
  
#### <a name="to-derive-and-extend-a-nontemplate-type-safe-collection"></a>Türetirseniz ve şablon Olmayandan tür kullanımı uyumlu koleksiyon genişletmek için  
  
1.  Kendi koleksiyon sınıfı önceden tanımlanmış şablon Olmayandan sınıflarının birinden türetilir.  
  
     Sınıfınıza türetilen bir tür kullanımı uyumlu arabirimi var olan işlevler sağlamak için tür kullanımı uyumlu sarmalayıcı işlevleri ekleyebilirsiniz.  
  
     Örneğin, bir listeden türetilmiş `CObList` tutmak için `CPerson` nesneleri sarmalayıcı işlevleri eklemek `AddHeadPerson` ve `GetHeadPerson`, aşağıda gösterildiği gibi.  
  
     [!code-cpp[NVC_MFCCollections#11](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_5.h)]  
  
     Bu sarmalayıcı işlevleri eklemek ve almak için bir tür kullanımı uyumlu şekilde sağlayan `CPerson` türetilmiş listeden nesneleri. İçin gördüğünüz `GetHeadPerson` işlevi, yalnızca tür atama şifrelenmiş.  
  
     Yalnızca var olan işlevselliği tür kullanımı uyumlu sarmalayıcıları kaydırma yerine koleksiyon yeteneklerini yeni işlevlerini tanımlama yeni işlevsellik de ekleyebilirsiniz. Örneğin, makale [CObject koleksiyonundaki tüm nesneleri silme](../mfc/deleting-all-objects-in-a-cobject-collection.md) listede yer alan tüm nesneleri silmek için bir işlev açıklar. Bu işlevi türetilmiş sınıf üye işlevi eklenemedi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koleksiyonlar](../mfc/collections.md)

