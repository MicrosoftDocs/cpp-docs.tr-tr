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
ms.openlocfilehash: 1880d5d43055966dea8ab16dc4f26bd4e4602ec5
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447132"
---
# <a name="tn002-persistent-object-data-format"></a>TN002: Kalıcı Nesne Veri Biçimi

Bu notta kalıcı C++ NESNELERI destekleyen MFC yordamları ve bir dosyada depolandığında nesne verilerinin biçimi açıklanmaktadır. Bu yalnızca [DECLARE_SERIAL](../mfc/reference/run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) makroları olan sınıflar için geçerlidir.

## <a name="the-problem"></a>Sorun

Kalıcı veriler için MFC uygulamasında, bir dosyanın tek bir bitişik bölümünde çok sayıda nesne için veriler depolanır. Nesnenin `Serialize` yöntemi nesnenin verilerini Compact binary biçimine dönüştürür.

Uygulama, tüm verilerin [CArchive sınıfı](../mfc/reference/carchive-class.md)kullanılarak aynı biçimde kaydedilmesini garanti eder. Çevirici olarak bir `CArchive` nesnesi kullanır. Bu nesne, [CArchive:: Close](../mfc/reference/carchive-class.md#close)öğesini çağırana kadar oluşturulduğu zamandan itibaren devam ettirir. Bu yöntem, program tarafından açık olarak ya da program `CArchive`içeren kapsamdan çıktığında yıkıcı tarafından örtük olarak çağrılabilir.

Bu notta [CArchive:: ReadObject](../mfc/reference/carchive-class.md#readobject) ve [CArchive:: WriteObject](../mfc/reference/carchive-class.md#writeobject)`CArchive` üyelerine yönelik uygulama açıklanmaktadır. Arcobj. cpp içinde bu işlevlere yönelik kodu ve Arccore. cpp içinde `CArchive` için ana uygulamayı bulacaksınız. Kullanıcı kodu `ReadObject` ve doğrudan `WriteObject` çağırmaz. Bunun yerine, bu nesneler, DECLARE_SERIAL ve IMPLEMENT_SERIAL makroları tarafından otomatik olarak oluşturulan sınıfa özgü tür kullanımı güvenli ekleme ve ayıklama işleçleri tarafından kullanılır. Aşağıdaki kod `WriteObject` ve `ReadObject` örtük olarak nasıl çağrıldığını gösterir:

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

## <a name="saving-objects-to-the-store-carchivewriteobject"></a>Nesneleri depoya kaydetme (CArchive:: WriteObject)

Yöntemi `CArchive::WriteObject`, nesneyi yeniden oluşturmak için kullanılan üst bilgi verilerini yazar. Bu veriler iki bölümden oluşur: nesnenin türü ve nesnenin durumu. Bu yöntem, yazılan nesnenin kimliğini korumadan da sorumludur. böylece, bu nesneye yönelik işaretçilerin sayısından bağımsız olarak yalnızca tek bir kopya kaydedilir (dairesel işaretçiler dahil).

Nesneleri kaydetme (ekleme) ve geri yükleme (ayıklama) nesneleri birkaç "bildirim sabitinden" yararlanır. Bunlar, ikili dosyada depolanan ve arşive önemli bilgiler sağlayan değerlerdir ("w" öneki 16-bit miktarları gösterir):

|Etiket|Açıklama|
|---------|-----------------|
|wNullTag|NULL nesne işaretçileri (0) için kullanılır.|
|wNewClassTag|Aşağıdaki sınıf açıklamasını bu arşiv bağlamı için yeni (-1) gösterir.|
|wOldClassTag|Okunan nesnenin sınıfının bu bağlamda (0x8000) görüldüğünü gösterir.|

Nesneler depolarken, arşiv bir [CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) ( *m_pStoreMap*), saklı bir nesneden 32 BITLIK kalıcı tanımlayıcı (PID) ile bir eşleme olur. Bir PID, her benzersiz nesneye ve arşiv bağlamına kaydedilen her benzersiz sınıf adına atanır. Bu PID 'ler, 1 ' den başlayarak sırayla dışarı dağıtılır. Bu PID 'ler arşiv kapsamı dışında bir anlam içermez ve özellikle, kayıt numaraları veya diğer kimlik öğeleriyle karıştırılmamalıdır.

`CArchive` sınıfında, PID 32 bittir, ancak 0x7FFE 'den büyük olmadıkları sürece 16 bit olarak yazılır. Büyük PID 'ler, 0x7FFF ve sonrasında 32 bitlik PID olarak yazılır. Bu, önceki sürümlerde oluşturulmuş projelerle uyumluluğu korur.

Bir nesneyi bir arşive kaydetmek için bir istek yapıldığında (genellikle genel ekleme işlecini kullanarak), NULL [CObject](../mfc/reference/cobject-class.md) işaretçisi için bir denetim yapılır. İşaretçi NULL ise, *wNullTag* arşiv akışına eklenir.

İşaretçi NULL değilse ve seri hale getirilebilir (sınıf bir `DECLARE_SERIAL` sınıftır), kod, nesnenin zaten kaydedilip kaydedilmediğini görmek için *m_pStoreMap* denetler. Varsa, kod bu nesneyle ilişkili 32 bitlik PID 'yi arşiv akışına ekler.

Nesne daha önce kaydedilmese de göz önünde bulundurmanız gereken iki olasılık vardır: hem nesne hem de nesnenin tam türü (yani, sınıfı) Bu arşiv bağlamı için yeni veya nesne zaten görülen tam bir tür. Türün gördük olup olmadığını anlamak için, kod, kaydedilmekte olan nesneyle ilişkili `CRuntimeClass` nesnesiyle eşleşen bir [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) nesnesi için *m_pStoreMap* sorgular. Bir eşleşme varsa `WriteObject`, *wOldClassTag* ve bu dizinin bit taraflı `OR` bir etiket ekler. `CRuntimeClass`, bu arşiv bağlamı için yeni bir `WriteObject`, bu sınıfa yeni bir PID atar ve önünde *wNewClassTag* değerinden önce onu arşive ekler.

Bu sınıf için tanımlayıcı daha sonra `CRuntimeClass::Store` yöntemi kullanılarak arşive eklenir. `CRuntimeClass::Store`, sınıfın şema numarasını (aşağıya bakın) ve sınıfın ASCII metin adını ekler. ASCII metin adının kullanılması, arşivin uygulamalar genelinde benzersizliğini garanti etmez. Bu nedenle, bozulmayı engellemek için veri dosyalarınızı etiketlemelisiniz. Sınıf bilgilerinin eklenmesini izleyerek arşiv nesneyi *m_pStoreMap* yerleştirir ve ardından sınıfa özgü verileri eklemek için `Serialize` yöntemini çağırır. `Serialize` çağrılmadan önce nesnenin *m_pStoreMap* yerleştirilmesi, nesnenin birden çok kopyasının depoya kaydedilmesini engeller.

Başlangıç çağıranına (genellikle nesnelerin ağının köküne) dönzaman, [CArchive:: Close](../mfc/reference/carchive-class.md#close)'u çağırmanız gerekir. Başka [CFile](../mfc/reference/cfile-class.md)işlemleri yapmayı planlıyorsanız, arşivin bozulmasını engellemek için `CArchive` yöntemi [Temizleme](../mfc/reference/carchive-class.md#flush) yöntemini çağırmanız gerekir.

> [!NOTE]
>  Bu uygulama, arşiv bağlamı başına 0x3FFFFFFE indisli bir sabit sınır uygular. Bu sayı, tek bir arşive kaydedilebilecek en fazla benzersiz nesne ve sınıf sayısını temsil eder, ancak tek bir disk dosyası sınırsız sayıda arşiv bağlamına sahip olabilir.

## <a name="loading-objects-from-the-store-carchivereadobject"></a>Depodan nesneler yükleme (CArchive:: ReadObject)

Nesneleri yükleme (ayıklama) `CArchive::ReadObject` yöntemini kullanır ve `WriteObject`dönüştürüdir. `WriteObject`olduğu gibi, `ReadObject` doğrudan Kullanıcı kodu tarafından çağrılmaz; Kullanıcı kodu, beklenen `CRuntimeClass``ReadObject` çağıran tür kullanımı güvenli ayıklama işlecini çağırmalıdır. Bu, ayıklama işleminin bütünlüğünü yöntem.

`WriteObject` uygulama, 1 ile başlayan (0 ' dan başlayarak) artan PID 'leri kullandığından, `ReadObject` uygulama arşiv bağlamının durumunu korumak için bir dizi kullanabilir. Bir PID depodan okunmadığında, PID *m_pLoadArray*geçerli üst sınırından büyükse, `ReadObject` yeni bir nesne (veya sınıf açıklaması) olduğunu bilir.

## <a name="schema-numbers"></a>Şema numaraları

Sınıfın `IMPLEMENT_SERIAL` yöntemi ile karşılaşıldığında sınıfa atanan şema numarası, sınıf uygulamasının "sürümüdür". Şema, belirli bir nesnenin kalıcı hale getirilme sayısına (genellikle nesne sürümü olarak adlandırılır) göre değil, sınıfının uygulamasını ifade eder.

Aynı sınıftan birkaç farklı uygulamayı zaman içinde sürdürmek istiyorsanız, nesnenin `Serialize` yöntemi uygulamasını düzelttiğinizde şemayı arttırmanız, uygulamanın eski sürümleri kullanılarak depolanan nesneleri yükleyebileceğiniz bir kod yazmanıza olanak sağlar.

`CArchive::ReadObject` yöntemi, bellekteki sınıf açıklamasının şema numarasından farklı olan kalıcı depodaki bir şema numarasıyla karşılaştığında bir [CArchiveException](../mfc/reference/carchiveexception-class.md) oluşturur. Bu özel durumun kurtarılması kolay değildir.

Bu özel durumun oluşturulması için şema sürümünüz ile birlikte `VERSIONABLE_SCHEMA` kullanabilirsiniz (bit düzeyinde **or**). `VERSIONABLE_SCHEMA`kullanarak kodunuz, [CArchive:: GetObjectSchema](../mfc/reference/carchive-class.md#getobjectschema)'dan döndürülen değeri denetleyerek `Serialize` işlevinde uygun eylemi gerçekleştirebilir.

## <a name="calling-serialize-directly"></a>Seri hale getirme doğrudan çağrılıyor

Çoğu durumda, `WriteObject` ve `ReadObject` genel nesne Arşivi Şeması ek yükü gerekli değildir. Bu, verileri bir [CDocument](../mfc/reference/cdocument-class.md)içinde serileştirmede kullanılan yaygın bir durumdur. Bu durumda, `CDocument` `Serialize` metodu doğrudan çağırılır, ayıklama veya INSERT işleçleriyle değil. Belgenin içeriği daha fazla genel nesne arşiv şemasını kullanabilir.

`Serialize` çağırmak doğrudan aşağıdaki avantajları ve dezavantajlara sahiptir:

- Nesne serileştirildikten önce veya sonra arşive ek bayt eklenmez. Bu, yalnızca kaydedilen verileri küçültün, ancak herhangi bir dosya biçimini işleyebilen `Serialize` yordamlar uygulamanıza olanak tanır.

- MFC, `WriteObject` ve `ReadObject` uygulamalarının ve ilgili koleksiyonların, başka bir amaçla daha genel nesne arşiv şemasına gerek duymadığınız takdirde uygulamanıza bağlanmayacak şekilde ayarlanır.

- Kodunuzun eski şema numaralarını kurtarmak zorunda değilsiniz. Bu, belge serileştirme kodunuzu, şema numaralarını, dosya biçimi sürüm numaralarını veya veri dosyalarınızın başlangıcında kullandığınız tanımlayıcı numaraları kodlamadan sorumlu hale getirir.

- `Serialize` doğrudan çağrısıyla seri hale getirilen herhangi bir nesne `CArchive::GetObjectSchema` kullanmamalıdır ya da sürümün bilinmediğini belirten (UINT)-1 dönüş değerini işlemelidir.

`Serialize` doğrudan belgenizde çağrıldığı için, belgenin alt nesnelerinin üst belgelere başvuruları arşivlemek genellikle mümkün değildir. Bu nesnelere kapsayıcı belgeleri açıkça bir işaretçi verilmelidir veya bu geri işaretçiler arşivlenmeden önce `CDocument` işaretçisini bir PID 'ye eşlemek için [CArchive:: MapObject](../mfc/reference/carchive-class.md#mapobject) işlevini kullanmanız gerekir.

Daha önce belirtildiği gibi, `Serialize` doğrudan çağırdığınızda sürümü ve sınıf bilgilerini kendiniz kodlamanız gerekir. daha sonra, eski dosyalarla geriye dönük uyumluluğu sürdürirken biçimi değiştirmenize olanak sağlar. `CArchive::SerializeClass` işlevi, bir nesneyi doğrudan serileştirmadan veya temel sınıf çağrılmadan önce açıkça çağrılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
