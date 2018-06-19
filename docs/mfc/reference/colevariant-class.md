---
title: COleVariant sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- COleVariant [MFC], COleVariant
- COleVariant [MFC], Attach
- COleVariant [MFC], ChangeType
- COleVariant [MFC], Clear
- COleVariant [MFC], Detach
- COleVariant [MFC], GetByteArrayFromVariantArray
- COleVariant [MFC], SetString
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b7f0da1f53bf2c6b0e216195be37746eab9abd1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378527"
---
# <a name="colevariant-class"></a>COleVariant sınıfı
Yalıtan [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) veri türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleVariant : public tagVARIANT  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleVariant::COleVariant](#colevariant)|Oluşturan bir `COleVariant` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleVariant::Attach](#attach)|Bağlayan bir **değişken** için bir `COleVariant`.|  
|[COleVariant::ChangeType](#changetype)|Bu değişken türünü değiştirir `COleVariant` nesnesi.|  
|[COleVariant::Clear](#clear)|Bu temizler `COleVariant` nesnesi.|  
|[COleVariant::Detach](#detach)|Ayırır bir **değişken** gelen bir `COleVariant` ve döndürür **değişken**.|  
|[COleVariant::GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|Bir bayt dizisi mevcut bir değişken dizisini alır.|  
|[COleVariant::SetString](#setstring)|Belirli bir tür, genellikle ANSI dizesini ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleVariant::operator LPCVARIANT](#operator_lpcvariant)|Dönüştüren bir `COleVariant` içine değeri bir `LPCVARIANT`.|  
|[COleVariant::operator LPVARIANT](#operator_lpvariant)|Dönüştüren bir `COleVariant` içine nesne bir `LPVARIANT`.|  
|[COleVariant::operator =](#operator_eq)|Kopya bir `COleVariant` değeri.|  
|[COleVariant::operator ==](#operator_eq_eq)|İki karşılaştırır `COleVariant` değerleri.|  
|[COleVariant::operator &lt; &lt;, &gt;&gt;](#operator_lt_lt__gt_gt)|Çıkış bir `COleVariant` değeri `CArchive` veya `CDumpContext` ve girdi bir `COleVariant` nesnesinin `CArchive`.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu veri türü OLE Otomasyon kullanılır. Özellikle, [DISPPARAMS](http://msdn.microsoft.com/en-us/a16e5a21-766e-4287-b039-13429aa78f8b) yapısı içeren bir dizi için bir işaretçi **değişken** yapıları. A **DISPPARAMS** yapısı parametrelerini iletmek için kullanılan [IDispatch::Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d).  
  
> [!NOTE]
>  Bu sınıfın türetildiği **değişken** yapısı. Bu, iletebilir anlamına gelir. bir `COleVariant` için çağıran bir parametreye bir **değişken** ve veri üyeleri **değişken** yapısı erişilebilir veri üyeleri olan `COleVariant`.  
  
 İki MFC sınıfları ilgili [COleCurrency](../../mfc/reference/colecurrency-class.md) ve [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) değişken veri türleri kapsülleyen **para birimi** ( `VT_CY`) ve **tarih** ( `VT_DATE`). `COleVariant` Sınıfı DAO sınıfları yaygın olarak kullanılır; Örneğin, bu sınıfın tipik kullanım için bu sınıfların bakın [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) ve [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Daha fazla bilgi için bkz: [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [para birimi](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e), [DISPPARAMS](http://msdn.microsoft.com/en-us/a16e5a21-766e-4287-b039-13429aa78f8b), ve [IDispatch::Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d) Windows SDK'sı giriş.  
  
 Daha fazla bilgi için `COleVariant` sınıfı ve kullanımını OLE Otomasyon "Geçirme parametreleri içinde OLE Otomasyon" makalesine bakın [Otomasyon](../../mfc/automation.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `tagVARIANT`  
  
 `COleVariant`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  
  
##  <a name="attach"></a>  COleVariant::Attach  
 Eklemek için bu işlevi çağırmak verilen [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) geçerli nesne `COleVariant` nesne.  
  
```  
void Attach(VARIANT& varSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 *varSrc*  
 Var olan **değişken** geçerli eklenecek nesne `COleVariant` nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev ayarlar [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) , *varSrc* için `VT_EMPTY`.  
  
 Daha fazla bilgi için bkz: [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) ve [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) Windows SDK'sı giriş.  
  
##  <a name="colevariant"></a>  COleVariant::COleVariant  
 Oluşturan bir `COleVariant` nesnesi.  
  
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
 *varSrc*  
 Var olan `COleVariant` veya **değişken** yeni içine kopyalanacak nesne `COleVariant` nesne.  
  
 `pSrc`  
 Bir işaretçi bir **değişken** yeni içine kopyalanacak nesne `COleVariant` nesne.  
  
 `lpszSrc`  
 Yeni içine kopyalanacak null ile sonlandırılmış bir dize `COleVariant` nesnesi.  
  
 `vtSrc`  
 `VARTYPE` Yeni `COleVariant` nesnesi.  
  
 `strSrc`  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) yeni içine kopyalanacak nesne `COleVariant` nesne.  
  
 `nSrc`, `lSrc`  
 Yeni içine kopyalanacak bir sayısal değer `COleVariant` nesnesi.  
  
 `vtSrc`  
 `VARTYPE` Yeni `COleVariant` nesnesi.  
  
 `curSrc`  
 A [COleCurrency](../../mfc/reference/colecurrency-class.md) yeni içine kopyalanacak nesne `COleVariant` nesne.  
  
 `fltSrc`, `dblSrc`  
 Yeni içine kopyalanacak bir sayısal değer `COleVariant` nesnesi.  
  
 `timeSrc`  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) yeni içine kopyalanacak nesne `COleVariant` nesne.  
  
 `arrSrc`  
 A [CLongBinary](../../mfc/reference/cbytearray-class.md) yeni içine kopyalanacak nesne `COleVariant` nesne.  
  
 `lbSrc`  
 A [CLongBinary](../../mfc/reference/clongbinary-class.md) yeni içine kopyalanacak nesne `COleVariant` nesne.  
  
 `pidl`  
 Bir işaretçi bir [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321) yeni içine kopyalanacak yapısı `COleVariant` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu oluşturucu Yeni Oluştur `COleVariant` nesneleri belirtilen değerle başlatılır. Bu oluşturucu her kısa bir açıklamasını izler.  
  
- **COleVariant ()** boş bir oluşturur `COleVariant` nesnesi `VT_EMPTY`.  
  
- **COleVariant (** *varSrc* **)** kopyalar varolan **değişken** veya `COleVariant` nesnesi. Değişken türü korunur.  
  
- **COleVariant (** `pSrc` **)** kopyalar varolan **değişken** veya `COleVariant` nesnesi. Değişken türü korunur.  
  
- **COleVariant (** `lpszSrc` **)** bir dize yeni nesnesine kopyalar `VT_BSTR` (UNICODE).  
  
- **COleVariant (** `lpszSrc` **,** `vtSrc` **)** bir dize yeni nesnesine kopyalar. Parametre `vtSrc` olmalıdır `VT_BSTR` (UNICODE) veya `VT_BSTRT` (ANSI).  
  
- **COleVariant (** `strSrc` **)** bir dize yeni nesnesine kopyalar **VT_BSTR** (UNICODE).  
  
- **COleVariant (** `nSrc` **)** 8 bit tam sayı yeni nesnesine kopyalar `VT_UI1`.  
  
- **COleVariant (** `nSrc` **,** `vtSrc` **)** bir 16 bit tamsayı (veya Boolean değeri) yeni nesnesine kopyalar. Parametre `vtSrc` olmalıdır `VT_I2` veya `VT_BOOL`.  
  
- **COleVariant (** `lSrc` **,** `vtSrc` **)** 32 bit tamsayı kopyalar (veya `SCODE` değeri) içine yeni bir nesne. Parametre `vtSrc` olmalıdır `VT_I4`, `VT_ERROR`, veya `VT_BOOL`.  
  
- **COleVariant (** `curSrc` **)** kopya bir **COleCurrency** yeni nesnesine değer `VT_CY`.  
  
- **COleVariant (** `fltSrc` **)** 32 bit kayan nokta değeri yeni nesnesine kopyalar `VT_R4`.  
  
- **COleVariant (** `dblSrc` **)** 64-bit kayan nokta değeri yeni nesnesine kopyalar `VT_R8`.  
  
- **COleVariant (** `timeSrc` **)** kopya bir `COleDateTime` yeni nesnesine değer `VT_DATE`.  
  
- **COleVariant (** `arrSrc` **)** kopya bir `CByteArray` yeni nesne nesnesine `VT_EMPTY`.  
  
- **COleVariant (** `lbSrc` **)** kopya bir `CLongBinary` yeni nesne nesnesine `VT_EMPTY`.  
  
 Daha fazla bilgi için `SCODE`, bkz: [COM hata kodları yapısı](http://msdn.microsoft.com/library/windows/desktop/ms690088) Windows SDK'sındaki.  
  
##  <a name="changetype"></a>  COleVariant::ChangeType  
 Bu değişken değeri türüne dönüştürür `COleVariant` nesnesi.  
  
```  
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `vartype`  
 [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) bu `COleVariant` nesnesi.  
  
 `pSrc`  
 Bir işaretçi [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) dönüştürülecek nesne. Bu değer ise **NULL**, bu `COleVariant` nesnesi, dönüştürme için kaynak olarak kullanılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4), ve [VariantChangeType](http://msdn.microsoft.com/en-us/48a51e32-95d7-4eeb-8106-f5043ffa2fd1) Windows SDK'sı giriş.  
  
##  <a name="clear"></a>  COleVariant::Clear  
 Temizler **değişken**.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu ayarlar **VARTYPE** bu nesne için `VT_EMPTY`. `COleVariant` Yıkıcı bu işlevi çağırır.  
  
 Daha fazla bilgi için bkz: `VARIANT`, `VARTYPE`, ve `VariantClear` Windows SDK'sı giriş.  
  
##  <a name="detach"></a>  COleVariant::Detach  
 Arka plandaki ayırır [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) bu nesneden `COleVariant` nesnesi.  
  
```  
VARIANT Detach();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev ayarlar [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) bu `COleVariant` nesnesine `VT_EMPTY`.  
  
> [!NOTE]
>  Çağırdıktan sonra **ayırma**, onu çağrı yapanın sorumluluğundadır **VariantClear** elde edilen üzerinde **değişken** yapısı.  
  
 Daha fazla bilgi için bkz: [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4), ve [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835) Windows SDK'sı giriş.  
  
##  <a name="getbytearrayfromvariantarray"></a>  COleVariant::GetByteArrayFromVariantArray  
 Bir bayt dizisi mevcut bir değişken dizisini alır.  
  
```  
void GetByteArrayFromVariantArray(CByteArray& bytes);
```  
  
### <a name="parameters"></a>Parametreler  
 `bytes`  
 Var olan bir başvuru [CLongBinary](../../mfc/reference/cbytearray-class.md) nesnesi.  
  
##  <a name="operator_lpcvariant"></a>  COleVariant::operator LPCVARIANT  
 Bu atama işleci döndüren bir `VARIANT` değeri öğesinden kopyalanır yapısı `COleVariant` nesnesi.  
  
```  
operator LPCVARIANT() const; 
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="operator_lpvariant"></a>  COleVariant::operator LPVARIANT  
 Arka plandaki erişmek için bu atama işleci çağrısı `VARIANT` yapısı bu `COleVariant` nesnesi.  
  
```  
operator LPVARIANT();
```   
  
### <a name="remarks"></a>Açıklamalar  
  
> [!CAUTION]
>  Değer değiştirme **değişken** bu işlev tarafından döndürülen işaretçi tarafından erişilen yapısı, bu değeri değiştirir `COleVariant` nesnesi.  
  
##  <a name="operator_eq"></a>  COleVariant::operator =  
 Bu aşırı yüklenmiş atama işleçleri kaynak değeri bu kopyalamak `COleVariant` nesnesi.  
  
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
 Her işleç kısa bir açıklamasını aşağıdaki gibidir:  
  
- **işleç = (** *varSrc ***)** kopyalar varolan **değişken** veya `COleVariant` bu nesne nesnesine.  
  
- **işleç = (** `pSrc` **)** kopya **değişken** tarafından erişilen nesne `pSrc` bu nesne içinde.  
  
- **işleç = (** `lpszSrc` **)** null sonlandırılmış bir dize bu nesnesine kopyalar ve ayarlar **VARTYPE** için `VT_BSTR`.  
  
- **işleç = (** `strSrc` **)** kopya bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) bu nesne ve ayarlar nesnesine **VARTYPE** için `VT_BSTR`.  
  
- **işleç = (** `nSrc` **)** bir 8 veya 16 bit tamsayı değeri bu nesnesine kopyalar. Varsa `nSrc` bir 8 bit değer **VARTYPE** bu ayarlamak `VT_UI1`. Varsa `nSrc` bir 16 bit değerdir ve **VARTYPE** bu `VT_BOOL`Tutuluyor; Aksi takdirde, ayarlanır `VT_I2`.  
  
- **işleç = (** `lSrc` **)** bir 32 bit tamsayı değeri bu nesnesine kopyalar. Varsa **VARTYPE** bu `VT_ERROR`Tutuluyor; Aksi takdirde, ayarlanır `VT_I4`.  
  
- **işleç = (** `curSrc` **)** kopya bir [COleCurrency](../../mfc/reference/colecurrency-class.md) bu nesne ve ayarlar nesnesine **VARTYPE** için `VT_CY`.  
  
- **işleç = (** `fltSrc` **)** 32 bit kayan nokta değeri bu nesnesine kopyalar ve ayarlar **VARTYPE** için `VT_R4`.  
  
- **işleç = (** `dblSrc` **)** 64-bit kayan nokta değeri bu nesnesine kopyalar ve ayarlar **VARTYPE** için `VT_R8`.  
  
- **işleç = (** `dateSrc` **)** kopya bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) bu nesne ve ayarlar nesnesine **VARTYPE** için `VT_DATE`.  
  
- **işleç = (** `arrSrc` **)** kopya bir [CLongBinary](../../mfc/reference/cbytearray-class.md) bu nesnesine `COleVariant` nesnesi.  
  
- **işleç = (** `lbSrc` **)** kopya bir [CLongBinary](../../mfc/reference/clongbinary-class.md) bu nesnesine `COleVariant` nesnesi.  
  
 Daha fazla bilgi için bkz: [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) ve [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) Windows SDK'sı giriş.  
  
##  <a name="operator_eq_eq"></a>  COleVariant::operator ==  
 Bu işleç iki değişken değerlerini karşılaştırır ve eşit olup olmadıkları sıfır olmayan döndürür; Aksi takdirde 0.  
  
```  
BOOL operator==(const VARIANT& varSrc) const; 
BOOL operator==(LPCVARIANT pSrc) const;
```  
  
##  <a name="operator_lt_lt__gt_gt"></a>  COleVariant::operator &lt; &lt;, &gt;&gt;  
 Çıkış bir `COleVariant` değeri `CArchive` veya **CdumpContext** ve girdi bir `COleVariant` nesnesinin `CArchive`.  
  
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
 `COleVariant` Ekleme ( **< \<**) işleci tanılama dökme ve arşive depolama destekler. Ayıklama ( **>>**) işleci bir arşiv yüklenmesini destekler.  
  
##  <a name="setstring"></a>  COleVariant::SetString  
 Dize için belirli bir tür ayarlar.  
  
```  
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszSrc`  
 Yeni içine kopyalanacak null ile sonlandırılmış bir dize `COleVariant` nesnesi.  
  
 *VtSrc*  
 **VARTYPE** yeni `COleVariant` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametre `vtSrc` olmalıdır `VT_BSTR` (UNICODE) veya `VT_BSTRT` (ANSI). `SetString` dizeler için varsayılan itibaren ANSI olarak ayarlamak için genellikle kullanılan [COleVariant::COleVariant](#colevariant) bir dize veya dize işaretçi parametresi ve Hayır Oluşturucusu **VARTYPE** Unicode.  
  
 DAO kayıt kümesinde bir UNICODE olmayan yapı dizeleri ANSI olmasını bekler. Bu nedenle, DAO için işlevleri kullanan `COleVariant` nesneleri, UNICODE kayıt kümesi oluşturuyorsanız değil, kullanmalıdır **COleVariant::COleVariant (** `lpszSrc` **,** `vtSrc` **)**  Oluşturucusu ile form `vtSrc` kümesine `VT_BSTRT` (ANSI) veya kullanın `SetString` ile `vtSrc` kümesine `VT_BSTRT` ANSI dizelerini yapma. Örneğin, `CDaoRecordset` işlevleri [CDaoRecordset::Seek](../../mfc/reference/cdaorecordset-class.md#seek) ve [CDaoRecordset::SetFieldValue](../../mfc/reference/cdaorecordset-class.md#setfieldvalue) kullanmak `COleVariant` parametre olarak nesneleri. DAO kayıt kümesi UNICODE değilse, bu nesnelerin ANSI olması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



