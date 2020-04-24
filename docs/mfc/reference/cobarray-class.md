---
title: CObArray Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CObArray
- AFXCOLL/CObArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 27894efd-2370-4776-9ed9-24a98492af17
ms.openlocfilehash: c19715f62704bfc97059421451929cbbec2506ce
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754465"
---
# <a name="cobarray-class"></a>CObArray Sınıfı

İşaretçiler dizilerini `CObject` destekler.

## <a name="syntax"></a>Sözdizimi

```
class CObArray : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CobArray::cobarray](#cobarray)|İşaretçiler için `CObject` boş bir dizi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CObArray::Ekle](#add)|Dizinin sonuna bir öğe ekler; gerekirse diziyi büyütür.|
|[CObArray::Ek](#append)|Diziye başka bir dizi ekler; gerekirse diziyi büyütür.|
|[CObArray::Kopyala](#copy)|Başka bir diziyi diziye kopyalar; gerekirse diziyi büyütür.|
|[Cobarray::elementat](#elementat)|Dizi içindeki öğe işaretçisine geçici bir başvuru verir.|
|[CObArray::FreeExtra](#freeextra)|Tüm kullanılmayan belleği geçerli üst sınır üzerinde serbest eder.|
|[CobArray::Getat](#getat)|Belirli bir dizindeki değeri döndürür.|
|[CobArray::GetCount](#getcount)|Bu dizideki öğelerin sayısını alır.|
|[CObArray::Veri Get](#getdata)|Dizideki öğelere erişim sağlar. NULL olabilir.|
|[CobArray::Getsize](#getsize)|Bu dizideki öğelerin sayısını alır.|
|[CobArray::GetUpperBound](#getupperbound)|En büyük geçerli dizini döndürür.|
|[CObArray::InsertAt](#insertat)|Belirli bir dizide bir öğe (veya başka bir dizideki tüm öğeler) ekler.|
|[CobArray::Boş](#isempty)|Dizinin boş olup olmadığını belirler.|
|[CObArray::RemoveAll](#removeall)|Bu dizideki tüm öğeleri kaldırır.|
|[CobArray::removeat](#removeat)|Belirli bir dizindeki bir öğeyi kaldırır.|
|[CobArray::Setat](#setat)|Belirli bir dizinin değerini ayarlar; dizi büyümeye izin verilmez.|
|[CobArray::setatgrow](#setatgrow)|Belirli bir dizinin değerini ayarlar; gerekirse diziyi büyütür.|
|[CobArray::Setsize](#setsize)|Bu dizide yer alan öğe sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CObArray::operatör \[\]](#operator_at)|Belirtilen dizilişte öğeyi ayarlar veya alır.|

## <a name="remarks"></a>Açıklamalar

Bu nesne dizileri C dizilerine benzer, ancak dinamik olarak küçülebilir ve gerektiği gibi büyüyebilir.

Dizi dizinleri her zaman 0 konumundan başlar. Geçerli sınırı aştığınızda üst sınırı düzeltmeye veya dizinin genişlemesine izin verip vermemeye karar verebilirsiniz. Bellek, bazı öğeler null olsa bile, üst sınıra bitişik olarak ayrılır.

Win32 altında, bir `CObArray` nesnenin boyutu yalnızca kullanılabilir bellekle sınırlıdır.

C dizisinde olduğu gibi, `CObArray` dizilimöğesinin erişim süresi sabittir ve dizi boyutundan bağımsızdır.

`CObArray`öğelerinin serileştirilmesini ve dampingini desteklemek için IMPLEMENT_SERIAL makroyu içerir. Bir dizi `CObject` işaretçi, aşırı yüklenen ekleme işleci yle veya `Serialize` üye işlevle bir arşive `CObject` depolanırsa, her öğe sırayla dizi dizilimiyle birlikte seri hale getirilir.

Bir dizideki tek `CObject` tek öğelerin dökümüne ihtiyacınız varsa, `CDumpContext` nesnenin derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Bir `CObArray` nesne silindiğinde veya öğeleri kaldırıldığında, `CObject` başvurulan nesneler değil, yalnızca işaretçiler kaldırılır.

> [!NOTE]
> Bir dizi kullanmadan `SetSize` önce, boyutunu oluşturmak ve bunun için bellek ayırmak için kullanın. `SetSize`Kullanmazsanız, dizinize öğe eklemek, dizinin sık sık yeniden tahsis edilmesine ve kopyalanmasını sağlar. Sık yeniden tahsis ve kopyalama verimsizdir ve belleği parçalayabilir.

Dizi sınıfı türetme liste türetme benzer. Özel amaçlı bir liste sınıfının türemiş ayrıntıları [için,](../../mfc/collections.md)makale Koleksiyonları'na bakın.

> [!NOTE]
> Diziyi seri hale getirmek istiyorsanız, türemiş sınıfınuzun uygulanmasında IMPLEMENT_SERIAL makroyu kullanmanız gerekir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CObArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll.h

## <a name="cobarrayadd"></a><a name="add"></a>CObArray::Ekle

Dizinin sonuna yeni bir öğe ekleyerek diziyi 1 büyütür.

```
INT_PTR Add(CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*newElement*<br/>
Bu `CObject` diziye eklenecek işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin dizin.

### <a name="remarks"></a>Açıklamalar

[SetSize](#setsize) 1'den büyük bir *nGrowBy* değeri ile kullanılmışsa, ek bellek ayrılabilir. Ancak, üst sınır sadece 1 artacaktır.

Aşağıdaki tabloda `CObArray::Add`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**INT_PTR Add (BYTE);** `newElement` **);**<br /><br /> **atmak (CMemoryException\* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR Ekle (DWORD);** `newElement` **);**<br /><br /> **atmak (CMemoryException\* );**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**INT_PTR Add (void);** <strong>\*</strong> `newElement` **);**<br /><br /> **atmak (CMemoryException\* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR Add (LPCTSTR** `newElement` **); atmak\* ( CMemoryException );**<br /><br /> **INT_PTR Add(const CString** `newElement` **&);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR Ekle (UINT);** `newElement` **);**<br /><br /> **atmak (CMemoryException\* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR Add (WORD);** `newElement` **);**<br /><br /> **atmak (CMemoryException\* );**|

### <a name="example"></a>Örnek

  Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#75](../../mfc/codesnippet/cpp/cobarray-class_1.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
Add example: A CObArray with 2 elements
[0] = a CAge at $442A 21
[1] = a CAge at $4468 40
```

## <a name="cobarrayappend"></a><a name="append"></a>CObArray::Ek

Verilen dizinin sonuna başka bir dizinin içeriğini eklemek için bu üye işlevi arayın.

```
INT_PTR Append(const CObArray& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
Diziye eklenecek öğelerin kaynağı.

### <a name="return-value"></a>Dönüş Değeri

İlk eklenen öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Diziler aynı türde olmalıdır.

Gerekirse, `Append` diziye eklenen öğeleri yerleştirmek için ek bellek ayırabilir.

Aşağıdaki tabloda `CObArray::Append`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**INT_PTR Append( const CByteArray&** *src);* **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR Append( const CDWordArray&** *src);* **);**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**INT_PTR Append( const CPtrArray&** *src);* **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR Append( const CStringArray&** *src* **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR Append(const CUIntArray&** *src);* **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR Append ( const CWordArray&** *src);* **);**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#76](../../mfc/codesnippet/cpp/cobarray-class_2.cpp)]

## <a name="cobarraycopy"></a><a name="copy"></a>CObArray::Kopyala

Aynı türdeki başka bir dizinin öğeleriyle verilen dizinin öğelerinin üzerine yazmak için bu üye işlevi arayın.

```cpp
void Copy(const CObArray& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
Diziye kopyalanacak öğelerin kaynağı.

### <a name="remarks"></a>Açıklamalar

`Copy`bellek serbest değildir; ancak, gerekirse, `Copy` diziye kopyalanan öğeleri yerleştirmek için ek bellek ayırabilir.

Aşağıdaki tabloda `CObArray::Copy`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**void Copy( const CByteArray&** *src);* **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void Copy( const CDWordArray&** *src* **);**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**void Copy( const CPtrArray&** *src* **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void Copy( const CStringArray&** *src* **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void Copy( const CUIntArray&** *src);* **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void Copy( const CWordArray&** *src* **);**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#77](../../mfc/codesnippet/cpp/cobarray-class_3.cpp)]

## <a name="cobarraycobarray"></a><a name="cobarray"></a>CobArray::cobarray

Boş `CObject` bir işaretçi dizisi oluşturuyor.

```
CObArray();
```

### <a name="remarks"></a>Açıklamalar

Dizi, aynı anda bir öğe büyür.

Aşağıdaki tabloda `CObArray::CObArray`benzer diğer yapıcılar gösterir.

|Sınıf|Oluşturucu|
|-----------|-----------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**CByteArray( );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**CDWordArray( );**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**CPtrArray( );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CStringArray( );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**CUIntArray( );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**CWordArray( );**|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#78](../../mfc/codesnippet/cpp/cobarray-class_4.cpp)]

## <a name="cobarrayelementat"></a><a name="elementat"></a>Cobarray::elementat

Dizi içindeki öğe işaretçisine geçici bir başvuru verir.

```
CObject*& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
0'dan büyük veya eşit ve döndürülen `GetUpperBound`değerden daha az veya eşit olan bir karşıcı dizin.

### <a name="return-value"></a>Dönüş Değeri

`CObject` İşaretçiye başvuru.

### <a name="remarks"></a>Açıklamalar

Diziler için sol taraftaki atama işlecinin uygulanması için kullanılır. Bunun yalnızca özel dizi işleçlerini uygulamak için kullanılması gereken gelişmiş bir işlev olduğunu unutmayın.

Aşağıdaki tabloda `CObArray::ElementAt`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**BYTE& Elementat( INT_PTR** `nIndex` **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD& Elementat ( INT_PTR** `nIndex` **);**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**void\*& Elementat(INT_PTR);** `nIndex` **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString& Elementat( INT_PTR** `nIndex` **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT& Elementat(** `nIndex` **INT_PTR);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD& Elementat( INT_PTR** `nIndex` **);**|

### <a name="example"></a>Örnek

  CObArray örneğine [bakın:GetSize](#getsize).

## <a name="cobarrayfreeextra"></a><a name="freeextra"></a>CObArray::FreeExtra

Dizi büyütülme sırasında ayrılan tüm ekstra belleği serbest eder.

```cpp
void FreeExtra();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, dizinin boyutu veya üst sınırı üzerinde hiçbir etkisi yoktur.

Aşağıdaki tabloda `CObArray::FreeExtra`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**void FreeExtra( );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void FreeExtra( );**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**void FreeExtra( );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void FreeExtra( );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void FreeExtra( );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void FreeExtra( );**|

### <a name="example"></a>Örnek

  CObArray örneğine [bakın:GetData](#getdata).

## <a name="cobarraygetat"></a><a name="getat"></a>CobArray::Getat

Belirtilen dizideki dizi öğesini döndürür.

```
CObject* GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
0'dan büyük veya eşit ve döndürülen `GetUpperBound`değerden daha az veya eşit olan bir karşıcı dizin.

### <a name="return-value"></a>Dönüş Değeri

Şu `CObject` anda bu dizinde işaretçi öğesi.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Negatif bir değer ingeçirilmesi veya döndürülen `GetUpperBound` değerden büyük bir değerin geçirilmesi başarısız bir iddiayla sonuçlanır.

Aşağıdaki tabloda `CObArray::GetAt`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**BYTE GetAt( INT_PTR)** `nIndex` **const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD GetAt ( INT_PTR)** `nIndex` **const;**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**void\* GetAt ( INT_PTR)** `nIndex` **const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString GetAt ( INT_PTR)** `nIndex` **const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT GetAt( INT_PTR)** `nIndex` **const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD GetAt ( INT_PTR)** `nIndex` **const;**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#79](../../mfc/codesnippet/cpp/cobarray-class_5.cpp)]

## <a name="cobarraygetcount"></a><a name="getcount"></a>CobArray::GetCount

Dizi öğelerinin sayısını verir.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Dizideki öğe sayısını almak için bu yöntemi çağırın. Dizinler sıfır tabanlı olduğundan, boyutu 1 en büyük dizin daha büyüktür.

Aşağıdaki tabloda `CObArray::GetCount`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetCount( ) const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetCount( ) const;**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetCount( ) const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetCount( ) const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetCount( ) const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetCount( ) const;**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#80](../../mfc/codesnippet/cpp/cobarray-class_6.cpp)]

## <a name="cobarraygetdata"></a><a name="getdata"></a>CObArray::Veri Get

Dizideki öğelere doğrudan erişim sağlamak için bu üye işlevi kullanın.

```
const CObject** GetData() const;

CObject** GetData();
```

### <a name="return-value"></a>Dönüş Değeri

`CObject` İşaretçiler dizisiiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kullanılabilir öğe yoksa, `GetData` null değeri döndürür.

Bir dizinin öğelerine doğrudan erişim daha hızlı çalışmanıza yardımcı olsa `GetData`da, ararken dikkatli olun; yaptığınız hatalar doğrudan dizinizin öğelerini etkiler.

Aşağıdaki tabloda `CObArray::GetData`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**const BYTE\* GetData( ) const; BYTE\* GetData( );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**const DWORD\* GetData( ) const;DWORD\* GetData( );**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**const\* \* void GetData( )\* \* const;void GetData( );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**const CString\* GetData( ) const; CString\* GetData( );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**const UINT\* GetData( ) const; UINT\* GetData( );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**const\* WORD GetData( ) const; WORD\* GetData( );**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#81](../../mfc/codesnippet/cpp/cobarray-class_7.cpp)]

## <a name="cobarraygetsize"></a><a name="getsize"></a>CobArray::Getsize

Dizinin boyutunu döndürür.

```
INT_PTR GetSize() const;
```

### <a name="remarks"></a>Açıklamalar

Dizinler sıfır tabanlı olduğundan, boyutu 1 en büyük dizin daha büyüktür.

Aşağıdaki tabloda `CObArray::GetSize`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetSize( ) const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetSize( ) const;**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetSize( ) const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetSize( ) const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetSize( ) const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetSize( ) const;**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#82](../../mfc/codesnippet/cpp/cobarray-class_8.cpp)]

## <a name="cobarraygetupperbound"></a><a name="getupperbound"></a>CobArray::GetUpperBound

Bu dizinin geçerli üst sınırını döndürür.

```
INT_PTR GetUpperBound() const;
```

### <a name="return-value"></a>Dönüş Değeri

Üst sınır (sıfır tabanlı) dizin.

### <a name="remarks"></a>Açıklamalar

Dizi dizinleri sıfır tabanlı olduğundan, bu işlev `GetSize`değeri 1'den daha az döndürür.

Durum `GetUpperBound( )` = -1 dizi hiçbir öğe içerdiğini gösterir.

Aşağıdaki tabloda `CObArray::GetUpperBound`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetUpperBound( ) const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetUpperBound( ) const;**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetUpperBound( ) const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetUpperBound( ) const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetUpperBound( ) const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetUpperBound( ) const;**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#83](../../mfc/codesnippet/cpp/cobarray-class_9.cpp)]

## <a name="cobarrayinsertat"></a><a name="insertat"></a>CObArray::InsertAt

Belirli bir dizide bir öğe (veya başka bir dizideki tüm öğeler) ekler.

```cpp
void InsertAt(
    INT_PTR nIndex,
    CObject* newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CObArray* pNewArray);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Tarafından döndürülen değerden büyük olabilecek bir `GetUpperBound`karşılayon dizini.

*newElement*<br/>
Bu `CObject` diziye yerleştirilecek işaretçi. Null değerinin yeni bir *öğesine* izin verilir.

*nSayısı*<br/>
Bu öğenin kaç kez eklenmesi gerekir (varsayılan olarak 1).

*nBaşlangıç Endeksi*<br/>
Tarafından döndürülen değerden büyük olabilecek bir `GetUpperBound`karşılayon dizini.

*pNewArray*<br/>
Bu diziye eklenecek öğeleri içeren başka bir dizi.

### <a name="remarks"></a>Açıklamalar

Bir dizideki `InsertAt` belirli bir diziye bir öğe (veya bir öğenin birden çok kopyası) ekler ilk sürümü. İşlemsırasında, bu dizindeki varolan öğeyi (dizini yükselterek) yukarı kaydırıyor ve üzerindeki tüm öğeleri yukarı kaydırıyor.

İkinci sürüm, *nStartIndex* konumundan `CObArray` başlayarak başka bir koleksiyondaki tüm öğeleri ekler.

İşlev, `SetAt` aksine, belirtilen bir dizi öğesi nin yerini alır ve herhangi bir öğeyi kaydırmaz.

Aşağıdaki tabloda `CObArray::InsertAt`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, BYTE** `newElement` **, int** `nCount` **= 1 );**<br /><br /> **atmak (CMemoryException\* );**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CByteArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **atmak (CMemoryException\* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, DWORD** `newElement` , **int** `nCount` **= 1 );**<br /><br /> **atmak (CMemoryException\* );**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CDWordArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **atmak (CMemoryException\* );**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, void** <strong>\*</strong> `newElement` **, int** `nCount` **= 1 );**<br /><br /> **atmak (CMemoryException\* );**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CPtrArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **atmak (CMemoryException\* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, LPCTSTR** `newElement` , **int** `nCount` **= 1 );**<br /><br /> **atmak (CMemoryException\* );**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CStringArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **atmak (CMemoryException\* );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, UINT** `newElement` , **int** `nCount` **= 1 );**<br /><br /> **atmak (CMemoryException\* );**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CUIntArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **atmak (CMemoryException\* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void InsertAt( INT_PTR** `nIndex` **, WORD** `newElement` **, int** `nCount` = 1 **);**<br /><br /> **atmak (CMemoryException\* );**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CWordArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **atmak (CMemoryException\* );**|

### <a name="example"></a>Örnek

  Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#84](../../mfc/codesnippet/cpp/cobarray-class_10.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
InsertAt example: A CObArray with 3 elements
[0] = a CAge at $45C8 21
[1] = a CAge at $4646 30
[2] = a CAge at $4606 40
```

## <a name="cobarrayisempty"></a><a name="isempty"></a>CobArray::Boş

Dizinin boş olup olmadığını belirler.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizi boşsa sıfırsız; aksi takdirde 0.

## <a name="cobarrayoperator--"></a><a name="operator_at"></a>CObArray::operator [ ]

Bu alt komut işleçleri `SetAt` ve `GetAt` işlevleri için uygun bir yedek vardır.

```
CObject*& operator[](int_ptr nindex);
CObject* operator[](int_ptr nindex) const;
```

### <a name="remarks"></a>Açıklamalar

**Const**olmayan diziler için çağrılan ilk işleç, atama deyiminin sağında (r değeri) veya sol (l-değeri) kullanılabilir. Const diziler **const** için çağrılan ikinci, yalnızca sağda kullanılabilir.

Kitaplığın Hata Ayıklama sürümü, alt yazının (atama deyiminin solunda veya sağ tarafında) sınırların dışında olduğunu ileri sürer.

Aşağıdaki tabloda `CObArray::operator []`benzer diğer işleçler gösterir.

|Sınıf|İşleç|
|-----------|--------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**BYTE& operatörü [](int_ptr;** `nindex` ** \)**<br /><br /> **BYTE operatörü [](int_ptr** `nindex` ** \) const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD& operatörü [](int_ptr;** `nindex` ** \)**<br /><br /> **DWORD işleci [](int_ptr** `nindex` ** \) const;**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**void\*& işleticisi [](int_ptr** `nindex` ** \);**<br /><br /> **void\* işletici [](int_ptr** `nindex` ** \) const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString& işleci [](int_ptr** `nindex` ** \);**<br /><br /> **CString işleci [](int_ptr** `nindex` ** \) const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT& operatörü [](int_ptr;** `nindex` ** \)**<br /><br /> **UINT işleci [](int_ptr** `nindex` ** \) const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD& operatörü [](int_ptr;** `nindex` ** \)**<br /><br /> **WORD işleci [](int_ptr** `nindex` ** \) const;**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#88](../../mfc/codesnippet/cpp/cobarray-class_11.cpp)]

## <a name="cobarrayremoveall"></a><a name="removeall"></a>CObArray::RemoveAll

Bu dizideki tüm işaretçileri kaldırır, ancak `CObject` nesneleri gerçekte silmez.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Dizi zaten boşsa, işlev yine de çalışır.

İşlev, `RemoveAll` işaretçi depolamaiçin kullanılan tüm belleği boşaltıyor.

Aşağıdaki tabloda `CObArray::RemoveAll`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**void RemoveAll( );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void RemoveAll( );**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**void RemoveAll( );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void RemoveAll( );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void RemoveAll( );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void RemoveAll( );**|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#85](../../mfc/codesnippet/cpp/cobarray-class_12.cpp)]

## <a name="cobarrayremoveat"></a><a name="removeat"></a>CobArray::removeat

Bir dizide belirli bir diziden başlayan bir veya daha fazla öğeyi kaldırır.

```cpp
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
0'dan büyük veya eşit ve döndürülen `GetUpperBound`değerden daha az veya eşit olan bir karşıcı dizin.

*nSayısı*<br/>
Kaldırılacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

İşlemde, kaldırılan öğenin (ler) üzerindeki tüm öğeleri aşağı kaydırıyor. Dizinin üst sınırını uzatır, ancak belleği boş almaz.

Kaldırma noktasının üzerindeki dizide bulunandan daha fazla öğeyi kaldırmaya çalışırsanız, kitaplığın Hata Ayıklama sürümü ileri sürüler.

İşlev `RemoveAt` işaretçiyi `CObject` diziden kaldırır, ancak nesnenin kendisini silmez.

Aşağıdaki tabloda `CObArray::RemoveAt`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** *nCount* **= 1 );**|

### <a name="example"></a>Örnek

  Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#112](../../mfc/codesnippet/cpp/cobarray-class_13.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
RemoveAt example: A CObArray with 1 elements
[0] = a CAge at $4606 40
```

## <a name="cobarraysetat"></a><a name="setat"></a>CobArray::Setat

Dizi öğesini belirtilen dizide ayarlar.

```cpp
void SetAt(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
0'dan büyük veya eşit ve döndürülen `GetUpperBound`değerden daha az veya eşit olan bir karşıcı dizin.

*newElement*<br/>
Bu diziye eklenecek nesne işaretçisi. NULL değerine izin verilir.

### <a name="remarks"></a>Açıklamalar

`SetAt`dizinin büyümesine neden olmaz. Dizinin `SetAtGrow` otomatik olarak büyümesini istiyorsanız kullanın.

Dizin değerinizin dizide geçerli bir konumu temsil ettiğinden emin olmalısınız. Sınırların dışındaysa, kitaplığın Hata Ayıklama sürümü ileri sürüler.

Aşağıdaki tabloda `CObArray::SetAt`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**void SetAt( INT_PTR** `nIndex` **, BYTE** `newElement` **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, DWORD** `newElement` **);**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, void** <strong>\*</strong> `newElement` **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, UINT** `newElement` **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, WORD** `newElement` **);**|

### <a name="example"></a>Örnek

  Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#86](../../mfc/codesnippet/cpp/cobarray-class_14.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
SetAt example: A CObArray with 2 elements
[0] = a CAge at $47E0 30
[1] = a CAge at $47A0 40
```

## <a name="cobarraysetatgrow"></a><a name="setatgrow"></a>CobArray::setatgrow

Dizi öğesini belirtilen dizide ayarlar.

```cpp
void SetAtGrow(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
0'dan büyük veya eşit bir sonsayı dizini.

*newElement*<br/>
Bu diziye eklenecek nesne işaretçisi. NULL değerine izin verilir.

### <a name="remarks"></a>Açıklamalar

Gerekirse dizi otomatik olarak büyür (diğer bir şekilde üst sınır yeni öğeyi barındıracak şekilde ayarlanır).

Aşağıdaki tabloda `CObArray::SetAtGrow`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, BYTE** `newElement` **);**<br /><br /> **atmak (CMemoryException\* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, DWORD** `newElement` **);**<br /><br /> **atmak (CMemoryException\* );**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, void** <strong>\*</strong> `newElement` **);**<br /><br /> **atmak (CMemoryException\* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**<br /><br /> **atmak (CMemoryException\* );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, UINT** `newElement` **);**<br /><br /> **atmak (CMemoryException\* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, WORD** `newElement` **);**<br /><br /> **atmak (CMemoryException\* );**|

### <a name="example"></a>Örnek

  Tüm koleksiyon örneklerinde kullanılan `CAge` sınıfın listesi için [CObList::CObList'e](../../mfc/reference/coblist-class.md#coblist) bakın.

[!code-cpp[NVC_MFCCollections#87](../../mfc/codesnippet/cpp/cobarray-class_15.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
SetAtGrow example: A CObArray with 4 elements
[0] = a CAge at $47C0 21
[1] = a CAge at $4800 40
[2] = NULL
[3] = a CAge at $4840 65
```

## <a name="cobarraysetsize"></a><a name="setsize"></a>CobArray::Setsize

Boş veya varolan bir dizinin boyutunu kurar; gerekirse bellek ayırır.

```cpp
void SetSize(
    INT_PTR nNewSize,
    INT_PTR nGrowBy = -1);
```

### <a name="parameters"></a>Parametreler

*nNewSize*<br/>
Yeni dizi boyutu (öğe sayısı). 0 değerinden büyük veya 0 değerine eşit olmalıdır.

*nGrowBy*<br/>
Boyut artışı gerekiyorsa ayrılacak en az öğe yuvası sayısı.

### <a name="remarks"></a>Açıklamalar

Yeni boyut eski boyuttan küçükse, dizi kesilir ve kullanılmayan tüm bellek serbest bırakılır. Verimlilik için, `SetSize` kullanmadan önce dizinin boyutunu ayarlamak için arayın. Bu, her öğe ekleninde diziyi yeniden tahsis etme ve kopyalama gereksinimini önler.

*nGrowBy* parametresi dizi büyürken dahili bellek ayırmaetkiler. Kullanımı tarafından bildirilen dizi boyutunu `GetSize` hiçbir `GetUpperBound`zaman etkilemez ve.

Dizinin boyutu büyüdüyse, yeni ayrılan tüm **CObject** <strong>\*</strong> işaretçileri NULL olarak ayarlanır.

Aşağıdaki tabloda `CObArray::SetSize`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cbytearray](../../mfc/reference/cbytearray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` = **-1 );**<br /><br /> **atmak (CMemoryException\* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` = **-1 );**<br /><br /> **atmak (CMemoryException\* );**|
|[Cptrarray](../../mfc/reference/cptrarray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` = **-1 );**<br /><br /> **atmak (CMemoryException\* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` = **-1 );**<br /><br /> **atmak (CMemoryException\* );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` = **-1 );**<br /><br /> **atmak (CMemoryException\* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetSize( INT_PTR** `nNewSize` **, int** `nGrowBy` = **-1 );**<br /><br /> **atmak (CMemoryException\* );**|

### <a name="example"></a>Örnek

  CObArray örneğine [bakın:GetData](#getdata).

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CStringArray Sınıfı](../../mfc/reference/cstringarray-class.md)<br/>
[CPtrArray Sınıfı](../../mfc/reference/cptrarray-class.md)<br/>
[CByteArray Sınıfı](../../mfc/reference/cbytearray-class.md)<br/>
[CWordArray Sınıfı](../../mfc/reference/cwordarray-class.md)<br/>
[CDWordArray Sınıfı](../../mfc/reference/cdwordarray-class.md)
