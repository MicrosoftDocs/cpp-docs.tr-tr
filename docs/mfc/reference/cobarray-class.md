---
title: CObArray sınıfı
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
ms.openlocfilehash: 78d736b53a2febe4f4a026e3aaf9db14dd7f9c0b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57300420"
---
# <a name="cobarray-class"></a>CObArray sınıfı

Dizilerini destekler `CObject` işaretçileri.

## <a name="syntax"></a>Sözdizimi

```
class CObArray : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CObArray::CObArray](#cobarray)|İçin boş bir dizi oluşturur `CObject` işaretçileri.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CObArray::Add](#add)|Dizinin sonuna bir öğe ekler; dizi gerekirse büyür.|
|[CObArray::Append](#append)|Diziyi başka diziye ekler; dizi gerekirse büyür.|
|[CObArray::Copy](#copy)|Diziyi başka diziye kopyalar; dizi gerekirse büyür.|
|[CObArray::ElementAt](#elementat)|Dizi içinde öğe işaretçisi için geçici bir başvuru döndürür.|
|[CObArray::FreeExtra](#freeextra)|Geçerli üst sınır yukarıdaki tüm kullanılmayan belleği serbest bırakır.|
|[CObArray::GetAt](#getat)|Belirtilen dizindeki değeri döndürür.|
|[CObArray::GetCount](#getcount)|Bu dizinin içinde öğe sayısını alır.|
|[CObArray::GetData](#getdata)|Dizide öğelere erişim sağlar. NULL olabilir.|
|[CObArray::GetSize](#getsize)|Bu dizinin içinde öğe sayısını alır.|
|[CObArray::GetUpperBound](#getupperbound)|En büyük geçerli dizinini döndürür.|
|[CObArray::InsertAt](#insertat)|Belirtilen dizindeki öğenin (veya başka bir dizideki tüm öğeler) ekler.|
|[CObArray::IsEmpty](#isempty)|Dizi boş olup olmadığını belirler.|
|[CObArray::RemoveAll](#removeall)|Bu dizisinden tüm öğeleri kaldırır.|
|[CObArray::RemoveAt](#removeat)|Belirli bir dizindeki öğeyi kaldırır.|
|[CObArray::SetAt](#setat)|Belirtilen dizin için değeri ayarlar; dizi büyümesine izin verilmiyor.|
|[CObArray::SetAtGrow](#setatgrow)|Belirtilen dizin için değeri ayarlar; dizi gerekirse büyür.|
|[CObArray::SetSize](#setsize)|Bu dizinin içinde yer alması için öğe sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CObArray::operator \[ \]](#operator_at)|Belirtilen dizindeki öğeyi alır veya ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bu nesne dizileri için C dizilerine benzer, ancak dinamik olarak daraltmak ve gerektikçe büyütün.

Dizi dizinleri her zaman 0 konumunda başlar. Üst sınır düzeltin veya dizi geçerli sınır geçmiş öğeler eklediğinizde, genişletmek izin vermek karar verebilirsiniz. Bazı öğeler null olsa bile, bellek için üst sınır, bitişik ayrılır.

Win32, boyutu altında bir `CObArray` nesne yalnızca kullanılabilir bellek sınırlıdır.

Bir C dizi için erişim zamanı olduğu gibi bir `CObArray` dizinlenmiş öğeye sabittir ve dizi boyutu bağımsızdır.

`CObArray` Serileştirme ve alt öğeleri dökme desteklemek için ımplement_serıal makrosu içerir. Bir dizi varsa `CObject` işaretçiler veya aşırı yüklenmiş bir ekleme operatörü ile birlikte bir arşivden depolandığı `Serialize` üye işlev, her `CObject` öğesi sırasıyla serileştirildiği yanı sıra, dizi dizini.

Tek bir dökümü gerekiyorsa `CObject` bir dizideki öğelerin, derinliğini ayarlamalısınız `CDumpContext` 1 veya daha büyük bir nesneye.

Olduğunda bir `CObArray` nesnesi silindiğinde veya ne zaman öğeleri kaldırılır, yalnızca `CObject` işaretçileri kaldırılır, nesneleri başvuruyor.

> [!NOTE]
>  Bir dizi kullanmadan önce kullanmayı `SetSize` boyutuna kurmak ve kendisi için bellek ayrılamadı. Kullanmıyorsanız, `SetSize`, diziniz için öğeleri ekleme, oluyor, sık sık yeniden ve kopyalanır. Sık sık yeniden ayırma ve kopyalama verimsiz ve bellek parçası.

Array sınıfı türetme için liste türetme benzerdir. Özel amaçlı listesi sınıfının türetme hakkında daha fazla bilgi için bkz [koleksiyonları](../../mfc/collections.md).

> [!NOTE]
>  Dizisi seri hale getirmek istiyorsanız, türetilmiş sınıfınızın uygulamasında ımplement_serıal makrosu kullanmanız gerekir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CObArray`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcoll.h

##  <a name="add"></a>  CObArray::Add

1 ile dizi büyüyen bir dizinin sonuna yeni bir öğe ekler.

```
INT_PTR Add(CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*newElement*<br/>
`CObject` Bu diziye eklenecek işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Varsa [SetSize](#setsize) ile kullanılan bir *nGrowBy* değeri 1 ve ardından ek bellek büyük ayrılan. Bununla birlikte, üst sınırı yalnızca 1 artar.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObArray::Add`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR ekleyin (bayt** `newElement` **);**<br /><br /> **throw( CMemoryException\* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR Add( DWORD** `newElement` **);**<br /><br /> **throw( CMemoryException\* );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR Add( void** <strong>\*</strong> `newElement` **);**<br /><br /> **throw( CMemoryException\* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR ekleyin (LPCTSTR** `newElement` **); throw (CMemoryException\* );**<br /><br /> **INT_PTR Add(const CString&** `newElement` **);**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**INT_PTR Add( UINT** `newElement` **);**<br /><br /> **throw( CMemoryException\* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR ekleyin (WORD** `newElement` **);**<br /><br /> **throw( CMemoryException\* );**|

### <a name="example"></a>Örnek

  Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#75](../../mfc/codesnippet/cpp/cobarray-class_1.cpp)]

Bu program sonuçları aşağıdaki gibidir:

```Output
Add example: A CObArray with 2 elements
[0] = a CAge at $442A 21
[1] = a CAge at $4468 40
```

##  <a name="append"></a>  CObArray::Append

Başka bir dizinin içeriğini belirtilen dizinin sonuna eklemek için bu üye işlevini çağırın.

```
INT_PTR Append(const CObArray& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
Diziye eklenecek öğeleri kaynağı.

### <a name="return-value"></a>Dönüş Değeri

Eklenen ilk öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Diziler, aynı türde olmalıdır.

Gerekirse, `Append` diziye eklenen öğeleri uyum sağlamak için ek bellek ayırabilirsiniz.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObArray::Append`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR ekleme (const CByteArray &** *src* **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR ekleme (const CDWordArray &** *src* **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR ekleme (const CPtrArray &** *src* **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR ekleme (const CStringArray &** *src* **);**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**INT_PTR ekleme (const Cuıntarray &** *src* **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR ekleme (const CWordArray &** *src* **);**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#76](../../mfc/codesnippet/cpp/cobarray-class_2.cpp)]

##  <a name="copy"></a>  CObArray::Copy

Belirtilen dizinin öğeleri aynı türde başka bir dizinin öğeleri ile üzerine yazmak için bu üye işlevini çağırın.

```
void Copy(const CObArray& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
Diziye kopyalanacak öğe kaynağı.

### <a name="remarks"></a>Açıklamalar

`Copy` belleği boşaltmak değil; Ancak, gerekirse `Copy` diziye kopyalanan öğelerin uyum sağlamak için ek bellek ayırabilirsiniz.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObArray::Copy`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void kopyalama (const CByteArray &** *src* **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void kopyalama (const CDWordArray &** *src* **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void kopyalama (const CPtrArray &** *src* **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void kopyalama (const CStringArray &** *src* **);**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**void kopyalama (const Cuıntarray &** *src* **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void kopyalama (const CWordArray &** *src* **);**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#77](../../mfc/codesnippet/cpp/cobarray-class_3.cpp)]

##  <a name="cobarray"></a>  CObArray::CObArray

Boş bir yapıları `CObject` işaretçi dizisi.

```
CObArray();
```

### <a name="remarks"></a>Açıklamalar

Diziye bir öğe aynı anda büyür.

Aşağıdaki tabloda, benzer diğer oluşturucular gösterilmektedir `CObArray::CObArray`.

|örneği|Oluşturucu|
|-----------|-----------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**CByteArray( );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**CDWordArray( );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**CPtrArray( );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CStringArray( );**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**CUIntArray( );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**CWordArray( );**|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#78](../../mfc/codesnippet/cpp/cobarray-class_4.cpp)]

##  <a name="elementat"></a>  CObArray::ElementAt

Dizi içinde öğe işaretçisi için geçici bir başvuru döndürür.

```
CObject*& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Büyük veya 0'a eşit bir tamsayı dizini ve tarafından döndürülen değer küçüktür veya eşittir `GetUpperBound`.

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru bir `CObject` işaretçi.

### <a name="remarks"></a>Açıklamalar

Diziler için sol taraftaki atama işleci uygulamak için kullanılır. Yalnızca özel bir dizi işleçler için kullanılması gereken gelişmiş bir işlevi olduğunu unutmayın.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObArray::ElementAt`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**BYTE& ElementAt( INT_PTR** `nIndex` **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD& ElementAt( INT_PTR** `nIndex` **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void\*& ElementAt( INT_PTR** `nIndex` **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString& ElementAt( INT_PTR** `nIndex` **);**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**UINT& ElementAt( INT_PTR** `nIndex` **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD& ElementAt( INT_PTR** `nIndex` **);**|

### <a name="example"></a>Örnek

  Örneğin bakın [CObArray::GetSize](#getsize).

##  <a name="freeextra"></a>  CObArray::FreeExtra

Dizi büyütmüş sırada ayrılmış ek bellek kazandırır.

```
void FreeExtra();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev boyutu veya dizi üst sınırı üzerinde etkisi yoktur.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObArray::FreeExtra`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void FreeExtra( );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void FreeExtra( );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void FreeExtra( );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void FreeExtra( );**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**void FreeExtra( );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void FreeExtra( );**|

### <a name="example"></a>Örnek

  Örneğin bakın [CObArray::GetData](#getdata).

##  <a name="getat"></a>  CObArray::GetAt

Dizi belirtilen dizindeki öğeyi döndürür.

```
CObject* GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Büyük veya 0'a eşit bir tamsayı dizini ve tarafından döndürülen değer küçüktür veya eşittir `GetUpperBound`.

### <a name="return-value"></a>Dönüş Değeri

`CObject` Şu anda bu dizindeki işaretçi öğe.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Negatif bir değer veya bir değer döndürdüğü değerden geçirme `GetUpperBound` başarısız bir onaylama işlemi neden olur.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObArray::GetAt`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**BAYT GetAt (INT_PTR** `nIndex` **) const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD GetAt (INT_PTR** `nIndex` **) const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void\* GetAt (INT_PTR** `nIndex` **) const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString GetAt (INT_PTR** `nIndex` **) const;**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**UINT GetAt (INT_PTR** `nIndex` **) const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD GetAt (INT_PTR** `nIndex` **) const;**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#79](../../mfc/codesnippet/cpp/cobarray-class_5.cpp)]

##  <a name="getcount"></a>  CObArray::GetCount

Dizi öğelerinin sayısını döndürür.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Dizideki öğelerin sayısını almak için bu yöntemi çağırın. Dizinler sıfır tabanlı olduğundan, boyutu en büyük dizinden daha büyük olan 1 ' dir.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObArray::GetCount`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetCount( ) const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetCount( ) const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetCount( ) const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetCount( ) const;**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetCount( ) const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetCount( ) const;**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#80](../../mfc/codesnippet/cpp/cobarray-class_6.cpp)]

##  <a name="getdata"></a>  CObArray::GetData

Dizideki öğelerin doğrudan erişim elde etmek için bu üye işlevini kullanın.

```
const CObject** GetData() const;

CObject** GetData();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi dizisinin işaretçisi `CObject` işaretçileri.

### <a name="remarks"></a>Açıklamalar

Hiçbir öğe varsa `GetData` bir null değer döndürür.

Bir dizinin öğeleri doğrudan erişim daha hızlı çalışmanıza yardımcı olabilir, ancak çağırırken dikkatli `GetData`; doğrudan yaptığınız herhangi bir hata, dizinin öğeleri etkiler.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObArray::GetData`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**const bayt\* const; GetData) BAYT\* GetData ();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**const DWORD\* GetData (const); DWORD\* GetData ();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**const void\* \* GetData () const; void\* \* GetData ();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**const CString\* const; GetData) CString\* GetData ();**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**const UINT\* const; GetData) UINT\* GetData ();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**const WORD\* const; GetData) WORD\* GetData ();**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#81](../../mfc/codesnippet/cpp/cobarray-class_7.cpp)]

##  <a name="getsize"></a>  CObArray::GetSize

Dizinin boyutunu döndürür.

```
INT_PTR GetSize() const;
```

### <a name="remarks"></a>Açıklamalar

Dizinler sıfır tabanlı olduğundan, boyutu en büyük dizinden daha büyük olan 1 ' dir.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObArray::GetSize`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetSize () const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetSize () const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetSize () const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetSize () const;**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetSize () const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetSize () const;**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#82](../../mfc/codesnippet/cpp/cobarray-class_8.cpp)]

##  <a name="getupperbound"></a>  CObArray::GetUpperBound

Bu dizinin geçerli üst sınırını döndürür.

```
INT_PTR GetUpperBound() const;
```

### <a name="return-value"></a>Dönüş Değeri

Üst dizinini (sıfır tabanlı) bağlı.

### <a name="remarks"></a>Açıklamalar

Dizi dizinleri sıfır tabanlı olduğundan, bu işlev, 1 değerini döndürür. kısa `GetSize`.

Koşul `GetUpperBound( )` = -1, dizi hiç öğe içerdiğini gösterir.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObArray::GetUpperBound`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetUpperBound () const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetUpperBound () const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetUpperBound () const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetUpperBound () const;**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetUpperBound () const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetUpperBound () const;**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#83](../../mfc/codesnippet/cpp/cobarray-class_9.cpp)]

##  <a name="insertat"></a>  CObArray::InsertAt

Belirtilen dizindeki öğenin (veya başka bir dizideki tüm öğeler) ekler.

```
void InsertAt(
    INT_PTR nIndex,
    CObject* newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CObArray* pNewArray);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Tarafından döndürülen değeri,'den büyük bir tamsayı dizini `GetUpperBound`.

*newElement*<br/>
`CObject` Bu dizinin içinde yer yönelik işaretçi. A *newElement* NULL değerine izin verilir.

*nCount*<br/>
Bu öğe olmalıdır sayısı (varsayılan 1) eklenir.

*nStartIndex*<br/>
Tarafından döndürülen değeri,'den büyük bir tamsayı dizini `GetUpperBound`.

*pNewArray*<br/>
Bu diziye eklenecek öğeleri içeren başka bir dizi.

### <a name="remarks"></a>Açıklamalar

Ürününün ilk sürümünü `InsertAt` belirli bir dizinden bir dizideki bir öğe (veya birden çok kopyasını bir öğe) ekler. İşlem sırasında yukarı kaydırır (dizin artırılarak) ve bu dizin mevcut öğe üzerindeki tüm öğeleri yukarı kaydırır.

Dosyanın ikinci sürümü tüm öğeleri bir diğerinden ekler `CObArray` başlayarak koleksiyon *nStartIndex* konumu.

`SetAt` İşlevi, buna karşılık, bir belirtilen dizi öğesi değiştirir ve tüm öğeleri kaydırmak değil.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObArray::InsertAt`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, bayt** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw( CMemoryException\* );**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CByteArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw( CMemoryException\* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, DWORD** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw( CMemoryException\* );**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CDWordArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw( CMemoryException\* );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, void** <strong>\*</strong> `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw( CMemoryException\* );**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CPtrArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw( CMemoryException\* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw( CMemoryException\* );**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CStringArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw( CMemoryException\* );**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, UINT** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw( CMemoryException\* );**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CUIntArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw( CMemoryException\* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, WORD** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw( CMemoryException\* );**<br /><br /> **void InsertAt( INT_PTR** `nStartIndex` **, CWordArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw( CMemoryException\* );**|

### <a name="example"></a>Örnek

  Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#84](../../mfc/codesnippet/cpp/cobarray-class_10.cpp)]

Bu program sonuçları aşağıdaki gibidir:

```Output
InsertAt example: A CObArray with 3 elements
[0] = a CAge at $45C8 21
[1] = a CAge at $4646 30
[2] = a CAge at $4606 40
```

##  <a name="isempty"></a>  CObArray::IsEmpty

Dizi boş olup olmadığını belirler.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizi boş ise sıfır olmayan; Aksi durumda 0.

##  <a name="operator_at"></a>  CObArray::operator]

Bu alt simge işleçlerini için kullanışlı bir alternatif olan `SetAt` ve `GetAt` işlevleri.

```
CObject*& operator[](int_ptr nindex);
CObject* operator[](int_ptr nindex) const;
```

### <a name="remarks"></a>Açıklamalar

İlk işleç değil diziler için çağrılır **const**, sağ (r) veya Atama ifadesinin solunda (lvalue) üzerinde kullanılabilir. İkinci adında için **const** diziler, yalnızca sağ tarafta kullanılır.

Kitaplığı hata ayıklama sürümünü (veya sol veya sağ tarafında bir atama ifadesi) alt simge sınırların dışında olup olmadığını onaylar.

Benzer diğer işleçleri aşağıdaki tabloda gösterilmektedir `CObArray::operator []`.

|örneği|İşleç|
|-----------|--------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**BAYT & işleci [] (int_ptr** `nindex`  **\);**<br /><br /> **BAYT [] işleci (int_ptr** `nindex`  **\) const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD & işleci [] (int_ptr** `nindex`  **\);**<br /><br /> **DWORD operator [] (int_ptr** `nindex`  **\) const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void\*& operator [] (int_ptr** `nindex`  **\);**<br /><br /> **void\* operator [] (int_ptr** `nindex`  **\) const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString & işleci [] (int_ptr** `nindex`  **\);**<br /><br /> **CString operator [] (int_ptr** `nindex`  **\) const;**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**UINT & işleci [] (int_ptr** `nindex`  **\);**<br /><br /> **UINT operator [] (int_ptr** `nindex`  **\) const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**SÖZCÜK & işleci [] (int_ptr** `nindex`  **\);**<br /><br /> **WORD operator [] (int_ptr** `nindex`  **\) const;**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#88](../../mfc/codesnippet/cpp/cobarray-class_11.cpp)]

##  <a name="removeall"></a>  CObArray::RemoveAll

Bu dizisinden tüm işaretçiler kaldırır ancak aslında silmediği `CObject` nesneleri.

```
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Dizi zaten boşsa, işlev hala çalışır.

`RemoveAll` İşlevi işaretçisi depolaması için kullanılan tüm belleği serbest bırakır.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObArray::RemoveAll`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void RemoveAll( );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void RemoveAll( );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void RemoveAll( );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void RemoveAll( );**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**void RemoveAll( );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void RemoveAll( );**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#85](../../mfc/codesnippet/cpp/cobarray-class_12.cpp)]

##  <a name="removeat"></a>  CObArray::RemoveAt

Bir dizideki belirli bir dizinden başlayarak bir veya daha fazla öğeleri kaldırır.

```
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Büyük veya 0'a eşit bir tamsayı dizini ve tarafından döndürülen değer küçüktür veya eşittir `GetUpperBound`.

*nCount*<br/>
Kaldırılacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

İşlem sırasında kaldırılan öğeyi/öğeleri yukarıdaki tüm öğeleri aşağı kaydırır. Bu üst dizisi bağlı, ancak bellek serbest değil azaltır.

Dizideki kaldırma noktası yukarıda yer alan çok daha fazla öğe ekleyip denerseniz, ardından kitaplığı hata ayıklama sürümünü onaylar.

`RemoveAt` İşlev kaldırır `CObject` işaretçisinden bir dizi, ancak nesnenin kendisi silinmez.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObArray::RemoveAt`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1 );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void RemoveAt( INT_PTR** `nIndex` **, INT_PTR** *nCount* **= 1 );**|

### <a name="example"></a>Örnek

  Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#112](../../mfc/codesnippet/cpp/cobarray-class_13.cpp)]

Bu program sonuçları aşağıdaki gibidir:

```Output
RemoveAt example: A CObArray with 1 elements
[0] = a CAge at $4606 40
```

##  <a name="setat"></a>  CObArray::SetAt

Belirtilen dizindeki dizi öğesini ayarlar.

```
void SetAt(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Büyük veya 0'a eşit bir tamsayı dizini ve tarafından döndürülen değer küçüktür veya eşittir `GetUpperBound`.

*newElement*<br/>
Bu dizinin içinde eklenecek nesne işaretçisi. NULL değerine izin verilir.

### <a name="remarks"></a>Açıklamalar

`SetAt` dizi büyümesine neden. Kullanım `SetAtGrow` otomatik olarak büyütmeyi dizi istiyorsanız.

Dizin değerinizi dizisindeki geçerli bir konum temsil eder emin olmanız gerekir. Sınırların dışında ise, ardından kitaplığı hata ayıklama sürümünü onaylar.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObArray::SetAt`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetAt( INT_PTR** `nIndex` **, BYTE** `newElement` **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, DWORD** `newElement` **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, void** <strong>\*</strong> `newElement` **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, UINT** `newElement` **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetAt( INT_PTR** `nIndex` **, WORD** `newElement` **);**|

### <a name="example"></a>Örnek

  Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#86](../../mfc/codesnippet/cpp/cobarray-class_14.cpp)]

Bu program sonuçları aşağıdaki gibidir:

```Output
SetAt example: A CObArray with 2 elements
[0] = a CAge at $47E0 30
[1] = a CAge at $47A0 40
```

##  <a name="setatgrow"></a>  CObArray::SetAtGrow

Belirtilen dizindeki dizi öğesini ayarlar.

```
void SetAtGrow(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Büyük veya 0'a eşit bir tamsayı dizini.

*newElement*<br/>
Bu diziye eklenecek nesne işaretçisi. NULL değerine izin verilir.

### <a name="remarks"></a>Açıklamalar

Gerekirse, dizi otomatik olarak artar (diğer bir deyişle, üst sınırı yeni öğeye uyum sağlamak için ayarlanır).

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObArray::SetAtGrow`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, bayt** `newElement` **);**<br /><br /> **throw( CMemoryException\* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, DWORD** `newElement` **);**<br /><br /> **throw( CMemoryException\* );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, void** <strong>\*</strong> `newElement` **);**<br /><br /> **throw( CMemoryException\* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**<br /><br /> **throw( CMemoryException\* );**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, UINT** `newElement` **);**<br /><br /> **throw( CMemoryException\* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetAtGrow( INT_PTR** `nIndex` **, WORD** `newElement` **);**<br /><br /> **throw( CMemoryException\* );**|

### <a name="example"></a>Örnek

  Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) bir listesi için `CAge` tüm koleksiyon örneklerde kullanılan sınıf.

[!code-cpp[NVC_MFCCollections#87](../../mfc/codesnippet/cpp/cobarray-class_15.cpp)]

Bu program sonuçları aşağıdaki gibidir:

```Output
SetAtGrow example: A CObArray with 4 elements
[0] = a CAge at $47C0 21
[1] = a CAge at $4800 40
[2] = NULL
[3] = a CAge at $4840 65
```

##  <a name="setsize"></a>  CObArray::SetSize

Boş veya varolan bir dizinin boyutunu belirler; Gerekirse, bellek ayırır.

```
void SetSize(
    INT_PTR nNewSize,
    INT_PTR nGrowBy = -1);
```

### <a name="parameters"></a>Parametreler

*nNewSize*<br/>
Yeni dizi boyutu (öğe sayısı). Büyük veya 0'a eşit olmalıdır.

*nGrowBy*<br/>
Öğe yuvaları boyutu artışı gerekliyse ayrılacak en küçük sayısı.

### <a name="remarks"></a>Açıklamalar

Yeni boyut eski boyuttan daha küçükse, dizi kesilmiş ve tüm kullanılmayan belleği serbest kalır. Verimlilik için çağrı `SetSize` kullanmadan önce dizinin boyutunu ayarlamak için. Bu yeniden ayırın ve her zaman bir öğe eklendiğinde dizisine kopyalamak için gereken engeller.

*NGrowBy* parametre dizi artan sırada iç bellek ayırma etkiler. Kullanımı hiçbir zaman tarafından raporlandığı şekilde dizi boyutu etkiler `GetSize` ve `GetUpperBound`.

Dizinin boyutunu büyüdü, tüm yeni ayrılan **CObject** <strong>\*</strong> işaretçisi, NULL olarak ayarlanır.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObArray::SetSize`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw( CMemoryException\* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw( CMemoryException\* );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw( CMemoryException\* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw( CMemoryException\* );**|
|[Cuıntarray](../../mfc/reference/cuintarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw( CMemoryException\* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw( CMemoryException\* );**|

### <a name="example"></a>Örnek

  Örneğin bakın [CObArray::GetData](#getdata).

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CStringArray Sınıfı](../../mfc/reference/cstringarray-class.md)<br/>
[CPtrArray Sınıfı](../../mfc/reference/cptrarray-class.md)<br/>
[CByteArray Sınıfı](../../mfc/reference/cbytearray-class.md)<br/>
[CWordArray Sınıfı](../../mfc/reference/cwordarray-class.md)<br/>
[CDWordArray Sınıfı](../../mfc/reference/cdwordarray-class.md)
