---
description: 'Hakkında daha fazla bilgi edinin: TN002: kalıcı nesne veri biçimi'
title: 'TN002: Kalıcı Nesne Veri Biçimi'
ms.date: 11/04/2016
helpviewer_keywords:
- VERSIONABLE_SCHEMA macro [MFC]
- persistent object data
- CArchive class [MFC], support for persistent data
- persistent C++ objects [MFC]
- TN002
ms.assetid: 553fe01d-c587-4c8d-a181-3244a15c2be9
ms.openlocfilehash: e99d54bd2624bffac4f5fea37c72bb7719e1e408
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216086"
---
# <a name="tn002-persistent-object-data-format"></a>TN002: Kalıcı Nesne Veri Biçimi

Bu notta kalıcı C++ nesnelerini destekleyen MFC yordamları ve bir dosyada depolandığında nesne verilerinin biçimi açıklanmaktadır. Bu yalnızca [DECLARE_SERIAL](../mfc/reference/run-time-object-model-services.md#declare_serial) ve [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) makroları olan sınıflar için geçerlidir.

## <a name="the-problem"></a>Sorun

Kalıcı veriler için MFC uygulamasında, bir dosyanın tek bir bitişik bölümünde çok sayıda nesne için veriler depolanır. Nesnenin `Serialize` yöntemi nesnenin verilerini Compact binary biçimine dönüştürür.

Uygulama, tüm verilerin [CArchive sınıfı](../mfc/reference/carchive-class.md)kullanılarak aynı biçimde kaydedilmesini garanti eder. `CArchive`Çevirici olarak bir nesnesi kullanır. Bu nesne, [CArchive:: Close](../mfc/reference/carchive-class.md#close)öğesini çağırana kadar oluşturulduğu zamandan itibaren devam ettirir. Bu yöntem, programlayıcı tarafından açıkça veya program, içeren kapsamdan çıktığında yıkıcı tarafından örtük olarak çağrılabilir `CArchive` .

Bu notta `CArchive` [CArchive:: ReadObject](../mfc/reference/carchive-class.md#readobject) ve [CArchive:: WriteObject](../mfc/reference/carchive-class.md#writeobject)üyelerinin uygulanması açıklanmaktadır. Arcobj. cpp içinde bu işlevlere yönelik kodu ve `CArchive` Arccore. cpp için ana uygulamayı bulacaksınız. Kullanıcı kodu çağrı yapmaz `ReadObject` ve `WriteObject` doğrudan. Bunun yerine, bu nesneler, DECLARE_SERIAL ve IMPLEMENT_SERIAL makroları tarafından otomatik olarak oluşturulan sınıfa özgü tür kullanımı güvenli ekleme ve ayıklama işleçleri tarafından kullanılır. Aşağıdaki kod, `WriteObject` ve örtülü olarak nasıl `ReadObject` çağrıldığını gösterir:

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

Yöntemi, `CArchive::WriteObject` nesneyi yeniden oluşturmak için kullanılan üst bilgi verilerini yazar. Bu veriler iki bölümden oluşur: nesnenin türü ve nesnenin durumu. Bu yöntem, yazılan nesnenin kimliğini korumadan da sorumludur. böylece, bu nesneye yönelik işaretçilerin sayısından bağımsız olarak yalnızca tek bir kopya kaydedilir (dairesel işaretçiler dahil).

Nesneleri kaydetme (ekleme) ve geri yükleme (ayıklama) nesneleri birkaç "bildirim sabitinden" yararlanır. Bunlar, ikili dosyada depolanan ve arşive önemli bilgiler sağlayan değerlerdir ("w" öneki 16-bit miktarları gösterir):

|Etiket|Açıklama|
|---------|-----------------|
|wNullTag|NULL nesne işaretçileri (0) için kullanılır.|
|wNewClassTag|Aşağıdaki sınıf açıklamasını bu arşiv bağlamı için yeni (-1) gösterir.|
|wOldClassTag|Okunan nesnenin sınıfının bu bağlamda (0x8000) görüldüğünü gösterir.|

Nesneler depolarken, arşiv bir [CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) ( *m_pStoreMap*), saklı bir nesneden 32 BITLIK kalıcı tanımlayıcı (PID) ile bir eşleme olur. Bir PID, her benzersiz nesneye ve arşiv bağlamına kaydedilen her benzersiz sınıf adına atanır. Bu PID 'ler, 1 ' den başlayarak sırayla dışarı dağıtılır. Bu PID 'ler arşiv kapsamı dışında bir anlam içermez ve özellikle, kayıt numaraları veya diğer kimlik öğeleriyle karıştırılmamalıdır.

`CArchive`Sınıfında, pıd 32 bittir, ancak 0x7FFE 'den büyük olmadıkları sürece 16 bit olarak yazılır. Büyük PID 'ler, 0x7FFF ve sonrasında 32 bitlik PID olarak yazılır. Bu, önceki sürümlerde oluşturulmuş projelerle uyumluluğu korur.

Bir nesneyi bir arşive kaydetmek için bir istek yapıldığında (genellikle genel ekleme işlecini kullanarak), NULL [CObject](../mfc/reference/cobject-class.md) işaretçisi için bir denetim yapılır. İşaretçi NULL ise, *wNullTag* arşiv akışına eklenir.

İşaretçi NULL değilse ve seri hale getirilebilir (sınıf bir `DECLARE_SERIAL` sınıftır), kod, nesnenin zaten kaydedilip kaydedilmediğini görmek için *m_pStoreMap* denetler. Varsa, kod bu nesneyle ilişkili 32 bitlik PID 'yi arşiv akışına ekler.

Nesne daha önce kaydedilmese de göz önünde bulundurmanız gereken iki olasılık vardır: hem nesne hem de nesnenin tam türü (yani, sınıfı) Bu arşiv bağlamı için yeni veya nesne zaten görülen tam bir tür. Türün gördük olup olmadığını anlamak için, kod, kaydedilmekte olan nesneyle ilişkili nesneyle eşleşen bir [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) nesnesi için *m_pStoreMap* sorgular `CRuntimeClass` . Bir eşleşme varsa, `WriteObject` `OR` *wOldClassTag* ve bu dizinin bit temelinde bir etiket ekler. `CRuntimeClass`Bu arşiv bağlamına yeni ise, bu `WriteObject` sınıfa yenı bir PID atar ve önünde *wNewClassTag* değerinden önce onu arşive ekler.

Daha sonra bu sınıfa ait tanımlayıcı yöntemi kullanılarak arşive eklenir `CRuntimeClass::Store` . `CRuntimeClass::Store` sınıfın şema numarasını (aşağıya bakın) ve sınıfın ASCII metin adını ekler. ASCII metin adının kullanılması, arşivin uygulamalar genelinde benzersizliğini garanti etmez. Bu nedenle, bozulmayı engellemek için veri dosyalarınızı etiketlemelisiniz. Sınıf bilgilerinin eklenmesini izleyerek arşiv nesneyi *m_pStoreMap* yerleştirir ve ardından `Serialize` sınıfa özgü verileri eklemek için yöntemini çağırır. Çağrılmadan önce nesnenin *m_pStoreMap* yerleştirilmesi, `Serialize` nesnenin birden çok kopyasının depoya kaydedilmesini engeller.

Başlangıç çağıranına (genellikle nesnelerin ağının köküne) dönzaman, [CArchive:: Close](../mfc/reference/carchive-class.md#close)'u çağırmanız gerekir. Başka [CFile](../mfc/reference/cfile-class.md)işlemleri yapmayı planlıyorsanız, `CArchive` arşivin bozulmasını engellemek için yöntemi [Temizleme](../mfc/reference/carchive-class.md#flush) yöntemini çağırmanız gerekir.

> [!NOTE]
> Bu uygulama, arşiv bağlamı başına 0x3FFFFFFE indisli bir sabit sınır uygular. Bu sayı, tek bir arşive kaydedilebilecek en fazla benzersiz nesne ve sınıf sayısını temsil eder, ancak tek bir disk dosyası sınırsız sayıda arşiv bağlamına sahip olabilir.

## <a name="loading-objects-from-the-store-carchivereadobject"></a>Depodan nesneler yükleme (CArchive:: ReadObject)

Nesneleri yükleme (ayıklama) yöntemini kullanır `CArchive::ReadObject` ve ' ın bir `WriteObject` . İle olduğu gibi `WriteObject` , `ReadObject` Kullanıcı kodu tarafından doğrudan çağrılmaz; Kullanıcı kodu, beklenen ile çağıran tür kullanımı güvenli ayıklama işlecini çağırmalıdır `ReadObject` `CRuntimeClass` . Bu, ayıklama işleminin bütünlüğünü yöntem.

Uygulama, `WriteObject` 1 (0 ' dan başlayarak, null nesne olarak önceden tanımlanmıştır) artan PID 'leri `ReadObject` kullandığından, uygulama arşiv bağlamının durumunu korumak için bir dizi kullanabilir. Bir PID depodan okunmadığında, PID *m_pLoadArray* geçerli üst sınırından büyükse, `ReadObject` Yeni bir nesne (veya sınıf açıklaması) aşağıda verilmiştir.

## <a name="schema-numbers"></a>Şema numaraları

Sınıf yöntemi ile karşılaşıldığında sınıfına atanan şema numarası `IMPLEMENT_SERIAL` , sınıf uygulamasının "sürümüdür". Şema, belirli bir nesnenin kalıcı hale getirilme sayısına (genellikle nesne sürümü olarak adlandırılır) göre değil, sınıfının uygulamasını ifade eder.

Zaman içinde aynı sınıfın birkaç farklı uygulamasını sürdürmek istiyorsanız, nesnenin Yöntem uygulamasını düzelttiğinizde şemayı arttırmanız, `Serialize` uygulamanın eski sürümleri kullanılarak depolanan nesneleri yükleyebileceğiniz bir kod yazmanıza olanak sağlar.

`CArchive::ReadObject`Yöntemi, bellekteki sınıf açıklamasının şema numarasından farklı olan kalıcı depodaki bir şema numarasıyla karşılaştığında bir [CArchiveException](../mfc/reference/carchiveexception-class.md) oluşturur. Bu özel durumun kurtarılması kolay değildir.

`VERSIONABLE_SCHEMA`Bu özel durumun oluşturulması için şema sürümünüz ile birlikte (bit düzeyinde **or**) kullanabilirsiniz. `VERSIONABLE_SCHEMA`' I kullanarak, `Serialize` [CArchive:: GetObjectSchema](../mfc/reference/carchive-class.md#getobjectschema)'dan döndürülen değeri denetleyerek, kodunuz kendi işlevinde uygun eylemi gerçekleştirebilir.

## <a name="calling-serialize-directly"></a>Seri hale getirme doğrudan çağrılıyor

Çoğu durumda, ve genel nesne arşiv düzeninin ek yükü `WriteObject` `ReadObject` gerekli değildir. Bu, verileri bir [CDocument](../mfc/reference/cdocument-class.md)içinde serileştirmede kullanılan yaygın bir durumdur. Bu durumda, ' `Serialize` nin yöntemi, `CDocument` Ayıkla veya Ekle işleçleriyle değil, doğrudan çağırılır. Belgenin içeriği daha fazla genel nesne arşiv şemasını kullanabilir.

`Serialize`Doğrudan çağırmanın aşağıdaki avantajları ve dezavantajları vardır:

- Nesne serileştirildikten önce veya sonra arşive ek bayt eklenmez. Bu, yalnızca kaydedilen verileri küçültün, ancak `Serialize` herhangi bir dosya biçimini işleyebilen yordamlar uygulamanıza olanak tanır.

- `WriteObject` `ReadObject` Diğer bir amaçla daha genel nesne arşiv şemasına gerek duymadığınız takdirde, ve uygulamalarının ve ilgili koleksiyonların uygulamanıza bağlanmayacak şekilde ayarlanır.

- Kodunuzun eski şema numaralarını kurtarmak zorunda değilsiniz. Bu, belge serileştirme kodunuzu, şema numaralarını, dosya biçimi sürüm numaralarını veya veri dosyalarınızın başlangıcında kullandığınız tanımlayıcı numaraları kodlamadan sorumlu hale getirir.

- Doğrudan çağrısıyla serileştirilmiş olan herhangi bir nesne, `Serialize` `CArchive::GetObjectSchema` sürümünün bilinmediğini belirten veya (UINT)-1 dönüş değerini işlemelidir.

`Serialize`Doğrudan belgeniz üzerinde çağrıldığı için, belgenin alt nesnelerinin üst belge başvurularını arşivlenmesi genellikle mümkün değildir. Bu nesnelere kapsayıcı belgeleri açıkça bir işaretçi verilmelidir veya bu geri işaretçiler arşivlenmeden önce işaretçiyi bir PID 'e eşlemek için [CArchive:: MapObject](../mfc/reference/carchive-class.md#mapobject) işlevini kullanmanız gerekir `CDocument` .

Daha önce belirtildiği gibi, doğrudan çağrı yaparken sürümü ve sınıf bilgilerini kendiniz kodlamanız gerekir `Serialize` . daha sonra, eski dosyalarla geriye dönük uyumluluğu sürdürirken biçimi değiştirmenize olanak sağlar. `CArchive::SerializeClass`İşlev, bir nesneyi doğrudan serileştirilmadan veya temel sınıf çağrılmadan önce açıkça çağrılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
