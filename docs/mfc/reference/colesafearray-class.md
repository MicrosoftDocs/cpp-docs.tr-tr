---
title: COleSafeArray sınıfı
ms.date: 08/27/2018
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
ms.openlocfilehash: 0833dca9311689063c2ebeadd3942d9f5ce376e2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267166"
---
# <a name="colesafearray-class"></a>COleSafeArray sınıfı

Rastgele tür ve boyut dizilerle çalışırken bir sınıf.

## <a name="syntax"></a>Sözdizimi

```
class COleSafeArray : public tagVARIANT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleSafeArray::COleSafeArray](#colesafearray)|Oluşturur bir `COleSafeArray` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleSafeArray::AccessData](#accessdata)|Dizi verileri için bir işaretçi alır.|
|[COleSafeArray::AllocData](#allocdata)|Dizi için bellek ayırır.|
|[COleSafeArray::AllocDescriptor](#allocdescriptor)|Güvenli bir dizi tanımlayıcısı için bellek ayırır.|
|[COleSafeArray::Attach](#attach)|Var olan denetim verir `VARIANT` için dizi `COleSafeArray` nesne.|
|[COleSafeArray::Clear](#clear)|Arka plandaki tüm verileri boşaltır `VARIANT`.|
|[COleSafeArray::Copy](#copy)|Varolan bir dizinin bir kopyasını oluşturur.|
|[COleSafeArray::Create](#create)|Güvenli bir dizi oluşturur.|
|[COleSafeArray::CreateOneDim](#createonedim)|Bir tek boyutlu oluşturur `COleSafeArray` nesne.|
|[COleSafeArray::Destroy](#destroy)|Var olan bir dizi yok eder.|
|[COleSafeArray::DestroyData](#destroydata)|Güvenli bir dizi verilerinde yok eder.|
|[COleSafeArray::DestroyDescriptor](#destroydescriptor)|Bir güvenli bir dizi tanımlayıcısı yok eder.|
|[COleSafeArray::Detach](#detach)|DEĞİŞKEN dizisinden ayırır `COleSafeArray` (veri açılmayacaktır böylece) nesne.|
|[COleSafeArray::GetByteArray](#getbytearray)|Güvenli diziye içeriğini kopyalar bir [CByteArray](../../mfc/reference/cbytearray-class.md).|
|[COleSafeArray::GetDim](#getdim)|Dizi boyut sayısını verir.|
|[COleSafeArray::GetElement](#getelement)|Tek bir güvenli dizi öğesini alır.|
|[COleSafeArray::GetElemSize](#getelemsize)|Baytlarında güvenli bir dizide bir öğe boyutu döndürür.|
|[COleSafeArray::GetLBound](#getlbound)|Herhangi bir boyuta güvenli bir dizinin alt sınırını döndürür.|
|[COleSafeArray::GetOneDimSize](#getonedimsize)|Tek boyutlu öğelerin sayısını döndürür `COleSafeArray` nesne.|
|[COleSafeArray::GetUBound](#getubound)|Güvenli bir dizinin tüm boyutu üst sınırını döndürür.|
|[COleSafeArray::Lock](#lock)|Bir dizinin kilit sayacını artırır ve dizi tanımlayıcısı bir dizi veri işaretçisine yerleştirir.|
|[COleSafeArray::PtrOfIndex](#ptrofindex)|Dizinlenmiş öğeye bir işaretçi döndürür.|
|[COleSafeArray::PutElement](#putelement)|Tek bir öğe diziye atar.|
|[COleSafeArray::Redim](#redim)|Güvenli bir dizinin en az önemli (sağdaki) bağlı olarak değiştirir.|
|[COleSafeArray::ResizeOneDim](#resizeonedim)|Bir tek boyutlu içindeki öğelerin sayısını değiştirir `COleSafeArray` nesne.|
|[COleSafeArray::UnaccessData](#unaccessdata)|Azaltır kilit sayısı bir dizi ve işaretçiyi tarafından alınan geçersiz kılar `AccessData`.|
|[COleSafeArray::Unlock](#unlock)|Kilit sayısını azaltır bir dizi, serbest veya yeniden boyutlandırıldı.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[COleSafeArray::operator LPCVARIANT](#operator_lpcvariant)|Erişen temel `VARIANT` yapısını `COleSafeArray` nesne.|
|[COleSafeArray::operator LPVARIANT](#operator_lpvariant)|Erişen temel `VARIANT` yapısını `COleSafeArray` nesne.|
|[COleSafeArray::operator =](#operator_eq)|Kopyalar değerlerini bir `COleSafeArray` nesne (`SAFEARRAY`, `VARIANT`, `COleVariant`, veya `COleSafeArray` dizisi).|
|[COleSafeArray::operator ==](#operator_eq_eq)|İki değişken dizileri karşılaştırır (`SAFEARRAY`, `VARIANT`, `COleVariant`, veya `COleSafeArray` Diziler).|
|[COleSafeArray::operator &lt;&lt;](#operator_lt_lt)|İçeriğini çıkaran bir `COleSafeArray` döküm bağlam nesnesi.|

## <a name="remarks"></a>Açıklamalar

`COleSafeArray` OLE türetilen `VARIANT` yapısı. OLE `SAFEARRAY` üye işlevleri aracılığıyla kullanılabilir `COleSafeArray`yanı üye işlevleri bayt boyutlu diziler için özel olarak tasarlanmış bir dizi olarak.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagVARIANT`

`COleSafeArray`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

##  <a name="accessdata"></a>  COleSafeArray::AccessData

Dizi verileri için bir işaretçi alır.

```
void AccessData(void** ppvData);
```

### <a name="parameters"></a>Parametreler

*ppvData*<br/>
Dizi verileri için bir işaretçi işaretçisi.

### <a name="remarks"></a>Açıklamalar

İşlevi, hata oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]

##  <a name="allocdata"></a>  COleSafeArray::AllocData

Bellek için güvenli diziye ayırır.

```
void AllocData();
```

### <a name="remarks"></a>Açıklamalar

İşlevi, hata oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="allocdescriptor"></a>  COleSafeArray::AllocDescriptor

Güvenli bir dizi tanımlayıcısı için bellek ayırır.

```
void AllocDescriptor(DWORD dwDims);
```

### <a name="parameters"></a>Parametreler

*dwDims*<br/>
Güvenli dizideki boyutların sayısı.

### <a name="remarks"></a>Açıklamalar

İşlevi, hata oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="attach"></a>  COleSafeArray::Attach

Mevcut verilerin denetimini verir `VARIANT` için dizi `COleSafeArray` nesne.

```
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>Parametreler

*varSrc*<br/>
A `VARIANT` nesne. *VarSrc* parametresi VARTYPE olmalıdır [VT_ARRAY](/windows/desktop/api/wtypes/ne-wtypes-varenum).

### <a name="remarks"></a>Açıklamalar

Kaynak `VARIANT`ın türü için VT_EMPTY ayarlayın. Varsa, bu işlev geçerli dizi verileri temizler.

### <a name="example"></a>Örnek

  Örneğin bakın [COleSafeArray::AccessData](#accessdata).

##  <a name="clear"></a>  COleSafeArray::Clear

Güvenli dizi temizler.

```
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Ayarlayarak güvenli bir dizi işlev temizler `VARTYPE` VT_EMPTY nesnesi. Geçerli içeriği serbest bırakılır ve dizi serbest bırakılır.

##  <a name="colesafearray"></a>  COleSafeArray::COleSafeArray

Oluşturur bir `COleSafeArray` nesne.

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
Mevcut bir `COleSafeArray` nesne veya `SAFEARRAY` yeni içine kopyalanacak `COleSafeArray` nesne.

*vtSrc*<br/>
Yeni VARTYPE `COleSafeArray` nesne.

*psaSrc*<br/>
Bir işaretçi bir `SAFEARRAY` yeni içine kopyalanacak `COleSafeArray` nesne.

*varSrc*<br/>
Mevcut bir `VARIANT` veya `COleVariant` yeni içine kopyalanacak nesne `COleSafeArray` nesne.

*pSrc*<br/>
Bir işaretçi bir `VARIANT` yeni içine kopyalanacak nesne `COleSafeArray` nesne.

### <a name="remarks"></a>Açıklamalar

Tüm bu oluşturucular Yeni Oluştur `COleSafeArray` nesneleri. Hiçbir parametre boş ise `COleSafeArray` nesnesi (VT_EMPTY) oluşturulur. Varsa `COleSafeArray` olan VARTYPE örtük olarak bilinen başka bir diziden kopyalanan (bir `COleSafeArray`, `COleVariant`, veya `VARIANT`), kaynak dizinin VARTYPE korunur ve belirtilmesi. Varsa `COleSafeArray` olan VARTYPE değil bilinen başka bir diziden kopyalanan (`SAFEARRAY`), VARTYPE belirtilmelidir *vtSrc* parametresi.

İşlevi, hata oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="copy"></a>  COleSafeArray::Copy

Mevcut güvenli dizinin bir kopyasını oluşturur.

```
void Copy(LPSAFEARRAY* ppsa);
```

### <a name="parameters"></a>Parametreler

*ppsa*<br/>
Yeni dizi tanımlayıcısı döndürülecek bir konuma yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

İşlevi, hata oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="create"></a>  COleSafeArray::Create

Ayırır ve dizi verilerini başlatır.

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
Dizi (diğer bir deyişle, dizideki her öğeye VARTYPE) taban türü. Bir değişken türlerinin alt kümesine VARTYPE sınırlıdır. VT_ARRAY ne VT_BYREF bayrak olarak ayarlanabilir. VT_EMPTY ve VT_NULL dizisi için geçerli temel türler değildir. Diğer tüm türleri kullanılabilir.

*dwDims*<br/>
Dizideki boyutların sayısı. Dizi ile oluşturulduktan sonra bu değiştirilebilir [Redim](#redim).

*rgElements*<br/>
Dizideki her boyut için öğelerin sayısını bir dizi için işaretçi.

*rgsabounds*<br/>
Sınırları (her boyut için bir tane) oluşan bir vektörü işaretçi dizisi için ayrılacak.

### <a name="remarks"></a>Açıklamalar

Gerekirse, bu işlev geçerli dizi verileri temizler. İşlevi, hata oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

##  <a name="createonedim"></a>  COleSafeArray::CreateOneDim

Yeni bir oluşturur tek boyutlu `COleSafeArray` nesne.

```
void CreateOneDim(
    VARTYPE vtSrc,
    DWORD dwElements,
    const void* pvSrcData = NULL,
    long nLBound = 0);
```

### <a name="parameters"></a>Parametreler

*vtSrc*<br/>
Dizi (diğer bir deyişle, dizideki her öğeye VARTYPE) taban türü.

*dwElements*<br/>
Dizideki öğelerin sayısı. Dizi ile oluşturulduktan sonra bu değiştirilebilir [ResizeOneDim](#resizeonedim).

*pvSrcData*<br/>
Diziye kopyalanacak verileri işaretçisi.

*nLBound*<br/>
Dizi alt sınırı.

### <a name="remarks"></a>Açıklamalar

İşlev ayırır ve başlatır, belirtilen verileri kopyalama, dizi verilerini işaretçi *pvSrcData* NULL değil.

İşlevi, hata oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]

##  <a name="destroy"></a>  COleSafeArray::Destroy

Var olan bir dizi tanımlayıcısı ve dizideki tüm veriler yok eder.

```
void Destroy();
```

### <a name="remarks"></a>Açıklamalar

Nesneleri dizide depolanıyorsa, her nesneyi serbest bırakılır. İşlevi, hata oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="destroydata"></a>  COleSafeArray::DestroyData

Güvenli bir dizideki tüm veriler yok eder.

```
void DestroyData();
```

### <a name="remarks"></a>Açıklamalar

Nesneleri dizide depolanıyorsa, her nesneyi serbest bırakılır. İşlevi, hata oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="destroydescriptor"></a>  COleSafeArray::DestroyDescriptor

Bir güvenli bir dizi tanımlayıcısı yok eder.

```
void DestroyDescriptor();
```

### <a name="remarks"></a>Açıklamalar

İşlevi, hata oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="detach"></a>  COleSafeArray::Detach

Ayırır `VARIANT` verilerden `COleSafeArray` nesne.

```
VARIANT Detach();
```

### <a name="return-value"></a>Dönüş Değeri

Arka plandaki `VARIANT` değerini `COleSafeArray` nesne.

### <a name="remarks"></a>Açıklamalar

İşlevi için VT_EMPTY nesnenin VARTYPE ayarlayarak verileri güvenli diziye ayırır. Bu dizi Windows işlevi çağrılarak serbest arayanın sorumluluğundadır [VariantClear](/windows/desktop/api/oleauto/nf-oleauto-variantclear).

İşlevi, hata oluşturur bir [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Örnek

  Örneğin bakın [COleSafeArray::PutElement](#putelement).

##  <a name="getbytearray"></a>  COleSafeArray::GetByteArray

Güvenli diziye içeriğini kopyalar bir `CByteArray`.

```
void GetByteArray(CByteArray& bytes);
```

### <a name="parameters"></a>Parametreler

*Bayt*<br/>
Bir başvuru bir [CByteArray](../../mfc/reference/cbytearray-class.md) nesne.

##  <a name="getdim"></a>  COleSafeArray::GetDim

Öğesindeki boyutların sayısı döndürür `COleSafeArray` nesne.

```
DWORD GetDim();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenli dizideki boyutların sayısı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]

##  <a name="getelement"></a>  COleSafeArray::GetElement

Tek bir güvenli dizi öğesini alır.

```
void GetElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>Parametreler

*rgIndices*<br/>
Bir dizinin her boyutunun için dizinleri dizi için işaretçi.

*pvData*<br/>
Dizinin öğesinin yerleştirileceği konumu için işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu işlev otomatik olarak windows işlevlerini çağıran `SafeArrayLock` ve `SafeArrayUnlock` öncesinde ve sonrasında öğe alınıyor. Veri öğesi, bir dize, nesne veya değişken ise, işlev öğesi doğru şekilde kopyalar. Parametre *pvData* büyük bir öğe içermesi için yeterli arabellek işaret etmelidir.

İşlevi, hata oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]

##  <a name="getelemsize"></a>  COleSafeArray::GetElemSize

İçindeki bir öğenin boyutunu alır bir `COleSafeArray` nesne.

```
DWORD GetElemSize();
```

### <a name="return-value"></a>Dönüş Değeri

Güvenli bir dizinin öğeleri bayt cinsinden boyutu.

##  <a name="getlbound"></a>  COleSafeArray::GetLBound

Herhangi bir boyutu alt sınırını döndüren bir `COleSafeArray` nesne.

```
void GetLBound(
    DWORD dwDim,
    long* pLBound);
```

### <a name="parameters"></a>Parametreler

*dwDim*<br/>
Dizi boyutu alt sınırı alınacağı.

*pLBound*<br/>
Alt sınır döndürülecek konumu için işaretçi.

### <a name="remarks"></a>Açıklamalar

İşlevi, hata oluşturur bir [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]

##  <a name="getonedimsize"></a>  COleSafeArray::GetOneDimSize

Tek boyutlu öğelerin sayısını döndürür `COleSafeArray` nesne.

```
DWORD GetOneDimSize();
```

### <a name="return-value"></a>Dönüş Değeri

Tek boyutlu güvenli dizideki öğelerin sayısı.

### <a name="example"></a>Örnek

  Örneğin bakın [COleSafeArray::CreateOneDim](#createonedim).

##  <a name="getubound"></a>  COleSafeArray::GetUBound

Güvenli bir dizinin tüm boyutu üst sınırını döndürür.

```
void GetUBound(
    DWORD dwDim,
    long* pUBound);
```

### <a name="parameters"></a>Parametreler

*dwDim*<br/>
Dizi boyut üst sınırı alınacağı.

*pUBound*<br/>
Konumun çokluğun döndürmek için işaretçi.

### <a name="remarks"></a>Açıklamalar

İşlevi, hata oluşturur bir [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]

##  <a name="lock"></a>  COleSafeArray::Lock

Bir dizi ve dizi tanımlayıcısı dizi verileri için bir işaretçi bir yerde kilit sayacını artırır.

```
void Lock();
```

### <a name="remarks"></a>Açıklamalar

Bu hata, oluşturur bir [COleException](../../mfc/reference/coleexception-class.md).

Dizi tanımlayıcısı işaretçinin geçerliliğinin `Unlock` çağrılır. Çağrılar `Lock` yuvalanabilir; çağrıları eşit sayıda `Unlock` gereklidir.

Kilitliyken dizi silinemiyor.

##  <a name="operator_lpcvariant"></a>  COleSafeArray::operator LPCVARIANT

Arka plandaki erişmek için bu atama işlecini çağırmak `VARIANT` yapısı bu `COleSafeArray` nesne.

```
operator LPCVARIANT() const;
```

##  <a name="operator_lpvariant"></a>  COleSafeArray::operator LPVARIANT

Arka plandaki erişmek için bu atama işlecini çağırmak `VARIANT` yapısı bu `COleSafeArray` nesne.

```
operator LPVARIANT();
```

### <a name="remarks"></a>Açıklamalar

Not Bu değiştirme değeri `VARIANT` bu işlev tarafından döndürülen işaretçi tarafından erişilen yapısı, bu değeri değişecek `COleSafeArray` nesne.

##  <a name="operator_eq"></a>  COleSafeArray::operator =

Bu aşırı yüklenmiş atama işleçleri bu kaynak değeri kopyalayın `COleSafeArray` nesne.

```
COleSafeArray& operator=(const COleSafeArray& saSrc);
COleSafeArray& operator=(const VARIANT& varSrc);
  COleSafeArray& operator=(LPCVARIANT pSrc);
COleSafeArray& operator=(const COleVariant& varSrc);
```

### <a name="remarks"></a>Açıklamalar

Her işleç kısa bir açıklaması aşağıdaki gibidir:

- **operator = (** *saSrc* **)** kopyalar mevcut bir `COleSafeArray` bu nesne bir nesnede.

- **operator = (** *varSrc* **)** kopyalar varolan `VARIANT` veya `COleVariant` bu nesne dizisine.

- **operator = (** *pSrc* **)** kopyaları `VARIANT` dizi nesnesi tarafından erişilen *pSrc* bu nesne içine.

##  <a name="operator_eq_eq"></a>  COleSafeArray::operator ==

Bu işleç iki dizileri karşılaştırır (`SAFEARRAY`, `VARIANT`, `COleVariant`, veya `COleSafeArray` Diziler) ve olmaları durumunda eşit; Aksi durumda 0 sıfır döndürür.

```
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;

BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;

BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;
```

### <a name="remarks"></a>Açıklamalar

İki dizi boyutları, aynı boyutta, her boyut, eşit öğe değerlerini eşit sayıda oluşturulduysa eşit olur.

##  <a name="operator_lt_lt"></a>  COleSafeArray::operator &lt;&lt;

`COleSafeArray` Ekleme (<<) işlecini destekler tanılama dökme ve depolama, bir `COleSafeArray` bir arşivden nesne.

```
CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    COleSafeArray& saSrc);
```

##  <a name="ptrofindex"></a>  COleSafeArray::PtrOfIndex

Dizin değerleri tarafından belirtilen öğeye bir işaretçi döndürür.

```
void PtrOfIndex(
    long* rgIndices,
    void** ppvData);
```

### <a name="parameters"></a>Parametreler

*rgIndices*<br/>
Dizinin bir öğeyi tanımlamak dizin değerleri dizisi. Tüm dizinler öğesinin belirtilmesi gerekir.

*ppvData*<br/>
Değerler tarafından tanımlanan öğesine dönüş, işaretçinin *rgIndices*.

##  <a name="putelement"></a>  COleSafeArray::PutElement

Tek bir öğe diziye atar.

```
void PutElement(
    long* rgIndices,
    void* pvData);
```

### <a name="parameters"></a>Parametreler

*rgIndices*<br/>
Bir dizinin her boyutunun için dizinleri dizi için işaretçi.

*pvData*<br/>
Diziye atamak için veri işaretçisi. Gt; vt_dıspatch & gt; VT_UNKNOWN & ve VT_BSTR değişken türleri işaretçileri ve başka bir yöneltme düzeyi gerektirmez.

### <a name="remarks"></a>Açıklamalar

Bu işlev otomatik olarak Windows işlevlerini çağıran [SafeArrayLock](/windows/desktop/api/oleauto/nf-oleauto-safearraylock) ve [SafeArrayUnlock](/windows/desktop/api/oleauto/nf-oleauto-safearrayunlock) önce ve sonra öğe atanıyor. Veri öğesi, bir dize, nesne veya değişken ise, işlev, doğru kopyalar ve var olan bir dize, nesne veya değişken öğeyse, doğru temizlenir.

Dizi diğer işlemler tarafından kilitliyken öğeleri bir dizi içine koyabilirsiniz için bir dizi üzerinde birden çok kilit sahip olabileceğini unutmayın.

İşlevi, hata oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]

##  <a name="redim"></a>  COleSafeArray::Redim

Güvenli bir dizinin en az önemli (sağdaki) bağlı olarak değiştirir.

```
void Redim(SAFEARRAYBOUND* psaboundNew);
```

### <a name="parameters"></a>Parametreler

*psaboundNew*<br/>
Yeni güvenli bir dizi işaretçi bağlı yeni bir dizi içeren yapı bağlı. Yalnızca en az önemli boyutta bir dizinin değiştirilebilir.

### <a name="remarks"></a>Açıklamalar

İşlevi, hata oluşturur bir [COleException](../../mfc/reference/coleexception-class.md).

##  <a name="resizeonedim"></a>  COleSafeArray::ResizeOneDim

Bir tek boyutlu içindeki öğelerin sayısını değiştirir `COleSafeArray` nesne.

```
void ResizeOneDim(DWORD dwElements);
```

### <a name="parameters"></a>Parametreler

*dwElements*<br/>
Tek boyutlu güvenli dizideki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

İşlevi, hata oluşturur bir [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Örnek

  Örneğin bakın [COleSafeArray::CreateOneDim](#createonedim).

##  <a name="unaccessdata"></a>  COleSafeArray::UnaccessData

Azaltır kilit sayısı bir dizi ve işaretçiyi tarafından alınan geçersiz kılar `AccessData`.

```
void UnaccessData();
```

### <a name="remarks"></a>Açıklamalar

İşlevi, hata oluşturur bir [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Örnek

  Örneğin bakın [COleSafeArray::AccessData](#accessdata).

##  <a name="unlock"></a>  COleSafeArray::Unlock

Kilit sayısını azaltır bir dizi, serbest veya yeniden boyutlandırıldı.

```
void Unlock();
```

### <a name="remarks"></a>Açıklamalar

Bir dizideki verilere erişim tamamlandıktan sonra bu işlev çağrılır. Bu hata, oluşturur bir [COleException](../../mfc/reference/coleexception-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleVariant Sınıfı](../../mfc/reference/colevariant-class.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)<br/>
[CDatabase Sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
