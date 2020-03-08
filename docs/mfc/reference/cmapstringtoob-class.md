---
title: CMapStringToOb sınıfı
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
ms.openlocfilehash: b56e9052533269ba62d248312f07ac16db71bf4a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78876380"
---
# <a name="cmapstringtoob-class"></a>CMapStringToOb sınıfı

Benzersiz `CString` nesnelerini `CObject` işaretçilere eşleyen sözlük toplama sınıfı.

## <a name="syntax"></a>Sözdizimi

```
class CMapStringToOb : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMapStringToOb:: CMapStringToOb](#cmapstringtoob)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMapStringToOb:: GetCount](#getcount)|Bu haritadaki öğelerin sayısını döndürür.|
|[CMapStringToOb:: GetHashTableSize](#gethashtablesize)|Karma tablodaki geçerli öğe sayısını belirler.|
|[CMapStringToOb:: GetNextAssoc](#getnextassoc)|Yineleme için bir sonraki öğeyi alır.|
|[CMapStringToOb:: GetSize](#getsize)|Bu haritadaki öğelerin sayısını döndürür.|
|[CMapStringToOb:: GetStartPosition](#getstartposition)|İlk öğenin konumunu döndürür.|
|[CMapStringToOb:: HashKey](#hashkey)|Belirtilen anahtarın karma değerini hesaplar.|
|[CMapStringToOb:: InitHashTable](#inithashtable)|Karma tabloyu başlatır.|
|[CMapStringToOb:: IsEmpty](#isempty)|Boş eşleme koşulunu sınar (öğe yok).|
|[CMapStringToOb:: Lookup](#lookup)|Void işaretçi tuşuna bağlı olarak void bir işaretçi arar. İşaret ettiği varlık değil işaretçi değeri, anahtar karşılaştırması için kullanılır.|
|[CMapStringToOb:: LookupKey](#lookupkey)|Belirtilen anahtar değeriyle ilişkili anahtara bir başvuru döndürür.|
|[CMapStringToOb:: RemoveAll](#removeall)|Tüm öğeleri bu eşlemden kaldırır.|
|[CMapStringToOb:: RemoveKey](#removekey)|Anahtar tarafından belirtilen öğeyi kaldırır.|
|[CMapStringToOb:: SetAt](#setat)|Haritaya bir öğe ekler; eşleşen bir anahtar bulunursa varolan bir öğeyi değiştirir.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CMapStringToOb:: operator \[ \]](#operator_at)|Map içine bir öğe ekler — `SetAt`için işleç değiştirme.|

## <a name="remarks"></a>Açıklamalar

Haritaya bir `CString`- `CObject*` çiftini (öğe) ekledikten sonra, bir dize veya bir `CString` değeri anahtar olarak kullanarak çift etkili bir şekilde alabilir veya silebilirsiniz. Ayrıca haritadaki tüm öğelerin üzerinde de yineleme yapabilirsiniz.

Tüm harita çeşitlemelerdeki alternatif giriş erişimi için konum türünde bir değişken kullanılır. Bir girişi "hatırlayabilmeniz" ve haritada yinelemek için bir konum kullanabilirsiniz. Bu yinelemenin anahtar değere göre sıralı olduğunu düşünebilirsiniz; Bu değildir. Alınan öğelerin sırası belirsiz.

`CMapStringToOb`, öğelerinin serileştirilmesi ve dökümünü desteklemek için `IMPLEMENT_SERIAL` makrosunu içerir. Bir eşleme bir arşive depolanıyorsa, aşırı yüklenmiş ekleme ( **<<** ) işleci veya `Serialize` member işleviyle birlikte her öğe sırayla serileştirilir.

Haritadaki ayrı öğelerin (`CString` değeri ve `CObject` içeriği) bir tanılama dökümünden birine ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük bir değere ayarlamanız gerekir.

`CMapStringToOb` nesne silindiğinde veya öğeleri kaldırıldığında, `CString` nesneler ve `CObject` işaretçileri kaldırılır. `CObject` işaretçileri tarafından başvurulan nesneler yok edilmez.

Harita sınıf türetme, liste türetmeye benzer. Özel amaçlı liste sınıfının türeme şekli için bkz. Makale [koleksiyonları](../../mfc/collections.md) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToOb`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll. h

##  <a name="cmapstringtoob"></a>CMapStringToOb:: CMapStringToOb

Boş bir `CString``CObject*` haritası oluşturur.

```
CMapStringToOb(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Haritayı uzatmak için bellek ayırma ayrıntı düzeyini belirtir.

### <a name="remarks"></a>Açıklamalar

Eşleme büyüdükçe, bellek *nBlockSize* girdileri birimlerinde ayrılır.

Aşağıdaki tabloda, `CMapStringToOb:: CMapStringToOb`benzer diğer üye işlevleri gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**CMapPtrToPtr (INT_PTR** `nBlockSize` **= 10);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**CMapPtrToWord (INT_PTR** `nBlockSize` **= 10);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**CMapStringToPtr (INT_PTR** `nBlockSize` **= 10);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CMapStringToString (INT_PTR** `nBlockSize` **= 10);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CMapWordToOb (INT_PTR** `nBlockSize` **= 10);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Mapwordtoptr (INT_PTR** `nBlockSize` **= 10);**|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#63](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfının listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) .

##  <a name="getcount"></a>CMapStringToOb:: GetCount

Haritada kaç öğe olduğunu belirler.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu haritadaki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda, `CMapStringToOb::GetCount`benzer diğer üye işlevleri gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetCount () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetCount () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetCount () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetCount () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetCount () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetCount () const;**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfının listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCollections#64](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]

##  <a name="gethashtablesize"></a>CMapStringToOb:: GetHashTableSize

Karma tablodaki geçerli öğe sayısını belirler.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Karma tablodaki öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda, `CMapStringToOb::GetHashTableSize`benzer diğer üye işlevleri gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT GetHashTableSize () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT GetHashTableSize () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT GetHashTableSize () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT GetHashTableSize () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT GetHashTableSize () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT GetHashTableSize () const;**|

##  <a name="getnextassoc"></a>CMapStringToOb:: GetNextAssoc

*RNextPosition*konumundaki Map öğesini alır, ardından *rNextPosition* öğesini haritadaki bir sonraki öğeye başvuracak şekilde güncelleştirir.

```
void GetNextAssoc(
    POSITION& rNextPosition,
    CString& rKey,
    CObject*& rValue) const;
```

### <a name="parameters"></a>Parametreler

*rNextPosition*<br/>
Önceki bir `GetNextAssoc` veya `GetStartPosition` çağrısı tarafından döndürülen bir konum değerine bir başvuru belirtir.

*rKey*<br/>
Alınan öğenin döndürülen anahtarını belirtir (bir dize).

*Başvurusuna*<br/>
Alınan öğenin döndürülen değerini belirtir (bir `CObject` işaretçisi). Bu parametre hakkında daha fazla bilgi için bkz. açıklamalar.

### <a name="remarks"></a>Açıklamalar

Bu işlev, haritadaki tüm öğeler arasında yineleme için en yararlı seçenektir. Konum sırasının, anahtar değer sırasıyla aynı olması gerekmediğini unutmayın.

Alınan öğe haritada son ise, *rNextPosition* yenı değeri null olarak ayarlanır.

*Rvalue* parametresi için, aşağıdaki örnekte gösterildiği gibi, nesne türünü, derleyicisinin gerektirdiği **&CObject\*** atamalısınız.

[!code-cpp[NVC_MFCCollections#65](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]

Bu, şablonlara göre haritalar için `GetNextAssoc` true değildir.

Aşağıdaki tabloda, `CMapStringToOb::GetNextAssoc`benzer diğer üye işlevleri gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void GetNextAssoc (konum &** *rnextposition* **, void\*&** *rKey* **, void\*&** *rvalue* **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void GetNextAssoc (konum &** *rNextPosition* **, void\*&** *rKey* **, Word &** *rvalue* **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void GetNextAssoc (konum &** *rNextPosition* **, CString &** *rKey* **, void\*&** *rvalue* **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void GetNextAssoc (konum &** *rNextPosition* **, CString &** *rKey* **, CString &** *rvalue* **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void GetNextAssoc (konum &** *rNextPosition* **, Word &** *rKey* **, CObject\*&** *rvalue* **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void GetNextAssoc (konum &** *rNextPosition* **, Word &** *rKey* **, void\*&** *rvalue* **) const;**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfının listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCollections#66](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
Lisa : a CAge at $4724 11
Marge : a CAge at $47A8 35
Homer : a CAge at $4766 36
Bart : a CAge at $45D4 13
```

##  <a name="getsize"></a>CMapStringToOb:: GetSize

Harita öğelerinin sayısını döndürür.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Haritadaki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Eşlemedeki öğelerin sayısını almak için bu yöntemi çağırın.

Aşağıdaki tabloda, `CMapStringToOb::GetSize`benzer diğer üye işlevleri gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetSize () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetSize () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetSize () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetSize () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetSize () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetSize () const;**|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#67](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]

##  <a name="getstartposition"></a>CMapStringToOb:: GetStartPosition

Bir `GetNextAssoc` çağrısına geçirilebileceğini bir konum değeri döndürerek bir harita yinelemesi başlatır.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Haritayı yineleme için başlangıç konumunu belirten bir konum değeri; veya eşleme boşsa NULL.

### <a name="remarks"></a>Açıklamalar

Yineleme sırası öngörülebilir değil; Bu nedenle, "haritadaki ilk öğe" özel bir anlam içermez.

Aşağıdaki tabloda, `CMapStringToOb::GetStartPosition`benzer diğer üye işlevleri gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Konum GetStartPosition () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Konum GetStartPosition () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Konum GetStartPosition () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Konum GetStartPosition () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Konum GetStartPosition () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Konum GetStartPosition () const;**|

### <a name="example"></a>Örnek

[CMapStringToOb:: GetNextAssoc](#getnextassoc)örneğine bakın.

##  <a name="hashkey"></a>CMapStringToOb:: HashKey

Belirtilen anahtarın karma değerini hesaplar.

```
UINT HashKey(LPCTSTR key) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Karma değeri hesaplanacak olan anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtarın karma değeri

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda, `CMapStringToOb::HashKey`benzer diğer üye işlevleri gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT HashKey (void** <strong>\*</strong> `key` **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT HashKey (void** <strong>\*</strong> `key` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT HashKey (LPCTSTR** `key` **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT HashKey (LPCTSTR** `key` **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT HashKey (WORD** `key` **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT HashKey (WORD** `key` **) const;**|

##  <a name="inithashtable"></a>CMapStringToOb:: InitHashTable

Karma tabloyu başlatır.

```
void InitHashTable(
    UINT hashSize,
    BOOL bAllocNow = TRUE);
```

### <a name="parameters"></a>Parametreler

*Diyez boyutu*<br/>
Karma tablodaki girdi sayısı.

*bAllocNow*<br/>
DOĞRU ise, başlatma sonrasında karma tabloyu ayırır; Aksi takdirde tablo gerektiğinde ayrılır.

### <a name="remarks"></a>Açıklamalar

En iyi performansı elde etmek için, karma tablo boyutu bir asal sayı olmalıdır. Çakışmaları en aza indirmek için boyut, beklenen en büyük veri kümesinden yaklaşık yüzde 20 daha büyük olmalıdır.

Aşağıdaki tabloda, `CMapStringToOb::InitHashTable`benzer diğer üye işlevleri gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, bool** `bAllocNow` **= true);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void InitHashTable (UINT** `hashSize` **, bool** `bAllocNow` **= true);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void InitHashTable (UINT** `hashSize` **, bool** `bAllocNow` **= true);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, bool** `bAllocNow` **= true);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void InitHashTable (UINT** `hashSize` **, bool** `bAllocNow` **= true);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, bool** `bAllocNow` **= true);**|

##  <a name="isempty"></a>CMapStringToOb:: IsEmpty

Haritanın boş olup olmadığını belirler.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu harita hiçbir öğe içermiyorsa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[RemoveAll](#removeall)için örneğe bakın.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda **CMapStringToOb:: IsEmpty**şuna benzer diğer üye işlevleri gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL IsEmpty () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL IsEmpty () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL IsEmpty () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL IsEmpty () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL IsEmpty () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL IsEmpty () const;**|

##  <a name="lookup"></a>CMapStringToOb:: Lookup

`CString` değerine göre `CObject` bir işaretçi döndürür.

```
BOOL Lookup(
    LPCTSTR key,
    CObject*& rValue) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak öğeyi tanımlayan dize anahtarını belirtir.

*Başvurusuna*<br/>
Aranan öğeden döndürülen değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Öğe bulunursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`Lookup`, tam olarak eşleşen bir anahtarla Map öğesini hızlı bir şekilde bulmak için bir karma algoritması kullanır (`CString` değeri).

Aşağıdaki tabloda, `CMapStringToOb::LookUp`benzer diğer üye işlevleri gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Bool Lookup (void** <strong>\*</strong> `key` **, void\*&** `rValue` **) sabit;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Bool arama (void** <strong>\*</strong> `key` **, Word &** `rValue` **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Bool Lookup (LPCTSTR** `key` **, void\*&** `rValue` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Bool arama (LPCTSTR** `key` **, CString &** `rValue` **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Bool arama (WORD** `key` **, CObject\*&** `rValue` **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Bool arama (WORD** `key` **, void\*&** `rValue` **) const;**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfının listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCollections#68](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]

##  <a name="lookupkey"></a>CMapStringToOb:: LookupKey

Belirtilen anahtar değeriyle ilişkili anahtara bir başvuru döndürür.

```
BOOL LookupKey(
    LPCTSTR key,
    LPCTSTR& rKey) const;
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak öğeyi tanımlayan dize anahtarını belirtir.

*rKey*<br/>
İlişkili anahtara başvuru.

### <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İlişkili öğe haritadan kaldırıldıktan sonra veya eşleme yok edildikten sonra kullanılırsa, anahtar başvurusunun kullanılması güvenli değildir.

Aşağıdaki tabloda, `CMapStringToOb:: LookupKey`benzer diğer üye işlevleri gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Bool LookupKey (lpctstr** `key` **, lpctstr &** `rKey` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Bool LookupKey (lpctstr** `key` **, lpctstr &** `rKey` **) const;**|

##  <a name="operator_at"></a>CMapStringToOb:: operator []

`SetAt` member işlevinin uygun bir alternatifi.

```
CObject*& operator[ ](lpctstr key);
```

### <a name="return-value"></a>Dönüş Değeri

`CObject` nesnesine bir işaretçiye yönelik başvuru; ya da eşleme boşsa veya *anahtar* Aralık dışında olduğunda null olur.

### <a name="remarks"></a>Açıklamalar

Bu nedenle, yalnızca bir atama ifadesinin (bir l-değeri) sol tarafında kullanılabilir. Belirtilen anahtara sahip bir eşleme öğesi yoksa, yeni bir öğe oluşturulur.

Haritada bir anahtarın bulunamaması olasılığı olduğu için bu işlece "sağ taraf" (r-değer) eşdeğeri yoktur. Öğe alımı için `Lookup` üye işlevini kullanın.

Aşağıdaki tabloda, `CMapStringToOb::operator []`benzer diğer üye işlevleri gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|<strong>void\*& işleci\[] (void \*</strong> `key` **\);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Sözcük & işleci\[] (void** <strong>\*</strong> `key` **\);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void\*& işleci\[] (LPCTSTR** `key` **\);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CString & işleci\[] (LPCTSTR** `key` **\);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CObject\*& işleci\[] (word** `key` **\);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void\*& işleci\[] (word** `key` **\);**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfının listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCollections#72](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
Operator [] example: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $4A02 11
[Bart] = a CAge at $497E 13
```

##  <a name="removeall"></a>CMapStringToOb:: RemoveAll

Tüm öğeleri bu eşlemden kaldırır ve `CString` anahtar nesnelerini yok eder.

```
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Her anahtar tarafından başvurulan `CObject` nesneleri yok edilmez. Başvurulan `CObject` nesnelerinin yok edileceği olmadığından emin değilseniz `RemoveAll` işlevi bellek sızıntılarına neden olabilir.

Eşleme zaten boşsa işlev doğru şekilde çalışır.

Aşağıdaki tabloda, `CMapStringToOb::RemoveAll`benzer diğer üye işlevleri gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void RemoveAll ();**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void RemoveAll ();**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void RemoveAll ();**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void RemoveAll ();**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void RemoveAll ();**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void RemoveAll ();**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfının listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCollections#69](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]

##  <a name="removekey"></a>CMapStringToOb:: RemoveKey

Sağlanan anahtara karşılık gelen eşleme girişini arar; anahtar bulunursa, girdiyi kaldırır.

```
BOOL RemoveKey(LPCTSTR key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Harita arama için kullanılan dizeyi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Giriş bulunursa ve başarıyla kaldırılmışsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CObject` nesne başka bir yerde silinmediği takdirde bu, bellek sızıntılarına neden olabilir.

Aşağıdaki tabloda, `CMapStringToOb::RemoveKey`benzer diğer üye işlevleri gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Bool RemoveKey (void** <strong>\*</strong> `key` **);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Bool RemoveKey (void** <strong>\*</strong> `key` **);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Bool RemoveKey (LPCTSTR** `key` **);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Bool RemoveKey (LPCTSTR** `key` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Bool RemoveKey (WORD** `key` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Bool RemoveKey (WORD** `key` **);**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfının listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCollections#70](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
RemoveKey example: A CMapStringToOb with 3 elements
[Marge] = a CAge at $49A0 35
[Homer] = a CAge at $495E 36
[Bart] = a CAge at $4634 13
```

##  <a name="setat"></a>CMapStringToOb:: SetAt

Birincil, haritaya bir öğe eklemek anlamına gelir.

```
void SetAt(
    LPCTSTR key,
    CObject* newValue);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Yeni öğenin anahtarı olan dizeyi belirtir.

*Değer*<br/>
Yeni öğenin değeri olan `CObject` işaretçisini belirtir.

### <a name="remarks"></a>Açıklamalar

İlk olarak, anahtar aranır. Anahtar bulunursa, ilgili değer değiştirilir; Aksi halde yeni bir anahtar-değer öğesi oluşturulur.

Aşağıdaki tabloda, `CMapStringToOb::SetAt`benzer diğer üye işlevleri gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**SetAt void (void** <strong>\*</strong> `key` **, void** <strong>\*</strong> `newValue` **);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**SetAt void (void** <strong>\*</strong> `key` **, sözcük** `newValue` **);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**SetAt void (LPCTSTR** `key` **, void** <strong>\*</strong> `newValue` **);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**SetAt void (lpctstr** `key` **, lpctstr** `newValue` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**SetAt void (WORD** `key` **, CObject** <strong>\*</strong> `newValue` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**SetAt void (WORD** `key` **, void** <strong>\*</strong> `newValue` **);**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfının listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) .

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
[CMapStringToString Sınıfı](../../mfc/reference/cmapstringtostring-class.md)<br/>
[CMapWordToOb Sınıfı](../../mfc/reference/cmapwordtoob-class.md)<br/>
[CMapWordToPtr Sınıfı](../../mfc/reference/cmapwordtoptr-class.md)
