---
title: Bir koleksiyonun tüm üyelerine erişme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, collections
- enumerations [MFC]
- enumerating collections [MFC]
- collections [MFC], accessing
- collection classes [MFC]
- ', '
- ', '
- ', '
- ', '
- ', '
- ', '
- ', '
ms.assetid: 7bbae518-062e-4393-81f9-b22abd2e5f59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf25b84c4ee9808210d2dbf2f5115319a517c71b
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931944"
---
# <a name="accessing-all-members-of-a-collection"></a>Bir Koleksiyonun Tüm Üyelerine Erişme
MFC dizi koleksiyon sınıfları — hem şablona dayalı ve — dizinleri öğelerini erişmek için kullanın. MFC liste ve eşleme koleksiyon sınıfları — hem şablona dayalı ve — türünün bir göstergesi kullanın **konumu** koleksiyonundaki belirli bir konuma açıklamak için. Bu koleksiyonun bir veya daha fazla üyelerini erişmek için ilk konumu göstergesi başlatmak sürekli olarak o konumdan koleksiyonuna geçirmek ve sonraki öğeye dönmek için isteyin. Koleksiyon yinelemeyi ilerleme durumu ile ilgili durum bilgilerini korumak için sorumlu değildir. Bu bilgiler konumu göstergesi tutulur. Ancak, belirli bir konuma göz önüne alındığında, koleksiyon sonraki öğeye döndürmek için sorumludur.  
  
 Aşağıdaki yordamlar MFC ile sağlanan koleksiyonları üç ana tür üzerinden yineleme gösterir:  
  
-   [Bir dizi yineleme](#_core_to_iterate_an_array)  
  
-   [Bir liste yineleme](#_core_to_iterate_a_list)  
  
-   [Bir harita yineleme](#_core_to_iterate_a_map)  
  
### <a name="_core_to_iterate_an_array"></a> Bir dizi yinelemek için  
  
1.  İle sıralı dizin numaralarını kullanın `GetAt` üye fonksiyonu:  
  
     [!code-cpp[NVC_MFCCollections#12](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_1.cpp)]  
  
     Bu örnek işaretçileri içeren yazılan işaretçi bir dizi kullanır `CPerson` nesneleri. Dizi sınıfından türetilen `CObArray`, önceden tanımlı bir şablon Olmayandan sınıfları. `GetAt` bir işaretçi döndüren bir `CPerson` nesnesi. Yazılan işaretçi koleksiyon sınıfları için — diziler veya listeleri — ilk parametresi, temel sınıf; belirtir. İkinci parametre depolamak için türünü belirtir.  
  
     `CTypedPtrArray` Sınıfı ayrıca aşırı **[]** işleci böylece her zamanki dizi erişim öğelerini dizi alt simge sözdizimine kullanabilirsiniz. Alternatif gövdesini deyiminde **için** yukarıdaki döngüsü  
  
     [!code-cpp[NVC_MFCCollections#13](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_2.cpp)]  
  
     Bu işleci hem de mevcut **const** ve olmayan-**const** sürümleri. **Const** için çağrılan sürüm **const** dizileri, yalnızca sağ tarafta Atama ifadesinin görünebilir.  
  
### <a name="_core_to_iterate_a_list"></a> Bir liste yinelemek için  
  
1.  Üye işlevlerini `GetHeadPosition` ve `GetNext` yolunuzu listesi kullanılarak çalışmak için:  
  
     [!code-cpp[NVC_MFCCollections#14](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_3.cpp)]  
  
     Bu örnek, işaretçileri içeren için yazılan işaretçi listesini kullanır. `CPerson` nesneleri. Liste bildirimi yordamda dizi benzer [bir dizi yinelemek için](#_core_to_iterate_an_array) sınıfından türetilen ancak `CObList`. `GetNext` bir işaretçi döndüren bir `CPerson` nesnesi.  
  
### <a name="_core_to_iterate_a_map"></a> Bir harita yinelemek için  
  
1.  Kullanım `GetStartPosition` harita başlangıcına almak için ve `GetNextAssoc` art arda sonraki anahtar ve değer eşlemesinden aşağıdaki örnekte gösterildiği gibi almak için:  
  
     [!code-cpp[NVC_MFCCollections#15](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_4.cpp)]  
  
     Bu örnek bir basit harita şablonunu kullanır (yazılan işaretçi koleksiyonu yerine) kullanan `CString` anahtarları ve işaretçiler depolar `CPerson` nesneleri. Erişim işlevleri gibi kullandığınızda `GetNextAssoc`, sınıf işaretçileri sağlar `CPerson` nesneleri. Şablon Olmayandan eşleme koleksiyonları birini yerine kullanırsanız döndürülen atamalısınız `CObject` gösteren bir işaretçi işaretçi bir `CPerson`.  
  
    > [!NOTE]
    >  Şablon Olmayandan maps için bir başvuru derleyici gerektiren bir `CObject` son parametresindeki işaretçi `GetNextAssoc`. Giriş, sonraki örnekte gösterildiği gibi bu türü işaretçileri dönüştürmeniz gerekir.  
  
     Şablonu çözümü daha kolaydır ve daha iyi türü güvenliğini sağlamaya yardımcı olur. Şablon Olmayandan kodu daha karmaşık aynıdır burada görebilirsiniz:  
  
     [!code-cpp[NVC_MFCCollections#16](../mfc/codesnippet/cpp/accessing-all-members-of-a-collection_5.cpp)]  
  
 Daha fazla bilgi için bkz: [CObject koleksiyonundaki tüm nesneleri silme](../mfc/deleting-all-objects-in-a-cobject-collection.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Koleksiyonlar](../mfc/collections.md)

