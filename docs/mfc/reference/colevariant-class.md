---
title: COleVariant Sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleVariant
- AFXDISP/COleVariant
- AFXDISP/COleVariant::COleVariant
- AFXDISP/COleVariant::Attach
- AFXDISP/COleVariant::ChangeType
- AFXDISP/COleVariant::Clear
- AFXDISP/COleVariant::Detach
- AFXDISP/COleVariant::GetByteArrayFromVariantArray
- AFXDISP/COleVariant::SetString
helpviewer_keywords:
- COleVariant [MFC], COleVariant
- COleVariant [MFC], Attach
- COleVariant [MFC], ChangeType
- COleVariant [MFC], Clear
- COleVariant [MFC], Detach
- COleVariant [MFC], GetByteArrayFromVariantArray
- COleVariant [MFC], SetString
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
ms.openlocfilehash: f907ed7c058f87cf03530411bc8fa4a3c108a4f0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374830"
---
# <a name="colevariant-class"></a>COleVariant Sınıfı

[VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) veri türünü kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class COleVariant : public tagVARIANT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleVariant::COleVariant](#colevariant)|Bir `COleVariant` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleVariant::Ekle](#attach)|Bir VARYANT'a `COleVariant`bir .|
|[COleVariant::ChangeType](#changetype)|Bu `COleVariant` nesnenin varyant türünü değiştirir.|
|[COleVariant::Açık](#clear)|Bu `COleVariant` nesneyi temizler.|
|[COleVariant::Detach](#detach)|Bir VARYANT'ı a'dan `COleVariant` ayırır ve VARYANT'ı döndürür.|
|[COleVariant::GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|Varolan bir varyant dizisinden bir bayt dizisi alır.|
|[COleVariant::SetString](#setstring)|Dizeyi genellikle ANSI olmak üzere belirli bir türe ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[COleVariant::operatör LPCVARIANT](#operator_lpcvariant)|Bir `COleVariant` değeri bir `LPCVARIANT`.|
|[COleVariant::operatör LPVARIANT](#operator_lpvariant)|Bir `COleVariant` nesneyi `LPVARIANT`bir .|
|[COleVariant::operator =](#operator_eq)|Bir `COleVariant` değeri kopyalar.|
|[COleVariant::operator ==](#operator_eq_eq)|İki `COleVariant` değeri karşılaştırır.|
|[COleVariant::operatör &lt; &lt;,&gt;&gt;](#operator_lt_lt__gt_gt)|Bir `COleVariant` değer çıkarır `CArchive` `CDumpContext` veya bir `COleVariant` nesneyi `CArchive`.|

## <a name="remarks"></a>Açıklamalar

Bu veri türü OLE otomasyonunda kullanılır. Özellikle, [DISPPARAMS](/windows/win32/api/oaidl/ns-oaidl-dispparams) yapısı VARYANT yapıları bir dizi için bir işaretçi içerir. Parametreleri `DISPPARAMS` IDispatch'e geçirmek için bir yapı [kullanılır::Çağır.](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)

> [!NOTE]
> Bu sınıf `VARIANT` yapıdan türetilmiştir. Bu, `COleVariant` bir parametrede bir `VARIANT` parametreyi geçebileceğiniz ve yapının `VARIANT` veri üyelerinin `COleVariant`erişilebilir veri üyeleri olduğu anlamına gelir.

İlgili iki MFC sınıfı [COleCurrency](../../mfc/reference/colecurrency-class.md) ve [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) varyant veri `VT_CY`türleri CURRENCY `VT_DATE`( ) ve DATE ( kapsüllemek. Sınıf `COleVariant` DAO sınıflarında yaygın olarak kullanılır; [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) ve [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)gibi bu sınıfın tipik kullanımı için bu sınıflara bakın.

Daha fazla bilgi için [VARYANT,](/windows/win32/api/oaidl/ns-oaidl-variant) [PARA BIRIMI,](/windows/win32/api/wtypes/ns-wtypes-cy~r1) [DISPPARAMS](/windows/win32/api/oaidl/ns-oaidl-dispparams)ve [IDispatch::Windows](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) SDK'daki girişleri çağırın.

`COleVariant` Sınıf ve OLE otomasyonundaki kullanımı hakkında daha fazla bilgi için [Otomasyon](../../mfc/automation.md)makalesinde "OLE Otomasyonunda Parametreleri Geçirme" başlıklı makaleye bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagVARIANT`

`COleVariant`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdisp.h

## <a name="colevariantattach"></a><a name="attach"></a>COleVariant::Ekle

Verilen [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) nesnesini geçerli `COleVariant` nesneye eklemek için bu işlevi çağırın.

```
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>Parametreler

*varSrc*<br/>
Geçerli `COleVariant` `VARIANT` nesneye eklenecek varolan bir nesne.

### <a name="remarks"></a>Açıklamalar

Bu işlev *varSrc* vartype VT_EMPTY ayarlar.

Daha fazla bilgi için Windows SDK'daki [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) ve [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum) girişlerine bakın.

## <a name="colevariantcolevariant"></a><a name="colevariant"></a>COleVariant::COleVariant

Bir `COleVariant` nesne inşa eder.

```
COleVariant();
COleVariant(const VARIANT& varSrc);
COleVariant(const COleVariant& varSrc);
COleVariant(LPCVARIANT pSrc);
COleVariant(LPCTSTR lpszSrc);
COleVariant(LPCTSTR lpszSrc, VARTYPE vtSrc);
COleVariant(CString& strSrc);
COleVariant(BYTE nSrc);
COleVariant(short nSrc, VARTYPE vtSrc = VT_I2);
COleVariant(long lSrc,VARTYPE vtSrc = VT_I4);
COleVariant(const COleCurrency& curSrc);
COleVariant(float fltSrc);
COleVariant(double dblSrc);
COleVariant(const COleDateTime& timeSrc);
COleVariant(const CByteArray& arrSrc);
COleVariant(const CLongBinary& lbSrc);
COleVariant(LPCITEMIDLIST pidl);
```

### <a name="parameters"></a>Parametreler

*varSrc*<br/>
Varolan `COleVariant` `VARIANT` veya yeni `COleVariant` nesneye kopyalanacak bir nesne.

*pSrc*<br/>
Yeni `COleVariant` nesneye `VARIANT` kopyalanacak bir nesneye işaretçi.

*lpszSrc*<br/>
Null-sonlandırılan dize yeni `COleVariant` nesneye kopyalanacak.

*vtSrc*<br/>
Yeni `VARTYPE` `COleVariant` nesne için.

*strSrc*<br/>
Yeni `COleVariant` nesneye kopyalanacak bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

*nSrc*, *lSrc* Yeni `COleVariant` nesneye kopyalanacak sayısal bir değer.

*vtSrc*<br/>
Yeni `VARTYPE` `COleVariant` nesne için.

*curSrc*<br/>
[COleCurrency](../../mfc/reference/colecurrency-class.md) nesnesi yeni `COleVariant` nesneye kopyalanacak.

*fltSrc*, *dblSrc*<br/>
Yeni `COleVariant` nesneye kopyalanacak sayısal bir değer.

*zamanSrc*<br/>
Yeni `COleVariant` nesneye kopyalanacak bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi.

*arrSrc*<br/>
Yeni `COleVariant` nesneye kopyalanacak bir [CByteArray](../../mfc/reference/cbytearray-class.md) nesnesi.

*lbSrc*<br/>
[CLongBinary](../../mfc/reference/clongbinary-class.md) nesnesi yeni `COleVariant` nesneye kopyalanacak.

*pidl*<br/>
Yeni `COleVariant` nesneye kopyalanacak bir [ITEMIDLIST](/windows/win32/api/shtypes/ns-shtypes-itemidlist) yapısıiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Tüm bu oluşturucular, belirtilen değere başlalanan yeni `COleVariant` nesneler oluştururlar. Bu yapıcıların her birinin kısa bir açıklaması aşağıdaki gibidir.

- **COleVariant( )** Boş `COleVariant` bir nesne oluşturur, VT_EMPTY.

- **COleVariant(** *varSrc* **)** Varolan `VARIANT` veya `COleVariant` nesneyi kopyalar. Varyant türü korunur.

- **COleVariant(** *pSrc* **)** Varolan `VARIANT` veya `COleVariant` nesneyi kopyalar. Varyant türü korunur.

- **COleVariant(** *lpszSrc* **)** Bir dizeyi yeni nesneye kopyalar, VT_BSTR (UNICODE).

- **COleVariant(** *lpszSrc* **,** *vtSrc* **)** Bir dizeyi yeni nesneye kopyalar. *VtSrc* parametresi VT_BSTR (UNICODE) veya VT_BSTRT (ANSI) olmalıdır.

- **COleVariant (** *strSrc* **)** Bir dizeyi yeni nesneye kopyalar, VT_BSTR (UNICODE).

- **COleVariant(** *nSrc* **)** Yeni nesneye 8 bitlik bir tamsayı kopyalar, VT_UI1.

- **COleVariant(** *nSrc* **,** *vtSrc* **)** Yeni nesneye 16 bit tamsayı (veya Boolean değeri) kopyalar. *VtSrc* parametresi VT_I2 veya VT_BOOL olmalıdır.

- **COleVariant(** *lSrc* **,** *vtSrc* **)** Yeni nesneye 32 bit tamsayı (veya SCODE değeri) kopyalar. *VtSrc* parametresi VT_I4, VT_ERROR veya VT_BOOL olmalıdır.

- **COleVariant(** *curSrc* **)** Yeni nesneye bir `COleCurrency` değer kopyalar, VT_CY.

- **COleVariant(** *fltSrc* **)** 32 bit kayan nokta değerini yeni nesneye kopyalar, VT_R4.

- **COleVariant(** *dblSrc* **)** 64 bit kayan nokta değerini yeni nesneye kopyalar, VT_R8.

- **COleVariant(** *timeSrc* **)** VT_DATE, `COleDateTime` yeni nesneye bir değer kopyalar.

- **COleVariant(** *arrSrc* **)** Bir `CByteArray` nesneyi yeni nesneye kopyalar, VT_EMPTY.

- **COleVariant(** *lbSrc* **)** Bir `CLongBinary` nesneyi yeni nesneye kopyalar, VT_EMPTY.

SCODE hakkında daha fazla bilgi için Windows SDK'daki [COM Hata Kodlarının Yapısı'na](/windows/win32/com/structure-of-com-error-codes) bakın.

## <a name="colevariantchangetype"></a><a name="changetype"></a>COleVariant::ChangeType

Bu `COleVariant` nesnedeki varyant değeri türünü dönüştürür.

```
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```

### <a name="parameters"></a>Parametreler

*Vartype*<br/>
Bu `COleVariant` nesne için VARTYPE.

*pSrc*<br/>
DÖNÜŞTÜRÜLECEK [VARYANT](/windows/win32/api/oaidl/ns-oaidl-variant) nesnesine bir işaretçi. Bu değer NULL ise, bu `COleVariant` nesne dönüştürme için kaynak olarak kullanılır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için, Windows SDK'daki [VARIANT,](/windows/win32/api/oaidl/ns-oaidl-variant) [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum)ve [VariantChangeType](/windows/win32/api/oleauto/nf-oleauto-variantchangetype) girişlerine bakın.

## <a name="colevariantclear"></a><a name="clear"></a>COleVariant::Açık

Temizler `VARIANT`.

```
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Bu, bu nesnenin VARTYPE'ını VT_EMPTY ayarlar. `COleVariant` Yıkıcı bu işlevi çağırır.

Daha fazla bilgi `VARIANT`için Windows SDK'daki VARTYPE ve `VariantClear` girişlere bakın.

## <a name="colevariantdetach"></a><a name="detach"></a>COleVariant::Detach

Alttaki [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) nesnesini bu `COleVariant` nesneden ayırır.

```
VARIANT Detach();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, bu `COleVariant` nesne nin VARTYPE'ını VT_EMPTY ayarlar.

> [!NOTE]
> Aradıktan `Detach`sonra, ortaya çıkan `VariantClear` `VARIANT` yapıyı aramak arayanın sorumluluğundadır.

Daha fazla bilgi için, Windows SDK'daki [VARIANT,](/windows/win32/api/oaidl/ns-oaidl-variant) [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum)ve [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear) girişlerine bakın.

## <a name="colevariantgetbytearrayfromvariantarray"></a><a name="getbytearrayfromvariantarray"></a>COleVariant::GetByteArrayFromVariantArray

Varolan bir varyant dizisinden bayt dizini alır

```
void GetByteArrayFromVariantArray(CByteArray& bytes);
```

### <a name="parameters"></a>Parametreler

*Bayt*<br/>
Varolan bir [CByteArray](../../mfc/reference/cbytearray-class.md) nesnesine başvuru.

## <a name="colevariantoperator-lpcvariant"></a><a name="operator_lpcvariant"></a>COleVariant::operatör LPCVARIANT

Bu döküm işleci, değeri bu `VARIANT` `COleVariant` nesneden kopyalanan bir yapı döndürür.

```
operator LPCVARIANT() const;
```

### <a name="remarks"></a>Açıklamalar

## <a name="colevariantoperator-lpvariant"></a><a name="operator_lpvariant"></a>COleVariant::operatör LPVARIANT

Bu `VARIANT` `COleVariant` nesnenin temel yapısına erişmek için bu döküm operatöre çağrı yapın.

```
operator LPVARIANT();
```

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
> Bu işlev tarafından `VARIANT` döndürülen işaretçi tarafından erişilen yapıdaki `COleVariant` değeri değiştirmek bu nesnenin değerini değiştirir.

## <a name="colevariantoperator-"></a><a name="operator_eq"></a>COleVariant::operator =

Bu aşırı yüklü atama işleçleri `COleVariant` kaynak değerini bu nesneye kopyalar.

```
const COleVariant& operator=(const VARIANT& varSrc);
const COleVariant& operator=(LPCVARIANT pSrc);
const COleVariant& operator=(const COleVariant& varSrc);
const COleVariant& operator=(const LPCTSTR lpszSrc);
const COleVariant& operator=(const CString& strSrc);
const COleVariant& operator=(BYTE nSrc);
const COleVariant& operator=(short nSrc);
const COleVariant& operator=(long lSrc);
const COleVariant& operator=(const COleCurrency& curSrc);
const COleVariant& operator=(float fltSrc);
const COleVariant& operator=(double dblSrc);
const COleVariant& operator=(const COleDateTime& dateSrc);
const COleVariant& operator=(const CByteArray& arrSrc);
const COleVariant& operator=(const CLongBinary& lbSrc);
```

### <a name="remarks"></a>Açıklamalar

Her işleç kısa bir açıklama aşağıdaki gibidir:

- **operatör =(** *varSrc* **)** Varolan bir VARYANT'ı veya `COleVariant` nesneyi bu nesneye kopyalar.

- **işleç =(** *pSrc* **)** *PSrc* tarafından erişilen VARIANT nesnesini bu nesneye kopyalar.

- **operatör =(** *lpszSrc* **)** Bu nesneye geçersiz sonlandırılan bir dize kopyalar ve VARTYPE'ı VT_BSTR ayarlar.

- **operatör =(** *strSrc* **)** CString [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesini bu nesneye kopyalar ve VARTYPE'ı VT_BSTR ayarlar.

- **operatör =(** *nSrc* **)** Bu nesneye 8 veya 16 bittaminer değerini kopyalar. *nSrc* 8 bit değeri ise, bunun VARTYPE VT_UI1 ayarlanır. *NSrc* 16 bit lik bir değerse ve bunun VARTYPE'ı VT_BOOL ise, tutulur; aksi takdirde, VT_I2 olarak ayarlanır.

- **operatör =(** *lSrc* **)** Bu nesneye 32 bit tamsayı değerini kopyalar. Bunun VARTYPE VT_ERROR ise, tutulur; aksi takdirde, VT_I4 olarak ayarlanır.

- **işleç =(** *curSrc* **)** [COleCurrency](../../mfc/reference/colecurrency-class.md) nesnesini bu nesneye kopyalar ve VARTYPE'ı VT_CY ayarlar.

- **operatör =(** *fltSrc* **)** 32 bit kayan nokta değerini bu nesneye kopyalar ve VARTYPE'ı VT_R4 ayarlar.

- **operatör =(** *dblSrc* **)** Bu nesneye 64 bit kayan nokta değerini kopyalar ve VARTYPE'ı VT_R8 ayarlar.

- **operatör =(** *dateSrc* **)** [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesini bu nesneye kopyalar ve VARTYPE'ı VT_DATE ayarlar.

- **operatör =(** *arrSrc* **)** [CByteArray](../../mfc/reference/cbytearray-class.md) nesnesi bu `COleVariant` nesneye kopyalar.

- **operatör =(** *lbSrc* **)** [CLongBinary](../../mfc/reference/clongbinary-class.md) nesnesi bu `COleVariant` nesneye kopyalar.

Daha fazla bilgi için Windows SDK'daki [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) ve [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum) girişlerine bakın.

## <a name="colevariantoperator-"></a><a name="operator_eq_eq"></a>COleVariant::operator ==

Bu işleç iki varyant değerini karşılaştırır ve eşitse sıfırsız döndürür; aksi takdirde 0.

```
BOOL operator==(const VARIANT& varSrc) const;
BOOL operator==(LPCVARIANT pSrc) const;
```

## <a name="colevariantoperator-ltlt-gtgt"></a><a name="operator_lt_lt__gt_gt"></a>COleVariant::operatör &lt; &lt;,&gt;&gt;

Bir `COleVariant` değer çıkarır `CArchive` `CdumpContext` veya bir `COleVariant` nesneyi `CArchive`.

```
friend CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,
    OleVariant varSrc);

friend CArchive& AFXAPI operator<<(
    CArchive& ar,
    COleVariant varSrc);

friend CArchive& AFXAPI operator>>(
    CArchive& ar,
    COleVariant& varSrc);
```

### <a name="remarks"></a>Açıklamalar

Ekleme `COleVariant` (**\<**) işleci tanılama boşaltma ve arşive depolama destekler. Çıkarma (**>>**) işleci bir arşivden yüklemeyi destekler.

## <a name="colevariantsetstring"></a><a name="setstring"></a>COleVariant::SetString

Dizeyi belirli bir türe ayarlar.

```
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```

### <a name="parameters"></a>Parametreler

*lpszSrc*<br/>
Null-sonlandırılan dize yeni `COleVariant` nesneye kopyalanacak.

*VtSrc*<br/>
Yeni `COleVariant` nesne için VARTYPE.

### <a name="remarks"></a>Açıklamalar

*VtSrc* parametresi VT_BSTR (UNICODE) veya VT_BSTRT (ANSI) olmalıdır. `SetString`[COleVariant için varsayılan::COleVariant](#colevariant) oluşturucu bir dize veya dize işaretçi parametresi ve hiçbir VARTYPE UNICODE olduğundan, genellikle ANSI dizeleri ayarlamak için kullanılır.

UNICODE olmayan bir yapıdaki BIR DAO kayıt kümesi dizeleri ANSI olmasını bekler. Bu nedenle, nesneleri kullanan `COleVariant` DAO işlevleri için, bir UNICODE kayıt kümesi oluşturmuyorsanız, **COleVariant'ı kullanmanız gerekir::COleVariant(lpszSrc** **,** *vtSrc* **)** vtSrc `SetString` ile konstrüktör biçimini VT_BSTRT (ANSI) veya ANSI dizeleri yapmak için VT_BSTRT ayarlanmış *lpszSrc* *vtSrc* ile kullanmanız gerekir. *vtSrc* Örneğin, `CDaoRecordset` [CDaoRecordset::Seek](../../mfc/reference/cdaorecordset-class.md#seek) ve [CDaoRecordset::SetFieldValue](../../mfc/reference/cdaorecordset-class.md#setfieldvalue) `COleVariant` nesneleri parametre olarak kullanır. DAO kayıt kümesi UNICODE değilse, bu nesneler ANSI olmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
