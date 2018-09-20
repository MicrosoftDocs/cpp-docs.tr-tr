---
title: 'TN002: Kalıcı nesne veri biçimi | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a23ade068fa0d71715a76d3a99a393cc5458947c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399970"
---
# <a name="tn002-persistent-object-data-format"></a>TN002: Kalıcı Nesne Veri Biçimi

Bu Not, bir dosyada depolandığında, kalıcı C++ nesneleri ve nesne veri biçimi destekleyen MFC yordamları açıklar. Bu yalnızca sınıflarıyla geçerlidir [declare_serıal](../mfc/reference/run-time-object-model-services.md#declare_serial) ve [ımplement_serıal](../mfc/reference/run-time-object-model-services.md#implement_serial) makroları.

## <a name="the-problem"></a>Sorun

Kalıcı veri için MFC uygulaması, bir dosya bitişik tek bir parçası birçok nesne verilerini depolar. Nesnenin `Serialize` yöntemi nesnenin veri sıkıştırılmış bir ikili biçimine çevirir.

Tüm verileri kaydedilir, aynı biçimde kullanarak uygulama garanti [CArchive sınıfı](../mfc/reference/carchive-class.md). Bunu kullanan bir `CArchive` bir translator olarak nesnesi. Bu nesne, çağırana kadar oluşturulduğu zamandan devam ederse [CArchive::Close](../mfc/reference/carchive-class.md#close). İçeren kapsamı program çıkış yaptığı andaki bu yöntem programcısı tarafından açıkça veya dolaylı olarak yok edici tarafından çağrılabilir `CArchive`.

Bu Not uygulamasını açıklar `CArchive` üyeleri [CArchive::ReadObject](../mfc/reference/carchive-class.md#readobject) ve [CArchive::WriteObject](../mfc/reference/carchive-class.md#writeobject). Bu işlevler Arcobj.cpp ve ana uygulama için kod bulabilirsiniz `CArchive` Arccore.cpp içinde. Kullanıcı kodu çağırmaz `ReadObject` ve `WriteObject` doğrudan. Bunun yerine, bu nesneler declare_serıal ve ımplement_serıal makroları tarafından otomatik olarak oluşturulan sınıfa özgü tür kullanımı uyumlu ekleme ve çıkarma işleçleri tarafından kullanılır. Aşağıdaki kodda gösterildiği nasıl `WriteObject` ve `ReadObject` örtük olarak çağırılamaz:

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

## <a name="saving-objects-to-the-store-carchivewriteobject"></a>Nesneleri Store (CArchive::WriteObject) kaydediliyor

Yöntem `CArchive::WriteObject` nesnesini yeniden oluşturmak için kullanılan üstbilgi verileri yazar. Bu veriler iki bölümden oluşur: türü nesneyi ve nesnenin durumu. Bu yöntem, böylece (döngüsel işaretçileri dahil), nesne işaretçileri sayısından bağımsız olarak yalnızca tek bir kopyası kaydedilir, yazılmakta olan nesne kimliği bakımından sorumludur.

(Eklemek) kaydetme ve (ayıklanan) nesneleri geri yüklemek, çeşitli "bildirim sabitleri üzerinde." dayanır İkili dosyada depolanır ve Arşiv (16-bit miktarlar "w" ön ekini belirtir. Not) için önemli bilgiler sağlayan değerleri şunlardır:

|Etiket|Açıklama|
|---------|-----------------|
|wNullTag|NULL nesne işaretçileri (0) için kullanılır.|
|wNewClassTag|Aşağıdaki sınıf tanımı bu arşiv içeriği (-1) yeni olduğunu gösterir.|
|wOldClassTag|Okunan nesne sınıfı bu bağlamda (0x8000) görüldü gösterir.|

Arşiv nesneleri depolarken, tutan bir [CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) ( *m_pStoreMap*) 32-bit kalıcı tanımlayıcısını (PID) depolanan nesne bir eşleme olduğu. Her benzersiz nesne ve Arşiv bağlamında kaydedilen her benzersiz sınıf adı için bir PID atanır. Bu PIDs 1'den başlayarak sıralı olarak verilir. Bu PIDs arşiv kapsamı dışında önemi yoktur ve özellikle, kayıt sayılarını veya diğer kimlik öğeleri ile karıştırılmamalıdır üzeresiniz.

İçinde `CArchive` sınıfı PIDs 32-bit, ancak 0x7FFE daha büyük olmadıkları sürece 16-bit yazıldığı. Büyük PIDs 32-bit PID tarafından izlenen 0x7FFF olarak yazılır. Bu, önceki sürümlerde oluşturulmuş projeler ile uyumluluk tutar.

Bir nesne için bir arşiv (genellikle genel ekleme işleci kullanılarak) kaydetmek için bir istek yapıldığında, bir NULL bir onay yapılır [CObject](../mfc/reference/cobject-class.md) işaretçi. NULL işaretçi ise *wNullTag* arşiv akışa eklenir.

İşaretçisi NULL değil ve seri hale getirilebilir (sınıf bir `DECLARE_SERIAL` sınıfı), kod denetimleri *m_pStoreMap* nesne zaten kaydedilip kaydedilmediğini görmek için. Varsa, kodu arşiv akışa o nesne ile ilişkili 32-bit PID ekler.

Önce nesne kaydedilmedi, dikkate alınması gereken iki olasılık vardır: hem nesne hem de tam (diğer bir deyişle, sınıfı) nesnenin türünü bu arşiv içeriği için yeni veya zaten görüldü tam bir tür olan nesnesidir. Türü görüldü olup olmadığını, belirlemek için kod sorguları *m_pStoreMap* için bir [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) eşleşen nesne `CRuntimeClass` kaydedilmesini nesnesiyle ilişkili nesne. Bir eşleşme varsa `WriteObject` temelinde olan bir etiketi ekler `OR` , *wOldClassTag* ve bu dizini. Varsa `CRuntimeClass` bu arşiv içeriği için yeni `WriteObject` koyarak arşiv ekler ve o sınıfın yeni bir PID atar *wNewClassTag* değeri.

Arşiv kullanarak bu sınıf için bir tanımlayıcı eklenir `CRuntimeClass::Store` yöntemi. `CRuntimeClass::Store` ' % s'sınıfı (aşağıya bakın) şema sayısı ve sınıfın ASCII metin adını ekler. ASCII metin adı kullanımını uygulamalarda arşiv benzersizliğini garantilemez unutmayın. Bu nedenle, bozulmasını önlemek için veri dosyalarını etiketlemelisiniz. Sınıf Bilgisi öğesinin eklenmesi, arşiv nesnesine koyar *m_pStoreMap* ve `Serialize` sınıfa özgü verileri eklemek için yöntemi. Nesnesine yerleştirme *m_pStoreMap* çağırmadan önce `Serialize` depoya kaydedilmiş nesne birden çok kopyasını engeller.

İlk çağıranın (genellikle kök ağ nesnelerini) döndürürken çağırmalısınız [CArchive::Close](../mfc/reference/carchive-class.md#close). Diğer yapmayı planlıyorsanız [CFile](../mfc/reference/cfile-class.md)işlemleri çağırmalıdır `CArchive` yöntemi [Temizleme](../mfc/reference/carchive-class.md#flush) arşiv bozulmasını önlemek için.

> [!NOTE]
>  Bu uygulama 0x3FFFFFFE dizinlerini arşiv bağlam başına sabit bir sınır uygular. Bu sayı, maksimum sayısı benzersiz nesneleri ve tek bir Arşiv'de kaydedilebilir sınıfları temsil eder, ancak tek disk dosyası arşiv bağlamları sınırsız sayıda olabilir.

## <a name="loading-objects-from-the-store-carchivereadobject"></a>' % S'Store (CArchive::ReadObject) nesnelerden yükleniyor

Nesneleri kullanır (ayıklanıyor) yüklenirken `CArchive::ReadObject` yöntemi ve listesiyse, `WriteObject`. Olduğu gibi `WriteObject`, `ReadObject` kullanıcı kodu tarafından doğrudan; çağrılmaz kullanıcı kodu çağıran tür kullanımı uyumlu ayıklama işleci çağırmalıdır `ReadObject` beklenen ile `CRuntimeClass`. Bu ayıklama işlemi türü bütünlüğünü oluşturmasını sağlar.

Bu yana `WriteObject` uygulama 1'den başlayarak, artan PIDs atanan (0 önceden tanımlı olarak NULL nesne) `ReadObject` uygulama arşiv bağlamının durumunu korumak üzere bir dizi kullanabilirsiniz. Ne zaman bir PID okuma Mağaza'dan PID geçerli üst sınırdan büyük olması durumunda *m_pLoadArray*, `ReadObject` yeni nesne (veya sınıf açıklaması) izlediğini bilir.

## <a name="schema-numbers"></a>Şema numaraları

Sınıfa atadığınız şema numarasını olduğunda `IMPLEMENT_SERIAL` sınıfının yöntemi karşılaşılırsa, sınıf uygulamasının "Sürüm". Değil sayısı için belirli bir nesne (genellikle nesne sürümü adlandırılır) kalıcı duruma getirildi, sınıfın uygulaması için şema'anlamına gelir.

Zaman içinde aynı sınıfın birkaç farklı uygulamalarını sağlamak istiyorsanız, nesnenizin gözden geçirme gibi şema artan `Serialize` yöntem uygulaması, eski sürümleri kullanılarak depolanan nesnelere yükleyebilir ve kod yazmanıza olanak etkinleştirilir uygulaması.

`CArchive::ReadObject` Yöntemi oluşturur bir [CArchiveException](../mfc/reference/carchiveexception-class.md) bellek sınıf tanımı şema sayısından farklı kalıcı depoya bir şema sayı karşılaştığında. Bu özel durumdan kurtarmak kolay değildir.

Kullanabileceğiniz `VERSIONABLE_SCHEMA` birlikte (bit düzeyinde **veya**) öğesinden oluşturulan bu özel durumun tutmak için şema sürümü. Kullanarak `VERSIONABLE_SCHEMA`, kodunuzu uygun eylemi gerçekleştirin kendi `Serialize` işlevi dönüş değerini denetleyerek [CArchive::GetObjectSchema](../mfc/reference/carchive-class.md#getobjectschema).

## <a name="calling-serialize-directly"></a>Serileştirilecek doğrudan çağırma

Çoğu durumda genel nesne arşiv düzeni yükü `WriteObject` ve `ReadObject` gerekli değildir. Verileri seri hale getirme, sık karşılaşılan durum budur bir [CDocument](../mfc/reference/cdocument-class.md). Bu durumda, `Serialize` yöntemi `CDocument` değil ayıklama veya INSERT işleçleri ile doğrudan çağrılır. Belgenin içeriğini sırayla daha genel bir nesne arşiv düzeni kullanabilir.

Çağırma `Serialize` doğrudan aşağıdaki avantajları ve dezavantajları vardır:

- Hiçbir ek bayt arşivlemeden önce veya sonra nesnenin serileştirildiği eklenir. Bu yalnızca kaydedilen verilerin daha küçük olmasını sağlar, ancak olanak tanır `Serialize` herhangi işleme rutinleri dosya biçimleri.

- MFC ayarlanan böylece `WriteObject` ve `ReadObject` uygulamaları ve ilgili koleksiyonlarda bağlı değil uygulamanıza başka bir amaç için daha genel bir nesne arşiv düzeni gerekmedikçe.

- Kodunuzu eski şema noktalarından kurtarmak yok. Bu belge serileştirme kodunuzu kodlama şema sayı, dosya biçimi sürüm numaraları veya hangi tanımlama numaraları sorumlu hale getirir, veri dosyalarını başlangıcında kullanın.

- Doğrudan çağrı ile seri herhangi bir nesne `Serialize` değil kullanmalısınız `CArchive::GetObjectSchema` veya gerekir tanıtıcısı (birim) -1 değerinin döndürüldüğünü belirten sürümü bilinmiyor.

Çünkü `Serialize` çağrılır, belge üzerinde doğrudan genellikle mümkün kendi üst belge başvuruları arşivlemek için belgenin alt nesneler için değildir. Bu nesneler bir işaretçi, kapsayıcı belgeye açıkça verilmelidir veya kullanmalısınız [CArchive::MapObject](../mfc/reference/carchive-class.md#mapobject) eşlemek için işlev `CDocument` bu geri işaretçileri arşivlenmiş önce bir PID işaretçisi.

Daha önce belirtildiği gibi sürüm kodlama ve çağırdığınızda bilgileri kendiniz sınıfı `Serialize` doğrudan, daha sonra hala eski dosyaları ile geriye dönük uyumluluğu koruyarak biçimini imkan tanır. `CArchive::SerializeClass` İşlevi çağrılabilir açıkça önce doğrudan bir nesneyi serileştirmek veya bir temel sınıfı çağırmadan önce.

## <a name="see-also"></a>Ayrıca Bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

