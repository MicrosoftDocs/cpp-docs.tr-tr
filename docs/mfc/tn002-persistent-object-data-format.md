---
title: "TN002: Kalıcı nesne veri biçimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.data
dev_langs:
- C++
helpviewer_keywords:
- VERSIONABLE_SCHEMA macro [MFC]
- persistent object data
- CArchive class [MFC], support for persistent data
- persistent C++ objects [MFC]
- TN002
ms.assetid: 553fe01d-c587-4c8d-a181-3244a15c2be9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ca6a78f19b43ded59efb56b87f9fe3f44887a31a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tn002-persistent-object-data-format"></a>TN002: Kalıcı Nesne Veri Biçimi
Bu Not bir dosyada depolandığında destekleyen kalıcı C++ nesneleri ve nesne veri biçimi MFC yordamları açıklar. Bu, yalnızca sınıflarıyla uygulanır [declare_serıal](../mfc/reference/run-time-object-model-services.md#declare_serial) ve [ımplement_serıal](../mfc/reference/run-time-object-model-services.md#implement_serial) makroları.  
  
## <a name="the-problem"></a>Sorun  
 MFC uygulaması kalıcı veri için bir dosya bir tek bitişik bölümünde birçok nesne verilerini depolar. Nesnenin `Serialize` yöntemi nesnenin veri sıkıştırılmış bir ikili biçimine çevirir.  
  
 Tüm verilerin kaydedildiğinden emin aynı biçimde kullanarak uygulama garanti [CArchive sınıfı](../mfc/reference/carchive-class.md). Kullandığı bir `CArchive` nesnesi Çevirmen olarak. Bu nesne, oluşturulduğunda, çağrısı tamamlanana kadar saati devam ederse [CArchive::Close](../mfc/reference/carchive-class.md#close). Program içeren kapsamı çıktığında bu yöntem Programcı tarafından açıkça ya da örtük olarak yıkıcı tarafından çağrılabilir `CArchive`.  
  
 Bu Not uygulamasını açıklar `CArchive` üyeleri [CArchive::ReadObject](../mfc/reference/carchive-class.md#readobject) ve [CArchive::WriteObject](../mfc/reference/carchive-class.md#writeobject). Bu işlevler Arcobj.cpp ve ana uygulamasını için kodu bulacaksınız `CArchive` Arccore.cpp içinde. Kullanıcı kodu çağırmaz `ReadObject` ve `WriteObject` doğrudan. Bunun yerine, bu nesneler tarafından otomatik olarak oluşturulan sınıfa özgü tür kullanımı uyumlu ekleme ve çıkarma işleçleri tarafından kullanılan `DECLARE_SERIAL` ve `IMPLEMENT_SERIAL` makroları. Aşağıdaki kodda gösterildiği nasıl `WriteObject` ve `ReadObject` örtük olarak adlandırılır:  
  
```  
class CMyObject : public CObject  
{  
    DECLARE_SERIAL(CMyObject) 
};  
 
IMPLEMENT_SERIAL(CMyObj, CObject, 1)  
 
// example usage (ar is a CArchive&)  
CMyObject* pObj;  
CArchive& ar;  
ar <<pObj;        // calls ar.WriteObject(pObj)  
ar>> pObj;        // calls ar.ReadObject(RUNTIME_CLASS(CObj))  
```  
  
## <a name="saving-objects-to-the-store-carchivewriteobject"></a>Nesneler (CArchive::WriteObject) depoya kaydetme  
 Yöntem `CArchive::WriteObject` nesne yeniden oluşturmak için kullanılan üstbilgi verileri yazar. Bu veriler iki bölümden oluşur: türünü nesneyi ve nesnenin durumu. Bu yöntem, böylece yalnızca tek bir kopya işaretçileri (döngüsel işaretçileri dahil), bu nesneye sayısından bağımsız olarak kaydedilir, yazılmakta nesnenin kimliği sürdürmek için sorumludur.  
  
 (Ekleme) kaydetme ve geri yükleme (ayıklanan) nesneleri kullanır. birkaç "bildirim sabitleri üzerinde." Bu ikili biçimde depolanır ve Arşiv (Not "w" önekini 16 bit miktarları gösterir) için önemli bilgiler sağlayan değerleri şunlardır:  
  
|Etiket|Açıklama|  
|---------|-----------------|  
|wNullTag|NULL nesne işaretçileri (0) kullanılır.|  
|wNewClassTag|Aşağıdaki sınıf tanımına bu arşiv içeriği (-1) için yeni olduğunu gösterir.|  
|wOldClassTag|Okunan nesne sınıfı bu bağlamda (0x8000) görülen gösterir.|  
  
 Arşiv nesneleri depolarken tutan bir [CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) ( `m_pStoreMap`) depolanan bir nesneden eşleme 32-bit kalıcı tanımlayıcısına (PID) olduğu. PID benzersiz her nesne ve Arşiv bağlamında kaydedilen her benzersiz sınıf adı atanır. Bu PID 1'den başlayarak sıralı olarak verilir. Bu PID arşiv kapsamı dışında önemi yoktur ve özellikle, kaydı sayılar veya diğer kimlik öğeler ile karıştırılmamalıdır üzeresiniz.  
  
 İçinde `CArchive` sınıfı, PID 32-bit, ancak 0x7FFE büyük olmadıkça 16 bit yazıldığı. Büyük PID 32-bit PID tarafından izlenen 0x7FFF olarak yazılır. Önceki sürümlerde oluşturulan projeleri ile uyumluluk tutar.  
  
 Bir nesne (genellikle genel ekleme işlecini kullanarak) arşive kaydetmek için bir istek yapıldığında, bir NULL bir denetim gerçekleştirilir [CObject](../mfc/reference/cobject-class.md) işaretçi. İşaretçi NULL ise `wNullTag` arşiv akışa eklenir.  
  
 İşaretçi NULL olmayan ve seri hale getirilebilir (sınıfı bir `DECLARE_SERIAL` sınıfı), kod denetimleri `m_pStoreMap` nesne zaten kaydedilip kaydedilmediğini görmek için. Varsa, kodu 32 bit PID arşiv akışa Bu nesneyle ilişkili ekler.  
  
 Nesne önce kaydedilmemiş olan, dikkate alınması gereken iki olasılık vardır: hem nesnenin hem de tam (diğer bir deyişle, sınıfı) nesnenin türünü bu arşiv bağlamı için yeni olan ya da nesne zaten görülen bir tam türüdür. Türü görüldü olup olmadığını, belirlemek için kod sorguları `m_pStoreMap` için bir [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) eşleşen nesne `CRuntimeClass` kaydedilmesini nesneyle ilişkili nesne. Bir eşleşme varsa `WriteObject` temelinde bir etiket ekler `OR` , `wOldClassTag` ve bu dizin. Varsa `CRuntimeClass` bu arşiv bağlamı için yeni `WriteObject` o sınıfın yeni bir PID atar ve öncesinde arşiv ekler `wNewClassTag` değeri.  
  
 Bu sınıf tanımlayıcısı Arşiv kullanarak daha sonra eklenen `CRuntimeClass::Store` yöntemi. `CRuntimeClass::Store`sınıf (aşağıya bakın) şema sayısı ve sınıfın ASCII metin adını ekler. ASCII metin adı kullanımını arşiv benzersizliğini uygulamalarda garanti etmez olduğunu unutmayın. Bu nedenle, veri dosyalarınızı bozulmasını önlemek için etiket. Sınıf bilgileri ekleme arşiv nesnesine koyar `m_pStoreMap` ve çağırır `Serialize` sınıfı özgü verileri eklemek için yöntem. Nesnesine yerleştirme `m_pStoreMap` çağırmadan önce `Serialize` deposuna kaydedildi nesne birden çok kopyası engeller.  
  
 İlk çağıran (genellikle ağ nesneleri, kök) döndürülürken çağırmalısınız [CArchive::Close](../mfc/reference/carchive-class.md#close). Diğer yapmayı planlıyorsanız [CFile](../mfc/reference/cfile-class.md)işlemleri çağırmalıdır `CArchive` yöntemi [Flush](../mfc/reference/carchive-class.md#flush) arşiv bozulmasını önlemek için.  
  
> [!NOTE]
>  Bu uygulama 0x3FFFFFFE dizinlerini arşiv bağlam başına sabit sınırı uygular. Bu sayı benzersiz nesneler ve tek bir arşivde kaydedilebilmesi için sınıflar en büyük sayısını temsil eder, ancak tek bir disk dosyası arşiv bağlamları sınırsız sayıda olabilir.  
  
## <a name="loading-objects-from-the-store-carchivereadobject"></a>Nesneler (CArchive::ReadObject) deposundan yükleniyor  
 Nesneleri kullanır (ayıklanıyor) yükleme `CArchive::ReadObject` yöntemi ve, ters `WriteObject`. İle `WriteObject`, `ReadObject` kullanıcı kodu tarafından doğrudan; çağrılmaz kullanıcı kodu çağırır tür kullanımı uyumlu ayıklama işleci çağrı `ReadObject` beklenen ile `CRuntimeClass`. Bu ayıklama işlemi türü bütünlüğünü oluşturmasını sağlar.  
  
 Bu yana `WriteObject` uygulama atanan 1'den başlayarak, artan PID (0 önceden tanımlanmış NULL nesnesi olarak), `ReadObject` uygulama arşiv bağlamının durumunu korumak için bir dizi kullanabilirsiniz. Ne zaman bir PID okunur Mağaza'dan PID geçerli üst sınırdan daha büyükse `m_pLoadArray`, `ReadObject` yeni bir nesne (veya sınıf tanımına) izlediğini bilir.  
  
## <a name="schema-numbers"></a>Şema numaraları  
 Sınıfa atadığınız şema numarasını olduğunda `IMPLEMENT_SERIAL` sınıfının yöntemi ile karşılaşıldı, "" sınıf uygulamasını sürümüdür. Şema sınıfı uyarlamasını anlamına gelir, değil sayısı için belirli bir nesne (genellikle nesne sürüm olarak adlandırılır) kalıcı yapıldı.  
  
 Zaman içinde aynı sınıfın birkaç farklı uygulamaları korumak istiyorsanız, nesnenin gözden gibi şema artırma `Serialize` yöntemi uygulama yükleyebilir ve daha eski sürümleri kullanılarak depolanan nesneler kod yazmanıza etkinleştirecek uygulaması.  
  
 `CArchive::ReadObject` Yöntemi oluşturur bir [CArchiveException](../mfc/reference/carchiveexception-class.md) bellek sınıfının açıklamasında şema sayısı farklıdır kalıcı depo şeması numarasında karşılaştığında. Bu özel durumdan kurtarmak kolay değildir.  
  
 Kullanabileceğiniz `VERSIONABLE_SCHEMA` birlikte (bit düzeyinde `OR`) bu özel durumlar gelen tutmak için şema sürümü. Kullanarak `VERSIONABLE_SCHEMA`, kodunuzu uygun eylemi gerçekleştirin kendi `Serialize` yönteminden döndürülen değer denetleyerek işlevi [CArchive::GetObjectSchema](../mfc/reference/carchive-class.md#getobjectschema).  
  
## <a name="calling-serialize-directly"></a>Seri doğrudan çağırma  
 Genel nesne arşiv düzeni yükü çoğunda durumlarda `WriteObject` ve `ReadObject` gerekli değildir. Bu, verileri seri hale getirme, ortak durumda bir [CDocument](../mfc/reference/cdocument-class.md). Bu durumda, `Serialize` yöntemi `CDocument` değil extract veya INSERT işleçlerle doğrudan çağrılır. Belgesinin içeriğini de daha genel nesne arşiv düzeni kullanabilir.  
  
 Çağırma `Serialize` doğrudan aşağıdaki avantajları ve dezavantajları vardır:  
  
-   Hiçbir ek bayt önce arşiv veya nesne seri sonra eklenir. Bu yalnızca kaydedilmiş veri küçültür, ancak uygulamak sağlar `Serialize` herhangi işleyebilir yordamları dosya biçimleri.  
  
-   MFC olarak ayarlanmış şekilde `WriteObject` ve `ReadObject` uygulamaları ve ilgili koleksiyonları bağlı değil uygulamanıza başka bir amaç için daha fazla genel nesne arşiv düzeni gerekmedikçe.  
  
-   Kodunuzu eski şema noktalarından kurtarmak mevcut değil. Bu belge serileştirme kodunuzu kodlama şema sayı, dosya biçimi sürüm numaralarını veya hangi tanımlama sayılar sorumlu hale getirir, veri dosyalarınızı başlangıcında kullanın.  
  
-   Doğrudan çağrısıyla serileştirilmiş herhangi bir nesne `Serialize` değil kullanmalısınız `CArchive::GetObjectSchema` veya gerekir tanıtıcısı (UINT) -1 dönüş değeri belirten sürümü bilinmiyor.  
  
 Çünkü `Serialize` çağrılır doğrudan belgenize, genellikle kendi üst belge başvuruları arşivlemek için belgenin alt nesneler için yoktur. Bu nesneler bir işaretçi kendi kapsayıcı belge açıkça verilmelidir veya kullanmalısınız [CArchive::MapObject](../mfc/reference/carchive-class.md#mapobject) eşlemek için işlevi `CDocument` bu geri işaretçileri arşivlenmiş önce PID işaretçi.  
  
 Daha önce belirtildiği gibi sürüm kodlamak ve çağırdığınızda bilgileri kendiniz sınıf `Serialize` doğrudan, daha sonra hala eski dosyaları ile geriye dönük uyumluluk korurken biçimini olanak sağlar. `CArchive::SerializeClass` İşlevi çağrılamaz açıkça doğrudan bir nesneyi seri hale getirme önce ya da bir taban sınıf çağırmadan önce.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

