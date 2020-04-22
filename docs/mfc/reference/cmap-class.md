---
title: CMap Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMap
- AFXTEMPL/CMap
- AFXTEMPL/CMap::CPair
- AFXTEMPL/CMap::CMap
- AFXTEMPL/CMap::GetCount
- AFXTEMPL/CMap::GetHashTableSize
- AFXTEMPL/CMap::GetNextAssoc
- AFXTEMPL/CMap::GetSize
- AFXTEMPL/CMap::GetStartPosition
- AFXTEMPL/CMap::InitHashTable
- AFXTEMPL/CMap::IsEmpty
- AFXTEMPL/CMap::Lookup
- AFXTEMPL/CMap::PGetFirstAssoc
- AFXTEMPL/CMap::PGetNextAssoc
- AFXTEMPL/CMap::PLookup
- AFXTEMPL/CMap::RemoveAll
- AFXTEMPL/CMap::RemoveKey
- AFXTEMPL/CMap::SetAt
helpviewer_keywords:
- CMap [MFC], CPair
- CMap [MFC], CMap
- CMap [MFC], GetCount
- CMap [MFC], GetHashTableSize
- CMap [MFC], GetNextAssoc
- CMap [MFC], GetSize
- CMap [MFC], GetStartPosition
- CMap [MFC], InitHashTable
- CMap [MFC], IsEmpty
- CMap [MFC], Lookup
- CMap [MFC], PGetFirstAssoc
- CMap [MFC], PGetNextAssoc
- CMap [MFC], PLookup
- CMap [MFC], RemoveAll
- CMap [MFC], RemoveKey
- CMap [MFC], SetAt
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
ms.openlocfilehash: fbb34d4db41ef11cd01a6a8a7f20cafa0e737268
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749078"
---
# <a name="cmap-class"></a>CMap Sınıfı

Benzersiz anahtarları değerlerle eşleyen bir sözlük koleksiyonu sınıfı.

## <a name="syntax"></a>Sözdizimi

```
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject
```

#### <a name="parameters"></a>Parametreler

*Anahtar*<br/>
Haritanın anahtarı olarak kullanılan nesnenin sınıfı.

*ARG_KEY*<br/>
*KEY* bağımsız değişkenleri için kullanılan veri türü; genellikle *KEY*bir referans .

*Değer*<br/>
Haritada depolanan nesnenin sınıfı.

*ARG_VALUE*<br/>
*VALUE* bağımsız değişkenleri için kullanılan veri türü; genellikle *VALUE'a*bir başvuru.

## <a name="members"></a>Üyeler

### <a name="public-structures"></a>Kamu Yapıları

|Adı|Açıklama|
|----------|-----------------|
|[CMap::CPair](#cpair)|Anahtar değeri ve ilişkili nesnenin değerini içeren iç içe bir yapı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMap::CMap](#cmap)|Anahtarları değerlerle eşleyen bir koleksiyon oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMap::GetCount](#getcount)|Bu haritadaki öğe sayısını döndürür.|
|[CMap::GetHashTableSize](#gethashtablesize)|Karma tablodaki öğe sayısını verir.|
|[CMap::GetNextAssoc](#getnextassoc)|Yinelenmenin bir sonraki öğesini alır.|
|[CMap::GetSize](#getsize)|Bu haritadaki öğe sayısını döndürür.|
|[CMap::GetStartPosition](#getstartposition)|İlk öğenin konumunu döndürür.|
|[CMap::InitHashTable](#inithashtable)|Karma tabloyu başolarak karşılar ve boyutunu belirtir.|
|[CMap::Boş](#isempty)|Boş eşlemi koşulu (öğe yok) için testler.|
|[CMap::Arama](#lookup)|Belirli bir anahtara eşlenen değeri arar.|
|[CMap::PGetFirstAssoc](#pgetfirstassoc)|İlk öğeye bir işaretçi döndürür.|
|[CMap::PGetNextAssoc](#pgetnextassoc)|Yinelemek için bir sonraki öğeye işaretçi alır.|
|[CMap::PLookup](#plookup)|Bir işaretçiyi, değeri belirtilen değerle eşleşen bir anahtara döndürür.|
|[CMap::RemoveAll](#removeall)|Bu haritadaki tüm öğeleri kaldırır.|
|[CMap::RemoveKey](#removekey)|Anahtar tarafından belirtilen bir öğeyi kaldırır.|
|[CMap::Setat](#setat)|Haritaya bir öğe ekler; eşleşen bir anahtar bulunursa varolan bir öğenin yerini alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CMap::operatör \[\]](#operator_at)|Eşama bir öğe ekler — operatör ikamesi `SetAt`için .|

## <a name="remarks"></a>Açıklamalar

Eşmeye bir anahtar değer çifti (öğe) ekledikten sonra, eşe erişmek için anahtarı kullanarak çifti verimli bir şekilde alabilir veya silebilirsiniz. Ayrıca haritadaki tüm öğeleri yineleyebilirsiniz.

Girişlere alternatif erişim için tür POSITION değişkeni kullanılır. Bir girişi "hatırlamak" ve harita üzerinden tekrarlamak için bir KONUM kullanabilirsiniz. Bu yinelemenin anahtar değerine göre sıralı olduğunu düşünebilirsiniz; Öyle değil. Alınan öğelerin sırası belirsizdir.

Bu sınıfın belirli üye işlevleri, `CMap` sınıfın çoğu kullanımı için özelleştirilmiş olması gereken genel yardımcı işlevleri çağırır. **MFC Başvurusu'nun**Makrolar ve Globaller [bölümündeki Koleksiyon Sınıfı Yardımcıları](../../mfc/reference/collection-class-helpers.md) bölümüne bakın.

`CMap`[CObject geçersiz kılar::Serileştirme](../../mfc/reference/cobject-class.md#serialize) ve öğelerinin damping desteklemek için. Bir harita kullanılarak `Serialize`bir arşive depolanırsa, her harita öğesi sırayla seri hale getirilir. Yardımcı işlevin `SerializeElements` varsayılan uygulaması biraz akıllıca yazmak yok. Türemiş `CObject` veya diğer kullanıcı tanımlı türlerden alınan işaretçi toplama öğelerinin serileştirilmesi hakkında bilgi için [bkz.](../../mfc/how-to-make-a-type-safe-collection.md)

Haritadaki tek tek öğelerin (anahtarlar ve değerler) tanılama dökümüne ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Bir `CMap` nesne silindiğinde veya öğeleri kaldırıldığında, anahtarlar ve değerler her ikisi de kaldırılır.

Harita sınıf türetme liste türetme benzer. Özel amaçlı bir liste sınıfının türemiş bir illüstrasyon için makale [Koleksiyonları](../../mfc/collections.md) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CMap`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtempl.h

## <a name="cmapcmap"></a><a name="cmap"></a>CMap::CMap

Boş bir harita oluşturur.

```
CMap(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Haritayı genişletmek için bellek ayırma parçalılığını belirtir.

### <a name="remarks"></a>Açıklamalar

Harita büyüdükçe, bellek *nBlockSize* girişleri birimlerine ayrılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#56](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]

## <a name="cmapcpair"></a><a name="cpair"></a>CMap::CPair

Anahtar değeri ve ilişkili nesnenin değerini içerir.

### <a name="remarks"></a>Açıklamalar

Bu sınıf [CMap](../../mfc/reference/cmap-class.md)içinde iç içe bir yapıdır.

Yapı iki alandan oluşur:

- `key`Anahtar türünün gerçek değeri.

- `value`İlişkili nesnenin değeri.

Bu CMap gelen dönüş değerlerini depolamak için [kullanılır::PLookup](#plookup), [CMap::PGetFirstAssoc](#pgetfirstassoc), ve [CMap::PGetNextAssoc](#pgetnextassoc).

### <a name="example"></a>Örnek

Kullanım örneği [için, CMap::PLookup](#plookup)için örneğe bakın.

## <a name="cmapgetcount"></a><a name="getcount"></a>CMap::GetCount

Haritadaki öğe sayısını alır.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğelerin sayısı.

### <a name="example"></a>Örnek

CMap örneğine [bakın:Arama](#lookup).

## <a name="cmapgethashtablesize"></a><a name="gethashtablesize"></a>CMap::GetHashTableSize

Harita için karma tablodaki öğelerin sayısını belirler.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Karma tablodaki öğelerin sayısı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#57](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]

## <a name="cmapgetnextassoc"></a><a name="getnextassoc"></a>CMap::GetNextAssoc

Harita öğesini `rNextPosition`alır, sonra `rNextPosition` haritadaki bir sonraki öğeye başvurmak için güncellenir.

```cpp
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>Parametreler

*rNextPosition*<br/>
Bir önceki `GetNextAssoc` veya `GetStartPosition` çağrı tarafından döndürülen bir POSITION değeriiçin bir başvuru belirtir.

*Anahtar*<br/>
Haritanın anahtarının türünü belirten şablon parametresi.

*rAnahtar*<br/>
Alınan öğenin döndürülen anahtarını belirtir.

*Değer*<br/>
Eşin değerinin türünü belirten şablon parametresi.

*Rvalue*<br/>
Alınan öğenin döndürülen değerini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, haritadaki tüm öğeleri yineetmek için en yararlıdır. Konum sırasının anahtar değer dizisiyle aynı olması gerekmediğini unutmayın.

Alınan öğe haritadaki son öğeyse, *rNextPosition'un* yeni değeri NULL olarak ayarlanır.

### <a name="example"></a>Örnek

CMap örneğine [bakın:SetAt](#setat).

## <a name="cmapgetsize"></a><a name="getsize"></a>CMap::GetSize

Harita öğelerinin sayısını verir.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Haritadaki öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Haritadaki öğe sayısını almak için bu yöntemi arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

## <a name="cmapgetstartposition"></a><a name="getstartposition"></a>CMap::GetStartPosition

`GetNextAssoc` Bir çağrıya geçirilebilen bir POSITION değerini döndürerek bir harita yinelemesini başlatır.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Haritayı yineleyen bir başlangıç konumunu gösteren bir KONUM değeri; veya harita boşsa NULL.

### <a name="remarks"></a>Açıklamalar

Yineleme sırası tahmin edilebilir değildir; bu nedenle, "haritadaki ilk öğenin" özel bir önemi yoktur.

### <a name="example"></a>Örnek

CMap örneğine [bakın:SetAt](#setat).

## <a name="cmapinithashtable"></a><a name="inithashtable"></a>CMap::InitHashTable

Karma tabloyu başharfe ait hale.

```cpp
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUE);
```

### <a name="parameters"></a>Parametreler

*hashSize*<br/>
Karma tablodaki giriş sayısı.

*bAllocNow*<br/>
DOĞRUysa, başlangıç üzerine karma tablo ayırır; aksi takdirde tablo gerektiğinde ayrılır.

### <a name="remarks"></a>Açıklamalar

En iyi performans için karma tablo boyutu bir asal sayı olmalıdır. Çakışmayı en aza indirmek için, boyutun beklenen en büyük veri kümesinden yaklaşık yüzde 20 daha büyük olması gerekir.

### <a name="example"></a>Örnek

CMap örneğine [bakın:Arama](#lookup).

## <a name="cmapisempty"></a><a name="isempty"></a>CMap::Boş

Haritanın boş olup olmadığını belirler.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu harita hiçbir öğe içeriyorsa sıfır olmayan; aksi takdirde 0.

### <a name="example"></a>Örnek

CMap örneğine [bakın:RemoveAll](#removeall).

## <a name="cmaplookup"></a><a name="lookup"></a>CMap::Arama

Belirli bir anahtara eşlenen değeri arar.

```
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>Parametreler

*ARG_KEY*<br/>
*Anahtar* değerinin türünü belirten şablon parametresi.

*anahtar*<br/>
Aranacak öğeyi tanımlayan anahtarı belirtir.

*Değer*<br/>
Aranacak değerin türünü belirtir.

*Rvalue*<br/>
Aranmama değerini alır.

### <a name="return-value"></a>Dönüş Değeri

Öğe bulunursa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`Lookup`verilen anahtarla tam olarak eşleşen bir anahtarla eşleşerek harita öğesini hızla bulmak için karma algoritması kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

## <a name="cmapoperator--"></a><a name="operator_at"></a>CMap::operator [ ]

Üye işlev için `SetAt` uygun bir yedek.

```
VALUE& operator[](arg_key key);
```

### <a name="parameters"></a>Parametreler

*Değer*<br/>
Harita değerinin türünü belirten şablon parametresi.

*ARG_KEY*<br/>
Anahtar değerinin türünü belirten şablon parametresi.

*anahtar*<br/>
Değeri haritadan almak için kullanılan anahtar.

### <a name="remarks"></a>Açıklamalar

Böylece yalnızca bir atama deyiminin (l-değeri) sol tarafında kullanılabilir. Belirtilen anahtara sahip bir eş öğesi yoksa, yeni bir öğe oluşturulur.

Haritada bir anahtarın bulunmama olasılığı olduğundan, bu işleçiçin "sağ taraf" (r-değeri) yoktur. Öğe `Lookup` almak için üye işlevi kullanın.

### <a name="example"></a>Örnek

CMap örneğine [bakın:Arama](#lookup).

## <a name="cmappgetfirstassoc"></a><a name="pgetfirstassoc"></a>CMap::PGetFirstAssoc

Harita nesnesinin ilk girişini döndürür.

```
const CPair* PGetFirstAssoc() const;
CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>Dönüş Değeri

Haritadaki ilk girişiçin bir işaretçi; bkz: [CMap::CPair](#cpair). Eşlemi giriş içermiyorsa, değer NULL'dur.

### <a name="remarks"></a>Açıklamalar

Bir işaretçiyi eşöğecitindeki ilk öğeyi döndürmek için bu işlevi çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#59](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]

## <a name="cmappgetnextassoc"></a><a name="pgetnextassoc"></a>CMap::PGetNextAssoc

*pAssocRec*tarafından işaret edilen harita öğesini alır.

```
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;

CPair *PGetNextAssoc(const CPair* pAssocRet);
```

### <a name="parameters"></a>Parametreler

*pAssocRet*<br/>
Önceki bir [PGetNextAssoc](#pgetnextassoc) veya [CMap::PGetFirstAssoc](#pgetfirstassoc) çağrısı yla döndürülen bir harita girişine işaret edilir.

### <a name="return-value"></a>Dönüş Değeri

Haritadaki bir sonraki girişiçin bir işaretçi; bkz: [CMap::CPair](#cpair). Öğe haritadaki son öğeyse, değer NULL'dur.

### <a name="remarks"></a>Açıklamalar

Haritadaki tüm öğeleri yinelemek için bu yöntemi çağırın. Bir çağrı ile ilk `PGetFirstAssoc` öğeyi alın ve sonra ardışık `PGetNextAssoc`aramalar ile harita üzerinden yineleyin.

### <a name="example"></a>Örnek

[CMap::PGetFirstAssoc](#pgetfirstassoc)için örnek bakın.

## <a name="cmapplookup"></a><a name="plookup"></a>CMap::PLookup

Belirli bir anahtara eşlenen değeri bulur.

```
const CPair* PLookup(ARG_KEY key) const;
CPair* PLookup(ARG_KEY key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak öğe için anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtar yapıya işaretçi; bkz: [CMap::CPair](#cpair). Eşleşme bulunmazsa NULL `CMap::PLookup` döndürür.

### <a name="remarks"></a>Açıklamalar

Verilen anahtarla tam olarak eşleşen bir anahtara sahip bir harita öğesi aramak için bu yöntemi arayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]

## <a name="cmapremoveall"></a><a name="removeall"></a>CMap::RemoveAll

Genel yardımcı işlevini `DestructElements`çağırarak bu haritadaki tüm değerleri kaldırır.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Harita zaten boşsa işlev düzgün çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]

## <a name="cmapremovekey"></a><a name="removekey"></a>CMap::RemoveKey

Verilen anahtara karşılık gelen harita girişini arar; sonra, anahtar bulunursa, girişi kaldırır.

```
BOOL RemoveKey(ARG_KEY key);
```

### <a name="parameters"></a>Parametreler

*ARG_KEY*<br/>
Anahtarın türünü belirten şablon parametresi.

*anahtar*<br/>
Öğenin kaldırılması için anahtar.

### <a name="return-value"></a>Dönüş Değeri

Giriş bulundu ve başarıyla kaldırıldı sıfır değil; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yardımcı `DestructElements` işlevi girişi kaldırmak için kullanılır.

### <a name="example"></a>Örnek

CMap örneğine [bakın:SetAt](#setat).

## <a name="cmapsetat"></a><a name="setat"></a>CMap::Setat

Birincil bir öğeyi bir haritaya eklemek anlamına gelir.

```cpp
void SetAt(ARG_KEY key, ARG_VALUE newValue);
```

### <a name="parameters"></a>Parametreler

*ARG_KEY*<br/>
*Anahtar* parametresinin türünü belirten şablon parametresi.

*anahtar*<br/>
Yeni öğenin anahtarını belirtir.

*ARG_VALUE*<br/>
*YeniDeğer* parametresinin türünü belirten şablon parametresi.

*Newvalue*<br/>
Yeni öğenin değerini belirtir.

### <a name="remarks"></a>Açıklamalar

İlk olarak, anahtar aranır. Anahtar bulunursa, karşılık gelen değer değiştirilir; aksi takdirde yeni bir anahtar değeri çifti oluşturulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek TOPLAMA](../../overview/visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
