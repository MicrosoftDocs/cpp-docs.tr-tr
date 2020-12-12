---
description: 'Daha fazla bilgi edinin: CMap sınıfı'
title: CMap sınıfı
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
ms.openlocfilehash: ff88d205608cc87f06d28e6d2d4b647c35909efa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207910"
---
# <a name="cmap-class"></a>CMap sınıfı

Benzersiz anahtarları değerlere eşleyen sözlük toplama sınıfı.

## <a name="syntax"></a>Sözdizimi

```
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject
```

#### <a name="parameters"></a>Parametreler

*ANAHTAR*<br/>
Haritada anahtar olarak kullanılan nesnenin sınıfı.

*ARG_KEY*<br/>
*Anahtar* bağımsız değişkenleri için kullanılan veri türü; genellikle *anahtara* bir başvurudur.

*VALUE*<br/>
Haritada depolanan nesnenin sınıfı.

*ARG_VALUE*<br/>
*Değer* bağımsız değişkenleri için kullanılan veri türü; genellikle *değere* bir başvurudur.

## <a name="members"></a>Üyeler

### <a name="public-structures"></a>Ortak yapılar

|Ad|Açıklama|
|----------|-----------------|
|[CMap:: CPair](#cpair)|Bir anahtar değeri ve ilişkili nesnenin değerini içeren iç içe bir yapı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMap:: CMap](#cmap)|Anahtarları değerlerle eşleyen bir koleksiyon oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMap:: GetCount](#getcount)|Bu haritadaki öğelerin sayısını döndürür.|
|[CMap:: GetHashTableSize](#gethashtablesize)|Karma tablodaki öğelerin sayısını döndürür.|
|[CMap:: GetNextAssoc](#getnextassoc)|Yineleme için bir sonraki öğeyi alır.|
|[CMap:: GetSize](#getsize)|Bu haritadaki öğelerin sayısını döndürür.|
|[CMap:: GetStartPosition](#getstartposition)|İlk öğenin konumunu döndürür.|
|[CMap:: InitHashTable](#inithashtable)|Karma tabloyu başlatır ve boyutunu belirtir.|
|[CMap:: IsEmpty](#isempty)|Boş eşleme koşulunu sınar (öğe yok).|
|[CMap:: Lookup](#lookup)|Verilen bir anahtara eşlenen değeri arar.|
|[CMap::P GetFirstAssoc](#pgetfirstassoc)|İlk öğeye bir işaretçi döndürür.|
|[CMap::P GetNextAssoc](#pgetnextassoc)|Yineleme için bir sonraki öğeye bir işaretçi alır.|
|[CMap::P arama](#plookup)|Değeri belirtilen değerle eşleşen bir anahtara bir işaretçi döndürür.|
|[CMap:: RemoveAll](#removeall)|Tüm öğeleri bu eşlemden kaldırır.|
|[CMap:: RemoveKey](#removekey)|Anahtar tarafından belirtilen öğeyi kaldırır.|
|[CMap:: SetAt](#setat)|Haritaya bir öğe ekler; eşleşen bir anahtar bulunursa varolan bir öğeyi değiştirir.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CMap:: işleci \[\]](#operator_at)|Map içine bir öğe ekler — için işleç değiştirme `SetAt` .|

## <a name="remarks"></a>Açıklamalar

Haritaya anahtar-değer çifti (öğe) ekledikten sonra, ona erişmek için anahtarı kullanarak çifti etkin bir şekilde alabilir veya silebilirsiniz. Ayrıca haritadaki tüm öğelerin üzerinde de yineleme yapabilirsiniz.

Girişlere alternatif erişim için, konum türünde bir değişken kullanılır. Bir girişi "hatırlayabilmeniz" ve haritada yinelemek için bir konum kullanabilirsiniz. Bu yinelemenin anahtar değere göre sıralı olduğunu düşünebilirsiniz; Bu değildir. Alınan öğelerin sırası belirsiz.

Bu sınıfın bazı üye işlevleri, sınıfının çoğu kullanımları için özelleştirilmek zorunda olan genel yardımcı işlevlerini çağırır `CMap` . **MFC başvurusunun** makrolar ve Genel bölümünde [koleksiyon sınıfı Yardımcıları](../../mfc/reference/collection-class-helpers.md) bölümüne bakın.

`CMap` öğelerinin serileştirilmesi ve dökümünü desteklemek için [CObject:: Serialize](../../mfc/reference/cobject-class.md#serialize) geçersiz kılar. Bir harita kullanarak bir arşive depolanıyorsa `Serialize` , her harita öğesi sırayla serileştirilir. `SerializeElements`Yardımcı işlevin varsayılan uygulama bit düzeyinde bir yazma işlemi yapar. Veya diğer Kullanıcı tanımlı türlerden türetilmiş işaretçi koleksiyon öğelerinin serileştirilmesi hakkında daha fazla bilgi için `CObject` bkz. [nasıl yapılır: Type-Safe koleksiyonu oluşturma](../../mfc/how-to-make-a-type-safe-collection.md).

Haritadaki ayrı öğelerin (anahtarlar ve değerler) bir tanılama dökümünden birine ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük bir değere ayarlamanız gerekir.

Bir `CMap` nesne silindiğinde veya öğeleri kaldırıldığında, her ikisi de anahtarlar ve değerler kaldırılır.

Harita sınıf türetme, liste türetmeye benzer. Özel amaçlı liste sınıfının türeme şekli için bkz. Makale [koleksiyonları](../../mfc/collections.md) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtempl. h

## <a name="cmapcmap"></a><a name="cmap"></a> CMap:: CMap

Boş bir harita oluşturur.

```
CMap(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Haritayı uzatmak için bellek ayırma ayrıntı düzeyini belirtir.

### <a name="remarks"></a>Açıklamalar

Eşleme büyüdükçe, bellek *nBlockSize* girdileri birimlerinde ayrılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#56](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]

## <a name="cmapcpair"></a><a name="cpair"></a> CMap:: CPair

İlişkili nesnenin bir anahtar değerini ve değerini içerir.

### <a name="remarks"></a>Açıklamalar

Bu sınıf [CMap](../../mfc/reference/cmap-class.md)içinde iç içe bir yapıdır.

Yapı iki alandan oluşur:

- `key` Anahtar türünün gerçek değeri.

- `value` İlişkili nesnenin değeri.

[CMap::P Lookup](#plookup), [cmap::P GetFirstAssoc](#pgetfirstassoc)ve [CMap::P GetNextAssoc](#pgetnextassoc)öğesinden dönüş değerlerini depolamak için kullanılır.

### <a name="example"></a>Örnek

Kullanım örneği için bkz. [CMap için örnek::P arama](#plookup).

## <a name="cmapgetcount"></a><a name="getcount"></a> CMap:: GetCount

Eşlemedeki öğelerin sayısını alır.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe sayısı.

### <a name="example"></a>Örnek

[CMap:: Lookup](#lookup)örneğine bakın.

## <a name="cmapgethashtablesize"></a><a name="gethashtablesize"></a> CMap:: GetHashTableSize

Harita için karma tablodaki öğelerin sayısını belirler.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Karma tablodaki öğelerin sayısı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#57](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]

## <a name="cmapgetnextassoc"></a><a name="getnextassoc"></a> CMap:: GetNextAssoc

Konumundaki Map öğesini alır `rNextPosition` ve ardından `rNextPosition` haritadaki bir sonraki öğeye başvuracak şekilde günceller.

```cpp
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>Parametreler

*rNextPosition*<br/>
Previous veya Call tarafından döndürülen bir konum değerine bir başvuru belirtir `GetNextAssoc` `GetStartPosition` .

*ANAHTAR*<br/>
Harita anahtarının türünü belirten şablon parametresi.

*rKey*<br/>
Alınan öğenin döndürülen anahtarını belirtir.

*VALUE*<br/>
Harita değerinin türünü belirten şablon parametresi.

*Başvurusuna*<br/>
Alınan öğenin döndürülen değerini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, haritadaki tüm öğeler arasında yineleme için en yararlı seçenektir. Konum sırasının, anahtar değer sırasıyla aynı olması gerekmediğini unutmayın.

Alınan öğe haritada son ise, *rNextPosition* yenı değeri null olarak ayarlanır.

### <a name="example"></a>Örnek

[CMap:: SetAt](#setat)örneğine bakın.

## <a name="cmapgetsize"></a><a name="getsize"></a> CMap:: GetSize

Harita öğelerinin sayısını döndürür.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Haritadaki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Eşlemedeki öğelerin sayısını almak için bu yöntemi çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

## <a name="cmapgetstartposition"></a><a name="getstartposition"></a> CMap:: GetStartPosition

Bir çağrıya geçirilebileceğini bir konum değeri döndürerek bir harita yinelemesi başlatır `GetNextAssoc` .

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Haritayı yineleme için başlangıç konumunu belirten bir konum değeri; veya eşleme boşsa NULL.

### <a name="remarks"></a>Açıklamalar

Yineleme sırası öngörülebilir değil; Bu nedenle, "haritadaki ilk öğe" özel bir anlam içermez.

### <a name="example"></a>Örnek

[CMap:: SetAt](#setat)örneğine bakın.

## <a name="cmapinithashtable"></a><a name="inithashtable"></a> CMap:: InitHashTable

Karma tabloyu başlatır.

```cpp
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUE);
```

### <a name="parameters"></a>Parametreler

*Diyez boyutu*<br/>
Karma tablodaki girdi sayısı.

*bAllocNow*<br/>
DOĞRU ise, başlatma sonrasında karma tabloyu ayırır; Aksi takdirde tablo gerektiğinde ayrılır.

### <a name="remarks"></a>Açıklamalar

En iyi performansı elde etmek için, karma tablo boyutu bir asal sayı olmalıdır. Çakışmaları en aza indirmek için boyut, beklenen en büyük veri kümesinden yaklaşık yüzde 20 daha büyük olmalıdır.

### <a name="example"></a>Örnek

[CMap:: Lookup](#lookup)örneğine bakın.

## <a name="cmapisempty"></a><a name="isempty"></a> CMap:: IsEmpty

Haritanın boş olup olmadığını belirler.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu harita hiçbir öğe içermiyorsa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[CMap:: RemoveAll](#removeall)örneğine bakın.

## <a name="cmaplookup"></a><a name="lookup"></a> CMap:: Lookup

Verilen bir anahtara eşlenen değeri arar.

```
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>Parametreler

*ARG_KEY*<br/>
*Anahtar* değerinin türünü belirten şablon parametresi.

*anahtar*<br/>
Aranacak öğeyi tanımlayan anahtarı belirtir.

*VALUE*<br/>
Aranacak değerin türünü belirtir.

*Başvurusuna*<br/>
Aranan değeri alır.

### <a name="return-value"></a>Dönüş Değeri

Öğe bulunursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`Lookup` verilen anahtarla tam olarak eşleşen bir anahtarla Map öğesini hızlı bir şekilde bulmak için bir karma algoritması kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

## <a name="cmapoperator--"></a><a name="operator_at"></a> CMap:: operator []

Üye işlevi için uygun bir değiştirme `SetAt` .

```
VALUE& operator[](arg_key key);
```

### <a name="parameters"></a>Parametreler

*VALUE*<br/>
Harita değerinin türünü belirten şablon parametresi.

*ARG_KEY*<br/>
Anahtar değerinin türünü belirten şablon parametresi.

*anahtar*<br/>
Eşlemedeki değeri almak için kullanılan anahtar.

### <a name="remarks"></a>Açıklamalar

Bu nedenle, yalnızca bir atama ifadesinin (bir l-değeri) sol tarafında kullanılabilir. Belirtilen anahtara sahip bir eşleme öğesi yoksa, yeni bir öğe oluşturulur.

Haritada bir anahtarın bulunamaması olasılığı olduğu için bu işlece "sağ taraf" (r-değer) eşdeğeri yoktur. `Lookup`Öğe alımı için üye işlevini kullanın.

### <a name="example"></a>Örnek

[CMap:: Lookup](#lookup)örneğine bakın.

## <a name="cmappgetfirstassoc"></a><a name="pgetfirstassoc"></a> CMap::P GetFirstAssoc

Map nesnesinin ilk girişini döndürür.

```
const CPair* PGetFirstAssoc() const;
CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>Dönüş Değeri

Haritadaki ilk girdinin işaretçisi; bkz. [CMap:: CPair](#cpair). Haritada hiçbir giriş yoksa değer NULL olur.

### <a name="remarks"></a>Açıklamalar

Map nesnesindeki ilk öğeyi bir işaretçi döndürmek için bu işlevi çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#59](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]

## <a name="cmappgetnextassoc"></a><a name="pgetnextassoc"></a> CMap::P GetNextAssoc

*Passocrec* tarafından işaret edilen harita öğesini alır.

```
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;

CPair *PGetNextAssoc(const CPair* pAssocRet);
```

### <a name="parameters"></a>Parametreler

*pAssocRet*<br/>
Önceki bir [PGetNextAssoc](#pgetnextassoc) veya CMap tarafından döndürülen bir eşleme girişine işaret eder [::P GetFirstAssoc](#pgetfirstassoc) çağrısı.

### <a name="return-value"></a>Dönüş Değeri

Haritada bir sonraki girdiye yönelik bir işaretçi; bkz. [CMap:: CPair](#cpair). Öğe haritada son ise değer NULL olur.

### <a name="remarks"></a>Açıklamalar

Haritadaki tüm öğeler arasında yinelemek için bu yöntemi çağırın. Çağrısı olan ilk öğeyi alın `PGetFirstAssoc` ve sonra öğesine yapılan birbirini izleyen çağrılar ile eşlemeyi yineleyin `PGetNextAssoc` .

### <a name="example"></a>Örnek

CMAP örneğine bakın [::P GetFirstAssoc](#pgetfirstassoc).

## <a name="cmapplookup"></a><a name="plookup"></a> CMap::P arama

Verilen bir anahtarla eşlenen değeri bulur.

```
const CPair* PLookup(ARG_KEY key) const;
CPair* PLookup(ARG_KEY key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak öğenin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Anahtar yapısına yönelik bir işaretçi; bkz. [CMap:: CPair](#cpair). Eşleşme bulunmazsa `CMap::PLookup` null değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Verilen anahtarla tam olarak eşleşen bir anahtarla bir map öğesi aramak için bu yöntemi çağırın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]

## <a name="cmapremoveall"></a><a name="removeall"></a> CMap:: RemoveAll

Genel yardımcı işlevini çağırarak bu haritadaki tüm değerleri kaldırır `DestructElements` .

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Eşleme zaten boşsa işlev doğru şekilde çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]

## <a name="cmapremovekey"></a><a name="removekey"></a> CMap:: RemoveKey

Sağlanan anahtara karşılık gelen eşleme girişini arar; anahtar bulunursa, girdiyi kaldırır.

```
BOOL RemoveKey(ARG_KEY key);
```

### <a name="parameters"></a>Parametreler

*ARG_KEY*<br/>
Anahtarın türünü belirten şablon parametresi.

*anahtar*<br/>
Kaldırılacak öğe için anahtar.

### <a name="return-value"></a>Dönüş Değeri

Giriş bulunursa ve başarıyla kaldırılmışsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`DestructElements`Yardımcı işlevi girişi kaldırmak için kullanılır.

### <a name="example"></a>Örnek

[CMap:: SetAt](#setat)örneğine bakın.

## <a name="cmapsetat"></a><a name="setat"></a> CMap:: SetAt

Birincil, haritaya bir öğe eklemek anlamına gelir.

```cpp
void SetAt(ARG_KEY key, ARG_VALUE newValue);
```

### <a name="parameters"></a>Parametreler

*ARG_KEY*<br/>
*Anahtar* parametresinin türünü belirten şablon parametresi.

*anahtar*<br/>
Yeni öğenin anahtarını belirtir.

*ARG_VALUE*<br/>
*NewValue* parametresinin türünü belirten şablon parametresi.

*Değer*<br/>
Yeni öğenin değerini belirtir.

### <a name="remarks"></a>Açıklamalar

İlk olarak, anahtar aranır. Anahtar bulunursa, ilgili değer değiştirilir; Aksi halde yeni bir anahtar-değer çifti oluşturulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek toplama](../../overview/visual-cpp-samples.md)<br/>
[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
