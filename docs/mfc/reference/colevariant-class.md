---
title: Cotavariant sınıfı
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
ms.openlocfilehash: 49cd4a8d3db436d5e3c4d29efbb4d80b4741a270
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739784"
---
# <a name="colevariant-class"></a>Cotavariant sınıfı

[Değişken](/windows/win32/api/oaidl/ns-oaidl-variant) veri türünü kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class COleVariant : public tagVARIANT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cotavariant:: Cotavariant](#colevariant)|Bir `COleVariant` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotavaryant:: Attach](#attach)|Bir `COleVariant`değişkeni öğesine ekler.|
|[Cotavariant:: ChangeType](#changetype)|Bu `COleVariant` nesnenin varyant türünü değiştirir.|
|[Colevarıant:: Clear](#clear)|Bu `COleVariant` nesneyi temizler.|
|[Cotavaryant::D etach](#detach)|Bir değişkeni bir `COleVariant` ile ayırır ve varyansı döndürür.|
|[Cotavariant:: GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|Varolan bir varyant dizisinden bir bayt dizisi alır.|
|[Cotavaryant:: SetString](#setstring)|Dizeyi genellikle ANSI olarak belirli bir türe ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Colevarıant:: operator LPCVARYANT](#operator_lpcvariant)|Bir `COleVariant` değeri`LPCVARIANT`öğesine dönüştürür.|
|[Colevarıant:: operator LPVARYANT](#operator_lpvariant)|Bir `COleVariant` nesneyi`LPVARIANT`öğesine dönüştürür.|
|[Colevarıant:: operator =](#operator_eq)|Bir `COleVariant` değeri kopyalar.|
|[Colevarıant:: operator = =](#operator_eq_eq)|İki `COleVariant` değeri karşılaştırır.|
|[Colevarıant:: işleci &lt;, &lt;&gt;&gt;](#operator_lt_lt__gt_gt)|`COleVariant` `CArchive` 'A`COleVariant` bir değer verirve`CArchive`öğesinden bir nesne girişi yapın. `CDumpContext`|

## <a name="remarks"></a>Açıklamalar

Bu veri türü OLE Otomasyonunda kullanılır. Özellikle, [Dispparams](/windows/win32/api/oaidl/ns-oaidl-dispparams) yapısı bir varyant yapıları dizisine yönelik bir işaretçi içerir. Bir `DISPPARAMS` yapı, parametreleri [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)öğesine geçirmek için kullanılır.

> [!NOTE]
> Bu sınıf `VARIANT` yapıdan türetilir. Bu, bir `VARIANT` ' a çağrı `COleVariant` yapan bir parametreye geçirebilmeniz ve `VARIANT` yapının veri üyelerinin erişilebilir veri üyeleri `COleVariant`olması anlamına gelir.

İki ilgili MFC sınıfı [copacurrency](../../mfc/reference/colecurrency-class.md) ve [copadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) , değişken veri türü para birimini ( `VT_CY`) ve tarihini ( `VT_DATE`) kapsüllemeli. Sınıf, DAO sınıflarında yaygın olarak kullanılır; bu sınıfın tipik kullanımı için, örneğin [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) ve [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)gibi bu sınıflara bakın. `COleVariant`

Daha fazla bilgi için, Windows SDK [değişken](/windows/win32/api/oaidl/ns-oaidl-variant), [para birimi](/windows/win32/api/wtypes/ns-wtypes-cy~r1), [Dispparams](/windows/win32/api/oaidl/ns-oaidl-dispparams)ve [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) girdileri bölümüne bakın.

`COleVariant` Sınıfı ve OLE Otomasyonunda kullanımı hakkında daha fazla bilgi için, makale [otomasyonunda](../../mfc/automation.md)"OLE Otomasyonunda parametreleri geçirme" konusuna bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagVARIANT`

`COleVariant`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

##  <a name="attach"></a>Cotavaryant:: Attach

Belirtilen [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) nesnesini geçerli `COleVariant` nesneye iliştirmek için bu işlevi çağırın.

```
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>Parametreler

*varSrc*<br/>
`VARIANT` Geçerli`COleVariant` nesneye eklenecek varolan bir nesne.

### <a name="remarks"></a>Açıklamalar

Bu işlev, *varSrc* 'nin VarType öğesini VT_EMPTY olarak ayarlar.

Daha fazla bilgi için Windows SDK [Varyant](/windows/win32/api/oaidl/ns-oaidl-variant) ve [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum) girişlerine bakın.

##  <a name="colevariant"></a>Cotavariant:: Cotavariant

Bir `COleVariant` nesnesi oluşturur.

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
Yeni `VARIANT` `COleVariant` nesneyeKopyalanacakvarolanveyanesne`COleVariant` .

*pSrc*<br/>
`VARIANT` Yeni`COleVariant` nesneye kopyalanacak bir nesne işaretçisi.

*lpszSrc*<br/>
Yeni `COleVariant` nesneye kopyalanacak null ile sonlandırılmış bir dize.

*vtSrc*<br/>
`VARTYPE` Yeni`COleVariant` nesne için.

*strSrc*<br/>
Yeni`COleVariant` nesneye kopyalanacak bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi.

*nSrc*, *lsrc* yeni `COleVariant` nesneye kopyalanacak sayısal bir değer.

*vtSrc*<br/>
`VARTYPE` Yeni`COleVariant` nesne için.

*curSrc*<br/>
Yeni`COleVariant` nesneye kopyalanacak [copapara birimi](../../mfc/reference/colecurrency-class.md) nesnesi.

*Fltsrc*, *dblsrc*<br/>
Yeni `COleVariant` nesneye kopyalanacak sayısal değer.

*zaman dilimlerini*<br/>
Yeni`COleVariant` nesneye kopyalanacak [colandatetime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi.

*arrSrc*<br/>
Yeni`COleVariant` nesneye kopyalanacak bir [CByteArray](../../mfc/reference/cbytearray-class.md) nesnesi.

*lbSrc*<br/>
Yeni`COleVariant` nesneye kopyalanacak bir [CLongBinary](../../mfc/reference/clongbinary-class.md) nesnesi.

*pidl*<br/>
Yeni`COleVariant` nesneye kopyalanacak bir [ımidlist](/windows/win32/api/shtypes/ns-shtypes-itemidlist) yapısına yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Tüm bu oluşturucular, belirtilen `COleVariant` değere başlatılan yeni nesneler oluşturur. Bu oluşturucuların her biri için kısa bir açıklama aşağıda verilmiştir.

- **Cotavariant ()** Boş `COleVariant` bir nesne oluşturur, VT_EMPTY.

- **Cotavariant (** *varSrc* **)** Varolan `VARIANT` bir veya `COleVariant` nesnesini kopyalar. Değişken türü korunur.

- **Cotavariant (** *pSrc* **)** Varolan `VARIANT` bir veya `COleVariant` nesnesini kopyalar. Değişken türü korunur.

- **Cotavariant (** *lpszSrc* **)** Bir dizeyi VT_BSTR (UNICODE) yeni nesnesine kopyalar.

- **Cotavariant (** *lpszSrc* **,** *vtSrc* **)** Bir dizeyi yeni nesnesine kopyalar. *VtSrc* parametresi VT_BSTR (UNICODE) veya VT_BSTRT (ANSI) olmalıdır.

- **Cotavariant (** *strSrc* **)** Bir dizeyi VT_BSTR (UNICODE) yeni nesnesine kopyalar.

- **Cotavariant (** *nSrc* **)** 8 bitlik bir tamsayıyı yeni nesnesine kopyalar, VT_UI1.

- **Cotavariant (** *nSrc* **,** *vtSrc* **)** 16 bit tam sayıyı (veya Boolean değeri) yeni nesneye kopyalar. *VtSrc* parametresi VT_I2 veya VT_BOOL olmalıdır.

- **Cotavariant (** *lsrc* **,** *vtSrc* **)** Yeni nesnesine 32 bitlik bir tamsayı (veya SCODE değeri) kopyalar. *VtSrc* parametresi VT_I4, VT_ERROR veya VT_BOOL olmalıdır.

- **Cotavariant (** *cursrc* **)** Bir `COleCurrency` değeri, VT_CY New nesnesine kopyalar.

- **Cotavariant (** *fltsrc* **)** 32 bitlik kayan noktalı bir değeri yeni nesnesine kopyalar, VT_R4.

- **Cotavariant (** *dblsrc* **)** 64 bitlik kayan noktalı bir değeri yeni nesnesine kopyalar, VT_R8.

- **Cotavariant (** *timesrc* **)** Bir `COleDateTime` değeri, VT_DATE New nesnesine kopyalar.

- **Cotavariant (** *arrSrc* **)** Bir `CByteArray` nesneyi VT_EMPTY New nesnesine kopyalar.

- **Cotavariant (** *lbsrc* **)** Bir `CLongBinary` nesneyi VT_EMPTY New nesnesine kopyalar.

SCODE hakkında daha fazla bilgi için bkz. Windows SDK [com hata kodları yapısı](/windows/win32/com/structure-of-com-error-codes) .

##  <a name="changetype"></a>Cotavariant:: ChangeType

Bu `COleVariant` nesnedeki değişken değer türünü dönüştürür.

```
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```

### <a name="parameters"></a>Parametreler

*vartype*<br/>
Bu `COleVariant` nesnenin vartype.

*pSrc*<br/>
Dönüştürülecek [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) nesnesine yönelik bir işaretçi. Bu değer null ise, bu `COleVariant` nesne dönüştürme kaynağı olarak kullanılır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant), [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum)ve [VariantChangeType](/windows/win32/api/oleauto/nf-oleauto-variantchangetype) girişlerine bakın.

##  <a name="clear"></a>Colevarıant:: Clear

Öğesini temizler `VARIANT`.

```
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Bu nesne için VARTYPE, VT_EMPTY olarak ayarlanır. `COleVariant` Yıkıcı bu işlevi çağırır.

Daha fazla bilgi için Windows SDK `VARIANT`, vartype ve `VariantClear` girişlere bakın.

##  <a name="detach"></a>Cotavaryant::D etach

Temel alınan [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) nesnesini bu `COleVariant` nesneden ayırır.

```
VARIANT Detach();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, bu `COleVariant` nesnenin VarType öğesini VT_EMPTY olarak ayarlar.

> [!NOTE]
>  Çağrıldıktan `Detach`sonra, çağıranın elde edilen `VARIANT` yapıda çağrı `VariantClear` yaptığı sorumluluğudur.

Daha fazla bilgi için Windows SDK [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant), [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum)ve [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear) girdileri bölümüne bakın.

##  <a name="getbytearrayfromvariantarray"></a>Cotavariant:: GetByteArrayFromVariantArray

Varolan bir varyant dizisinden bir bayt dizisi alır

```
void GetByteArrayFromVariantArray(CByteArray& bytes);
```

### <a name="parameters"></a>Parametreler

*sayacının*<br/>
Varolan bir [CByteArray](../../mfc/reference/cbytearray-class.md) nesnesine başvuru.

##  <a name="operator_lpcvariant"></a>Colevarıant:: operator LPCVARYANT

Bu atama işleci, değeri `VARIANT` bu `COleVariant` nesneden kopyalanmış olan bir yapıyı döndürür.

```
operator LPCVARIANT() const;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="operator_lpvariant"></a>Colevarıant:: operator LPVARYANT

`VARIANT` Bu`COleVariant` nesne için temel yapıya erişmek üzere bu atama işlecini çağırın.

```
operator LPVARIANT();
```

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
> Bu işlevin döndürdüğü işaretçinin eriştiği `VARIANT` yapıda değeri değiştirmek, bu `COleVariant` nesnenin değerini değiştirecek.

##  <a name="operator_eq"></a>Colevarıant:: operator =

Bu aşırı yüklenmiş atama işleçleri kaynak değeri bu `COleVariant` nesneye kopyalar.

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

Her işlecin kısa bir açıklaması aşağıdadır:

- **operator = (** *varSrc* **)** Varolan bir varyantı veya `COleVariant` nesneyi bu nesneye kopyalar.

- **operator = (** *pSrc* **)** *PSrc* tarafından erişilen VARIANT nesnesini bu nesneye kopyalar.

- **operator = (** *lpszSrc* **)** Null ile sonlandırılmış bir dizeyi bu nesneye kopyalar ve VARTYPE değerini VT_BSTR olarak ayarlar.

- **operator = (** *strSrc* **)** Bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesini bu nesneye kopyalar ve vartype öğesini VT_BSTR olarak ayarlar.

- **operator = (** *nSrc* **)** 8 veya 16 bitlik bir tamsayı değerini bu nesneye kopyalar. *NSrc* , 8 bitlik bir değer ise, bu DEĞERIN VarType VT_UI1 olarak ayarlanır. *NSrc* , 16 bitlik bir değer ise ve bunun VarType VT_BOOL ise, tutulur; Aksi takdirde, VT_I2 olarak ayarlanır.

- **operator = (** *lsrc* **)** 32 bitlik bir tamsayı değerini bu nesneye kopyalar. Bunun VARTYPE VT_ERROR ise, tutulur; Aksi takdirde, VT_I4 olarak ayarlanır.

- **operator = (** *cursrc* **)** [Copacurrency](../../mfc/reference/colecurrency-class.md) nesnesini bu nesneye kopyalar ve vartype öğesini VT_CY olarak ayarlar.

- **operator = (** *fltsrc* **)** 32 bitlik kayan noktalı bir değeri bu nesneye kopyalar ve VARTYPE değerini VT_R4 olarak ayarlar.

- **operator = (** *dblsrc* **)** 64 bitlik kayan noktalı bir değeri bu nesneye kopyalar ve VARTYPE değerini VT_R8 olarak ayarlar.

- **operator = (** *datesrc* **)** Bir [Cotadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesini bu nesneye kopyalar ve vartype öğesini VT_DATE olarak ayarlar.

- **operator = (** *arrSrc* **)** Bir [CByteArray](../../mfc/reference/cbytearray-class.md) nesnesini bu `COleVariant` nesneye kopyalar.

- **operator = (** *lbsrc* **)** Bir [CLongBinary](../../mfc/reference/clongbinary-class.md) nesnesini bu `COleVariant` nesneye kopyalar.

Daha fazla bilgi için Windows SDK [Varyant](/windows/win32/api/oaidl/ns-oaidl-variant) ve [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum) girişlerine bakın.

##  <a name="operator_eq_eq"></a>Colevarıant:: operator = =

Bu işleç iki değişken değeri karşılaştırır ve eşitse sıfır dışında bir değer döndürür; Aksi takdirde 0.

```
BOOL operator==(const VARIANT& varSrc) const;
BOOL operator==(LPCVARIANT pSrc) const;
```

##  <a name="operator_lt_lt__gt_gt"></a>Colevarıant:: işleci &lt;, &lt;&gt;&gt;

`COleVariant` `CArchive` 'A`COleVariant` bir değer verirve`CArchive`öğesinden bir nesne girişi yapın. `CdumpContext`

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

Ekleme `COleVariant` **(\<) işleci, tanılama dökümünü ve bir arşive depolamayı destekler.\<** Ayıklama ( **>>** ) işleci bir arşivden yüklemeyi destekler.

##  <a name="setstring"></a>Cotavaryant:: SetString

Dizeyi belirli bir türe ayarlar.

```
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```

### <a name="parameters"></a>Parametreler

*lpszSrc*<br/>
Yeni `COleVariant` nesneye kopyalanacak null ile sonlandırılmış bir dize.

*VtSrc*<br/>
Yeni `COleVariant` nesne için VarType.

### <a name="remarks"></a>Açıklamalar

*VtSrc* parametresi VT_BSTR (UNICODE) veya VT_BSTRT (ANSI) olmalıdır. `SetString`genellikle dize veya dize işaretçisi parametresi ile [COleVariant:: colevarıant](#colevariant) Oluşturucusu için varsayılan değer UNICODE olmadığından, dizeleri ANSI olarak ayarlamak için kullanılır.

UNICODE olmayan bir derlemede bir DAO Kayıt kümesi dizelerin ANSI olmasını bekler. `COleVariant` Bu nedenle, nesneleri kullanan DAO işlevleri için, bir UNICODE kayıt kümesi oluşturmadıysanız, *vtSrc* 'i VT olarak ayarlanmış bir oluşturucunun **cotavariant:: copavariant (** *lpszSrc* **,** *vtSrc* **)** formunu kullanmanız gerekir ANSI dizelerini yapmak için _bstrt ( `SetString` ANSI) veya VT_BSTRT olarak ayarlanmış *vtSrc* ile kullanın. Örneğin, `CDaoRecordset` [CDaoRecordset:: Seek](../../mfc/reference/cdaorecordset-class.md#seek) ve [CDaoRecordset:: SetFieldValue](../../mfc/reference/cdaorecordset-class.md#setfieldvalue) işlevleri, nesneleri parametre `COleVariant` olarak kullanır. DAO Kayıt kümesi UNICODE değilse, bu nesneler ANSI olmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
