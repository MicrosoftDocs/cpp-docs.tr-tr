---
title: COleVariant sınıfı
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
ms.openlocfilehash: 528b46f1b370f8679b86e3d734712f936a153b9c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625006"
---
# <a name="colevariant-class"></a>COleVariant sınıfı

Kapsülleyen [değişken](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) veri türü.

## <a name="syntax"></a>Sözdizimi

```
class COleVariant : public tagVARIANT
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleVariant::COleVariant](#colevariant)|Oluşturur bir `COleVariant` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleVariant::Attach](#attach)|Bir değişken için bağlayan bir `COleVariant`.|
|[COleVariant::ChangeType](#changetype)|Bu değişken türünü değiştirir `COleVariant` nesne.|
|[COleVariant::Clear](#clear)|Bu temizler `COleVariant` nesne.|
|[COleVariant::Detach](#detach)|Bir DEĞİŞKENDEN ayırır bir `COleVariant` ve değişken döndürür.|
|[COleVariant::GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|Mevcut bir değişken dizisinden bir bayt dizisi alır.|
|[COleVariant::SetString](#setstring)|Belirli bir tür, genellikle ANSI dizesini ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[COleVariant::operator LPCVARIANT](#operator_lpcvariant)|Dönüştürür bir `COleVariant` içine değeri bir `LPCVARIANT`.|
|[COleVariant::operator LPVARIANT](#operator_lpvariant)|Dönüştürür bir `COleVariant` içine nesnesi bir `LPVARIANT`.|
|[COleVariant::operator =](#operator_eq)|Kopya bir `COleVariant` değeri.|
|[COleVariant::operator ==](#operator_eq_eq)|İki karşılaştırır `COleVariant` değerleri.|
|[COleVariant::operator &lt; &lt;, &gt;&gt;](#operator_lt_lt__gt_gt)|Çıkış bir `COleVariant` değerini `CArchive` veya `CDumpContext` ve girdi bir `COleVariant` nesnesinden `CArchive`.|

## <a name="remarks"></a>Açıklamalar

Bu veri türü OLE Otomasyonu nesnesi etkin kullanılır. Özellikle, [DISPPARAMS](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagdispparams) yapısı, bir dizi değişken yapıları işaretçi içerir. A `DISPPARAMS` yapısı için parametreleri geçirmek için kullanılan [IDispatch::Invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke).

> [!NOTE]
> Bu sınıf türetilir `VARIANT` yapısı. Bu, geçirebilirsiniz anlamına gelir. bir `COleVariant` için çağıran bir parametreye bir `VARIANT` ve veri üyeleri `VARIANT` yapısı erişilebilir veri üyeleri olan `COleVariant`.

İki ilgili MFC sınıfları [COleCurrency](../../mfc/reference/colecurrency-class.md) ve [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) değişken veri türleri para birimi kapsülle ( `VT_CY`) ve tarih ( `VT_DATE`). `COleVariant` Sınıfı DAO sınıfları yaygın olarak kullanılır; örneğin tipik kullanım için bu sınıflar bu sınıfın bkz [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) ve [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

Daha fazla bilgi için [değişken](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant), [para birimi](/windows/desktop/api/wtypes/ns-wtypes-tagcy), [DISPPARAMS](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagdispparams), ve [IDispatch::Invoke](/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) Windows SDK'sı girdileri.

Daha fazla bilgi için `COleVariant` sınıfı ve OLE Otomasyonu, kullanım "Geçirme parametreleri olarak OLE Otomasyonu" makalesine bakın [Otomasyon](../../mfc/automation.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`tagVARIANT`

`COleVariant`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdisp.h

##  <a name="attach"></a>  COleVariant::Attach

Eklemek için bu işlevi çağırın verilen [değişken](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) geçerli nesneye `COleVariant` nesne.

```
void Attach(VARIANT& varSrc);
```

### <a name="parameters"></a>Parametreler

*varSrc*<br/>
Mevcut bir `VARIANT` geçerli eklenecek nesne `COleVariant` nesne.

### <a name="remarks"></a>Açıklamalar

Bu işlev, VARTYPE ayarlar *varSrc* VT_EMPTY için.

Daha fazla bilgi için [değişken](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) ve [VARENUM](/windows/desktop/api/wtypes/ne-wtypes-varenum) Windows SDK'sı girdileri.

##  <a name="colevariant"></a>  COleVariant::COleVariant

Oluşturur bir `COleVariant` nesne.

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
Mevcut bir `COleVariant` veya `VARIANT` yeni içine kopyalanacak nesne `COleVariant` nesne.

*pSrc*<br/>
Bir işaretçi bir `VARIANT` yeni içine kopyalanacak nesne `COleVariant` nesne.

*lpszSrc*<br/>
Null ile sonlandırılmış bir dize yeni içine kopyalanacak `COleVariant` nesne.

*vtSrc*<br/>
`VARTYPE` Yeni `COleVariant` nesne.

*strSrc*<br/>
A [CString](../../atl-mfc-shared/reference/cstringt-class.md) yeni içine kopyalanacak nesne `COleVariant` nesne.

*nSrc*, *lSrc* yeni içine kopyalanacak bir sayısal değer `COleVariant` nesne.

*vtSrc*<br/>
`VARTYPE` Yeni `COleVariant` nesne.

*curSrc*<br/>
A [COleCurrency](../../mfc/reference/colecurrency-class.md) yeni içine kopyalanacak nesne `COleVariant` nesne.

*fltsrc &*, *; dblsrc &*<br/>
Yeni içine kopyalanacak bir sayısal değer `COleVariant` nesne.

*timeSrc*<br/>
A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) yeni içine kopyalanacak nesne `COleVariant` nesne.

*arrSrc*<br/>
A [CByteArray](../../mfc/reference/cbytearray-class.md) yeni içine kopyalanacak nesne `COleVariant` nesne.

*lbSrc*<br/>
A [CLongBinary](../../mfc/reference/clongbinary-class.md) yeni içine kopyalanacak nesne `COleVariant` nesne.

*PIDL işaretçisiyle birlikte*<br/>
Bir işaretçi bir [ITEMIDLIST](/windows/desktop/api/shtypes/ns-shtypes-_itemidlist) yeni içine kopyalanacak yapısı `COleVariant` nesne.

### <a name="remarks"></a>Açıklamalar

Bu oluşturucular Yeni Oluştur `COleVariant` nesneleri belirtilen değerle başlatılır. Bu oluşturucular her kısa bir açıklaması aşağıdadır.

- **COleVariant ()** boş bir `COleVariant` VT_EMPTY nesnesi.

- **COleVariant (** *varSrc* **)** kopyalar varolan `VARIANT` veya `COleVariant` nesne. Değişken türü korunur.

- **COleVariant (** *pSrc* **)** kopyalar varolan `VARIANT` veya `COleVariant` nesne. Değişken türü korunur.

- **COleVariant (** *lpszSrc* **)** VT_BSTR (UNICODE) yeni nesnesine bir dizeyi kopyalar.

- **COleVariant (** *lpszSrc* **,** *vtSrc* **)** bir dize yeni nesneye kopyalar. Parametre *vtSrc* VT_BSTR (UNICODE) veya VT_BSTRT (ANSI) olmalıdır.

- **COleVariant (** *strSrc* **)** VT_BSTR (UNICODE) yeni nesnesine bir dizeyi kopyalar.

- **COleVariant (** *nSrc* **)** 8 bit tamsayı VT_UI1 yeni nesnesine kopyalar.

- **COleVariant (** *nSrc* **,** *vtSrc* **)** 16-bit tamsayı (veya Boolean değeri) yeni nesneye kopyalar. Parametre *vtSrc* VT_I2 veya VT_BOOL olması gerekir.

- **COleVariant (** *lSrc* **,** *vtSrc* **)** 32-bit tamsayı (veya SCODE değeri) yeni nesneye kopyalar. Parametre *vtSrc* VT_I4, VT_ERROR veya VT_BOOL olması gerekir.

- **COleVariant (** *curSrc* **)** kopya bir `COleCurrency` VT_CY yeni nesne değeri.

- **COleVariant (** *; fltsrc &* **)** 32 bit kayan nokta değeri yeni nesneye, VT_R4 kopyalar.

- **COleVariant (** *; dblsrc &* **)** 64-bit kayan nokta değeri yeni nesneye, VT_R8 kopyalar.

- **COleVariant (** *timeSrc* **)** kopya bir `COleDateTime` yeni nesne VT_DATE değeri.

- **COleVariant (** *arrSrc* **)** kopya bir `CByteArray` nesnesine VT_EMPTY yeni nesne.

- **COleVariant (** *lbSrc* **)** kopya bir `CLongBinary` nesnesine VT_EMPTY yeni nesne.

SCODE hakkında daha fazla bilgi için bkz. [yapısı COM hata kodlarını](/windows/desktop/com/structure-of-com-error-codes) Windows SDK.

##  <a name="changetype"></a>  COleVariant::ChangeType

Bu değişken değerinin türü dönüştürür `COleVariant` nesne.

```
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```

### <a name="parameters"></a>Parametreler

*VarType*<br/>
Bu VARTYPE `COleVariant` nesne.

*pSrc*<br/>
Bir işaretçi [değişken](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) dönüştürülecek nesne. Bu değer NULL ise bu `COleVariant` nesnesi dönüştürme için kaynak olarak kullanılır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [değişken](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant), [VARENUM](/windows/desktop/api/wtypes/ne-wtypes-varenum), ve [VariantChangeType](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantchangetype) Windows SDK'sı girdileri.

##  <a name="clear"></a>  COleVariant::Clear

Temizler `VARIANT`.

```
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Bu, bu nesne için VARTYPE VT_EMPTY için ayarlar. `COleVariant` Yıkıcı bu işlevi çağırır.

Daha fazla bilgi için `VARIANT`, VARTYPE, ve `VariantClear` Windows SDK'sı girdileri.

##  <a name="detach"></a>  COleVariant::Detach

Arka plandaki ayırır [değişken](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) bu nesneden `COleVariant` nesne.

```
VARIANT Detach();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev VARTYPE bu ayarlar `COleVariant` VT_EMPTY nesnesine.

> [!NOTE]
>  Arama sonra `Detach`, bu çağrı çağıranın sorumluluğundadır `VariantClear` sonuç üzerinde `VARIANT` yapısı.

Daha fazla bilgi için [değişken](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant), [VARENUM](/windows/desktop/api/wtypes/ne-wtypes-varenum), ve [VariantClear](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantclear) Windows SDK'sı girdileri.

##  <a name="getbytearrayfromvariantarray"></a>  COleVariant::GetByteArrayFromVariantArray

Mevcut bir değişken dizisinden bir bayt dizisi alır.

```
void GetByteArrayFromVariantArray(CByteArray& bytes);
```

### <a name="parameters"></a>Parametreler

*Bayt*<br/>
Var olan bir başvuru [CByteArray](../../mfc/reference/cbytearray-class.md) nesne.

##  <a name="operator_lpcvariant"></a>  COleVariant::operator LPCVARIANT

Bu atama işleci döndürür bir `VARIANT` değeri bu kopyalanır yapısı `COleVariant` nesne.

```
operator LPCVARIANT() const;
```

### <a name="remarks"></a>Açıklamalar

##  <a name="operator_lpvariant"></a>  COleVariant::operator LPVARIANT

Arka plandaki erişmek için bu atama işlecini çağırmak `VARIANT` yapısı bu `COleVariant` nesne.

```
operator LPVARIANT();
```

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
> Değer değiştirme `VARIANT` bu işlev tarafından döndürülen işaretçi tarafından erişilen yapısı, bu değeri değişecek `COleVariant` nesne.

##  <a name="operator_eq"></a>  COleVariant::operator =

Bu aşırı yüklenmiş atama işleçleri bu kaynak değeri kopyalayın `COleVariant` nesne.

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

Her işleç kısa bir açıklaması aşağıdaki gibidir:

- **operator = (** *varSrc* **)** mevcut bir değişken kopyalar veya `COleVariant` bu nesne bir nesnede.

- **operator = (** *pSrc* **)** tarafından erişilen değişken nesnesini kopyalar *pSrc* bu nesne içine.

- **operator = (** *lpszSrc* **)** null ile sonlandırılmış bir dize bu nesneye kopyalar ve VARTYPE VT_BSTR için ayarlar.

- **operator = (** *strSrc* **)** kopya bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) bu nesne ve ayarlar için VT_BSTR VARTYPE nesnesine.

- **operator = (** *nSrc* **)** bir 8 veya 16 bit tamsayı değeri bu nesneye kopyalar. Varsa *nSrc* 8-bit bir değer olan bu VARTYPE VT_UI1 için ayarlanır. Varsa *nSrc* 16 bitlik bir değerdir ve bu VARTYPE VT_BOOL olup, tutulan; Aksi takdirde ve VT_I2 için ayarlanır.

- **operator = (** *lSrc* **)** 32-bit tamsayı değeri bu nesneye kopyalar. Bu VARTYPE VT_ERROR ise tutulur; Aksi takdirde, VT_I4 için ayarlanır.

- **operator = (** *curSrc* **)** kopya bir [COleCurrency](../../mfc/reference/colecurrency-class.md) bu nesne ve ayarlar için VT_CY VARTYPE nesnesine.

- **operator = (** *; fltsrc &* **)** VARTYPE VT_R4 için ayarlar ve bir 32 bit kayan nokta değeri bu nesneye kopyalar.

- **operator = (** *; dblsrc &* **)** VARTYPE VT_R8 için ayarlar ve bir 64-bit kayan nokta değeri bu nesneye kopyalar.

- **operator = (** *dateSrc* **)** kopya bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) bu nesne ve ayarlar için VT_DATE VARTYPE nesnesine.

- **operator = (** *arrSrc* **)** kopya bir [CByteArray](../../mfc/reference/cbytearray-class.md) bu nesnede `COleVariant` nesne.

- **operator = (** *lbSrc* **)** kopya bir [CLongBinary](../../mfc/reference/clongbinary-class.md) bu nesnede `COleVariant` nesne.

Daha fazla bilgi için [değişken](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) ve [VARENUM](/windows/desktop/api/wtypes/ne-wtypes-varenum) Windows SDK'sı girdileri.

##  <a name="operator_eq_eq"></a>  COleVariant::operator ==

Bu işleç, iki değişken değerlerini karşılaştırır ve eşitlerse sıfır döndürür; Aksi durumda 0.

```
BOOL operator==(const VARIANT& varSrc) const;
BOOL operator==(LPCVARIANT pSrc) const;
```

##  <a name="operator_lt_lt__gt_gt"></a>  COleVariant::operator &lt; &lt;, &gt;&gt;

Çıkış bir `COleVariant` değerini `CArchive` veya `CdumpContext` ve girdi bir `COleVariant` nesnesinden `CArchive`.

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

`COleVariant` Ekleme (**\<\<**) işleci, tanılama dökme ve arşive depolama destekler. Çıkarma (**>>**) işleci bir arşiv yüklenmesini destekler.

##  <a name="setstring"></a>  COleVariant::SetString

Dizeyi belirli bir türe belirler.

```
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```

### <a name="parameters"></a>Parametreler

*lpszSrc*<br/>
Null ile sonlandırılmış bir dize yeni içine kopyalanacak `COleVariant` nesne.

*vtSrc*<br/>
Yeni VARTYPE `COleVariant` nesne.

### <a name="remarks"></a>Açıklamalar

Parametre *vtSrc* VT_BSTR (UNICODE) veya VT_BSTRT (ANSI) olmalıdır. `SetString` dizeleri ANSI olarak varsayılan kümesinin için genellikle kullanılan [COleVariant::COleVariant](#colevariant) oluşturucudur bir dize veya dize işaretçisi parametresi ve hiçbir VARTYPE UNICODE.

DAO kayıt kümesinde bir UNICODE olmayan derleme dizeleri ANSI olmasını bekliyor. Bu nedenle, kullanan işlevler için DAO `COleVariant` nesneleri, UNICODE kayıt oluşturmuyorsanız, kullanmalıdır **COleVariant::COleVariant (** *lpszSrc* **,** *vtSrc* **)** oluşturucuyla biçiminin *vtSrc* VT_BSTRT (ANSI) olarak ayarlayabilir veya kullanabilirsiniz `SetString` ile *vtSrc* VT için ayarlayın ANSI dizelerini yapmak _BSTRT. Örneğin, `CDaoRecordset` işlevleri [CDaoRecordset::Seek](../../mfc/reference/cdaorecordset-class.md#seek) ve [CDaoRecordset::SetFieldValue](../../mfc/reference/cdaorecordset-class.md#setfieldvalue) kullanın `COleVariant` parametre olarak nesne. DAO kayıt UNICODE değilse, bu nesnelerin ANSI olması gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
