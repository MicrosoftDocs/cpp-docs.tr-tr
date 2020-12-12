---
description: 'Daha fazla bilgi edinin: Cotasafearray sınıfı'
title: Colet SAFEARRAY sınıfı
ms.date: 08/29/2019
f1_keywords:
- COleSafeArray
- AFXDISP/COleSafeArray
- AFXDISP/COleSafeArray::COleSafeArray
- AFXDISP/COleSafeArray::AccessData
- AFXDISP/COleSafeArray::AllocData
- AFXDISP/COleSafeArray::AllocDescriptor
- AFXDISP/COleSafeArray::Attach
- AFXDISP/COleSafeArray::Clear
- AFXDISP/COleSafeArray::Copy
- AFXDISP/COleSafeArray::Create
- AFXDISP/COleSafeArray::CreateOneDim
- AFXDISP/COleSafeArray::Destroy
- AFXDISP/COleSafeArray::DestroyData
- AFXDISP/COleSafeArray::DestroyDescriptor
- AFXDISP/COleSafeArray::Detach
- AFXDISP/COleSafeArray::GetByteArray
- AFXDISP/COleSafeArray::GetDim
- AFXDISP/COleSafeArray::GetElement
- AFXDISP/COleSafeArray::GetElemSize
- AFXDISP/COleSafeArray::GetLBound
- AFXDISP/COleSafeArray::GetOneDimSize
- AFXDISP/COleSafeArray::GetUBound
- AFXDISP/COleSafeArray::Lock
- AFXDISP/COleSafeArray::PtrOfIndex
- AFXDISP/COleSafeArray::PutElement
- AFXDISP/COleSafeArray::Redim
- AFXDISP/COleSafeArray::ResizeOneDim
- AFXDISP/COleSafeArray::UnaccessData
- AFXDISP/COleSafeArray::Unlock
helpviewer_keywords:
- COleSafeArray [MFC], COleSafeArray
- COleSafeArray [MFC], AccessData
- COleSafeArray [MFC], AllocData
- COleSafeArray [MFC], AllocDescriptor
- COleSafeArray [MFC], Attach
- COleSafeArray [MFC], Clear
- COleSafeArray [MFC], Copy
- COleSafeArray [MFC], Create
- COleSafeArray [MFC], CreateOneDim
- COleSafeArray [MFC], Destroy
- COleSafeArray [MFC], DestroyData
- COleSafeArray [MFC], DestroyDescriptor
- COleSafeArray [MFC], Detach
- COleSafeArray [MFC], GetByteArray
- COleSafeArray [MFC], GetDim
- COleSafeArray [MFC], GetElement
- COleSafeArray [MFC], GetElemSize
- COleSafeArray [MFC], GetLBound
- COleSafeArray [MFC], GetOneDimSize
- COleSafeArray [MFC], GetUBound
- COleSafeArray [MFC], Lock
- COleSafeArray [MFC], PtrOfIndex
- COleSafeArray [MFC], PutElement
- COleSafeArray [MFC], Redim
- COleSafeArray [MFC], ResizeOneDim
- COleSafeArray [MFC], UnaccessData
- COleSafeArray [MFC], Unlock
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
ms.openlocfilehash: 6c33f58f71167c492883a25b05fce6bb8fb09916
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226707"
---
# <a name="colesafearray-class"></a>Colet SAFEARRAY sınıfı

Rastgele tür ve boyut dizileri ile çalışmaya yönelik bir sınıf.

## <a name="syntax"></a>Syntax

```
class COleSafeArray : public tagVARIANT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Colet SAFEARRAY:: Cotasafearray](#colesafearray)|Bir `COleSafeArray` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Colet SAFEARRAY:: AccessData](#accessdata)|Dizi verilerine yönelik bir işaretçi alır.|
|[Colet SAFEARRAY:: AllocData](#allocdata)|Dizi için bellek ayırır.|
|[Colet SAFEARRAY:: AllocDescriptor](#allocdescriptor)|Güvenli dizi tanımlayıcısı için bellek ayırır.|
|[Colet SAFEARRAY:: Attach](#attach)|Nesnenin varolan dizisinin denetimini verir `VARIANT` `COleSafeArray` .|
|[COleSafeArray:: Clear](#clear)|Temeldeki tüm verileri serbest bırakır `VARIANT` .|
|[Cotasafearray:: Copy](#copy)|Varolan bir dizinin kopyasını oluşturur.|
|[Colet SAFEARRAY:: Create](#create)|Güvenli bir dizi oluşturur.|
|[Colet SAFEARRAY:: Createonedid](#createonedim)|Tek boyutlu bir nesne oluşturur `COleSafeArray` .|
|[Colet SAFEARRAY::D estroy](#destroy)|Var olan bir diziyi yok eder.|
|[Colet SAFEARRAY::D estroyData](#destroydata)|Güvenli bir dizide verileri yok eder.|
|[Colet SAFEARRAY::D estroyDescriptor](#destroydescriptor)|Güvenli dizi tanımlayıcısını yok eder.|
|[Colet SAFEARRAY::D etach](#detach)|DEĞIŞKEN diziyi `COleSafeArray` nesnesinden ayırır (böylece veriler serbest bırakılmaz).|
|[Colet SAFEARRAY:: GetByteArray](#getbytearray)|Güvenli dizinin içeriğini bir [CByteArray](../../mfc/reference/cbytearray-class.md)öğesine kopyalar.|
|[Colet SAFEARRAY:: GetDim](#getdim)|Dizideki boyutların sayısını döndürür.|
|[Colet SAFEARRAY:: GetElement](#getelement)|Güvenli dizinin tek bir öğesini alır.|
|[Colet SAFEARRAY:: GetElemSize](#getelemsize)|Güvenli bir dizideki bir öğenin bayt cinsinden boyutunu döndürür.|
|[Cotasafearray:: Getllimit](#getlbound)|Güvenli bir dizinin herhangi bir boyutu için alt sınır döndürür.|
|[Cotasafearray:: GetOneDimSize](#getonedimsize)|Tek boyutlu nesnedeki öğe sayısını döndürür `COleSafeArray` .|
|[Colet SAFEARRAY:: Getubağlanacak](#getubound)|Güvenli bir dizinin herhangi bir boyutu için üst sınırı döndürür.|
|[COleSafeArray:: Lock](#lock)|Bir dizinin kilit sayısını artırır ve dizi Tanımlayıcıdaki dizi verilerine bir işaretçi koyar.|
|[Colet SAFEARRAY::P trOfIndex](#ptrofindex)|Dizinli öğe için bir işaretçi döndürür.|
|[Colet SAFEARRAY::P Uıtelement](#putelement)|Diziye tek bir öğe atar.|
|[Colet SAFEARRAY:: ReDim](#redim)|Güvenli bir dizinin en az önemli (en sağdaki) ilişkisini değiştirir.|
|[Colet SAFEARRAY:: Resizeonedid](#resizeonedim)|Tek boyutlu bir nesnedeki öğelerin sayısını değiştirir `COleSafeArray` .|
|[Cotasafearray:: UnaccessData](#unaccessdata)|Bir dizinin kilit sayısını azaltır ve tarafından alınan işaretçiyi geçersiz kılar `AccessData` .|
|[Cotasafearray:: unlock](#unlock)|Boşaltılacak veya yeniden boyutlandırılabilmesi için bir dizinin kilit sayısını azaltır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[COleSafeArray:: operator LPCVARYANT](#operator_lpcvariant)|`VARIANT`Nesnenin temel yapısına erişir `COleSafeArray` .|
|[COleSafeArray:: operator LPVARYANT](#operator_lpvariant)|`VARIANT`Nesnenin temel yapısına erişir `COleSafeArray` .|
|[COleSafeArray:: operator =](#operator_eq)|Değerleri bir `COleSafeArray` nesneye (,, `SAFEARRAY` `VARIANT` `COleVariant` veya `COleSafeArray` diziye) kopyalar.|
|[COleSafeArray:: operator = =](#operator_eq_eq)|İki varyant dizilerini ( `SAFEARRAY` ,, `VARIANT` `COleVariant` veya `COleSafeArray` dizilerini) karşılaştırır.|
|[COleSafeArray:: işleci &lt;&lt;](#operator_lt_lt)|Bir `COleSafeArray` nesnenin içeriğini döküm bağlamına çıkarır.|

## <a name="remarks"></a>Açıklamalar

`COleSafeArray` OLE `VARIANT` yapısından türetilir. OLE `SAFEARRAY` üye işlevleri ile birlikte kullanılabilir ve `COleSafeArray` özel olarak tek boyutlu bayt dizileri için tasarlanmış bir üye işlevleri kümesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagVARIANT`

`COleSafeArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="colesafearrayaccessdata"></a><a name="accessdata"></a> Colet SAFEARRAY:: AccessData

Dizi verilerine yönelik bir işaretçi alır.

```cpp
void AccessData(void** ppvData);
```

### <a name="parameters"></a>Parametreler

*ppvData*<br/>
Dizi verilerine yönelik işaretçiye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]

## <a name="colesafearrayallocdata"></a><a name="allocdata"></a> Colet SAFEARRAY:: AllocData

Güvenli bir dizi için belleği ayırır.

```cpp
void AllocData();
```

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

## <a name="colesafearrayallocdescriptor"></a><a name="allocdescriptor"></a> Colet SAFEARRAY:: AllocDescriptor

Güvenli bir dizinin tanımlayıcısı için belleği ayırır.

```cpp
void AllocDescriptor(DWORD dwDims);
```

### <a name="parameters"></a>Parametreler

*Dwdıms*<br/>
Güvenli dizideki boyut sayısı.

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

## <a name="colesafearrayattach"></a><a name="attach"></a> Colet SAFEARRAY:: Attach

Nesneye varolan bir dizideki verilerin denetimini verir `VARIANT` `COleSafeArray` .

```cpp
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>Parametreler

*varSrc*<br/>
Bir `VARIANT` nesnesi. *VarSrc* parametresinin VarType [vt_array](/windows/win32/api/wtypes/ne-wtypes-varenum)olması gerekir.

### <a name="remarks"></a>Açıklamalar

Kaynağın `VARIANT` türü VT_EMPTY olarak ayarlanır. Bu işlev, varsa geçerli dizi verilerini temizler.

### <a name="example"></a>Örnek

  [Cotasafearray:: AccessData](#accessdata)için örneğe bakın.

## <a name="colesafearrayclear"></a><a name="clear"></a> COleSafeArray:: Clear

Güvenli diziyi temizler.

```cpp
void Clear();
```

### <a name="remarks"></a>Açıklamalar

İşlevi, nesnesini VT_EMPTY olarak ayarlayarak güvenli bir diziyi temizler `VARTYPE` . Geçerli içerik serbest bırakılır ve dizi serbest bırakılır.

## <a name="colesafearraycolesafearray"></a><a name="colesafearray"></a> Colet SAFEARRAY:: Cotasafearray

Bir `COleSafeArray` nesnesi oluşturur.

```
COleSafeArray();

COleSafeArray(
    const SAFEARRAY& saSrc,
    VARTYPE vtSrc);

COleSafeArray(
    LPCSAFEARRAY pSrc,
    VARTYPE vtSrc);

COleSafeArray(const COleSafeArray& saSrc);
COleSafeArray(const VARIANT& varSrc);
COleSafeArray(LPCVARIANT pSrc);
COleSafeArray(const COleVariant& varSrc);
```

### <a name="parameters"></a>Parametreler

*saSrc*<br/>
Varolan bir `COleSafeArray` nesne veya `SAFEARRAY` Yeni `COleSafeArray` nesneye kopyalanacak.

*vtSrc*<br/>
Yeni `COleSafeArray` NESNENIN vartype.

*psaSrc*<br/>
`SAFEARRAY`Yeni nesnesine kopyalanacak bir işaretçisi `COleSafeArray` .

*varSrc*<br/>
`VARIANT` `COleVariant` Yeni nesneye Kopyalanacak varolan veya nesne `COleSafeArray` .

*pSrc*<br/>
`VARIANT`Yeni nesneye kopyalanacak bir nesne işaretçisi `COleSafeArray` .

### <a name="remarks"></a>Açıklamalar

Bu oluşturucuların hepsi yeni nesneler oluşturur `COleSafeArray` . Parametre yoksa boş bir `COleSafeArray` nesne oluşturulur (VT_EMPTY). `COleSafeArray`VarType örtük olarak bilinen başka bir diziden (bir, veya) kopyalanırsa `COleSafeArray` `COleVariant` `VARIANT` , kaynak dizisinin VarType korunur ve belirtilmesi gerekmez. , `COleSafeArray` VarType bilinmeyen olmayan başka bir diziden kopyalanırsa ( `SAFEARRAY` ), bir vartype, *vtSrc* parametresinde belirtilmelidir.

Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

## <a name="colesafearraycopy"></a><a name="copy"></a> Cotasafearray:: Copy

Var olan bir güvenli dizinin kopyasını oluşturur.

```cpp
void Copy(LPSAFEARRAY* ppsa);
```

### <a name="parameters"></a>Parametreler

*ppsa*<br/>
Yeni dizi tanımlayıcısının döndürüleceği konuma yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

## <a name="colesafearraycreate"></a><a name="create"></a> Colet SAFEARRAY:: Create

Dizi için verileri ayırır ve başlatır.

```cpp
void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    DWORD* rgElements);

void Create(
    VARTYPE vtSrc,
    DWORD dwDims,
    SAFEARRAYBOUND* rgsabounds);
```

### <a name="parameters"></a>Parametreler

*vtSrc*<br/>
Dizinin temel türü (yani, dizinin her bir öğesinin VARTYPE). VARTYPE, değişken türlerinin bir alt kümesiyle kısıtlıdır. Ne VT_ARRAY ne de VT_BYREF bayrağı ayarlanabilir. VT_EMPTY ve VT_NULL dizi için geçerli temel türler değil. Diğer tüm türler geçerlidir.

*Dwdıms*<br/>
Dizideki boyut sayısı. Bu, dizi [ReDim](#redim)ile oluşturulduktan sonra değiştirilebilir.

*rgElements*<br/>
Dizideki her boyut için öğe sayısı dizisine yönelik işaretçi.

*rgsasınır*<br/>
Dizi için ayrılacak sınırlara yönelik bir vektör (her boyut için bir tane) işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu işlev, gerekirse geçerli dizi verilerini temizler. Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md)oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

## <a name="colesafearraycreateonedim"></a><a name="createonedim"></a> Colet SAFEARRAY:: Createonedid

Yeni bir boyutlu `COleSafeArray` nesne oluşturur.

```cpp
void CreateOneDim(
    VARTYPE vtSrc,
    DWORD dwElements,
    const void* pvSrcData = NULL,
    long nLBound = 0);
```

### <a name="parameters"></a>Parametreler

*vtSrc*<br/>
Dizinin temel türü (yani, dizinin her bir öğesinin VARTYPE).

*dwElements*<br/>
Dizideki öğe sayısı. Bu, array [Resizeonedid](#resizeonedim)ile oluşturulduktan sonra değiştirilebilir.

*pvSrcData*<br/>
Diziye kopyalanacak verilerin işaretçisi.

*Nlbağlanmadı*<br/>
Dizinin alt sınırı.

### <a name="remarks"></a>Açıklamalar

İşlevi, dizi verilerini ayırır ve başlatır, bu, *pvSrcData* işaretçisi null değilse belirtilen verileri kopyalar.

Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md)oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]

## <a name="colesafearraydestroy"></a><a name="destroy"></a> Colet SAFEARRAY::D estroy

Varolan bir dizi tanımlayıcısını ve dizideki tüm verileri yok eder.

```cpp
void Destroy();
```

### <a name="remarks"></a>Açıklamalar

Nesneler dizide depolanıyorsa, her nesne serbest bırakılır. Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

## <a name="colesafearraydestroydata"></a><a name="destroydata"></a> Colet SAFEARRAY::D estroyData

Tüm verileri güvenli bir dizide yok eder.

```cpp
void DestroyData();
```

### <a name="remarks"></a>Açıklamalar

Nesneler dizide depolanıyorsa, her nesne serbest bırakılır. Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

## <a name="colesafearraydestroydescriptor"></a><a name="destroydescriptor"></a> Colet SAFEARRAY::D estroyDescriptor

Güvenli dizi tanımlayıcısını yok eder.

```cpp
void DestroyDescriptor();
```

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

## <a name="colesafearraydetach"></a><a name="detach"></a> Colet SAFEARRAY::D etach

`VARIANT`Verileri `COleSafeArray` nesneden ayırır.

```
VARIANT Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki temel alınan `VARIANT` değer `COleSafeArray` .

### <a name="remarks"></a>Açıklamalar

İşlevi, nesnenin VARTYPE VT_EMPTY olarak ayarlanarak verileri güvenli bir dizide ayırır. Windows işlevi [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear)' ı çağırarak diziyi serbest bırakma sorumluluğudur.

Hatada, işlev bir [Copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

### <a name="example"></a>Örnek

  [Cotasafearray::P Uıtelement](#putelement)örneğine bakın.

## <a name="colesafearraygetbytearray"></a><a name="getbytearray"></a> Colet SAFEARRAY:: GetByteArray

Güvenli dizinin içeriğini bir ' a kopyalar `CByteArray` .

```cpp
void GetByteArray(CByteArray& bytes);
```

### <a name="parameters"></a>Parametreler

*sayacının*<br/>
Bir [CByteArray](../../mfc/reference/cbytearray-class.md) nesnesine başvuru.

## <a name="colesafearraygetdim"></a><a name="getdim"></a> Colet SAFEARRAY:: GetDim

Nesnedeki boyut sayısını döndürür `COleSafeArray` .

```
DWORD GetDim();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenli dizideki boyutların sayısı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

## <a name="colesafearraygetelement"></a><a name="getelement"></a> Colet SAFEARRAY:: GetElement

Güvenli dizinin tek bir öğesini alır.

```cpp
void GetElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>Parametreler

*Rgindeksler*<br/>
Dizinin her boyutu için Dizin dizisine yönelik işaretçi.

*pvData*<br/>
Dizinin öğesine yerleştirilecek konuma yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev Windows işlevlerini otomatik olarak çağırır `SafeArrayLock` ve `SafeArrayUnlock` öğesinden önce ve sonra. Veri öğesi bir dize, nesne veya varyant ise, işlev öğeyi doğru şekilde kopyalar. *PvData* parametresi, öğeyi içermesi için yeterince büyük bir arabelleğe işaret etmelidir.

Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]

## <a name="colesafearraygetelemsize"></a><a name="getelemsize"></a> Colet SAFEARRAY:: GetElemSize

Bir nesne içindeki bir öğenin boyutunu alır `COleSafeArray` .

```
DWORD GetElemSize();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenli bir dizinin öğelerinin bayt cinsinden boyutu.

## <a name="colesafearraygetlbound"></a><a name="getlbound"></a> Cotasafearray:: Getllimit

Bir nesnenin herhangi bir boyutu için alt sınır döndürür `COleSafeArray` .

```cpp
void GetLBound(
    DWORD dwDim,
    long* pLBound);
```

### <a name="parameters"></a>Parametreler

*dwDim*<br/>
Alt sınırın alınacağı dizi boyutu.

*Pllimit*<br/>
Alt sınır döndürecek konuma yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [Copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]

## <a name="colesafearraygetonedimsize"></a><a name="getonedimsize"></a> Cotasafearray:: GetOneDimSize

Tek boyutlu nesnedeki öğe sayısını döndürür `COleSafeArray` .

```
DWORD GetOneDimSize();
```

### <a name="return-value"></a>Dönüş Değeri

Tek boyutlu güvenli dizideki öğelerin sayısı.

### <a name="example"></a>Örnek

  [Cotasafearray:: Createonedid](#createonedim)için örneğe bakın.

## <a name="colesafearraygetubound"></a><a name="getubound"></a> Colet SAFEARRAY:: Getubağlanacak

Güvenli bir dizinin herhangi bir boyutu için üst sınırı döndürür.

```cpp
void GetUBound(
    DWORD dwDim,
    long* pUBound);
```

### <a name="parameters"></a>Parametreler

*dwDim*<br/>
Üst sınır alınacak dizi boyutu.

*Pusınırı*<br/>
Üst sınırı döndürecek konuma yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [Copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]

## <a name="colesafearraylock"></a><a name="lock"></a> COleSafeArray:: Lock

Bir dizinin kilit sayısını artırır ve dizi Tanımlayıcıdaki dizi verilerine bir işaretçi yerleştirir.

```cpp
void Lock();
```

### <a name="remarks"></a>Açıklamalar

Hatada, bir [Copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

Dizi Tanımlayıcıdaki işaretçi, çağrılana kadar geçerlidir `Unlock` . İçin yapılan çağrılar `Lock` iç içe olabilir; buna eşit sayıda çağrı `Unlock` yapılması gerekir.

Bir dizi kilitliyken silinemez.

## <a name="colesafearrayoperator-lpcvariant"></a><a name="operator_lpcvariant"></a> COleSafeArray:: operator LPCVARYANT

Bu nesne için temel yapıya erişmek üzere bu atama işlecini çağırın `VARIANT` `COleSafeArray` .

```
operator LPCVARIANT() const;
```

## <a name="colesafearrayoperator-lpvariant"></a><a name="operator_lpvariant"></a> COleSafeArray:: operator LPVARYANT

Bu nesne için temel yapıya erişmek üzere bu atama işlecini çağırın `VARIANT` `COleSafeArray` .

```
operator LPVARIANT();
```

### <a name="remarks"></a>Açıklamalar

`VARIANT`Bu işlevin döndürdüğü işaretçinin eriştiği yapıda değerin değiştirilmesinin, bu nesnenin değerini değiştirecek olduğunu unutmayın `COleSafeArray` .

## <a name="colesafearrayoperator-"></a><a name="operator_eq"></a> COleSafeArray:: operator =

Bu aşırı yüklenmiş atama işleçleri kaynak değeri bu nesneye kopyalar `COleSafeArray` .

```
COleSafeArray& operator=(const COleSafeArray& saSrc);
COleSafeArray& operator=(const VARIANT& varSrc);
COleSafeArray& operator=(LPCVARIANT pSrc);
COleSafeArray& operator=(const COleVariant& varSrc);
```

### <a name="remarks"></a>Açıklamalar

Her işlecin kısa bir açıklaması aşağıdadır:

- **operator = (** *sasrc* **)** Varolan bir `COleSafeArray` nesneyi bu nesneye kopyalar.

- **operator = (** *varSrc* **)** Varolan bir `VARIANT` veya `COleVariant` diziyi bu nesneye kopyalar.

- **operator = (** *pSrc* **)** `VARIANT` *PSrc* tarafından erişilen dizi nesnesini bu nesneye kopyalar.

## <a name="colesafearrayoperator-"></a><a name="operator_eq_eq"></a> COleSafeArray:: operator = =

Bu işleç iki diziyi ( `SAFEARRAY` ,, `VARIANT` `COleVariant` veya `COleSafeArray` dizileri) karşılaştırır ve eşitse sıfır dışında bir değer döndürür; Aksi takdirde 0.

```
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;

BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;

BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;
```

### <a name="remarks"></a>Açıklamalar

Eşit sayıda boyut, her boyutta eşit boyut ve eşit öğe değeri varsa iki dizi eşittir.

## <a name="colesafearrayoperator-ltlt"></a><a name="operator_lt_lt"></a> COleSafeArray:: işleci &lt;&lt;

`COleSafeArray`Ekleme (<<) işleci, bir nesneyi bir arşive yönelik tanılama dökümünü ve depolamayı destekler `COleSafeArray` .

```
CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    COleSafeArray& saSrc);
```

## <a name="colesafearrayptrofindex"></a><a name="ptrofindex"></a> Colet SAFEARRAY::P trOfIndex

Dizin değerleri tarafından belirtilen öğeye bir işaretçi döndürür.

```cpp
void PtrOfIndex(
    long* rgIndices,
    void** ppvData);
```

### <a name="parameters"></a>Parametreler

*Rgindeksler*<br/>
Dizinin bir öğesini tanımlayan dizin değerleri dizisi. Öğe için tüm dizinler belirtilmelidir.

*ppvData*<br/>
Dönüşte, *Rgdizinler* içindeki değerler tarafından tanımlanan öğe işaretçisi.

## <a name="colesafearrayputelement"></a><a name="putelement"></a> Colet SAFEARRAY::P Uıtelement

Diziye tek bir öğe atar.

```cpp
void PutElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>Parametreler

*Rgindeksler*<br/>
Dizinin her boyutu için Dizin dizisine yönelik işaretçi.

*pvData*<br/>
Diziye atanacak verilerin işaretçisi. VT_DISPATCH, VT_UNKNOWN ve VT_BSTR değişken türleri işaretçilerdir ve başka bir yöneltme düzeyi gerektirmez.

### <a name="remarks"></a>Açıklamalar

Bu işlev, öğe atamadan önce ve sonra [SafeArrayLock](/windows/win32/api/oleauto/nf-oleauto-safearraylock) ve [SafeArrayUnlock](/windows/win32/api/oleauto/nf-oleauto-safearrayunlock) Windows işlevlerini otomatik olarak çağırır. Veri öğesi bir dize, nesne veya varyant ise, işlev onu doğru şekilde kopyalar ve varolan öğe bir dize, nesne veya varyant ise doğru temizlenir.

Dizi üzerinde birden çok kilitleme olabileceğini unutmayın, bu sayede dizi başka işlemler tarafından kilitliyken diziyi bir diziye yerleştirebilirsiniz.

Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]

## <a name="colesafearrayredim"></a><a name="redim"></a> Colet SAFEARRAY:: ReDim

Güvenli bir dizinin en az önemli (en sağdaki) ilişkisini değiştirir.

```cpp
void Redim(SAFEARRAYBOUND* psaboundNew);
```

### <a name="parameters"></a>Parametreler

*psaboundNew*<br/>
Yeni dizi ilişkisini içeren yeni bir güvenli dizi bağlantılı yapısına yönelik işaretçi. Bir dizinin yalnızca en az önemli boyutu değişebilir.

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [Copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

## <a name="colesafearrayresizeonedim"></a><a name="resizeonedim"></a> Colet SAFEARRAY:: Resizeonedid

Tek boyutlu bir nesnedeki öğelerin sayısını değiştirir `COleSafeArray` .

```cpp
void ResizeOneDim(DWORD dwElements);
```

### <a name="parameters"></a>Parametreler

*dwElements*<br/>
Tek boyutlu güvenli dizideki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [Copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

### <a name="example"></a>Örnek

  [Cotasafearray:: Createonedid](#createonedim)için örneğe bakın.

## <a name="colesafearrayunaccessdata"></a><a name="unaccessdata"></a> Cotasafearray:: UnaccessData

Bir dizinin kilit sayısını azaltır ve tarafından alınan işaretçiyi geçersiz kılar `AccessData` .

```cpp
void UnaccessData();
```

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [Copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

### <a name="example"></a>Örnek

  [Cotasafearray:: AccessData](#accessdata)için örneğe bakın.

## <a name="colesafearrayunlock"></a><a name="unlock"></a> Cotasafearray:: unlock

Boşaltılacak veya yeniden boyutlandırılabilmesi için bir dizinin kilit sayısını azaltır.

```cpp
void Unlock();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, bir dizideki verilere erişim bittiğinde çağrılır. Hatada, bir [Copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Cotavariant sınıfı](../../mfc/reference/colevariant-class.md)<br/>
[CRecordset sınıfı](../../mfc/reference/crecordset-class.md)<br/>
[CDatabase sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
