---
title: Cmapstringtoob Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMapStringToOb
- AFXCOLL/CMapStringToOb
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
helpviewer_keywords:
- CMapStringToOb [MFC], CMapStringToOb
- CMapStringToOb [MFC], GetCount
- CMapStringToOb [MFC], GetHashTableSize
- CMapStringToOb [MFC], GetNextAssoc
- CMapStringToOb [MFC], GetSize
- CMapStringToOb [MFC], GetStartPosition
- CMapStringToOb [MFC], HashKey
- CMapStringToOb [MFC], InitHashTable
- CMapStringToOb [MFC], IsEmpty
- CMapStringToOb [MFC], Lookup
- CMapStringToOb [MFC], LookupKey
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
ms.openlocfilehash: 12de7bd72f643f08cebf948634703172d6725ce6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370114"
---
# <a name="cmapstringtoob-class"></a>Cmapstringtoob Sınıfı

Benzersiz `CString` nesneleri işaretçilerle `CObject` eşleyen bir sözlük koleksiyonu sınıfı.

## <a name="syntax"></a>Sözdizimi

```
class CMapStringToOb : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Cmapstringtoob::cmapstringtoob](#cmapstringtoob)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Cmapstringtoob::GetCount](#getcount)|Bu haritadaki öğe sayısını döndürür.|
|[CMapStringToOb::GetHashTableSize](#gethashtablesize)|Karma tablodaki geçerli öğe sayısını belirler.|
|[CMapStringToOb::GetNextAssoc](#getnextassoc)|Yinelenmenin bir sonraki öğesini alır.|
|[Cmapstringtoob::Getsize](#getsize)|Bu haritadaki öğe sayısını döndürür.|
|[Cmapstringtoob::Getstartposition](#getstartposition)|İlk öğenin konumunu döndürür.|
|[CMapStringToOb::HashKey](#hashkey)|Belirtilen anahtarın karma değerini hesaplar.|
|[CMapStringToOb::InitHashTable](#inithashtable)|Karma tabloyu başharfe ait hale.|
|[Cmapstringtoob::Boş](#isempty)|Boş eşlemi koşulu (öğe yok) için testler.|
|[CMapStringToOb::Arama](#lookup)|Void pointer tuşuna göre geçersiz bir işaretçi arar. İşaretçi değeri, işaret aldığı varlık değil, anahtar karşılaştırması için kullanılır.|
|[CMapStringToOb::LookupKey](#lookupkey)|Belirtilen anahtar değeriyle ilişkili anahtara bir başvuru verir.|
|[Cmapstringtoob::RemoveAll](#removeall)|Bu haritadaki tüm öğeleri kaldırır.|
|[Cmapstringtoob::RemoveKey](#removekey)|Anahtar tarafından belirtilen bir öğeyi kaldırır.|
|[Cmapstringtoob::Setat](#setat)|Haritaya bir öğe ekler; eşleşen bir anahtar bulunursa varolan bir öğenin yerini alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CMapStringToOb::operatör \[\]](#operator_at)|Eşama bir öğe ekler — operatör ikamesi `SetAt`için .|

## <a name="remarks"></a>Açıklamalar

Eşama `CString` -  `CObject*` bir çift (öğe) ekledikten sonra, bir dize veya anahtar olarak bir `CString` değer kullanarak çifti verimli bir şekilde alabilir veya silebilirsiniz. Ayrıca haritadaki tüm öğeleri yineleyebilirsiniz.

Tüm harita varyasyonlarında alternatif giriş erişimi için tür POSITION değişkeni kullanılır. Bir girişi "hatırlamak" ve harita üzerinden tekrarlamak için bir KONUM kullanabilirsiniz. Bu yinelemenin anahtar değerine göre sıralı olduğunu düşünebilirsiniz; Öyle değil. Alınan öğelerin sırası belirsizdir.

`CMapStringToOb`öğelerinin serileştirilmesini `IMPLEMENT_SERIAL` ve dampingini desteklemek için makroyu içerir. Bir harita bir arşive depolanırsa, aşırı yüklenmiş ekleme ( **<<**) işleci veya `Serialize` üye işlevle her öğe sırayla seri hale getirilir.

Haritadaki tek tek öğelerin `CString` (değer ve `CObject` içindekiler) tanılama dökümüne ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Bir `CMapStringToOb` nesne silindiğinde veya öğeleri kaldırıldığında, `CString` nesneler ve `CObject` işaretçiler kaldırılır. `CObject` İşaretçiler tarafından başvurulan nesneler yok edilmez.

Harita sınıf türetme liste türetme benzer. Özel amaçlı bir liste sınıfının türemiş bir illüstrasyon için makale [Koleksiyonları](../../mfc/collections.md) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CMapStringToOb`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll.h

## <a name="cmapstringtoobcmapstringtoob"></a><a name="cmapstringtoob"></a>Cmapstringtoob::cmapstringtoob

Boş `CString`bir `CObject*` harita oluşturur.

```
CMapStringToOb(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Haritayı genişletmek için bellek ayırma parçalılığını belirtir.

### <a name="remarks"></a>Açıklamalar

Harita büyüdükçe, bellek *nBlockSize* girişleri birimlerine ayrılır.

Aşağıdaki tabloda `CMapStringToOb:: CMapStringToOb`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**CMapPtrToPtr( INT_PTR** `nBlockSize` **= 10 );**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**CMapPtrToWord( INT_PTR** `nBlockSize` **= 10 );**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**CMapStringToPtr( INT_PTR** `nBlockSize` **= 10 );**|
|[CmapstringtoString](../../mfc/reference/cmapstringtostring-class.md)|**CmapstringTostring( INT_PTR** `nBlockSize` **= 10 );**|
|[CMapWordToob](../../mfc/reference/cmapwordtoob-class.md)|**CMapWordToob( INT_PTR** `nBlockSize` **= 10 );**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**MapWordToPtr( INT_PTR** `nBlockSize` **= 10 );**|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#63](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

## <a name="cmapstringtoobgetcount"></a><a name="getcount"></a>Cmapstringtoob::GetCount

Haritada kaç öğe olduğunu belirler.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu haritadaki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda `CMapStringToOb::GetCount`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetCount( ) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetCount( ) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetCount( ) const;**|
|[CmapstringtoString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetCount( ) const;**|
|[CMapWordToob](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetCount( ) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetCount( ) const;**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#64](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]

## <a name="cmapstringtoobgethashtablesize"></a><a name="gethashtablesize"></a>CMapStringToOb::GetHashTableSize

Karma tablodaki geçerli öğe sayısını belirler.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Karma tablodaki öğe sayısını verir.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda `CMapStringToOb::GetHashTableSize`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT GetHashTableSize( ) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT GetHashTableSize( ) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT GetHashTableSize( ) const;**|
|[CmapstringtoString](../../mfc/reference/cmapstringtostring-class.md)|**UINT GetHashTableSize( ) const;**|
|[CMapWordToob](../../mfc/reference/cmapwordtoob-class.md)|**UINT GetHashTableSize( ) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT GetHashTableSize( ) const;**|

## <a name="cmapstringtoobgetnextassoc"></a><a name="getnextassoc"></a>CMapStringToOb::GetNextAssoc

*rNextPosition'ta*harita öğesini alır, ardından haritadaki bir sonraki öğeye başvurmak için *rNextPosition'ı* güncelleştirir.

```
void GetNextAssoc(
    POSITION& rNextPosition,
    CString& rKey,
    CObject*& rValue) const;
```

### <a name="parameters"></a>Parametreler

*rNextPosition*<br/>
Bir önceki `GetNextAssoc` veya `GetStartPosition` çağrı tarafından döndürülen bir POSITION değeriiçin bir başvuru belirtir.

*rAnahtar*<br/>
Alınan öğenin (bir dize) döndürülen anahtarını belirtir.

*Rvalue*<br/>
Alınan öğenin (bir `CObject` işaretçi) döndürülen değerini belirtir. Bu parametre hakkında daha fazla şey için Açıklamalar'a bakın.

### <a name="remarks"></a>Açıklamalar

Bu işlev, haritadaki tüm öğeleri yineetmek için en yararlıdır. Konum sırasının anahtar değer dizisiyle aynı olması gerekmediğini unutmayın.

Alınan öğe haritadaki son öğeyse, *rNextPosition'un* yeni değeri NULL olarak ayarlanır.

*rValue* parametresi için, aşağıdaki örnekte gösterildiği gibi, derleyicinin gerektirdiği nesne türünü **\*CObject'e**attığınızdan emin olun:

[!code-cpp[NVC_MFCCollections#65](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]

Bu, şablonlara `GetNextAssoc` dayalı haritalar için geçerli değildir.

Aşağıdaki tabloda `CMapStringToOb::GetNextAssoc`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void GetNextAssoc( POSITION&** *rNextPosition* **, void\* ** *rKey* **, void\* ** *rValue* **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void GetNextAssoc( POZISYON&** *rNextPosition* **, void\* ** *rKey* **, WORD&** *rValue* **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void GetNextAssoc( POZISYON&** *rNextPosition* **, CString&** *rKey* **, void\* ** *rValue* **) const;**|
|[CmapstringtoString](../../mfc/reference/cmapstringtostring-class.md)|**void GetNextAssoc( POZISYON&** *rNextPosition* **, CString&** *rKey* **, CString&** *rValue* **) const;**|
|[CMapWordToob](../../mfc/reference/cmapwordtoob-class.md)|**void GetNextAssoc( POZISYON&** *rNextPosition* **, WORD&** *rKey* **, CObject\* ** *rValue* **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void GetNextAssoc( POZISYON&** *rNextPosition* **, WORD&** *rKey* **, void\* ** *rValue* **) const;**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#66](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
Lisa : a CAge at $4724 11
Marge : a CAge at $47A8 35
Homer : a CAge at $4766 36
Bart : a CAge at $45D4 13
```

## <a name="cmapstringtoobgetsize"></a><a name="getsize"></a>Cmapstringtoob::Getsize

Harita öğelerinin sayısını verir.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Haritadaki öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Haritadaki öğe sayısını almak için bu yöntemi arayın.

Aşağıdaki tabloda `CMapStringToOb::GetSize`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetSize( ) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetSize( ) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetSize( ) const;**|
|[CmapstringtoString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetSize( ) const;**|
|[CMapWordToob](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetSize( ) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetSize( ) const;**|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#67](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]

## <a name="cmapstringtoobgetstartposition"></a><a name="getstartposition"></a>Cmapstringtoob::Getstartposition

`GetNextAssoc` Bir çağrıya geçirilebilen bir POSITION değerini döndürerek bir harita yinelemesini başlatır.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Haritayı yineleyen bir başlangıç konumunu gösteren bir KONUM değeri; veya harita boşsa NULL.

### <a name="remarks"></a>Açıklamalar

Yineleme sırası tahmin edilebilir değildir; bu nedenle, "haritadaki ilk öğenin" özel bir önemi yoktur.

Aşağıdaki tabloda `CMapStringToOb::GetStartPosition`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**POSITION GetStartPosition( ) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**POSITION GetStartPosition( ) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**POSITION GetStartPosition( ) const;**|
|[CmapstringtoString](../../mfc/reference/cmapstringtostring-class.md)|**POSITION GetStartPosition( ) const;**|
|[CMapWordToob](../../mfc/reference/cmapwordtoob-class.md)|**POSITION GetStartPosition( ) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**POSITION GetStartPosition( ) const;**|

### <a name="example"></a>Örnek

[CMapStringToOb örneğine bakın:GetNextAssoc](#getnextassoc).

## <a name="cmapstringtoobhashkey"></a><a name="hashkey"></a>CMapStringToOb::HashKey

Belirtilen anahtarın karma değerini hesaplar.

```
UINT HashKey(LPCTSTR key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Karma değeri hesaplanacak anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtarın karma değeri

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda `CMapStringToOb::HashKey`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT HashKey (void)** <strong>\*</strong> `key` **const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT HashKey (void)** <strong>\*</strong> `key` **const;**|
|[CmapstringtoString](../../mfc/reference/cmapstringtostring-class.md)|**UINT HashKey (LPCTSTR)** `key` **const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT HashKey (LPCTSTR)** `key` **const;**|
|[CMapWordToob](../../mfc/reference/cmapwordtoob-class.md)|**UINT HashKey ( WORD** `key` **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT HashKey ( WORD** `key` **) const;**|

## <a name="cmapstringtoobinithashtable"></a><a name="inithashtable"></a>CMapStringToOb::InitHashTable

Karma tabloyu başharfe ait hale.

```
void InitHashTable(
    UINT hashSize,
    BOOL bAllocNow = TRUE);
```

### <a name="parameters"></a>Parametreler

*hashSize*<br/>
Karma tablodaki giriş sayısı.

*bAllocNow*<br/>
DOĞRUysa, başlangıç üzerine karma tablo ayırır; aksi takdirde tablo gerektiğinde ayrılır.

### <a name="remarks"></a>Açıklamalar

En iyi performans için karma tablo boyutu bir asal sayı olmalıdır. Çakışmayı en aza indirmek için, boyutun beklenen en büyük veri kümesinden yaklaşık yüzde 20 daha büyük olması gerekir.

Aşağıdaki tabloda `CMapStringToOb::InitHashTable`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= DOĞRU );**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= DOĞRU );**|
|[CmapstringtoString](../../mfc/reference/cmapstringtostring-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= DOĞRU );**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= DOĞRU );**|
|[CMapWordToob](../../mfc/reference/cmapwordtoob-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= DOĞRU );**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void InitHashTable( UINT** `hashSize` **, BOOL** `bAllocNow` **= DOĞRU );**|

## <a name="cmapstringtoobisempty"></a><a name="isempty"></a>Cmapstringtoob::Boş

Haritanın boş olup olmadığını belirler.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu harita hiçbir öğe içeriyorsa sıfır olmayan; aksi takdirde 0.

### <a name="example"></a>Örnek

[RemoveAll](#removeall)için örneğe bakın.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki **tabloda CMapStringToOb**benzer diğer üye işlevleri gösterir:: Boş .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL Boş( ) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL Boş( ) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL Boş( ) const;**|
|[CmapstringtoString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL Boş( ) const;**|
|[CMapWordToob](../../mfc/reference/cmapwordtoob-class.md)|**BOOL Boş( ) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL Boş( ) const;**|

## <a name="cmapstringtooblookup"></a><a name="lookup"></a>CMapStringToOb::Arama

Bir `CObject` `CString` değere dayalı bir işaretçi döndürür.

```
BOOL Lookup(
    LPCTSTR key,
    CObject*& rValue) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak öğeyi tanımlayan dize anahtarını belirtir.

*Rvalue*<br/>
Geri dönen değeri, ara"daki öğeden belirtir.

### <a name="return-value"></a>Dönüş Değeri

Öğe bulunursa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`Lookup`harita öğesini tam olarak eşleşen bir anahtarla (değer) `CString` hızlı bir şekilde bulmak için karma algoritması kullanır.

Aşağıdaki tabloda `CMapStringToOb::LookUp`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL Arama ( void** <strong>\*</strong> `key` **, void\* ** `rValue` ) **const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL Lookup( void** <strong>\*</strong> `key` **, WORD&** `rValue` **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL Arama ( LPCTSTR** `key` **, void\* ** `rValue` ) **const;**|
|[CmapstringtoString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL Arama ( LPCTSTR** `key` **, CString&** `rValue` **) const;**|
|[CMapWordToob](../../mfc/reference/cmapwordtoob-class.md)|**BOOL Arama ( WORD** `key` **,\* CObject** `rValue` ) **const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL Lookup ( WORD** `key` **, void\* ** `rValue` ) **const;**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#68](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]

## <a name="cmapstringtooblookupkey"></a><a name="lookupkey"></a>CMapStringToOb::LookupKey

Belirtilen anahtar değeriyle ilişkili anahtara bir başvuru verir.

```
BOOL LookupKey(
    LPCTSTR key,
    LPCTSTR& rKey) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak öğeyi tanımlayan dize anahtarını belirtir.

*rAnahtar*<br/>
İlişkili anahtara başvuru.

### <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İlişkili öğe haritadan kaldırıldıktan sonra veya harita yok edildikten sonra kullanıldığında bir anahtara başvuru kullanmak güvenli değildir.

Aşağıdaki tabloda `CMapStringToOb:: LookupKey`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL LookupKey ( LPCTSTR** `key` **, LPCTSTR&** `rKey` **) const;**|
|[CmapstringtoString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL LookupKey ( LPCTSTR** `key` **, LPCTSTR&** `rKey` **) const;**|

## <a name="cmapstringtooboperator--"></a><a name="operator_at"></a>CMapStringToOb::operatör [ ]

Üye işlev için `SetAt` uygun bir yedek.

```
CObject*& operator[ ](lpctstr key);
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CObject` nesneye işaretçi başvurusu; veya harita boşsa veya *anahtar* kapsama alanı dışındaysa NULL.

### <a name="remarks"></a>Açıklamalar

Böylece yalnızca bir atama deyiminin (l-değeri) sol tarafında kullanılabilir. Belirtilen anahtara sahip bir eş öğesi yoksa, yeni bir öğe oluşturulur.

Haritada bir anahtarın bulunmama olasılığı olduğundan, bu işleçiçin "sağ taraf" (r-değeri) yoktur. Öğe `Lookup` almak için üye işlevi kullanın.

Aşağıdaki tabloda `CMapStringToOb::operator []`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|<strong>void\*&\[işleticisi \* ](void</strong> `key` ** \);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**WORD&\[operatörü ](void** <strong>\*</strong> `key` ** \);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void\*&\[operatörü ](lpctstr** `key` ** \);**|
|[CmapstringtoString](../../mfc/reference/cmapstringtostring-class.md)|**CString&\[operatörü ](lpctstr** `key` ** \);**|
|[CMapWordToob](../../mfc/reference/cmapwordtoob-class.md)|**CObject\*&\[işleci ](word** `key` ** \);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void\*&\[işleticisi ](word** `key` ** \);**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#72](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
Operator [] example: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $4A02 11
[Bart] = a CAge at $497E 13
```

## <a name="cmapstringtoobremoveall"></a><a name="removeall"></a>Cmapstringtoob::RemoveAll

Bu haritadaki tüm öğeleri kaldırır ve `CString` anahtar nesneleri yok eder.

```
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Her `CObject` anahtar tarafından başvurulan nesneler yok edilmez. Başvurulan `RemoveAll` `CObject` nesnelerin yok edilmesini sağlamazsanız işlev bellek sızıntılarına neden olabilir.

Harita zaten boşsa işlev düzgün çalışır.

Aşağıdaki tabloda `CMapStringToOb::RemoveAll`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void RemoveAll( );**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void RemoveAll( );**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void RemoveAll( );**|
|[CmapstringtoString](../../mfc/reference/cmapstringtostring-class.md)|**void RemoveAll( );**|
|[CMapWordToob](../../mfc/reference/cmapwordtoob-class.md)|**void RemoveAll( );**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void RemoveAll( );**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#69](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]

## <a name="cmapstringtoobremovekey"></a><a name="removekey"></a>Cmapstringtoob::RemoveKey

Verilen anahtara karşılık gelen harita girişini arar; sonra, anahtar bulunursa, girişi kaldırır.

```
BOOL RemoveKey(LPCTSTR key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Harita araması için kullanılan dizeyi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Giriş bulundu ve başarıyla kaldırıldı sıfır değil; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CObject` Nesne başka bir yerde silinmezse bu bellek sızıntıları neden olabilir.

Aşağıdaki tabloda `CMapStringToOb::RemoveKey`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL RemoveKey (boşluk);** <strong>\*</strong> `key` **);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL RemoveKey (boşluk);** <strong>\*</strong> `key` **);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL RemoveKey (LPCTSTR);** `key` **);**|
|[CmapstringtoString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL RemoveKey (LPCTSTR);** `key` **);**|
|[CMapWordToob](../../mfc/reference/cmapwordtoob-class.md)|**BOOL RemoveKey (WORD);** `key` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL RemoveKey (WORD);** `key` **);**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#70](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
RemoveKey example: A CMapStringToOb with 3 elements
[Marge] = a CAge at $49A0 35
[Homer] = a CAge at $495E 36
[Bart] = a CAge at $4634 13
```

## <a name="cmapstringtoobsetat"></a><a name="setat"></a>Cmapstringtoob::Setat

Birincil bir öğeyi bir haritaya eklemek anlamına gelir.

```
void SetAt(
    LPCTSTR key,
    CObject* newValue);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Yeni öğenin anahtarı olan dizeyi belirtir.

*Newvalue*<br/>
Yeni öğenin `CObject` değerini işaretçi belirtir.

### <a name="remarks"></a>Açıklamalar

İlk olarak, anahtar aranır. Anahtar bulunursa, karşılık gelen değer değiştirilir; aksi takdirde yeni bir anahtar değeri öğesi oluşturulur.

Aşağıdaki tabloda `CMapStringToOb::SetAt`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void SetAt( void** <strong>\*</strong> `key` **, void** <strong>\*</strong> `newValue` **);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void SetAt( void** <strong>\*</strong> `key` **, WORD** `newValue` **);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void SetAt( LPCTSTR** `key` **, void** <strong>\*</strong> `newValue` **);**|
|[CmapstringtoString](../../mfc/reference/cmapstringtostring-class.md)|**void SetAt( LPCTSTR** `key` **, LPCTSTR** `newValue` **);**|
|[CMapWordToob](../../mfc/reference/cmapwordtoob-class.md)|**void SetAt( WORD** `key` **, CObject** <strong>\*</strong> `newValue` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void SetAt( WORD** `key` **, void** <strong>\*</strong> `newValue` **);**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#71](../../mfc/codesnippet/cpp/cmapstringtoob-class_10.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
before Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $493C 11
[Bart] = a CAge at $4654 13
after Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $49C0 12
[Bart] = a CAge at $4654 13
```

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMapPtrToPtr Sınıfı](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[CMapPtrToWord Sınıfı](../../mfc/reference/cmapptrtoword-class.md)<br/>
[CMapStringToPtr Sınıfı](../../mfc/reference/cmapstringtoptr-class.md)<br/>
[Cmapstringtostring Sınıfı](../../mfc/reference/cmapstringtostring-class.md)<br/>
[CMapWordToOb Sınıfı](../../mfc/reference/cmapwordtoob-class.md)<br/>
[CMapWordToPtr Sınıfı](../../mfc/reference/cmapwordtoptr-class.md)
