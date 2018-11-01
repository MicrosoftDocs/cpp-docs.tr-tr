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
ms.openlocfilehash: 29f60748f8ff0681a3a73e31cbb049c27c3a45be
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656179"
---
# <a name="cmapstringtoob-class"></a>CMapStringToOb sınıfı

Benzersiz eşleyen sözlük koleksiyon sınıfı `CString` nesneleri için `CObject` işaretçileri.

## <a name="syntax"></a>Sözdizimi

```
class CMapStringToOb : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMapStringToOb::CMapStringToOb](#cmapstringtoob)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMapStringToOb::GetCount](#getcount)|Bu haritada öğelerin sayısını döndürür.|
|[CMapStringToOb::GetHashTableSize](#gethashtablesize)|Geçerli bir karma tablo içindeki öğelerin sayısını belirler.|
|[CMapStringToOb::GetNextAssoc](#getnextassoc)|Yineleme için sonraki öğeyi alır.|
|[CMapStringToOb::GetSize](#getsize)|Bu haritada öğelerin sayısını döndürür.|
|[CMapStringToOb::GetStartPosition](#getstartposition)|İlk öğenin konumunu döndürür.|
|[CMapStringToOb::HashKey](#hashkey)|Belirtilen bir anahtarı karma değerini hesaplar.|
|[CMapStringToOb::InitHashTable](#inithashtable)|Karma tablo başlatır.|
|[CMapStringToOb::IsEmpty](#isempty)|(Öğe yok) boş-map koşulu sınar.|
|[CMapStringToOb::Lookup](#lookup)|Void bir işaretçi void işaretçisine anahtara göre arar. İşaretçi değeri değil, işaret varlık anahtar karşılaştırma için kullanılır.|
|[CMapStringToOb::LookupKey](#lookupkey)|Belirtilen anahtar değeriyle ilişkili anahtar için bir başvuru döndürür.|
|[CMapStringToOb::RemoveAll](#removeall)|Tüm öğeleri bu eşlemden kaldırır.|
|[CMapStringToOb::RemoveKey](#removekey)|Bir anahtar tarafından belirtilen bir öğeyi kaldırır.|
|[CMapStringToOb::SetAt](#setat)|Haritayı bir öğe ekler; eşleşen bir anahtar bulunursa, var olan öğenin yerini alır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CMapStringToOb::operator [ ]](#operator_at)|Haritayı bir öğe ekler; işleci alternatifi için `SetAt`.|

## <a name="remarks"></a>Açıklamalar

Siz ekledikten sonra bir `CString` -  `CObject*` çifti (öğesi) eşlemeye verimli bir şekilde alabileceğiniz veya bir dize kullanarak çifti silmek veya `CString` bir anahtar değeri. Eşlem içindeki tüm öğeleri üzerinde yineleyebilirsiniz.

KONUM türünde bir değişken, tüm harita çeşitlemeleri alternatif giriş erişmek için kullanılır. Bir konum "unutmayın bir giriş için" ve eşlemesi üzerinden yineleme yapmak için kullanabilirsiniz. Bu yineleme anahtar değere göre sıralı olduğunu düşünebilirsiniz; Bu değil. Alınan öğe dizisi belirsiz.

`CMapStringToOb` içerir `IMPLEMENT_SERIAL` seri hale getirme ve alt öğeleri dökme desteklemek için makrosu. Bir eşleme bir arşiv, aşırı yüklenmiş ekleme ile depolanıyorsa her öğesi sırayla seri ( **<<**) işleci veya `Serialize` üye işlevi.

Bir eşlem içindeki tek tek öğelerine tanılama dökümü ihtiyacınız varsa ( `CString` değeri ve `CObject` içeriği), 1 veya daha büyük derinliği döküm bağlam ayarlamanız gerekir.

Olduğunda bir `CMapStringToOb` nesnesi silindiğinde veya ne zaman öğeleri kaldırılır, `CString` nesneleri ve `CObject` işaretçileri kaldırılır. Tarafından başvurulan nesneleri `CObject` işaretçileri yok edilmez.

Map sınıfı türetme için liste türetme benzerdir. Makaleye göz atın [koleksiyonları](../../mfc/collections.md) özel amaçlı listesi sınıfının türetme bir gösterim.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToOb`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcoll.h

##  <a name="cmapstringtoob"></a>  CMapStringToOb::CMapStringToOb

Boş bir yapıları `CString`- için - `CObject*` eşleme.

```
CMapStringToOb(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Harita genişletmek için bellek ayırma ayrıntı düzeyi belirtir.

### <a name="remarks"></a>Açıklamalar

Harita büyüdükçe, birimleri cinsinden ayrılan bellek *nBlockSize* girdileri.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CMapStringToOb:: CMapStringToOb`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**CMapPtrToPtr( INT_PTR** `nBlockSize` **= 10 );**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**CMapPtrToWord( INT_PTR** `nBlockSize` **= 10 );**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**CMapStringToPtr( INT_PTR** `nBlockSize` **= 10 );**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CMapStringToString( INT_PTR** `nBlockSize` **= 10 );**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CMapWordToOb( INT_PTR** `nBlockSize` **= 10 );**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**MapWordToPtr( INT_PTR** `nBlockSize` **= 10 );**|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#63](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

##  <a name="getcount"></a>  CMapStringToOb::GetCount

Haritada kaç öğenin olduğunu belirler.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu eşlem içindeki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CMapStringToOb::GetCount`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetCount () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetCount () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetCount () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetCount () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetCount () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetCount () const;**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#64](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]

##  <a name="gethashtablesize"></a>  CMapStringToOb::GetHashTableSize

Geçerli bir karma tablo içindeki öğelerin sayısını belirler.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Karma tablodaki öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CMapStringToOb::GetHashTableSize`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT GetHashTableSize () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT GetHashTableSize () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT GetHashTableSize () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT GetHashTableSize () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT GetHashTableSize () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT GetHashTableSize () const;**|

##  <a name="getnextassoc"></a>  CMapStringToOb::GetNextAssoc

Harita öğe alır *rNextPosition*, ardından güncelleştirmeleri *rNextPosition* haritadaki sonraki öğeye başvurmak için.

```
void GetNextAssoc(
    POSITION& rNextPosition,
    CString& rKey,
    CObject*& rValue) const;
```

### <a name="parameters"></a>Parametreler

*rNextPosition*<br/>
Bir önceki tarafından döndürülen bir konum değeri bir başvuru belirtir `GetNextAssoc` veya `GetStartPosition` çağırın.

*rKey*<br/>
Alınan öğenin (dize) döndürülen anahtarını belirtir.

*rValue*<br/>
Alınan öğenin döndürülen değeri belirtir (bir `CObject` işaretçisi). Açıklamalar Bu parametre hakkında daha fazla bilgi için bkz.

### <a name="remarks"></a>Açıklamalar

Bu işlev bir eşlem içindeki tüm öğeleri arasında yineleme için kullanışlıdır. Konumu sıranın mutlaka anahtar değeri serisi ile aynı olmadığını unutmayın.

Alınan öğe eşlem içindeki son öğesinin yeni değeri ise *rNextPosition* NULL olarak ayarlandı.

İçin *rValue* parametresi, nesne türüne mutlaka **CObject\*&**, olduğu ne derleyicisi gerektirir, aşağıdaki örnekte gösterildiği gibi:

[!code-cpp[NVC_MFCCollections#65](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]

Bu doğru değildir `GetNextAssoc` şablonları temel alan eşlemeleri.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CMapStringToOb::GetNextAssoc`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void GetNextAssoc (konum &** *rNextPosition* **, void\* &**  *rKey* **, void\* &**  *rValue* **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void GetNextAssoc (konum &** *rNextPosition* **, void\* &**  *rKey* **, WORD ve** *rValue* **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void GetNextAssoc (konum &** *rNextPosition* **, CString &** *rKey* **, void\* &**  *rValue* **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void GetNextAssoc (konum &** *rNextPosition* **, CString &** *rKey* **, CString &** *rValue* **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void GetNextAssoc (konum &** *rNextPosition* **, sözcük &** *rKey* **, CObject\* &**  *rValue* **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void GetNextAssoc (konum &** *rNextPosition* **, sözcük &** *rKey* **, void\* &**  *rValue* **) const;**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#66](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]

Bu program sonuçları aşağıdaki gibidir:

```Output
Lisa : a CAge at $4724 11
Marge : a CAge at $47A8 35
Homer : a CAge at $4766 36
Bart : a CAge at $45D4 13
```

##  <a name="getsize"></a>  CMapStringToOb::GetSize

Harita öğelerin sayısını döndürür.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eşlem içindeki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Eşlem içindeki öğelerin sayısını almak için bu yöntemi çağırın.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CMapStringToOb::GetSize`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetSize () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetSize () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetSize () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetSize () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetSize () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetSize () const;**|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#67](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]

##  <a name="getstartposition"></a>  CMapStringToOb::GetStartPosition

Harita yineleme, geçirilebilir bir konum değeri döndürerek başlar bir `GetNextAssoc` çağırın.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Harita yineleme için bir başlangıç konumunu belirten bir konum değeri; ya da bir eşlem boşsa, NULL.

### <a name="remarks"></a>Açıklamalar

Yineleme sırası tahmin edilebilir değil; Bu nedenle, "eşlem içindeki ilk öğeyi" özel bir önemi yoktur.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CMapStringToOb::GetStartPosition`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**GetStartPosition (const) getirin;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**GetStartPosition (const) getirin;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**GetStartPosition (const) getirin;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**GetStartPosition (const) getirin;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**GetStartPosition (const) getirin;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**GetStartPosition (const) getirin;**|

### <a name="example"></a>Örnek

Örneğin bakın [CMapStringToOb::GetNextAssoc](#getnextassoc).

##  <a name="hashkey"></a>  CMapStringToOb::HashKey

Belirtilen bir anahtarı karma değerini hesaplar.

```
UINT HashKey(LPCTSTR key) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Karma değeri hesaplanacak olan anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtarın karma değeri

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CMapStringToOb::HashKey`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT HashKey (void** <strong>\*</strong> `key` **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT HashKey (void** <strong>\*</strong> `key` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT HashKey (LPCTSTR** `key` **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT HashKey (LPCTSTR** `key` **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT HashKey (WORD** `key` **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT HashKey (WORD** `key` **) const;**|

##  <a name="inithashtable"></a>  CMapStringToOb::InitHashTable

Karma tablo başlatır.

```
void InitHashTable(
    UINT hashSize,
    BOOL bAllocNow = TRUE);
```

### <a name="parameters"></a>Parametreler

*hashSize*<br/>
Girdi karma tablosunda sayısı.

*bAllocNow*<br/>
TRUE ise başlatma sırasında karma tablo ayırır; Aksi takdirde tablo gerektiğinde ayrılır.

### <a name="remarks"></a>Açıklamalar

En iyi performans için bir karma tablo boyutu olmalıdır. Çakışmaları en aza indirmek için boyutu yaklaşık yüzde 20 oranında daha büyük beklenen veri kümesi daha büyük olmalıdır.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CMapStringToOb::InitHashTable`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|

##  <a name="isempty"></a>  CMapStringToOb::IsEmpty

Harita boş olup olmadığını belirler.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu harita hiçbir öğe içeren olursa sıfır dışı; Aksi durumda 0.

### <a name="example"></a>Örnek

Örneğin bakın [RemoveAll](#removeall).

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tablo diğer üye benzer işlevleri gösterir **CMapStringToOb:: IsEmpty**.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL IsEmpty () const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL IsEmpty () const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL IsEmpty () const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL IsEmpty () const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL IsEmpty () const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL IsEmpty () const;**|

##  <a name="lookup"></a>  CMapStringToOb::Lookup

Döndürür bir `CObject` işaretçi temel alan bir `CString` değeri.

```
BOOL Lookup(
    LPCTSTR key,
    CObject*& rValue) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Bakılacak öğeyi tanımlayan dize anahtar belirtir.

*rValue*<br/>
Aranan yukarı öğesinden döndürülen değeri belirtir.

### <a name="return-value"></a>Dönüş Değeri

Öğesi bulundu; olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

`Lookup` eşleme öğesi tam olarak eşleşen bir anahtar ile hızla bulmak için bir karma algoritma kullanır ( `CString` değeri).

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CMapStringToOb::LookUp`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL arama (void** <strong>\*</strong> `key` **, void\* &**  `rValue` **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL arama (void** <strong>\*</strong> `key` **, sözcük &** `rValue` **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL arama (LPCTSTR** `key` **, void\* &**  `rValue` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL arama (LPCTSTR** `key` **, CString &** `rValue` **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL arama (WORD** `key` **, CObject\* &**  `rValue` **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL arama (WORD** `key` **, void\* &**  `rValue` **) const;**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#68](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]

##  <a name="lookupkey"></a>  CMapStringToOb::LookupKey

Belirtilen anahtar değeriyle ilişkili anahtar için bir başvuru döndürür.

```
BOOL LookupKey(
    LPCTSTR key,
    LPCTSTR& rKey) const;
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Bakılacak öğeyi tanımlayan dize anahtar belirtir.

*rKey*<br/>
Başvuru ilişkili anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtar bulunduysa sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir anahtara bir başvuru kullanarak ilişkili öğeyi bir eşlemden kaldırıldıktan sonra kullandıysanız veya eşleme yok edildi sonra güvenli değildir.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CMapStringToOb:: LookupKey`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL LookupKey (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL LookupKey (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|

##  <a name="operator_at"></a>  CMapStringToOb::operator [ ]

Uygun bir alternatif için `SetAt` üye işlevi.

```
CObject*& operator[ ](lpctstr key);
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçiye başvuru bir `CObject` nesne; veya bir eşlem boşsa, boş veya *anahtar* je mimo rozsah.

### <a name="remarks"></a>Açıklamalar

Bu nedenle yalnızca (lvalue) atama deyiminin sol tarafında kullanılabilir. Ardından, belirtilen anahtara sahip herhangi bir harita öğe varsa, yeni bir öğe oluşturulur.

Yoktur yok "sağ tarafında" (r) bu operatörü için eşdeğeri anahtar haritada bulunamamış olabilir bir olasılık olduğundan. Kullanım `Lookup` öğesi alma için üye işlevi.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CMapStringToOb::operator []`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|<strong>void\*& işleci\[] (void \*</strong>  `key`  **\);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**SÖZCÜK & işleci\[] (void** <strong>\*</strong> `key`  **\);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void\*& işleci\[] (lpctstr** `key`  **\);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CString & işleci\[] (lpctstr** `key`  **\);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CObject\*& işleci\[] (word** `key`  **\);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void\*& işleci\[] (word** `key`  **\);**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#72](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]

Bu program sonuçları aşağıdaki gibidir:

```Output
Operator [] example: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $4A02 11
[Bart] = a CAge at $497E 13
```

##  <a name="removeall"></a>  CMapStringToOb::RemoveAll

Tüm öğeleri bu eşlemden kaldırır ve yok eder `CString` anahtar nesneleri.

```
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

`CObject` Her anahtar tarafından başvurulan nesneler yok edilmez. `RemoveAll` İşlevi, bellek sızıntıları açabilir, başvurulan emin değil, `CObject` nesneler yok edilir.

Eşleme zaten boşsa, işlev düzgün çalışır.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CMapStringToOb::RemoveAll`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void RemoveAll( );**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void RemoveAll( );**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void RemoveAll( );**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void RemoveAll( );**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void RemoveAll( );**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void RemoveAll( );**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#69](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]

##  <a name="removekey"></a>  CMapStringToOb::RemoveKey

Sağlanan anahtara karşılık gelen eşleme girişi arar; Ardından, anahtar bulunursa, giriş kaldırır.

```
BOOL RemoveKey(LPCTSTR key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Harita araması için kullanılan dizeyi belirtir.

### <a name="return-value"></a>Dönüş Değeri

Giriş bulundu ve başarıyla kaldırıldı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu, bellek sızıntılarının neden olabilir `CObject` nesne başka bir yerde silinmez.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CMapStringToOb::RemoveKey`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL RemoveKey (void** <strong>\*</strong> `key` **);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL RemoveKey (void** <strong>\*</strong> `key` **);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL RemoveKey (LPCTSTR** `key` **);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL RemoveKey (LPCTSTR** `key` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL RemoveKey (WORD** `key` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL RemoveKey (WORD** `key` **);**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#70](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]

Bu program sonuçları aşağıdaki gibidir:

```Output
RemoveKey example: A CMapStringToOb with 3 elements
[Marge] = a CAge at $49A0 35
[Homer] = a CAge at $495E 36
[Bart] = a CAge at $4634 13
```

##  <a name="setat"></a>  CMapStringToOb::SetAt

Bir eşlem içinde bir öğe eklemek birincil anlamına gelir.

```
void SetAt(
    LPCTSTR key,
    CObject* newValue);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Yeni öğenin anahtarı dize belirtir.

*newValue*<br/>
Belirtir `CObject` , yeni öğenin değerini işaretçi.

### <a name="remarks"></a>Açıklamalar

İlk olarak, anahtar aranır. Anahtar bulunursa, karşılık gelen değeri değiştirildikten sonra; Aksi takdirde, yeni bir anahtar-değer öğesi oluşturulur.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CMapStringToOb::SetAt`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void SetAt (void** <strong>\*</strong> `key` **, void** <strong>\*</strong> `newValue` **);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void SetAt (void** <strong>\*</strong> `key` **, WORD** `newValue` **);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void SetAt (LPCTSTR** `key` **, void** <strong>\*</strong> `newValue` **);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void SetAt (LPCTSTR** `key` **, LPCTSTR** `newValue` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void SetAt (WORD** `key` **, CObject** <strong>\*</strong> `newValue` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void SetAt (WORD** `key` **, void** <strong>\*</strong> `newValue` **);**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#71](../../mfc/codesnippet/cpp/cmapstringtoob-class_10.cpp)]

Bu program sonuçları aşağıdaki gibidir:

```Output
before Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $493C 11
[Bart] = a CAge at $4654 13
after Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $49C0 12
[Bart] = a CAge at $4654 13
```

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMapPtrToPtr Sınıfı](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[CMapPtrToWord Sınıfı](../../mfc/reference/cmapptrtoword-class.md)<br/>
[CMapStringToPtr Sınıfı](../../mfc/reference/cmapstringtoptr-class.md)<br/>
[CMapStringToString Sınıfı](../../mfc/reference/cmapstringtostring-class.md)<br/>
[CMapWordToOb Sınıfı](../../mfc/reference/cmapwordtoob-class.md)<br/>
[CMapWordToPtr Sınıfı](../../mfc/reference/cmapwordtoptr-class.md)
