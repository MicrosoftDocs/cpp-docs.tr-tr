---
title: COleSafeArray Sınıfı
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
ms.openlocfilehash: 10e9975bac776429a38bfc707215a9465ce35c2e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753764"
---
# <a name="colesafearray-class"></a>COleSafeArray Sınıfı

Rasgele tür ve boyut dizileri ile çalışmak için bir sınıf.

## <a name="syntax"></a>Sözdizimi

```
class COleSafeArray : public tagVARIANT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleSafeArray::COleSafeArray](#colesafearray)|Bir `COleSafeArray` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleSafeArray::AccessData](#accessdata)|Dizi verilerine bir işaretçi alır.|
|[COleSafeArray::AllocData](#allocdata)|Dizi için bellek ayırır.|
|[COleSafeArray::AllocDescriptor](#allocdescriptor)|Belleği güvenli dizi tanımlayıcısı için ayırır.|
|[COleSafeArray::Ekle](#attach)|Nesneye varolan `VARIANT` dizinin `COleSafeArray` denetimini verir.|
|[COleSafeArray::Temiz](#clear)|Temeldeki `VARIANT`tüm verileri boşaltıyor.|
|[COleSafeArray::Kopyala](#copy)|Varolan bir dizinin kopyasını oluşturur.|
|[COleSafeArray::Oluştur](#create)|Güvenli bir dizi oluşturur.|
|[COleSafeArray::CreateOneDim](#createonedim)|Tek boyutlu bir `COleSafeArray` nesne oluşturur.|
|[COleSafeArray::Destroy](#destroy)|Varolan bir diziyi yok eder.|
|[COleSafeArray::DestroyData](#destroydata)|Verileri güvenli bir dizide yok eder.|
|[COleSafeArray::DestroyDescriptor](#destroydescriptor)|Güvenli bir dizinin tanımlayıcısı yok eder.|
|[COleSafeArray::Detach](#detach)|VARYANT dizisini `COleSafeArray` nesneden ayırır (böylece veriler serbest bırakılmaz).|
|[COleSafeArray::GetByteArray](#getbytearray)|Güvenli dizinin içeriğini [cbyteArray'e](../../mfc/reference/cbytearray-class.md)kopyalar.|
|[COleSafeArray::GetDim](#getdim)|Dizideki boyut sayısını verir.|
|[COleSafeArray::GetElement](#getelement)|Güvenli dizinin tek bir öğesini alır.|
|[COleSafeArray::GetElemSize](#getelemsize)|Güvenli bir dizideki bir öğenin boyutunu baytolarak döndürür.|
|[COleSafeArray::GetLBound](#getlbound)|Güvenli bir dizinin herhangi bir boyutu için alt sınırı döndürür.|
|[COleSafeArray::GetOneDimSize](#getonedimsize)|Tek boyutlu `COleSafeArray` nesnedeki öğe sayısını verir.|
|[COleSafeArray::GetUBound](#getubound)|Güvenli bir dizinin herhangi bir boyutu için üst sınırı döndürür.|
|[COleSafeArray::Kilit](#lock)|Bir dizinin kilit sayısını artımlar ve dizi tanımlayıcısındaki dizi verilerine bir işaretçi yerleştirir.|
|[COleSafeArray::PtrOfIndex](#ptrofindex)|Dizinlenen öğeye bir işaretçi döndürür.|
|[COleSafeArray::PutElement](#putelement)|Diziye tek bir öğe atar.|
|[COleSafeArray::Redim](#redim)|Güvenli bir dizinin en az önemli (en sağ) bağlı olduğunu değiştirir.|
|[COleSafeArray::ResizeOneDim](#resizeonedim)|Tek boyutlu `COleSafeArray` bir nesnedeki öğelerin sayısını değiştirir.|
|[COleSafeArray::Erişimsiz Veri](#unaccessdata)|Bir dizinin kilit sayısını atar ve '' `AccessData`tarafından alınan işaretçiyi geçersiz kılmışolur.|
|[COleSafeArray::Kilidini aç](#unlock)|Bir dizinin kilit sayısını serbest bırakılabilmek veya yeniden boyutlandırılabilmek için atar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[COleSafeArray::operatör LPCVARIANT](#operator_lpcvariant)|Nesnenin alt `VARIANT` yapısına `COleSafeArray` erişer.|
|[COleSafeArray::operatör LPVARIANT](#operator_lpvariant)|Nesnenin alt `VARIANT` yapısına `COleSafeArray` erişer.|
|[COleSafeArray::operatör =](#operator_eq)|`COleSafeArray` Değerleri bir nesneye`SAFEARRAY`(, `COleVariant`, `COleSafeArray` `VARIANT`, veya dizi) kopyalar.|
|[COleSafeArray::operatör ==](#operator_eq_eq)|İki varyant diziyi`SAFEARRAY`(, `COleVariant`, `COleSafeArray` `VARIANT`, veya dizi) karşılaştırır.|
|[COleSafeArray::operatör&lt;&lt;](#operator_lt_lt)|Bir `COleSafeArray` nesnenin içeriğini döküm bağlamına çıkar.|

## <a name="remarks"></a>Açıklamalar

`COleSafeArray`OLE `VARIANT` yapısından türetilmiştir. OLE `SAFEARRAY` üye `COleSafeArray`işlevleri, tek boyutlu bayt dizileri için özel olarak tasarlanmış bir dizi üye işlevin yanı sıra kullanılabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagVARIANT`

`COleSafeArray`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="colesafearrayaccessdata"></a><a name="accessdata"></a>COleSafeArray::AccessData

Dizi verilerine bir işaretçi alır.

```cpp
void AccessData(void** ppvData);
```

### <a name="parameters"></a>Parametreler

*ppvData*<br/>
Dizi verilerine işaretçi.

### <a name="remarks"></a>Açıklamalar

Hata üzerine, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md)atar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]

## <a name="colesafearrayallocdata"></a><a name="allocdata"></a>COleSafeArray::AllocData

Belleği güvenli bir dizi için ayırır.

```cpp
void AllocData();
```

### <a name="remarks"></a>Açıklamalar

Hata üzerine, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md)atar.

## <a name="colesafearrayallocdescriptor"></a><a name="allocdescriptor"></a>COleSafeArray::AllocDescriptor

Belleği güvenli bir dizinin tanımlayıcısı için ayırır.

```cpp
void AllocDescriptor(DWORD dwDims);
```

### <a name="parameters"></a>Parametreler

*dwDims*<br/>
Güvenli dizideki boyut sayısı.

### <a name="remarks"></a>Açıklamalar

Hata üzerine, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md)atar.

## <a name="colesafearrayattach"></a><a name="attach"></a>COleSafeArray::Ekle

Varolan `VARIANT` bir dizideki verilerin denetimini `COleSafeArray` nesneye verir.

```cpp
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>Parametreler

*varSrc*<br/>
Bir `VARIANT` nesnesi. *VarSrc* parametresi VARTYPE [VT_ARRAY](/windows/win32/api/wtypes/ne-wtypes-varenum)olmalıdır.

### <a name="remarks"></a>Açıklamalar

Kaynak `VARIANT`türü VT_EMPTY olarak ayarlanır. Bu işlev varsa geçerli dizi verilerini temizler.

### <a name="example"></a>Örnek

  [COleSafeArray örneğine bakın:AccessData](#accessdata).

## <a name="colesafearrayclear"></a><a name="clear"></a>COleSafeArray::Temiz

Güvenli diziyi temizler.

```cpp
void Clear();
```

### <a name="remarks"></a>Açıklamalar

İşlev, `VARTYPE` nesnenin VT_EMPTY ayarlayarak güvenli bir dizi temizler. Geçerli içerik serbest bırakılır ve dizi serbest bırakılır.

## <a name="colesafearraycolesafearray"></a><a name="colesafearray"></a>COleSafeArray::COleSafeArray

Bir `COleSafeArray` nesne inşa eder.

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
Varolan `COleSafeArray` bir `SAFEARRAY` nesne veya yeni `COleSafeArray` nesneye kopyalanacak.

*vtSrc*<br/>
Yeni `COleSafeArray` nesnenin VARTYPE..

*psaSrc*<br/>
A'nın `SAFEARRAY` yeni nesneye kopyalanmasını `COleSafeArray` işaretçisi.

*varSrc*<br/>
Varolan `VARIANT` `COleVariant` veya yeni `COleSafeArray` nesneye kopyalanacak bir nesne.

*pSrc*<br/>
Yeni `COleSafeArray` nesneye `VARIANT` kopyalanacak bir nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Tüm bu kurucular yeni `COleSafeArray` nesneler oluştururlar. Parametre yoksa boş `COleSafeArray` bir nesne oluşturulur (VT_EMPTY). VARTYPE'ı örtülü olarak bilinen başka bir diziden `COleSafeArray` `COleVariant`kopyalanırsa `VARIANT`(a , veya ), kaynak dizinin VARTYPE'ı korunur ve belirtilmesi gerekmez. `COleSafeArray` `COleSafeArray` VARTYPE ()`SAFEARRAY`bilmeyen başka bir diziden kopyalanırsa, *VARTYPE vtSrc* parametresinde belirtilmelidir.

Hata üzerine, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md)atar.

## <a name="colesafearraycopy"></a><a name="copy"></a>COleSafeArray::Kopyala

Varolan güvenli dizinin bir kopyasını oluşturur.

```cpp
void Copy(LPSAFEARRAY* ppsa);
```

### <a name="parameters"></a>Parametreler

*ppsa*<br/>
Yeni dizi tanımlayıcısını döndürecek bir konuma işaretçi.

### <a name="remarks"></a>Açıklamalar

Hata üzerine, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md)atar.

## <a name="colesafearraycreate"></a><a name="create"></a>COleSafeArray::Oluştur

Dizi için verileri ayırır ve başharfe ayırır.

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
Dizinin temel türü (diğer bir şekilde, dizinin her öğesinin VARTYPE'ı). VARTYPE varyant türlerinin bir alt kümesiile sınırlıdır. Ne VT_ARRAY ne de VT_BYREF bayrağı ayarlanabilir. VT_EMPTY ve VT_NULL dizi için geçerli temel türleri değildir. Diğer tüm türleri yasaldır.

*dwDims*<br/>
Dizideki boyut sayısı. Bu, dizi [Redim](#redim)ile oluşturulduktan sonra değiştirilebilir.

*rgElements*<br/>
Dizideki her boyut için öğe sayısının bir diziişaretçisi.

*rgsabounds*<br/>
Diziye tahsis etmek üzere bir sınır vektörü (her boyut için bir tane) işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev gerekirse geçerli dizi verilerini temizler. Hata üzerine, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md)atar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

## <a name="colesafearraycreateonedim"></a><a name="createonedim"></a>COleSafeArray::CreateOneDim

Yeni bir tek boyutlu `COleSafeArray` nesne oluşturur.

```cpp
void CreateOneDim(
    VARTYPE vtSrc,
    DWORD dwElements,
    const void* pvSrcData = NULL,
    long nLBound = 0);
```

### <a name="parameters"></a>Parametreler

*vtSrc*<br/>
Dizinin temel türü (diğer bir şekilde, dizinin her öğesinin VARTYPE'ı).

*dwElements*<br/>
Dizideki öğe sayısı. Bu, dizi [ResizeOneDim](#resizeonedim)ile oluşturulduktan sonra değiştirilebilir.

*pvSrcData*<br/>
Diziye kopyalamak için verileri işaretçi.

*nLBound*<br/>
Dizinin alt sınırı.

### <a name="remarks"></a>Açıklamalar

İşlev, *işaretçi pvSrcData* NULL değilse, belirtilen verileri kopyalayarak dizi için verileri ayırır ve başharfe ayırır.

Hata üzerine, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md)atar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]

## <a name="colesafearraydestroy"></a><a name="destroy"></a>COleSafeArray::Destroy

Varolan bir dizi tanımlayıcısını ve dizideki tüm verileri yok eder.

```cpp
void Destroy();
```

### <a name="remarks"></a>Açıklamalar

Nesneler dizide depolanırsa, her nesne serbest bırakılır. Hata üzerine, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md)atar.

## <a name="colesafearraydestroydata"></a><a name="destroydata"></a>COleSafeArray::DestroyData

Güvenli bir dizideki tüm verileri yok eder.

```cpp
void DestroyData();
```

### <a name="remarks"></a>Açıklamalar

Nesneler dizide depolanırsa, her nesne serbest bırakılır. Hata üzerine, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md)atar.

## <a name="colesafearraydestroydescriptor"></a><a name="destroydescriptor"></a>COleSafeArray::DestroyDescriptor

Güvenli bir dizinin tanımlayıcısı yok eder.

```cpp
void DestroyDescriptor();
```

### <a name="remarks"></a>Açıklamalar

Hata üzerine, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md)atar.

## <a name="colesafearraydetach"></a><a name="detach"></a>COleSafeArray::Detach

`VARIANT` Verileri nesneden `COleSafeArray` ayırır.

```
VARIANT Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki `VARIANT` `COleSafeArray` temel değer.

### <a name="remarks"></a>Açıklamalar

İşlev, nesnenin VARTYPE'ını VT_EMPTY ayarlayarak verileri güvenli bir dizide ayırır. Windows işlevi [VariantClear'i](/windows/win32/api/oleauto/nf-oleauto-variantclear)arayarak diziyi serbest hale getirmek arayanın sorumluluğundadır.

Hata üzerine, işlev bir [COleException](../../mfc/reference/coleexception-class.md)atar.

### <a name="example"></a>Örnek

  COleSafeArray için örneğe [bakın::PutElement](#putelement).

## <a name="colesafearraygetbytearray"></a><a name="getbytearray"></a>COleSafeArray::GetByteArray

Güvenli dizinin içeriğini bir `CByteArray`.

```cpp
void GetByteArray(CByteArray& bytes);
```

### <a name="parameters"></a>Parametreler

*Bayt*<br/>
[CByteArray](../../mfc/reference/cbytearray-class.md) nesnesine başvuru.

## <a name="colesafearraygetdim"></a><a name="getdim"></a>COleSafeArray::GetDim

Nesnedeki `COleSafeArray` boyut sayısını verir.

```
DWORD GetDim();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenli dizideki boyut sayısı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

## <a name="colesafearraygetelement"></a><a name="getelement"></a>COleSafeArray::GetElement

Güvenli dizinin tek bir öğesini alır.

```cpp
void GetElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>Parametreler

*rgIndices*<br/>
Dizinin her boyutu için bir dizi dizin işaretçisi.

*pvData*<br/>
Dizinin öğesini yerleştirmek için konuma işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev, windows `SafeArrayLock` işlevlerini `SafeArrayUnlock` otomatik olarak çağırır ve öğeyi aldıktan önce ve sonra. Veri öğesi bir dize, nesne veya varyantsa, işlev öğeyi doğru şekilde kopyalar. *Parametre pvData* öğeyi içerecek kadar büyük bir arabelleğe işaret etmelidir.

Hata üzerine, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md)atar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]

## <a name="colesafearraygetelemsize"></a><a name="getelemsize"></a>COleSafeArray::GetElemSize

Bir `COleSafeArray` nesnedeki öğenin boyutunu alır.

```
DWORD GetElemSize();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenli bir dizinin öğelerinin baytboyutu.

## <a name="colesafearraygetlbound"></a><a name="getlbound"></a>COleSafeArray::GetLBound

Nesnenin herhangi bir `COleSafeArray` boyutu için alt sınırı döndürür.

```cpp
void GetLBound(
    DWORD dwDim,
    long* pLBound);
```

### <a name="parameters"></a>Parametreler

*dwDim*<br/>
Alt sınırı almak için dizi boyutu.

*pLBound*<br/>
Alt sınırı döndürmek için konumu işaretçi.

### <a name="remarks"></a>Açıklamalar

Hata üzerine, işlev bir [COleException](../../mfc/reference/coleexception-class.md)atar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]

## <a name="colesafearraygetonedimsize"></a><a name="getonedimsize"></a>COleSafeArray::GetOneDimSize

Tek boyutlu `COleSafeArray` nesnedeki öğe sayısını verir.

```
DWORD GetOneDimSize();
```

### <a name="return-value"></a>Dönüş Değeri

Tek boyutlu güvenli dizideki öğelerin sayısı.

### <a name="example"></a>Örnek

  [COleSafeArray örneğine bakın:CreateOneDim](#createonedim).

## <a name="colesafearraygetubound"></a><a name="getubound"></a>COleSafeArray::GetUBound

Güvenli bir dizinin herhangi bir boyutu için üst sınırı döndürür.

```cpp
void GetUBound(
    DWORD dwDim,
    long* pUBound);
```

### <a name="parameters"></a>Parametreler

*dwDim*<br/>
Üst sınırı almak için dizi boyutu.

*pUBound*<br/>
Üst sınırı döndürmek için konumu işaretle.

### <a name="remarks"></a>Açıklamalar

Hata üzerine, işlev bir [COleException](../../mfc/reference/coleexception-class.md)atar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]

## <a name="colesafearraylock"></a><a name="lock"></a>COleSafeArray::Kilit

Bir dizinin kilit sayısını artımlar ve dizi tanımlayıcısındadizi verilerine bir işaretçi yer.

```cpp
void Lock();
```

### <a name="remarks"></a>Açıklamalar

Hata üzerine, bir [COleException](../../mfc/reference/coleexception-class.md)atar.

Dizi tanımlayıcısındaki işaretçi çağrılana `Unlock` kadar geçerlidir. Yapılacak `Lock` aramalar iç içe olabilir; eşit sayıda çağrı `Unlock` yapılması gerekir.

Bir dizi kilitliyken silinemez.

## <a name="colesafearrayoperator-lpcvariant"></a><a name="operator_lpcvariant"></a>COleSafeArray::operatör LPCVARIANT

Bu `VARIANT` `COleSafeArray` nesnenin temel yapısına erişmek için bu döküm operatöre çağrı yapın.

```
operator LPCVARIANT() const;
```

## <a name="colesafearrayoperator-lpvariant"></a><a name="operator_lpvariant"></a>COleSafeArray::operatör LPVARIANT

Bu `VARIANT` `COleSafeArray` nesnenin temel yapısına erişmek için bu döküm operatöre çağrı yapın.

```
operator LPVARIANT();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev tarafından döndürülen işaretçi tarafından erişilen `VARIANT` yapıdaki değeri `COleSafeArray` değiştirmenin bu nesnenin değerini değiştireceğini unutmayın.

## <a name="colesafearrayoperator-"></a><a name="operator_eq"></a>COleSafeArray::operatör =

Bu aşırı yüklü atama işleçleri `COleSafeArray` kaynak değerini bu nesneye kopyalar.

```
COleSafeArray& operator=(const COleSafeArray& saSrc);
COleSafeArray& operator=(const VARIANT& varSrc);
COleSafeArray& operator=(LPCVARIANT pSrc);
COleSafeArray& operator=(const COleVariant& varSrc);
```

### <a name="remarks"></a>Açıklamalar

Her işleç kısa bir açıklama aşağıdaki gibidir:

- **operatör =(** *saSrc* **)** Varolan `COleSafeArray` bir nesneyi bu nesneye kopyalar.

- **operatör =(** *varSrc* **)** Varolan `VARIANT` bir `COleVariant` veya diziyi bu nesneye kopyalar.

- **işleç =(** *pSrc* **)** `VARIANT` *PSrc* tarafından erişilen dizi nesnesini bu nesneye kopyalar.

## <a name="colesafearrayoperator-"></a><a name="operator_eq_eq"></a>COleSafeArray::operatör ==

Bu işleç iki diziyi `VARIANT` `COleVariant`(, `COleSafeArray` `SAFEARRAY`, , veya diziler) karşılaştırır ve eşitse sıfırsız döndürür; aksi takdirde 0.

```
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;

BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;

BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;
```

### <a name="remarks"></a>Açıklamalar

Eşit sayıda boyut, her boyutta eşit boyut ve eşit öğe değerlerine sahiplerse, iki dizi eşittir.

## <a name="colesafearrayoperator-ltlt"></a><a name="operator_lt_lt"></a>COleSafeArray::operatör&lt;&lt;

Ekleme `COleSafeArray` (<<) işleci, bir `COleSafeArray` nesnenin tanısal olarak boşaltılmasını ve arşive depolanmasını destekler.

```
CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    COleSafeArray& saSrc);
```

## <a name="colesafearrayptrofindex"></a><a name="ptrofindex"></a>COleSafeArray::PtrOfIndex

Dizin değerleri tarafından belirtilen öğeye bir işaretçi döndürür.

```cpp
void PtrOfIndex(
    long* rgIndices,
    void** ppvData);
```

### <a name="parameters"></a>Parametreler

*rgIndices*<br/>
Dizinin bir öğesini tanımlayan dizin değerleri dizisi. Öğenin tüm dizinleri belirtilmelidir.

*ppvData*<br/>
Döndükten sonra, *rgIndices*değerleri tarafından tanımlanan öğeyi işaretçi .

## <a name="colesafearrayputelement"></a><a name="putelement"></a>COleSafeArray::PutElement

Diziye tek bir öğe atar.

```cpp
void PutElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>Parametreler

*rgIndices*<br/>
Dizinin her boyutu için bir dizi dizin işaretçisi.

*pvData*<br/>
Diziye atamak için verileri işaretçi. VT_DISPATCH, VT_UNKNOWN ve VT_BSTR varyant türleri işaretçilerdir ve başka bir yönlendirme düzeyi gerektirmez.

### <a name="remarks"></a>Açıklamalar

Bu işlev, öğeyi atamadan önce ve sonra Windows [işlevlerisafeArrayLock](/windows/win32/api/oleauto/nf-oleauto-safearraylock) ve [SafeArrayUnlock](/windows/win32/api/oleauto/nf-oleauto-safearrayunlock) otomatik olarak çağırır. Veri öğesi bir dize, nesne veya varyantsa, işlev onu doğru kopyalarsa ve varolan öğe bir dize, nesne veya varyantsa, doğru şekilde temizlenir.

Bir dizide birden çok kilit olabileceğini unutmayın, böylece dizi diğer işlemler tarafından kilitlenirken öğeleri diziye koyabilirsiniz.

Hata üzerine, işlev bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md)atar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]

## <a name="colesafearrayredim"></a><a name="redim"></a>COleSafeArray::Redim

Güvenli bir dizinin en az önemli (en sağ) bağlı olduğunu değiştirir.

```cpp
void Redim(SAFEARRAYBOUND* psaboundNew);
```

### <a name="parameters"></a>Parametreler

*psaboundYeni*<br/>
Yeni dizi bağlı içeren yeni bir güvenli dizi bağlı yapı işaretçisi. Bir dizinin yalnızca en az önemli boyutu değiştirilebilir.

### <a name="remarks"></a>Açıklamalar

Hata üzerine, işlev bir [COleException](../../mfc/reference/coleexception-class.md)atar.

## <a name="colesafearrayresizeonedim"></a><a name="resizeonedim"></a>COleSafeArray::ResizeOneDim

Tek boyutlu `COleSafeArray` bir nesnedeki öğelerin sayısını değiştirir.

```cpp
void ResizeOneDim(DWORD dwElements);
```

### <a name="parameters"></a>Parametreler

*dwElements*<br/>
Tek boyutlu güvenli dizideki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Hata üzerine, işlev bir [COleException](../../mfc/reference/coleexception-class.md)atar.

### <a name="example"></a>Örnek

  [COleSafeArray örneğine bakın:CreateOneDim](#createonedim).

## <a name="colesafearrayunaccessdata"></a><a name="unaccessdata"></a>COleSafeArray::Erişimsiz Veri

Bir dizinin kilit sayısını atar ve '' `AccessData`tarafından alınan işaretçiyi geçersiz kılmışolur.

```cpp
void UnaccessData();
```

### <a name="remarks"></a>Açıklamalar

Hata üzerine, işlev bir [COleException](../../mfc/reference/coleexception-class.md)atar.

### <a name="example"></a>Örnek

  [COleSafeArray örneğine bakın:AccessData](#accessdata).

## <a name="colesafearrayunlock"></a><a name="unlock"></a>COleSafeArray::Kilidini aç

Bir dizinin kilit sayısını serbest bırakılabilmek veya yeniden boyutlandırılabilmek için atar.

```cpp
void Unlock();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, bir dizideki verilere erişim tamamlandıktan sonra çağrılır. Hata üzerine, bir [COleException](../../mfc/reference/coleexception-class.md)atar.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleVariant Sınıfı](../../mfc/reference/colevariant-class.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)<br/>
[CDatabase Sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
