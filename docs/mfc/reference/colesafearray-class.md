---
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
ms.openlocfilehash: a0ce0fc03923806c9e044a7edae3178fd3429b76
ms.sourcegitcommit: e10a5feea193c249ddc5a6faba48e7c6d8784e73
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70177402"
---
# <a name="colesafearray-class"></a>Colet SAFEARRAY sınıfı

Rastgele tür ve boyut dizileri ile çalışmaya yönelik bir sınıf.

## <a name="syntax"></a>Sözdizimi

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
|[Colet SAFEARRAY:: Attach](#attach)|`COleSafeArray` Nesnenin varolan `VARIANT` dizisinin denetimini verir.|
|[COleSafeArray:: Clear](#clear)|Temeldeki `VARIANT`tüm verileri serbest bırakır.|
|[Cotasafearray:: Copy](#copy)|Varolan bir dizinin kopyasını oluşturur.|
|[Colet SAFEARRAY:: Create](#create)|Güvenli bir dizi oluşturur.|
|[Colet SAFEARRAY:: Createonedid](#createonedim)|Tek boyutlu `COleSafeArray` bir nesne oluşturur.|
|[Colet SAFEARRAY::D estroy](#destroy)|Var olan bir diziyi yok eder.|
|[Colet SAFEARRAY::D estroyData](#destroydata)|Güvenli bir dizide verileri yok eder.|
|[Colet SAFEARRAY::D estroyDescriptor](#destroydescriptor)|Güvenli dizi tanımlayıcısını yok eder.|
|[Colet SAFEARRAY::D etach](#detach)|Değişken diziyi `COleSafeArray` nesnesinden ayırır (böylece veriler serbest bırakılmaz).|
|[Colet SAFEARRAY:: GetByteArray](#getbytearray)|Güvenli dizinin içeriğini bir [CByteArray](../../mfc/reference/cbytearray-class.md)öğesine kopyalar.|
|[Colet SAFEARRAY:: GetDim](#getdim)|Dizideki boyutların sayısını döndürür.|
|[Colet SAFEARRAY:: GetElement](#getelement)|Güvenli dizinin tek bir öğesini alır.|
|[Colet SAFEARRAY:: GetElemSize](#getelemsize)|Güvenli bir dizideki bir öğenin bayt cinsinden boyutunu döndürür.|
|[Cotasafearray:: Getllimit](#getlbound)|Güvenli bir dizinin herhangi bir boyutu için alt sınır döndürür.|
|[Cotasafearray:: GetOneDimSize](#getonedimsize)|Tek boyutlu `COleSafeArray` nesnedeki öğe sayısını döndürür.|
|[Colet SAFEARRAY:: Getubağlanacak](#getubound)|Güvenli bir dizinin herhangi bir boyutu için üst sınırı döndürür.|
|[COleSafeArray:: Lock](#lock)|Bir dizinin kilit sayısını artırır ve dizi Tanımlayıcıdaki dizi verilerine bir işaretçi koyar.|
|[Colet SAFEARRAY::P trOfIndex](#ptrofindex)|Dizinli öğe için bir işaretçi döndürür.|
|[Colet SAFEARRAY::P Uıtelement](#putelement)|Diziye tek bir öğe atar.|
|[Colet SAFEARRAY:: ReDim](#redim)|Güvenli bir dizinin en az önemli (en sağdaki) ilişkisini değiştirir.|
|[Colet SAFEARRAY:: Resizeonedid](#resizeonedim)|Tek boyutlu `COleSafeArray` bir nesnedeki öğelerin sayısını değiştirir.|
|[Cotasafearray:: UnaccessData](#unaccessdata)|Bir dizinin kilit sayısını azaltır ve tarafından `AccessData`alınan işaretçiyi geçersiz kılar.|
|[Cotasafearray:: unlock](#unlock)|Boşaltılacak veya yeniden boyutlandırılabilmesi için bir dizinin kilit sayısını azaltır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[COleSafeArray:: operator LPCVARYANT](#operator_lpcvariant)|`COleSafeArray` Nesnenin temel `VARIANT` yapısına erişir.|
|[COleSafeArray:: operator LPVARYANT](#operator_lpvariant)|`COleSafeArray` Nesnenin temel `VARIANT` yapısına erişir.|
|[COleSafeArray:: operator =](#operator_eq)|Değerleri bir `COleSafeArray` nesneye (`SAFEARRAY`, `VARIANT` ,`COleVariant`veya diziye`COleSafeArray` ) kopyalar.|
|[COleSafeArray:: operator = =](#operator_eq_eq)|`SAFEARRAY`İki varyant dizilerini ( `VARIANT` `COleVariant`,, veya `COleSafeArray` dizilerini) karşılaştırır.|
|[COleSafeArray:: işleci&lt;&lt;](#operator_lt_lt)|Bir `COleSafeArray` nesnenin içeriğini döküm bağlamına çıkarır.|

## <a name="remarks"></a>Açıklamalar

`COleSafeArray`OLE `VARIANT` yapısından türetilir. OLE `SAFEARRAY` üye işlevleri ile `COleSafeArray`birlikte kullanılabilir ve özel olarak tek boyutlu bayt dizileri için tasarlanmış bir üye işlevleri kümesi.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagVARIANT`

`COleSafeArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

##  <a name="accessdata"></a>Colet SAFEARRAY:: AccessData

Dizi verilerine yönelik bir işaretçi alır.

```
void AccessData(void** ppvData);
```

### <a name="parameters"></a>Parametreler

*ppvData*<br/>
Dizi verilerine yönelik işaretçiye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]

##  <a name="allocdata"></a>Colet SAFEARRAY:: AllocData

Güvenli bir dizi için belleği ayırır.

```
void AllocData();
```

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

##  <a name="allocdescriptor"></a>Colet SAFEARRAY:: AllocDescriptor

Güvenli bir dizinin tanımlayıcısı için belleği ayırır.

```
void AllocDescriptor(DWORD dwDims);
```

### <a name="parameters"></a>Parametreler

*Dwdıms*<br/>
Güvenli dizideki boyut sayısı.

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

##  <a name="attach"></a>Colet SAFEARRAY:: Attach

`COleSafeArray` Nesneye varolan `VARIANT` bir dizideki verilerin denetimini verir.

```
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>Parametreler

*varSrc*<br/>
A `VARIANT` nesne. *VarSrc* parametresinin VarType [vt_array](/windows/win32/api/wtypes/ne-wtypes-varenum)olması gerekir.

### <a name="remarks"></a>Açıklamalar

Kaynağın `VARIANT`türü VT_EMPTY olarak ayarlanır. Bu işlev, varsa geçerli dizi verilerini temizler.

### <a name="example"></a>Örnek

  [Cotasafearray:: AccessData](#accessdata)için örneğe bakın.

##  <a name="clear"></a>COleSafeArray:: Clear

Güvenli diziyi temizler.

```
void Clear();
```

### <a name="remarks"></a>Açıklamalar

İşlevi, nesnesinin öğesini VT_EMPTY olarak ayarlayarak `VARTYPE` güvenli bir diziyi temizler. Geçerli içerik serbest bırakılır ve dizi serbest bırakılır.

##  <a name="colesafearray"></a>Colet SAFEARRAY:: Cotasafearray

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
Varolan `COleSafeArray` bir nesne veya `SAFEARRAY` yeni `COleSafeArray` nesneye kopyalanacak.

*vtSrc*<br/>
Yeni `COleSafeArray` nesnenin vartype.

*psaSrc*<br/>
`SAFEARRAY` Yeni`COleSafeArray` nesnesine kopyalanacak bir işaretçisi.

*varSrc*<br/>
Yeni `COleVariant` `VARIANT` nesneyeKopyalanacakvarolanveyanesne`COleSafeArray` .

*pSrc*<br/>
`VARIANT` Yeni`COleSafeArray` nesneye kopyalanacak bir nesne işaretçisi.

### <a name="remarks"></a>Açıklamalar

Bu oluşturucuların hepsi yeni `COleSafeArray` nesneler oluşturur. Parametre yoksa boş `COleSafeArray` bir nesne oluşturulur (VT_EMPTY). VARTYPE örtük olarak bilinen başka bir diziden `COleVariant`(bir `COleSafeArray`, veya `VARIANT`) kopyalanırsa, kaynak dizisinin VarType korunur ve belirtilmesi gerekmez. `COleSafeArray` , `COleSafeArray` VarType bilinmeyen olmayan başka bir diziden kopyalanırsa (`SAFEARRAY`), bir vartype, *vtSrc* parametresinde belirtilmelidir.

Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

##  <a name="copy"></a>Cotasafearray:: Copy

Var olan bir güvenli dizinin kopyasını oluşturur.

```
void Copy(LPSAFEARRAY* ppsa);
```

### <a name="parameters"></a>Parametreler

*ppsa*<br/>
Yeni dizi tanımlayıcısının döndürüleceği konuma yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

##  <a name="create"></a>Colet SAFEARRAY:: Create

Dizi için verileri ayırır ve başlatır.

```
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
Dizinin temel türü (yani, dizinin her bir öğesinin VARTYPE). VARTYPE, değişken türlerinin bir alt kümesiyle kısıtlıdır. Ne VT_ARRAY ne de VT_BYREF bayrağı ayarlanabilir. VT_EMPTY ve VT_NULL, dizi için geçerli temel türler değildir. Diğer tüm türler geçerlidir.

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

##  <a name="createonedim"></a>Colet SAFEARRAY:: Createonedid

Yeni bir boyutlu `COleSafeArray` nesne oluşturur.

```
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

##  <a name="destroy"></a>Colet SAFEARRAY::D estroy

Varolan bir dizi tanımlayıcısını ve dizideki tüm verileri yok eder.

```
void Destroy();
```

### <a name="remarks"></a>Açıklamalar

Nesneler dizide depolanıyorsa, her nesne serbest bırakılır. Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

##  <a name="destroydata"></a>Colet SAFEARRAY::D estroyData

Tüm verileri güvenli bir dizide yok eder.

```
void DestroyData();
```

### <a name="remarks"></a>Açıklamalar

Nesneler dizide depolanıyorsa, her nesne serbest bırakılır. Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

##  <a name="destroydescriptor"></a>Colet SAFEARRAY::D estroyDescriptor

Güvenli dizi tanımlayıcısını yok eder.

```
void DestroyDescriptor();
```

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

##  <a name="detach"></a>Colet SAFEARRAY::D etach

`VARIANT` Verileri`COleSafeArray` nesneden ayırır.

```
VARIANT Detach();
```

### <a name="return-value"></a>Dönüş Değeri

`COleSafeArray` Nesnedeki temel alınan `VARIANT` değer.

### <a name="remarks"></a>Açıklamalar

İşlevi, nesnenin VARTYPE VT_EMPTY olarak ayarlanarak verileri güvenli bir dizide ayırır. Windows işlevi [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear)' ı çağırarak diziyi serbest bırakma sorumluluğudur.

Hatada, işlev bir [Copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

### <a name="example"></a>Örnek

  [Cotasafearray::P Uıtelement](#putelement)örneğine bakın.

##  <a name="getbytearray"></a>Colet SAFEARRAY:: GetByteArray

Güvenli dizinin içeriğini bir ' a `CByteArray`kopyalar.

```
void GetByteArray(CByteArray& bytes);
```

### <a name="parameters"></a>Parametreler

*sayacının*<br/>
Bir [CByteArray](../../mfc/reference/cbytearray-class.md) nesnesine başvuru.

##  <a name="getdim"></a>Colet SAFEARRAY:: GetDim

`COleSafeArray` Nesnedeki boyut sayısını döndürür.

```
DWORD GetDim();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenli dizideki boyutların sayısı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

##  <a name="getelement"></a>Colet SAFEARRAY:: GetElement

Güvenli dizinin tek bir öğesini alır.

```
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

Bu işlev Windows işlevlerini `SafeArrayLock` otomatik olarak çağırır ve `SafeArrayUnlock` öğesinden önce ve sonra. Veri öğesi bir dize, nesne veya varyant ise, işlev öğeyi doğru şekilde kopyalar. *PvData* parametresi, öğeyi içermesi için yeterince büyük bir arabelleğe işaret etmelidir.

Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]

##  <a name="getelemsize"></a>Colet SAFEARRAY:: GetElemSize

Bir `COleSafeArray` nesne içindeki bir öğenin boyutunu alır.

```
DWORD GetElemSize();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenli bir dizinin öğelerinin bayt cinsinden boyutu.

##  <a name="getlbound"></a>Cotasafearray:: Getllimit

Bir nesnenin herhangi bir `COleSafeArray` boyutu için alt sınır döndürür.

```
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

##  <a name="getonedimsize"></a>Cotasafearray:: GetOneDimSize

Tek boyutlu `COleSafeArray` nesnedeki öğe sayısını döndürür.

```
DWORD GetOneDimSize();
```

### <a name="return-value"></a>Dönüş Değeri

Tek boyutlu güvenli dizideki öğelerin sayısı.

### <a name="example"></a>Örnek

  [Cotasafearray:: Createonedid](#createonedim)için örneğe bakın.

##  <a name="getubound"></a>Colet SAFEARRAY:: Getubağlanacak

Güvenli bir dizinin herhangi bir boyutu için üst sınırı döndürür.

```
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

##  <a name="lock"></a>COleSafeArray:: Lock

Bir dizinin kilit sayısını artırır ve dizi Tanımlayıcıdaki dizi verilerine bir işaretçi yerleştirir.

```
void Lock();
```

### <a name="remarks"></a>Açıklamalar

Hatada, bir [Copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

Dizi Tanımlayıcıdaki işaretçi, çağrılana kadar `Unlock` geçerlidir. İçin `Lock` yapılan çağrılar iç içe olabilir; buna eşit sayıda `Unlock` çağrı yapılması gerekir.

Bir dizi kilitliyken silinemez.

##  <a name="operator_lpcvariant"></a>COleSafeArray:: operator LPCVARYANT

`VARIANT` Bu`COleSafeArray` nesne için temel yapıya erişmek üzere bu atama işlecini çağırın.

```
operator LPCVARIANT() const;
```

##  <a name="operator_lpvariant"></a>COleSafeArray:: operator LPVARYANT

`VARIANT` Bu`COleSafeArray` nesne için temel yapıya erişmek üzere bu atama işlecini çağırın.

```
operator LPVARIANT();
```

### <a name="remarks"></a>Açıklamalar

Bu işlevin döndürdüğü işaretçinin eriştiği `VARIANT` yapıda değerin değiştirilmesinin, bu `COleSafeArray` nesnenin değerini değiştirecek olduğunu unutmayın.

##  <a name="operator_eq"></a>COleSafeArray:: operator =

Bu aşırı yüklenmiş atama işleçleri kaynak değeri bu `COleSafeArray` nesneye kopyalar.

```
COleSafeArray& operator=(const COleSafeArray& saSrc);
COleSafeArray& operator=(const VARIANT& varSrc);
COleSafeArray& operator=(LPCVARIANT pSrc);
COleSafeArray& operator=(const COleVariant& varSrc);
```

### <a name="remarks"></a>Açıklamalar

Her işlecin kısa bir açıklaması aşağıdadır:

- **operator = (** *sasrc* **)** Varolan `COleSafeArray` bir nesneyi bu nesneye kopyalar.

- **operator = (** *varSrc* **)** Varolan `VARIANT` bir veya `COleVariant` diziyi bu nesneye kopyalar.

- **operator = (** *pSrc* **)** *PSrc* tarafından erişilen dizinesnesinibunesneyekopyalar.`VARIANT`

##  <a name="operator_eq_eq"></a>COleSafeArray:: operator = =

Bu işleç iki`SAFEARRAY`diziyi ( `COleVariant`, `VARIANT`, veya `COleSafeArray` dizileri) karşılaştırır ve eşitse sıfır dışında bir değer döndürür; Aksi takdirde 0.

```
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;

BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;

BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;
```

### <a name="remarks"></a>Açıklamalar

Eşit sayıda boyut, her boyutta eşit boyut ve eşit öğe değeri varsa iki dizi eşittir.

##  <a name="operator_lt_lt"></a>COleSafeArray:: işleci&lt;&lt;

Ekleme `COleSafeArray` (< <) işleci, bir `COleSafeArray` nesneyi bir arşive yönelik tanılama dökümünü ve depolamayı destekler.

```
CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    COleSafeArray& saSrc);
```

##  <a name="ptrofindex"></a>Colet SAFEARRAY::P trOfIndex

Dizin değerleri tarafından belirtilen öğeye bir işaretçi döndürür.

```
void PtrOfIndex(
    long* rgIndices,
    void** ppvData);
```

### <a name="parameters"></a>Parametreler

*Rgindeksler*<br/>
Dizinin bir öğesini tanımlayan dizin değerleri dizisi. Öğe için tüm dizinler belirtilmelidir.

*ppvData*<br/>
Dönüşte, *Rgdizinler*içindeki değerler tarafından tanımlanan öğe işaretçisi.

##  <a name="putelement"></a>Colet SAFEARRAY::P Uıtelement

Diziye tek bir öğe atar.

```
void PutElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>Parametreler

*Rgindeksler*<br/>
Dizinin her boyutu için Dizin dizisine yönelik işaretçi.

*pvData*<br/>
Diziye atanacak verilerin işaretçisi. VT_DISPATCH, VT_UNKNOWN ve VT_BSTR VARIANT türleri işaretçilerdir ve başka bir yöneltme düzeyi gerektirmez.

### <a name="remarks"></a>Açıklamalar

Bu işlev, öğe atamadan önce ve sonra [SafeArrayLock](/windows/win32/api/oleauto/nf-oleauto-safearraylock) ve [SafeArrayUnlock](/windows/win32/api/oleauto/nf-oleauto-safearrayunlock) Windows işlevlerini otomatik olarak çağırır. Veri öğesi bir dize, nesne veya varyant ise, işlev onu doğru şekilde kopyalar ve varolan öğe bir dize, nesne veya varyant ise doğru temizlenir.

Dizi üzerinde birden çok kilitleme olabileceğini unutmayın, bu sayede dizi başka işlemler tarafından kilitliyken diziyi bir diziye yerleştirebilirsiniz.

Hatada, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]

##  <a name="redim"></a>Colet SAFEARRAY:: ReDim

Güvenli bir dizinin en az önemli (en sağdaki) ilişkisini değiştirir.

```
void Redim(SAFEARRAYBOUND* psaboundNew);
```

### <a name="parameters"></a>Parametreler

*psaboundNew*<br/>
Yeni dizi ilişkisini içeren yeni bir güvenli dizi bağlantılı yapısına yönelik işaretçi. Bir dizinin yalnızca en az önemli boyutu değişebilir.

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [Copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

##  <a name="resizeonedim"></a>Colet SAFEARRAY:: Resizeonedid

Tek boyutlu `COleSafeArray` bir nesnedeki öğelerin sayısını değiştirir.

```
void ResizeOneDim(DWORD dwElements);
```

### <a name="parameters"></a>Parametreler

*dwElements*<br/>
Tek boyutlu güvenli dizideki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [Copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

### <a name="example"></a>Örnek

  [Cotasafearray:: Createonedid](#createonedim)için örneğe bakın.

##  <a name="unaccessdata"></a>Cotasafearray:: UnaccessData

Bir dizinin kilit sayısını azaltır ve tarafından `AccessData`alınan işaretçiyi geçersiz kılar.

```
void UnaccessData();
```

### <a name="remarks"></a>Açıklamalar

Hatada, işlev bir [Copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

### <a name="example"></a>Örnek

  [Cotasafearray:: AccessData](#accessdata)için örneğe bakın.

##  <a name="unlock"></a>Cotasafearray:: unlock

Boşaltılacak veya yeniden boyutlandırılabilmesi için bir dizinin kilit sayısını azaltır.

```
void Unlock();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, bir dizideki verilere erişim bittiğinde çağrılır. Hatada, bir [Copaexception](../../mfc/reference/coleexception-class.md)oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleVariant Sınıfı](../../mfc/reference/colevariant-class.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)<br/>
[CDatabase Sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
