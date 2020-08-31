---
title: CObArray sınıfı
description: '`CObArray` `MFC` Bir dizide işaretçiler depolayan sınıf için API başvurusu `CObject` .'
ms.date: 08/27/2020
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
ms.openlocfilehash: cbc1799a9634b3d8c09077b755b8a097289460fd
ms.sourcegitcommit: c8f1605354724a13566bc3b0fac3c5d98265f1d0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/28/2020
ms.locfileid: "89062164"
---
# <a name="cobarray-class"></a>CObArray sınıfı

İşaretçiler dizilerini destekler `CObject` .

## <a name="syntax"></a>Syntax

```cpp
class CObArray : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CObArray:: CObArray](#cobarray)|İşaretçiler için boş bir dizi oluşturur `CObject` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CObArray:: Add](#add)|Dizinin sonuna bir öğesi ekler; gerekirse diziyi büyür.|
|[CObArray:: Append](#append)|Diziye başka bir dizi ekler; gerekirse diziyi büyür.|
|[CObArray:: Copy](#copy)|Başka bir diziyi diziye kopyalar; gerekirse diziyi büyür.|
|[CObArray:: ElementAt](#elementat)|Dizi içindeki öğe işaretçisine geçici bir başvuru döndürür.|
|[CObArray:: FreeExtra](#freeextra)|Geçerli üst sınırın üzerinde kullanılmayan tüm belleği serbest bırakır.|
|[CObArray:: GetAt](#getat)|Verilen dizindeki değeri döndürür.|
|[CObArray:: GetCount](#getcount)|Bu dizideki öğelerin sayısını alır.|
|[CObArray:: GetData](#getdata)|Dizideki öğelere erişime izin verir. Olabilir `NULL` .|
|[CObArray:: GetSize](#getsize)|Bu dizideki öğelerin sayısını alır.|
|[CObArray:: Getüstsınırı](#getupperbound)|En büyük geçerli dizini döndürür.|
|[CObArray:: InsertAt](#insertat)|Belirtilen dizine bir öğe (veya başka bir dizide bulunan tüm öğeleri) ekler.|
|[CObArray:: IsEmpty](#isempty)|Dizinin boş olup olmadığını belirler.|
|[CObArray:: RemoveAll](#removeall)|Bu dizideki tüm öğeleri kaldırır.|
|[CObArray:: RemoveAt](#removeat)|Belirli bir dizindeki bir öğeyi kaldırır.|
|[CObArray:: SetAt](#setat)|Belirli bir dizin için değeri ayarlar; dizinin büyümesine izin verilmiyor.|
|[CObArray:: SetAtGrow](#setatgrow)|Belirli bir dizin için değeri ayarlar; gerekirse diziyi büyür.|
|[CObArray:: SetSize](#setsize)|Bu dizide yer alan öğelerin sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CObArray:: işleci \[\]](#operator_at)|Belirtilen dizindeki öğeyi ayarlar veya alır.|

## <a name="remarks"></a>Açıklamalar

Bu nesne dizileri C dizilerine benzerdir, ancak gerektiğinde dinamik olarak küçültülebilir ve büyüyebilir.

Dizi dizinleri her zaman 0 konumunda başlar. Üst sınırı düzeltireceğinize karar verebilir veya geçerli sınırı aşan öğeleri eklediğinizde dizinin genişlemesine izin verebilirsiniz. Bellek, bazı öğeler olsa bile üst sınır bitişik olarak ayrılır `NULL` .

Win32 altında, bir `CObArray` nesnenin boyutu yalnızca kullanılabilir bellekle sınırlıdır.

C dizisinde olduğu gibi, dizinli bir öğe için erişim süresi `CObArray` sabittir ve dizi boyutundan bağımsızdır.

`CObArray` öğelerinin serileştirilmesi ve dökümünü desteklemek için IMPLEMENT_SERIAL makrosunu ekler. Bir `CObject` işaretçiler dizisi, aşırı yüklenmiş ekleme işleci veya üye işlevi ile birlikte bir arşive depolanıyorsa, `Serialize` her `CObject` öğe sırasıyla dizi diziniyle birlikte sıralanır.

Bir dizideki tek tek öğelerin dökümünden birine ihtiyacınız varsa `CObject` , `CDumpContext` nesnenin derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Bir `CObArray` nesne silindiğinde veya öğeleri kaldırıldığında, `CObject` başvurdukları nesneler değil yalnızca işaretçiler kaldırılır.

> [!NOTE]
> Bir dizi kullanmadan önce, `SetSize` boyutunu belirlemek ve için bellek ayırmak üzere kullanın. Kullanmıyorsanız `SetSize` , diziye öğe eklemek, bu öğenin sık olarak yeniden tahsis edilmesine ve kopyalanmasına neden olur. Sık yeniden ayırma ve kopyalama verimsiz ve bellek parçalara ayırma yapılabilir.

Dizi sınıfı türetme, liste türetmeye benzer. Özel amaçlı bir liste sınıfının türetmesi hakkındaki ayrıntılar için bkz. Makale [koleksiyonları](../../mfc/collections.md).

> [!NOTE]
> Diziyi seri hale getirmek istiyorsanız türetilmiş sınıfınızın uygulamasındaki IMPLEMENT_SERIAL makrosunu kullanmanız gerekir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CObArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll. h

## <a name="cobarrayadd"></a><a name="add"></a> CObArray:: Add

Dizinin sonuna yeni bir öğe ekler ve diziyi 1 artırır.

```cpp
INT_PTR Add(CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*newElement*\
`CObject`Bu diziye eklenecek işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin dizini.

### <a name="remarks"></a>Açıklamalar

[SetSize](#setsize) , 1 ' den büyük bir *nGrowBy* değeri ile kullanılmışsa, ek bellek ayrılabilir. Ancak, üst sınır yalnızca 1 ' i arttırır.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObArray::Add` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`INT_PTR Add(BYTE newElement);`<br /><br />`throw(CMemoryException*);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`INT_PTR Add(DWORD newElement);`<br /><br />`throw(CMemoryException*);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`INT_PTR Add(void* newElement);`<br /><br />`throw(CMemoryException*);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`INT_PTR Add(LPCTSTR newElement); throw(CMemoryException*);`<br /><br />`INT_PTR Add(const CString& newElement);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`INT_PTR Add(UINT newElement);`<br /><br />`throw(CMemoryException*);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`INT_PTR Add(WORD newElement);`<br /><br />`throw(CMemoryException*);`|

### <a name="example"></a>Örnek

  Tüm koleksiyon örneklerinde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#75](../../mfc/codesnippet/cpp/cobarray-class_1.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
Add example: A CObArray with 2 elements
[0] = a CAge at $442A 21
[1] = a CAge at $4468 40
```

## <a name="cobarrayappend"></a><a name="append"></a> CObArray:: Append

Başka bir dizinin içeriğini verilen dizinin sonuna eklemek için bu üye işlevini çağırın.

```cpp
INT_PTR Append(const CObArray& src);
```

### <a name="parameters"></a>Parametreler

*YN*\
Diziye eklenecek öğelerin kaynağı.

### <a name="return-value"></a>Dönüş Değeri

İlk eklenen öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Diziler aynı türde olmalıdır.

Gerekirse, `Append` diziye eklenen öğeleri karşılamak için ek bellek ayırabilir.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObArray::Append` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`INT_PTR Append(const CByteArray& src);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`INT_PTR Append(const CDWordArray& src);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`INT_PTR Append(const CPtrArray& src);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`INT_PTR Append(const CStringArray& src);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`INT_PTR Append(const CUIntArray& src);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`INT_PTR Append(const CWordArray& src);`|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#76](../../mfc/codesnippet/cpp/cobarray-class_2.cpp)]

## <a name="cobarraycopy"></a><a name="copy"></a> CObArray:: Copy

Aynı türdeki başka bir dizinin öğeleriyle verilen dizinin öğelerinin üzerine yazmak için bu üye işlevi çağırın.

```cpp
void Copy(const CObArray& src);
```

### <a name="parameters"></a>Parametreler

*YN*\
Diziye kopyalanacak öğelerin kaynağı.

### <a name="remarks"></a>Açıklamalar

`Copy` belleği serbest vermez. Gerekirse, `Copy` diziye kopyalanmış öğeleri karşılamak için ek bellek ayırabilir.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObArray::Copy` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`void Copy(const CByteArray& src);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`void Copy(const CDWordArray& src);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void Copy(const CPtrArray& src);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`void Copy(const CStringArray& src);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`void Copy(const CUIntArray& src);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`void Copy(const CWordArray& src);`|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#77](../../mfc/codesnippet/cpp/cobarray-class_3.cpp)]

## <a name="cobarraycobarray"></a><a name="cobarray"></a> CObArray:: CObArray

Boş bir `CObject` işaretçi dizisi oluşturur.

```cpp
CObArray();
```

### <a name="remarks"></a>Açıklamalar

Dizi tek seferde bir öğeyi büyürken.

Aşağıdaki tabloda şuna benzer diğer oluşturucular gösterilmektedir `CObArray::CObArray` .

|Sınıf|Oluşturucu|
|-----------|-----------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`CByteArray();`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`CDWordArray();`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`CPtrArray();`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`CStringArray();`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`CUIntArray();`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`CWordArray();`|

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#78](../../mfc/codesnippet/cpp/cobarray-class_4.cpp)]

## <a name="cobarrayelementat"></a><a name="elementat"></a> CObArray:: ElementAt

Dizi içindeki öğe işaretçisine geçici bir başvuru döndürür.

```cpp
CObject*& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*\
0 ' dan büyük veya buna eşit ve tarafından döndürülen değerden küçük veya buna eşit bir tamsayı dizini `GetUpperBound` .

### <a name="return-value"></a>Dönüş Değeri

Bir `CObject` işaretçiye başvuru.

### <a name="remarks"></a>Açıklamalar

Diziler için sol taraftaki atama işlecini uygulamak için kullanılır. Bu, yalnızca özel dizi işleçleri uygulamak için kullanılması gereken gelişmiş bir işlevdir.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObArray::ElementAt` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`BYTE& ElementAt(INT_PTR nIndex);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`DWORD& ElementAt(INT_PTR nIndex);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void*& ElementAt(INT_PTR nIndex);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`CString& ElementAt(INT_PTR nIndex);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`UINT& ElementAt(INT_PTR nIndex);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`WORD& ElementAt(INT_PTR nIndex);`|

### <a name="example"></a>Örnek

[CObArray:: GetSize](#getsize)örneğine bakın.

## <a name="cobarrayfreeextra"></a><a name="freeextra"></a> CObArray:: FreeExtra

Dizi büyüirken ayrılan ek belleği serbest bırakır.

```cpp
void FreeExtra();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevin, dizinin boyutu veya üst sınırı üzerinde hiçbir etkisi yoktur.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObArray::FreeExtra` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`void FreeExtra();`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`void FreeExtra();`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void FreeExtra();`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`void FreeExtra();`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`void FreeExtra();`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`void FreeExtra();`|

### <a name="example"></a>Örnek

  [CObArray:: GetData](#getdata)örneğine bakın.

## <a name="cobarraygetat"></a><a name="getat"></a> CObArray:: GetAt

Belirtilen dizindeki dizi öğesini döndürür.

```cpp
CObject* GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*\
0 ' dan büyük veya buna eşit ve tarafından döndürülen değerden küçük veya buna eşit bir tamsayı dizini `GetUpperBound` .

### <a name="return-value"></a>Dönüş Değeri

`CObject`Şu anda bu dizindeki işaretçi öğesi.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Negatif bir değer veya tarafından döndürülen değerden daha büyük bir değer geçirilmesi `GetUpperBound` , başarısız bir onaylama işlemi oluşmasına neden olur.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObArray::GetAt` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`BYTE GetAt(INT_PTR nIndex) const;`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`DWORD GetAt(INT_PTR nIndex) const;`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void* GetAt(INT_PTR nIndex) const;`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`CString GetAt(INT_PTR nIndex) const;`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`UINT GetAt(INT_PTR nIndex) const;`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`WORD GetAt(INT_PTR nIndex) const;`|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#79](../../mfc/codesnippet/cpp/cobarray-class_5.cpp)]

## <a name="cobarraygetcount"></a><a name="getcount"></a> CObArray:: GetCount

Dizi öğelerinin sayısını döndürür.

```cpp
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Dizideki öğe sayısını almak için bu yöntemi çağırın. Dizinler sıfır tabanlı olduğundan, boyut en büyük dizinden 1 büyük olur.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObArray::GetCount` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`INT_PTR GetCount() const;`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`INT_PTR GetCount() const;`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`INT_PTR GetCount() const;`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`INT_PTR GetCount() const;`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`INT_PTR GetCount() const;`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`INT_PTR GetCount() const;`|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#80](../../mfc/codesnippet/cpp/cobarray-class_6.cpp)]

## <a name="cobarraygetdata"></a><a name="getdata"></a> CObArray:: GetData

Dizideki öğelere doğrudan erişim kazanmak için bu üye işlevini kullanın.

```cpp
const CObject** GetData() const;

CObject** GetData();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçiler dizisine yönelik bir işaretçi `CObject` .

### <a name="remarks"></a>Açıklamalar

Kullanılabilir öğe yoksa `GetData` bir `NULL` değer döndürür.

Bir dizinin öğelerine doğrudan erişim daha hızlı çalışmanıza yardımcı olsa da, çağrılırken dikkatli `GetData` olun; yaptığınız tüm hatalar dizinizdeki öğeleri doğrudan etkiler.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObArray::GetData` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`const BYTE* GetData() const; BYTE* GetData();`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`const DWORD* GetData() const; DWORD* GetData();`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`const void** GetData() const; void** GetData();`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`const CString* GetData() const; CString* GetData();`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`const UINT* GetData() const; UINT* GetData();`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`const WORD* GetData() const; WORD* GetData();`|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#81](../../mfc/codesnippet/cpp/cobarray-class_7.cpp)]

## <a name="cobarraygetsize"></a><a name="getsize"></a> CObArray:: GetSize

Dizinin boyutunu döndürür.

```cpp
INT_PTR GetSize() const;
```

### <a name="remarks"></a>Açıklamalar

Dizinler sıfır tabanlı olduğundan, boyut en büyük dizinden 1 büyük olur.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObArray::GetSize` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`INT_PTR GetSize() const;`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`INT_PTR GetSize() const;`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`INT_PTR GetSize() const;`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`INT_PTR GetSize() const;`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`INT_PTR GetSize() const;`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`INT_PTR GetSize() const;`|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#82](../../mfc/codesnippet/cpp/cobarray-class_8.cpp)]

## <a name="cobarraygetupperbound"></a><a name="getupperbound"></a> CObArray:: Getüstsınırı

Bu dizinin geçerli üst sınırını döndürür.

```cpp
INT_PTR GetUpperBound() const;
```

### <a name="return-value"></a>Dönüş Değeri

Üst sınır (sıfır tabanlı) dizini.

### <a name="remarks"></a>Açıklamalar

Dizi dizinleri sıfır tabanlı olduğundan, bu işlev 1 ' den küçük bir değer döndürür `GetSize` .

Koşul `GetUpperBound() = -1` , dizinin hiçbir öğe içermediğini belirtir.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObArray::GetUpperBound` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`INT_PTR GetUpperBound() const;`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`INT_PTR GetUpperBound() const;`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`INT_PTR GetUpperBound() const;`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`INT_PTR GetUpperBound() const;`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`INT_PTR GetUpperBound() const;`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`INT_PTR GetUpperBound() const;`|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#83](../../mfc/codesnippet/cpp/cobarray-class_9.cpp)]

## <a name="cobarrayinsertat"></a><a name="insertat"></a> CObArray:: InsertAt

Belirtilen dizine bir öğe (veya başka bir dizide bulunan tüm öğeleri) ekler.

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

*nDizin*\
Tarafından döndürülen değerden daha büyük olabilecek bir tamsayı dizini `GetUpperBound` .

*newElement*\
`CObject`Bu diziye yerleştirilecek işaretçi. Değer bir *Newwelement* öğesine `NULL` izin verilir.

*nCount*\
Bu öğenin Eklenme sayısı (varsayılan 1 ' dir).

*nStartIndex*\
Tarafından döndürülen değerden daha büyük olabilecek bir tamsayı dizini `GetUpperBound` .

*pNewArray*\
Bu diziye eklenecek öğeleri içeren başka bir dizi.

### <a name="remarks"></a>Açıklamalar

İlk sürümü bir `InsertAt` dizide belirtilen bir dizine bir öğe (veya bir öğenin birden çok kopyasını) ekler. İşlemde, (dizini arttırarak) Bu dizindeki mevcut öğeyi yukarı kaydırır ve yukarıdaki tüm öğeleri kaydırır.

İkinci sürüm, diğer bir koleksiyondaki tüm öğeleri `CObArray` , *nStartIndex* konumundan başlayarak ekler.

Bu `SetAt` işlev, belirtilen bir dizi öğesinin yerini alır ve herhangi bir öğeyi kaydıramaz.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObArray::InsertAt` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`void InsertAt(INT_PTR nIndex, BYTE newElement, int nCount = 1);`<br /><br />`throw(CMemoryException*);`<br /><br />`void InsertAt(INT_PTR nStartIndex, CByteArray* pNewArray);`<br /><br />`throw(CMemoryException*);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`void InsertAt(INT_PTR nIndex, DWORD newElement, int nCount = 1);`<br /><br />`throw(CMemoryException*);`<br /><br />`void InsertAt(INT_PTR nStartIndex, CDWordArray* pNewArray);`<br /><br />`throw(CMemoryException*);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void InsertAt(INT_PTR nIndex, void* newElement, int nCount = 1);`<br /><br />`throw(CMemoryException*);`<br /><br />`void InsertAt(INT_PTR nStartIndex, CPtrArray* pNewArray);`<br /><br />`throw(CMemoryException*);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`void InsertAt(INT_PTR nIndex, LPCTSTR newElement, int nCount = 1);`<br /><br />`throw(CMemoryException*);`<br /><br />`void InsertAt(INT_PTR nStartIndex, CStringArray* pNewArray);`<br /><br />`throw(CMemoryException*);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`void InsertAt(INT_PTR nIndex, UINT newElement, int nCount = 1);`<br /><br />`throw(CMemoryException*);`<br /><br />`void InsertAt(INT_PTR nStartIndex, CUIntArray* pNewArray);`<br /><br />`throw(CMemoryException*);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`void InsertAt(INT_PTR nIndex, WORD newElement, int nCount = 1);`<br /><br />`throw(CMemoryException*);`<br /><br />`void InsertAt(INT_PTR nStartIndex, CWordArray* pNewArray);`<br /><br />`throw(CMemoryException*);`|

### <a name="example"></a>Örnek

  Tüm koleksiyon örneklerinde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#84](../../mfc/codesnippet/cpp/cobarray-class_10.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
InsertAt example: A CObArray with 3 elements
[0] = a CAge at $45C8 21
[1] = a CAge at $4646 30
[2] = a CAge at $4606 40
```

## <a name="cobarrayisempty"></a><a name="isempty"></a> CObArray:: IsEmpty

Dizinin boş olup olmadığını belirler.

```cpp
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizi boşsa sıfır dışı; Aksi takdirde 0.

## <a name="cobarrayoperator--"></a><a name="operator_at"></a> CObArray:: operator []

Bu alt simge işleçleri ve işlevleri için kullanışlı bir yerdir `SetAt` `GetAt` .

```cpp
CObject*& operator[](int_ptr nindex);
CObject* operator[](int_ptr nindex) const;
```

### <a name="remarks"></a>Açıklamalar

Olmayan diziler için çağrılan ilk işleç **`const`** , atama ifadesinin sağ (r-value) veya Left (l-value) üzerinde kullanılabilir. Diziler için çağrılan ikinci, **`const`** yalnızca sağda kullanılabilir.

Kitaplığın hata ayıklama sürümü, alt simge (atama ifadesinin solunda ya da sağ tarafında) sınırların dışında olup olmadığını onaylar.

Aşağıdaki tabloda şuna benzer diğer işleçler gösterilmektedir `CObArray::operator []` .

|Sınıf|Operatör|
|-----------|--------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`BYTE& operator [](INT_PTR nindex);`<br /><br />`BYTE operator [](INT_PTR nindex) const;`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`DWORD& operator [](INT_PTR nindex);`<br /><br />`DWORD operator [](INT_PTR nindex) const;`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void*& operator [](INT_PTR nindex);`<br /><br />`void* operator [](INT_PTR nindex) const;`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`CString& operator [](INT_PTR nindex);`<br /><br />`CString operator [](INT_PTR nindex) const;`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`UINT& operator [](INT_PTR nindex);`<br /><br />`UINT operator [](INT_PTR nindex) const;`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`WORD& operator [](INT_PTR nindex);`<br /><br />`WORD operator [](INT_PTR nindex) const;`|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#88](../../mfc/codesnippet/cpp/cobarray-class_11.cpp)]

## <a name="cobarrayremoveall"></a><a name="removeall"></a> CObArray:: RemoveAll

Bu dizideki tüm işaretçileri kaldırır ancak gerçekten `CObject` nesneleri silmez.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Dizi zaten boşsa, işlev hala çalışır.

`RemoveAll`İşlevi, işaretçi depolaması için kullanılan tüm belleği serbest bırakır.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObArray::RemoveAll` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`void RemoveAll();`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`void RemoveAll();`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void RemoveAll();`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`void RemoveAll();`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`void RemoveAll();`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`void RemoveAll();`|

### <a name="example"></a>Örnek

Tüm koleksiyon örneklerinde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#85](../../mfc/codesnippet/cpp/cobarray-class_12.cpp)]

## <a name="cobarrayremoveat"></a><a name="removeat"></a> CObArray:: RemoveAt

Bir dizide belirtilen dizinden başlayarak bir veya daha fazla öğeyi kaldırır.

```cpp
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>Parametreler

*nDizin*\
0 ' dan büyük veya buna eşit ve tarafından döndürülen değerden küçük veya buna eşit bir tamsayı dizini `GetUpperBound` .

*nCount*\
Kaldırılacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

İşlemde, kaldırılan öğelerin üzerindeki tüm öğeleri aşağı kaydırır. Dizinin üst sınırını azaltır, ancak belleği serbest kalmaz.

Kaldırma noktasının üzerindeki dizide yer alan daha fazla öğeyi kaldırmaya çalışırsanız, kitaplığın hata ayıklama sürümü onaylar.

`RemoveAt`İşlev, `CObject` diziden işaretçiyi kaldırır, ancak nesnenin kendisini silmez.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObArray::RemoveAt` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`void RemoveAt(INT_PTR nIndex, INT_PTR nCount = 1);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`void RemoveAt(INT_PTR nIndex, INT_PTR nCount = 1);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void RemoveAt(INT_PTR nIndex, INT_PTR nCount = 1);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`void RemoveAt(INT_PTR nIndex, INT_PTR nCount = 1);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`void RemoveAt(INT_PTR nIndex, INT_PTR nCount = 1);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`void RemoveAt(INT_PTR nIndex, INT_PTR nCount = 1);`|

### <a name="example"></a>Örnek

  Tüm koleksiyon örneklerinde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#112](../../mfc/codesnippet/cpp/cobarray-class_13.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
RemoveAt example: A CObArray with 1 elements
[0] = a CAge at $4606 40
```

## <a name="cobarraysetat"></a><a name="setat"></a> CObArray:: SetAt

Belirtilen dizinde dizi öğesini ayarlar.

```cpp
void SetAt(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*nDizin*\
0 ' dan büyük veya buna eşit ve tarafından döndürülen değerden küçük veya buna eşit bir tamsayı dizini `GetUpperBound` .

*newElement*\
Bu diziye eklenecek nesne işaretçisi. Bir `NULL` değere izin verilir.

### <a name="remarks"></a>Açıklamalar

`SetAt` dizinin büyümesine neden olmaz. `SetAtGrow`Dizinin otomatik olarak büyümesini istiyorsanız kullanın.

Dizin değerinin dizideki geçerli bir konumu temsil ettiğinden emin olun. Sınırların dışında ise, kitaplığın hata ayıklama sürümü Onaylamalar olur.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObArray::SetAt` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`void SetAt(INT_PTR nIndex, BYTE newElement);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`void SetAt(INT_PTR nIndex, DWORD newElement);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void SetAt(INT_PTR nIndex, void* newElement);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`void SetAt(INT_PTR nIndex, LPCTSTR newElement);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`void SetAt(INT_PTR nIndex, UINT newElement);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`void SetAt(INT_PTR nIndex, WORD newElement);`|

### <a name="example"></a>Örnek

  Tüm koleksiyon örneklerinde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#86](../../mfc/codesnippet/cpp/cobarray-class_14.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
SetAt example: A CObArray with 2 elements
[0] = a CAge at $47E0 30
[1] = a CAge at $47A0 40
```

## <a name="cobarraysetatgrow"></a><a name="setatgrow"></a> CObArray:: SetAtGrow

Belirtilen dizinde dizi öğesini ayarlar.

```cpp
void SetAtGrow(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*nDizin*\
0 ' dan büyük veya buna eşit bir tamsayı dizini.

*newElement*\
Bu diziye eklenecek nesne işaretçisi. Bir `NULL` değere izin verilir.

### <a name="remarks"></a>Açıklamalar

Dizi gerektiğinde otomatik olarak büyür (yani, üst sınır yeni öğeye uyum sağlayacak şekilde ayarlanır).

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObArray::SetAtGrow` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`void SetAtGrow(INT_PTR nIndex, BYTE newElement);`<br /><br />`throw(CMemoryException*);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`void SetAtGrow(INT_PTR nIndex, DWORD newElement);`<br /><br />`throw(CMemoryException*);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void SetAtGrow(INT_PTR nIndex, void* newElement);`<br /><br />`throw( CMemoryException*);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`void SetAtGrow(INT_PTR nIndex, LPCTSTR newElement);`<br /><br />`throw(CMemoryException*);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`void SetAtGrow(INT_PTR nIndex, UINT newElement);`<br /><br />`throw(CMemoryException*);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`void SetAtGrow(INT_PTR nIndex, WORD newElement);`<br /><br />`throw(CMemoryException*);`|

### <a name="example"></a>Örnek

  Tüm koleksiyon örneklerinde kullanılan sınıfın listesi için bkz. [CObList:: CObList](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#87](../../mfc/codesnippet/cpp/cobarray-class_15.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
SetAtGrow example: A CObArray with 4 elements
[0] = a CAge at $47C0 21
[1] = a CAge at $4800 40
[2] = NULL
[3] = a CAge at $4840 65
```

## <a name="cobarraysetsize"></a><a name="setsize"></a> CObArray:: SetSize

Boş veya mevcut bir dizinin boyutunu oluşturur; gerekirse belleği ayırır.

```cpp
void SetSize(
    INT_PTR nNewSize,
    INT_PTR nGrowBy = -1);
```

### <a name="parameters"></a>Parametreler

*nNewSize*\
Yeni dizi boyutu (öğe sayısı). 0 değerinden büyük veya 0 değerine eşit olmalıdır.

*nGrowBy*\
Boyut artışı gerekliyse ayrılacak en az öğe yuvası sayısı.

### <a name="remarks"></a>Açıklamalar

Yeni boyut eski boyuttan küçükse, dizi kesilir ve kullanılmayan tüm bellek serbest bırakılır. Verimlilik için, kullanmadan `SetSize` önce dizinin boyutunu ayarlama çağrısı yapın. Bu, bir öğe her eklendiğinde diziyi yeniden tahsis etmek ve kopyalamak gereksinimini ortadan önler.

*NGrowBy* parametresi, dizi büyüirken iç bellek ayırmayı etkiler. Kullanımı, ve tarafından raporlanarak dizi boyutunu hiçbir şekilde etkilemez `GetSize` `GetUpperBound` .

Dizinin boyutu artmışsa, tüm yeni ayrılmış `CObject *` işaretçiler olarak ayarlanır `NULL` .

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObArray::SetSize` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|`void SetSize(INT_PTR nNewSize, int nGrowBy = -1);`<br /><br /> `throw(CMemoryException*);`|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|`void SetSize(INT_PTR nNewSize, int nGrowBy = -1);`<br /><br /> `throw(CMemoryException*);`|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|`void SetSize(INT_PTR nNewSize, int nGrowBy = -1);`<br /><br /> `throw(CMemoryException*);`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|`void SetSize(INT_PTR nNewSize, int nGrowBy = -1);`<br /><br /> `throw(CMemoryException*);`|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|`void SetSize(INT_PTR nNewSize, int nGrowBy = -1);`<br /><br /> `throw(CMemoryException*);`|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|`void SetSize(INT_PTR nNewSize, int nGrowBy = -1);`<br /><br /> `throw(CMemoryException*);`|

### <a name="example"></a>Örnek

  [CObArray:: GetData](#getdata)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)\
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)\
[CStringArray sınıfı](../../mfc/reference/cstringarray-class.md)\
[CPtrArray sınıfı](../../mfc/reference/cptrarray-class.md)\
[CByteArray sınıfı](../../mfc/reference/cbytearray-class.md)\
[CWordArray sınıfı](../../mfc/reference/cwordarray-class.md)\
[CDWordArray sınıfı](../../mfc/reference/cdwordarray-class.md)
