---
title: 'TN002: Kalıcı Nesne Veri Biçimi'
ms.date: 11/04/2016
helpviewer_keywords:
- VERSIONABLE_SCHEMA macro [MFC]
- persistent object data
- CArchive class [MFC], support for persistent data
- persistent C++ objects [MFC]
- TN002
ms.assetid: 553fe01d-c587-4c8d-a181-3244a15c2be9
ms.openlocfilehash: f65a7b7afcf6bd832c9c23560bb29374038fae1b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370451"
---
# <a name="tn002-persistent-object-data-format"></a>TN002: Kalıcı Nesne Veri Biçimi

Bu not, kalıcı C++ nesnelerini destekleyen MFC yordamlarını ve bir dosyada depolandığında nesne verilerinin biçimini açıklar. Bu yalnızca [DECLARE_SERIAL](../mfc/reference/run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) makroları olan sınıflar için geçerlidir.

## <a name="the-problem"></a>Sorun

Kalıcı veriler için MFC uygulaması, birçok nesneiçin verileri bir dosyanın tek bir bitişik bölümünde depolar. Nesnenin `Serialize` yöntemi, nesnenin verilerini kompakt ikili biçime çevirir.

Uygulama, [CArchive Class](../mfc/reference/carchive-class.md)kullanılarak tüm verilerin aynı biçimde kaydedilen garanti eder. Bir `CArchive` nesneyi çevirmen olarak kullanır. Bu nesne, [carchive::Close'u](../mfc/reference/carchive-class.md#close)arayana kadar oluşturulduğu andan itibaren devam eder. Bu yöntem, programcı tarafından açık olarak veya dolaylı olarak yıkıcı tarafından `CArchive`çağrılabilir.

Bu `CArchive` not, carchive üyelerinin uygulanmasını [açıklar::ReadObject](../mfc/reference/carchive-class.md#readobject) ve [CArchive::WriteObject](../mfc/reference/carchive-class.md#writeobject). Arcobj.cpp bu işlevlerin kodunu ve Arccore.cpp `CArchive` için ana uygulama bulacaksınız. Kullanıcı kodu `ReadObject` aramaz `WriteObject` ve doğrudan. Bunun yerine, bu nesneler, DECLARE_SERIAL ve IMPLEMENT_SERIAL makroları tarafından otomatik olarak oluşturulan sınıfa özgü tür güvenli ekleme ve çıkarma işleçleri tarafından kullanılır. Aşağıdaki kod nasıl `WriteObject` `ReadObject` ve örtülü olarak adlandırılır gösterir:

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

## <a name="saving-objects-to-the-store-carchivewriteobject"></a>Nesneleri Mağazaya Kaydetme (CArchive::WriteObject)

Yöntem, `CArchive::WriteObject` nesneyi yeniden oluşturmak için kullanılan üstbilgi verilerini yazar. Bu veriler iki bölümden oluşur: nesnenin türü ve nesnenin durumu. Bu yöntem, bu nesneye giden işaretçi sayısına (dairesel işaretçiler dahil) bakılmaksızın yalnızca tek bir kopyanın kaydedilmesi için, yazılan nesnenin kimliğini korumaktan da sorumludur.

Nesneleri kaydetme (ekleme) ve geri alma (ayıklama) birkaç "bildirim sabitine" dayanır. Bunlar ikili olarak depolanan ve arşive önemli bilgiler sağlayan değerlerdir ("w" önekinin 16 bitlik miktarları gösterdiğine dikkat edin):

|Etiket|Açıklama|
|---------|-----------------|
|wNullTag|NULL nesne işaretçileri (0) için kullanılır.|
|wNewClassTag|Aşağıdaki sınıf açıklamasını gösterir bu arşiv bağlamında yenidir (-1).|
|wOldClassTag|Bu bağlamda (0x8000) okunan nesnenin sınıfını gösterir.|

Nesneleri depolarken, arşivde depolanan bir nesneden 32 bit kalıcı tanımlayıcıya (PID) eşleme olan bir [CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) *(m_pStoreMap)* bulunur. Pid, arşiv bağlamında kaydedilen her benzersiz nesneye ve her benzersiz sınıf adına atanır. Bu PID'ler 1'den başlayarak sırayla dağıtılır. Bu PID'lerin arşiv kapsamı dışında bir önemi yoktur ve özellikle kayıt numaraları veya diğer kimlik öğeleriyle karıştırılmamalıdır.

`CArchive` Sınıfta, PID'ler 32 bittir, ancak 0x7FFE'den büyük olmadıkları sürece 16 bit olarak yazılırlar. Büyük PID'ler 0x7FFF ve ardından 32-bit PID olarak yazılır. Bu, önceki sürümlerde oluşturulan projelerle uyumluluğu korur.

Bir nesneyi arşive kaydetmek için bir istek yapıldığında (genellikle genel ekleme işleci kullanılarak), NULL [CObject](../mfc/reference/cobject-class.md) işaretçisi için bir denetim yapılır. İşaretçi NULL ise, *wNullTag* arşiv akışına eklenir.

İşaretçi NULL değilse ve serileştirilebiliyorsa `DECLARE_SERIAL` (sınıf bir sınıftır), kod nesnenin zaten kaydedilip kaydedildiğini görmek için *m_pStoreMap* denetler. Varsa, kod arşiv akışına bu nesneyle ilişkili 32 bit PID ekler.

Nesne daha önce kaydedilmemişse, göz önünde bulundurulması gereken iki olasılık vardır: nesnenin hem nesnesi hem de tam türü (yani sınıf) bu arşiv bağlamında yenidir veya nesne zaten görülen tam bir türdedir. Türün görülüp görülmediğini belirlemek için, kod, kaydedilen nesneyle ilişkili `CRuntimeClass` nesneyle eşleşen bir [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) nesnesi için *m_pStoreMap* sorgular. Bir eşleşme varsa, `WriteObject` *wOldClassTag* ve bu dizinin `OR` bit açısından bilge bir etiket ekler. Bu `CRuntimeClass` arşiv bağlamında yeniyse, `WriteObject` bu sınıfa yeni bir PID atar ve *wNewClassTag* değerinden önce arşive ekler.

Bu sınıfın tanımlayıcısı daha sonra `CRuntimeClass::Store` yöntem kullanılarak arşive eklenir. `CRuntimeClass::Store`sınıfın şema numarasını (aşağıya bakın) ve sınıfın ASCII metin adını ekler. ASCII metin adının kullanılmasının arşivin uygulamalar arasında benzersizliğini garanti etmediğini unutmayın. Bu nedenle, bozulmayı önlemek için veri dosyalarınızı etiketlemeniz gerekir. Sınıf bilgilerinin eklenmesinden sonra, arşiv nesneyi *m_pStoreMap* koyar ve sınıfa özgü verileri ekleme yöntemini `Serialize` çağırır. Aramadan `Serialize` önce nesneyi *m_pStoreMap* yerleştirmek, nesnenin birden çok kopyasının depoya kaydolmasını engeller.

İlk arayanın (genellikle nesne ağının kökü) geri dönerken [CArchive::Close'u](../mfc/reference/carchive-class.md#close)aramanız gerekir. Diğer [CFile](../mfc/reference/cfile-class.md)işlemlerini gerçekleştirmeyi planlıyorsanız, `CArchive` arşivin bozulmasını önlemek için [Flush](../mfc/reference/carchive-class.md#flush) yöntemini aramanız gerekir.

> [!NOTE]
> Bu uygulama, arşiv bağlamı başına 0x3FFFFFFE endeksleri sabit bir sınır uygular. Bu sayı, tek bir arşive kaydedilebilen en fazla benzersiz nesne ve sınıf sayısını temsil eder, ancak tek bir disk dosyasında sınırsız sayıda arşiv bağlamı olabilir.

## <a name="loading-objects-from-the-store-carchivereadobject"></a>Depodan Nesneleri Yükleme (CArchive::ReadObject)

Yükleme (ayıklama) nesneleri `CArchive::ReadObject` yöntemini kullanır ve `WriteObject`converse. Olduğu `WriteObject`gibi `ReadObject` , doğrudan kullanıcı kodu ile çağrılmaz; kullanıcı kodu beklenen `ReadObject` `CRuntimeClass`ile çağıran tür güvenli çıkarma işleci çağırmalıdır. Bu, ayıklama işleminin tür bütünlüğünü sigortalar.

1 `WriteObject` (0 NULL nesnesi olarak önceden tanımlanmıştır) ile başlayan `ReadObject` artan PIN'ler atanan uygulama dan, uygulama arşiv bağlamının durumunu korumak için bir dizi kullanabilirsiniz. Bir PID mağazadan okunduğunda, PID *m_pLoadArray*geçerli üst sınırdan daha `ReadObject` büyükse, yeni bir nesnenin (veya sınıf açıklamasının) izlediğini bilir.

## <a name="schema-numbers"></a>Şema Numaraları

Sınıfın `IMPLEMENT_SERIAL` yöntemine rastlandığında sınıfa atanan şema numarası, sınıf uygulamasının "sürümüdür". Şema, belirli bir nesnenin kalıcı hale getirilmiş olduğu (genellikle nesne sürümü olarak adlandırılır) kaç kez değil, sınıfın uygulanmasını ifade eder.

Zaman içinde aynı sınıfın birkaç farklı uygulamasını korumak istiyorsanız, nesnenizin `Serialize` yöntem uygulamasını gözden geçirirken şemayı artımlı hale getirmek, uygulamanın eski sürümlerini kullanarak depolanan nesneleri yükleyebilen kod yazmanıza olanak tanır.

Yöntem, `CArchive::ReadObject` kalıcı depoda bellekteki sınıf açıklamasının şema sayısından farklı bir şema numarasıyla karşılaştığında [CArchiveException](../mfc/reference/carchiveexception-class.md) atar. Bu özel durum kurtarmak kolay değildir.

Bu özel `VERSIONABLE_SCHEMA` durum atılmasını engellemek için şema sürümünüzle (bitwise **VEYA)** birlikte kullanabilirsiniz. Kullanarak, `VERSIONABLE_SCHEMA`kod carchive gelen dönüş `Serialize` değerini kontrol ederek işlevinde uygun eylemi [alabilir::GetObjectSchema](../mfc/reference/carchive-class.md#getobjectschema).

## <a name="calling-serialize-directly"></a>Doğrudan Serialize'i Arama

Birçok durumda genel nesne arşiv düzeninin `WriteObject` genel `ReadObject` yükü ve gerekli değildir. Bu, verileri bir [CDocument'e](../mfc/reference/cdocument-class.md)serileştirme nin yaygın örneğidir. Bu durumda, `Serialize` yöntem `CDocument` doğrudan değil, ayıklama veya ekleme işleçleri ile çağrılır. Belgenin içeriği sırayla daha genel nesne arşiv düzenini kullanabilir.

Doğrudan `Serialize` arama aşağıdaki avantajları ve dezavantajları vardır:

- Nesne seri hale getirilmeden önce veya sonra arşive fazladan bayt eklenmez. Bu yalnızca kaydedilen verileri küçültmekle kalmıyor, `Serialize` aynı zamanda dosya biçimlerini işletebilecek yordamları da uygulamanızı sağlar.

- MFC, başka bir `WriteObject` amaç `ReadObject` için daha genel nesne arşiv düzenine ihtiyacınız olmadığı sürece, uygulamalar ve ilgili koleksiyonlar uygulamanız ile bağlantılı olmayacak şekilde ayarlanır.

- Kodunuz eski şema numaralarından kurtarmak zorunda değildir. Bu, belge serileştirme kodunuzu şema numaralarının, dosya biçimi sürüm numaralarının veya veri dosyalarınızın başında kullandığınız tanımlayıcı numaraların kodlanmasından sorumlu kılar.

- Doğrudan çağrı ile seri hale getirilen herhangi bir nesne, sürümün bilinmediğini belirten (UINT)-1'in iade değerini `Serialize` kullanmamalıdır. `CArchive::GetObjectSchema`

Doğrudan `Serialize` belgenizde çağrıldığından, belgenin alt nesnelerinin ana belgeye yapılan başvuruları arşivlemesi genellikle mümkün değildir. Bu nesnelere açıkça kapsayıcı belgelerine bir işaretçi verilmelidir veya bu geri işaretçiler `CDocument` arşivlenmeden önce işaretçiyi PID ile eşlemek için [CArchive::MapObject](../mfc/reference/carchive-class.md#mapobject) işlevini kullanmanız gerekir.

Daha önce de belirtildiği gibi, doğrudan aradiğinizde `Serialize` sürümü ve sınıf bilgilerini kendiniz kodlamanız gerekir ve eski dosyalarla geriye dönük uyumluluğu korurken biçimi daha sonra değiştirmenizi sağlar. İşlev, `CArchive::SerializeClass` nesneyi doğrudan serileştirmeden önce veya taban sınıf çağırmadan önce açıkça çağrılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
