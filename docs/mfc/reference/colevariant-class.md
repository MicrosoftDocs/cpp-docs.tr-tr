---
description: 'Daha fazla bilgi edinin: Cotavaryant sınıfı'
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
ms.openlocfilehash: dcf59fe1d9f67ce47a1a8587209649f56147a9f2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331409"
---
# <a name="colevariant-class"></a>Cotavariant sınıfı

[Değişken](/windows/win32/api/oaidl/ns-oaidl-variant) veri türünü kapsüller.

## <a name="syntax"></a>Syntax

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
|[Cotavaryant:: Attach](#attach)|Bir DEĞIŞKENI öğesine ekler `COleVariant` .|
|[Cotavariant:: ChangeType](#changetype)|Bu nesnenin varyant türünü değiştirir `COleVariant` .|
|[Colevarıant:: Clear](#clear)|Bu `COleVariant` nesneyi temizler.|
|[Cotavaryant::D etach](#detach)|Bir DEĞIŞKENI bir ile ayırır `COleVariant` ve varyansı döndürür.|
|[Cotavariant:: GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|Varolan bir varyant dizisinden bir bayt dizisi alır.|
|[Cotavaryant:: SetString](#setstring)|Dizeyi genellikle ANSI olarak belirli bir türe ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[Colevarıant:: operator LPCVARYANT](#operator_lpcvariant)|Bir `COleVariant` değeri öğesine dönüştürür `LPCVARIANT` .|
|[Colevarıant:: operator LPVARYANT](#operator_lpvariant)|Bir `COleVariant` nesneyi öğesine dönüştürür `LPVARIANT` .|
|[Colevarıant:: operator =](#operator_eq)|Bir `COleVariant` değeri kopyalar.|
|[Colevarıant:: operator = =](#operator_eq_eq)|İki `COleVariant` değeri karşılaştırır.|
|[Colevarıant:: işleci &lt; &lt; ,&gt;&gt;](#operator_lt_lt__gt_gt)|' A bir `COleVariant` değer `CArchive` verir `CDumpContext` ve öğesinden bir `COleVariant` nesne girişi yapın `CArchive` .|

## <a name="remarks"></a>Açıklamalar

Bu veri türü OLE Otomasyonunda kullanılır. Özellikle, [Dispparams](/windows/win32/api/oaidl/ns-oaidl-dispparams) yapısı bir varyant yapıları dizisine yönelik bir işaretçi içerir. Bir `DISPPARAMS` Yapı, parametreleri [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)öğesine geçirmek için kullanılır.

> [!NOTE]
> Bu sınıf `VARIANT` yapıdan türetilir. Bu, bir `COleVariant` ' a çağrı yapan bir parametreye geçirebilmeniz `VARIANT` ve yapının veri üyelerinin `VARIANT` erişilebilir veri üyeleri olması anlamına gelir `COleVariant` .

İki ilgili MFC sınıfı [Copacurrency](../../mfc/reference/colecurrency-class.md) ve [copadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) , DEĞIŞKEN veri türü para BIRIMINI ( `VT_CY` ) ve tarihini () kapsüllemeli `VT_DATE` . `COleVariant`Sınıf, DAO sınıflarında yaygın olarak kullanılır; bu sınıfın tipik kullanımı için, örneğin [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) ve [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)gibi bu sınıflara bakın.

Daha fazla bilgi için, Windows SDK [değişken](/windows/win32/api/oaidl/ns-oaidl-variant), [para birimi](/windows/win32/api/wtypes/ns-wtypes-cy-r1), [Dispparams](/windows/win32/api/oaidl/ns-oaidl-dispparams)ve [IDispatch:: Invoke](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke) girdileri bölümüne bakın.

`COleVariant`Sınıfı ve OLE Otomasyonunda kullanımı hakkında daha fazla bilgi için, makale [OTOMASYONUNDA](../../mfc/automation.md)"OLE Otomasyonunda parametreleri geçirme" konusuna bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagVARIANT`

`COleVariant`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** AfxDisp. h

## <a name="colevariantattach"></a><a name="attach"></a> Cotavaryant:: Attach

Belirtilen [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) nesnesini geçerli nesneye iliştirmek için bu işlevi çağırın `COleVariant` .

```cpp
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>Parametreler

*varSrc*<br/>
Geçerli nesneye eklenecek varolan bir `VARIANT` nesne `COleVariant` .

### <a name="remarks"></a>Açıklamalar

Bu işlev, *varSrc* 'nin VarType VT_EMPTY olarak ayarlar.

Daha fazla bilgi için Windows SDK [Varyant](/windows/win32/api/oaidl/ns-oaidl-variant) ve [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum) girişlerine bakın.

## <a name="colevariantcolevariant"></a><a name="colevariant"></a> Cotavariant:: Cotavariant

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
`COleVariant` `VARIANT` Yeni nesneye Kopyalanacak varolan veya nesne `COleVariant` .

*pSrc*<br/>
`VARIANT`Yeni nesneye kopyalanacak bir nesne işaretçisi `COleVariant` .

*lpszSrc*<br/>
Yeni nesneye kopyalanacak null ile sonlandırılmış bir dize `COleVariant` .

*vtSrc*<br/>
`VARTYPE`Yeni `COleVariant` nesne için.

*strSrc*<br/>
Yeni nesneye kopyalanacak bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesi `COleVariant` .

*nSrc*, *lsrc* yeni nesneye kopyalanacak sayısal bir değer `COleVariant` .

*vtSrc*<br/>
`VARTYPE`Yeni `COleVariant` nesne için.

*curSrc*<br/>
Yeni nesneye kopyalanacak [Copapara birimi](../../mfc/reference/colecurrency-class.md) nesnesi `COleVariant` .

*Fltsrc*, *dblsrc*<br/>
Yeni nesneye kopyalanacak sayısal değer `COleVariant` .

*zaman dilimlerini*<br/>
Yeni nesneye kopyalanacak [Colandatetime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi `COleVariant` .

*arrSrc*<br/>
Yeni nesneye kopyalanacak bir [CByteArray](../../mfc/reference/cbytearray-class.md) nesnesi `COleVariant` .

*lbSrc*<br/>
Yeni nesneye kopyalanacak bir [CLongBinary](../../mfc/reference/clongbinary-class.md) nesnesi `COleVariant` .

*pidl*<br/>
Yeni nesneye kopyalanacak bir [ımidlist](/windows/win32/api/shtypes/ns-shtypes-itemidlist) yapısına yönelik işaretçi `COleVariant` .

### <a name="remarks"></a>Açıklamalar

Tüm bu oluşturucular `COleVariant` , belirtilen değere başlatılan yeni nesneler oluşturur. Bu oluşturucuların her biri için kısa bir açıklama aşağıda verilmiştir.

- **Cotavariant ()** Boş bir `COleVariant` nesne oluşturur VT_EMPTY.

- **Cotavariant (** *varSrc* **)** Varolan bir `VARIANT` veya `COleVariant` nesnesini kopyalar. Değişken türü korunur.

- **Cotavariant (** *pSrc* **)** Varolan bir `VARIANT` veya `COleVariant` nesnesini kopyalar. Değişken türü korunur.

- **Cotavariant (** *lpszSrc* **)** Bir dizeyi yeni nesneye kopyalar, VT_BSTR (UNICODE).

- **Cotavariant (** *lpszSrc* **,** *vtSrc* **)** Bir dizeyi yeni nesnesine kopyalar. *VtSrc* parametresi VT_BSTR (UNICODE) veya VT_BSTRT (ANSI) olmalıdır.

- **Cotavariant (** *strSrc* **)** Bir dizeyi yeni nesneye kopyalar, VT_BSTR (UNICODE).

- **Cotavariant (** *nSrc* **)** 8 bitlik bir tamsayıyı yeni nesneye kopyalar, VT_UI1.

- **Cotavariant (** *nSrc* **,** *vtSrc* **)** 16 bit tam sayıyı (veya Boolean değeri) yeni nesneye kopyalar. *VtSrc* parametresi VT_I2 veya VT_BOOL olmalıdır.

- **Cotavariant (** *lsrc* **,** *vtSrc* **)** Yeni nesnesine 32 bitlik bir tamsayı (veya SCODE değeri) kopyalar. *VtSrc* parametresi VT_I4, VT_ERROR veya VT_BOOL olmalıdır.

- **Cotavariant (** *cursrc* **)** `COleCurrency` VT_CY yeni nesnesine bir değer kopyalar.

- **Cotavariant (** *fltsrc* **)** 32 bitlik kayan noktalı bir değeri yeni nesneye kopyalar, VT_R4.

- **Cotavariant (** *dblsrc* **)** 64 bitlik kayan noktalı bir değeri yeni nesneye kopyalar, VT_R8.

- **Cotavariant (** *timesrc* **)** `COleDateTime` VT_DATE yeni nesnesine bir değer kopyalar.

- **Cotavariant (** *arrSrc* **)** Bir `CByteArray` nesneyi VT_EMPTY yeni nesnesine kopyalar.

- **Cotavariant (** *lbsrc* **)** Bir `CLongBinary` nesneyi VT_EMPTY yeni nesnesine kopyalar.

SCODE hakkında daha fazla bilgi için bkz. Windows SDK [com hata kodları yapısı](/windows/win32/com/structure-of-com-error-codes) .

## <a name="colevariantchangetype"></a><a name="changetype"></a> Cotavariant:: ChangeType

Bu nesnedeki değişken değer türünü dönüştürür `COleVariant` .

```cpp
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```

### <a name="parameters"></a>Parametreler

*vartype*<br/>
Bu `COleVariant` NESNENIN vartype.

*pSrc*<br/>
Dönüştürülecek [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) nesnesine yönelik bir işaretçi. Bu değer NULL ise, bu `COleVariant` nesne dönüştürme kaynağı olarak kullanılır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant), [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum)ve [VariantChangeType](/windows/win32/api/oleauto/nf-oleauto-variantchangetype) girişlerine bakın.

## <a name="colevariantclear"></a><a name="clear"></a> Colevarıant:: Clear

Öğesini temizler `VARIANT` .

```cpp
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Bu, bu nesnenin VARTYPE VT_EMPTY olarak ayarlanır. `COleVariant`Yıkıcı bu işlevi çağırır.

Daha fazla bilgi için `VARIANT` Windows SDK, vartype ve girişlere bakın `VariantClear` .

## <a name="colevariantdetach"></a><a name="detach"></a> Cotavaryant::D etach

Temel alınan [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) nesnesini bu nesneden ayırır `COleVariant` .

```
VARIANT Detach();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, bu `COleVariant` NESNENIN VARTYPE VT_EMPTY olarak ayarlar.

> [!NOTE]
> Çağrıldıktan sonra `Detach` , çağıranın elde edilen yapıda çağrı yaptığı sorumluluğudur `VariantClear` `VARIANT` .

Daha fazla bilgi için Windows SDK [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant), [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum)ve [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear) girdileri bölümüne bakın.

## <a name="colevariantgetbytearrayfromvariantarray"></a><a name="getbytearrayfromvariantarray"></a> Cotavariant:: GetByteArrayFromVariantArray

Varolan bir varyant dizisinden bir bayt dizisi alır

```cpp
void GetByteArrayFromVariantArray(CByteArray& bytes);
```

### <a name="parameters"></a>Parametreler

*sayacının*<br/>
Varolan bir [CByteArray](../../mfc/reference/cbytearray-class.md) nesnesine başvuru.

## <a name="colevariantoperator-lpcvariant"></a><a name="operator_lpcvariant"></a> Colevarıant:: operator LPCVARYANT

Bu atama işleci `VARIANT` , değeri bu nesneden kopyalanmış olan bir yapıyı döndürür `COleVariant` .

```
operator LPCVARIANT() const;
```

### <a name="remarks"></a>Açıklamalar

## <a name="colevariantoperator-lpvariant"></a><a name="operator_lpvariant"></a> Colevarıant:: operator LPVARYANT

Bu nesne için temel yapıya erişmek üzere bu atama işlecini çağırın `VARIANT` `COleVariant` .

```
operator LPVARIANT();
```

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
> `VARIANT`Bu işlevin döndürdüğü işaretçinin eriştiği yapıda değeri değiştirmek, bu nesnenin değerini değiştirecek `COleVariant` .

## <a name="colevariantoperator-"></a><a name="operator_eq"></a> Colevarıant:: operator =

Bu aşırı yüklenmiş atama işleçleri kaynak değeri bu nesneye kopyalar `COleVariant` .

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

- **operator = (** *varSrc* **)** Varolan bir VARYANTı veya `COleVariant` nesneyi bu nesneye kopyalar.

- **operator = (** *pSrc* **)** *PSrc* tarafından erişilen VARIANT nesnesini bu nesneye kopyalar.

- **operator = (** *lpszSrc* **)** Null ile sonlandırılmış bir dizeyi bu nesneye kopyalar ve VARTYPE VT_BSTR olarak ayarlar.

- **operator = (** *strSrc* **)** Bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesini bu nesneye kopyalar ve vartype VT_BSTR olarak ayarlar.

- **operator = (** *nSrc* **)** 8 veya 16 bitlik bir tamsayı değerini bu nesneye kopyalar. *NSrc* , 8 bitlik bir değer ise, bu değerin VarType VT_UI1 olarak ayarlanır. *NSrc* , 16 bitlik bir değer ise ve bunun VarType VT_BOOL, tutulur; Aksi takdirde, VT_I2 olarak ayarlanır.

- **operator = (** *lsrc* **)** 32 bitlik bir tamsayı değerini bu nesneye kopyalar. Bunun VARTYPE VT_ERROR ise tutulur; Aksi takdirde, VT_I4 olarak ayarlanır.

- **operator = (** *cursrc* **)** [Copacurrency](../../mfc/reference/colecurrency-class.md) nesnesini bu nesneye kopyalar ve vartype VT_CY olarak ayarlar.

- **operator = (** *fltsrc* **)** 32 bitlik kayan noktalı bir değeri bu nesneye kopyalar ve VARTYPE VT_R4 olarak ayarlar.

- **operator = (** *dblsrc* **)** 64 bitlik kayan noktalı bir değeri bu nesneye kopyalar ve VARTYPE VT_R8 olarak ayarlar.

- **operator = (** *datesrc* **)** Bir [Cotadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesini bu nesneye kopyalar ve vartype VT_DATE olarak ayarlar.

- **operator = (** *arrSrc* **)** Bir [CByteArray](../../mfc/reference/cbytearray-class.md) nesnesini bu nesneye kopyalar `COleVariant` .

- **operator = (** *lbsrc* **)** Bir [CLongBinary](../../mfc/reference/clongbinary-class.md) nesnesini bu nesneye kopyalar `COleVariant` .

Daha fazla bilgi için Windows SDK [Varyant](/windows/win32/api/oaidl/ns-oaidl-variant) ve [VARENUM](/windows/win32/api/wtypes/ne-wtypes-varenum) girişlerine bakın.

## <a name="colevariantoperator-"></a><a name="operator_eq_eq"></a> Colevarıant:: operator = =

Bu işleç iki değişken değeri karşılaştırır ve eşitse sıfır dışında bir değer döndürür; Aksi takdirde 0.

```
BOOL operator==(const VARIANT& varSrc) const;
BOOL operator==(LPCVARIANT pSrc) const;
```

## <a name="colevariantoperator-ltlt-gtgt"></a><a name="operator_lt_lt__gt_gt"></a>Colevarıant:: işleci &lt; &lt; ,&gt;&gt;

' A bir `COleVariant` değer `CArchive` verir `CdumpContext` ve öğesinden bir `COleVariant` nesne girişi yapın `CArchive` .

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

`COleVariant`Ekleme ( **\<\<**) operator supports diagnostic dumping and storing to an archive. The extraction (**>>** ) işleci bir arşivden yüklemeyi destekler.

## <a name="colevariantsetstring"></a><a name="setstring"></a> Cotavaryant:: SetString

Dizeyi belirli bir türe ayarlar.

```cpp
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```

### <a name="parameters"></a>Parametreler

*lpszSrc*<br/>
Yeni nesneye kopyalanacak null ile sonlandırılmış bir dize `COleVariant` .

*VtSrc*<br/>
Yeni nesne için VARTYPE `COleVariant` .

### <a name="remarks"></a>Açıklamalar

*VtSrc* parametresi VT_BSTR (UNICODE) veya VT_BSTRT (ANSI) olmalıdır. `SetString` genellikle dize veya dize işaretçisi parametresi ile [COleVariant:: colevarıant](#colevariant) Oluşturucusu için varsayılan değer UNICODE olmadığından, dizeleri ANSI olarak ayarlamak için kullanılır.

UNICODE olmayan bir derlemede bir DAO Kayıt kümesi dizelerin ANSI olmasını bekler. Bu nedenle, nesneleri kullanan DAO işlevleri için, `COleVariant` bir UNICODE kayıt kümesi oluşturmadıysanız, lpszSrc (ANSI) VT_BSTRT olarak ya *da*   vtVT_BSTRT src ile birlikte kullanarak, ANSI dizelerini oluşturmak için *,* **olarak,** **vtSrc ile** birlikte kullanın `SetString` .  Örneğin, `CDaoRecordset` [CDaoRecordset:: Seek](../../mfc/reference/cdaorecordset-class.md#seek) ve [CDaoRecordset:: SetFieldValue](../../mfc/reference/cdaorecordset-class.md#setfieldvalue) işlevleri, `COleVariant` nesneleri parametre olarak kullanır. DAO Kayıt kümesi UNICODE değilse, bu nesneler ANSI olmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
