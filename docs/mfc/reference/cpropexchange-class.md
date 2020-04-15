---
title: CpropExchange Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CPropExchange
- AFXCTL/CPropExchange
- AFXCTL/CPropExchange::ExchangeBlobProp
- AFXCTL/CPropExchange::ExchangeFontProp
- AFXCTL/CPropExchange::ExchangePersistentProp
- AFXCTL/CPropExchange::ExchangeProp
- AFXCTL/CPropExchange::ExchangeVersion
- AFXCTL/CPropExchange::GetVersion
- AFXCTL/CPropExchange::IsAsynchronous
- AFXCTL/CPropExchange::IsLoading
helpviewer_keywords:
- CPropExchange [MFC], ExchangeBlobProp
- CPropExchange [MFC], ExchangeFontProp
- CPropExchange [MFC], ExchangePersistentProp
- CPropExchange [MFC], ExchangeProp
- CPropExchange [MFC], ExchangeVersion
- CPropExchange [MFC], GetVersion
- CPropExchange [MFC], IsAsynchronous
- CPropExchange [MFC], IsLoading
ms.assetid: ed872180-e770-4942-892a-92139d501fab
ms.openlocfilehash: 7818b15e502bb32640d6b9dbfe1a6e4927c70650
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363984"
---
# <a name="cpropexchange-class"></a>CpropExchange Sınıfı

OLE denetimleriniz için kalıcılığın uygulanmasını destekler.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CPropExchange
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CPropExchange::ExchangeBlobProp](#exchangeblobprop)|İkili büyük nesne (BLOB) özelliğini değiştirir.|
|[CpropExchange::ExchangeFontProp](#exchangefontprop)|Bir yazı tipi özelliğini değiştirir.|
|[CpropExchange::ExchangePersistentProp](#exchangepersistentprop)|Bir özelliği denetim ve dosya arasında değiştirir.|
|[CpropExchange::ExchangeProp](#exchangeprop)|Herhangi bir yerleşik türdeki özellikleri değiştirir.|
|[CpropExchange::ExchangeVersion](#exchangeversion)|OLE denetiminin sürüm numarasını değiştirir.|
|[CpropExchange::GetVersion](#getversion)|OLE denetiminin sürüm numarasını alır.|
|[CPropExchange::IsAsynchronous](#isasynchronous)|Özellik değişimlerinin eşzamanlı olarak yapIlip yapılmadığını belirler.|
|[CpropExchange::Isloading](#isloading)|Özelliklerin denetime yüklenip yüklenmediğini veya denetimden kaydedilip kaydedilemeyeceğini gösterir.|

## <a name="remarks"></a>Açıklamalar

`CPropExchange`taban sınıfa sahip değildir.

Bir mülk değişiminin bağlamını ve yönünü belirler.

Kalıcılık, denetimin genellikle özellikleriyle temsil edilen durum bilgilerinin, denetimin kendisi ile bir ortam arasında değişimidir.

Çerçeve, Bir OLE `CPropExchange` denetiminin özelliklerinin yüklenmesi veya kalıcı depolama alanına depolanması gerektiği bildirildiğinde türetilen bir nesne yi inşa eder.

Çerçeve, bu `CPropExchange` nesneye bir işaretçi `DoPropExchange` yi denetiminizin işlevine geçirir. Denetiminiz için başlangıç dosyalarını oluşturmak için bir sihirbaz `DoPropExchange` kullandıysanız, denetiminizin işlevi çağırır. `COleControl::DoPropExchange` Taban sınıf sürümü, denetimin stok özelliklerini değiştirir; denetiminize eklediğiniz özellikleri değiştirmek için türetilmiş sınıfınızın sürümünü değiştirirsiniz.

`CPropExchange`bir denetimin özelliklerini seri hale getirmek veya bir denetimin yükü veya oluşturulması üzerine bir denetimin özelliklerini başlatmak için kullanılabilir. Ve `ExchangeProp` `ExchangeFontProp` üye işlevleri `CPropExchange` özellikleri depolamak ve farklı medya bunları yüklemek edebiliyoruz.

Kullanma `CPropExchange`hakkında daha fazla bilgi için, makaleye bakın [MFC ActiveX Denetimleri: Özellik Sayfaları](../../mfc/mfc-activex-controls-property-pages.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CPropExchange`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxctl.h

## <a name="cpropexchangeexchangeblobprop"></a><a name="exchangeblobprop"></a>CPropExchange::ExchangeBlobProp

İkili büyük nesne (BLOB) verilerini depolayan bir özelliği seri hale getiren bir özellik.

```
virtual BOOL ExchangeBlobProp(
    LPCTSTR pszPropName,
    HGLOBAL* phBlob,
    HGLOBAL hBlobDefault = NULL) = 0;
```

### <a name="parameters"></a>Parametreler

*pszPropName*<br/>
Değiştirilen mülkün adı.

*phBlob*<br/>
Özelliğin depolandığı yeri gösteren bir değişkene işaretçi (değişken genellikle sınıfınızın bir üyesidir).

*hBlobVarsayılan*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, *phBlob*tarafından başvurulan değişkenden okunur veya yazıldığı gibi. *hBlobDefault* belirtilirse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirme başarısız olursa kullanılır.

`CArchivePropExchange::ExchangeBlobProp`İşlevler `CResetPropExchange::ExchangeBlobProp`, `CPropsetPropExchange::ExchangeBlobProp` ve bu saf sanal işlevi geçersiz kılar.

## <a name="cpropexchangeexchangefontprop"></a><a name="exchangefontprop"></a>CpropExchange::ExchangeFontProp

Bir depolama ortamı ile denetim arasında bir yazı tipi özelliği değişimi.

```
virtual BOOL ExchangeFontProp(
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC* pFontDesc,
    LPFONTDISP pFontDispAmbient) = 0;
```

### <a name="parameters"></a>Parametreler

*pszPropName*<br/>
Değiştirilen mülkün adı.

*Yazı tipi*<br/>
Yazı tipi özelliğini içeren bir [CFontHolder](../../mfc/reference/cfontholder-class.md) nesnesine başvuru.

*pFontDesc*<br/>
*pFontDispAmbient* NULL olduğunda yazı tipi özelliğinin varsayılan durumunu başlatmaya yönelik değerleri içeren bir [FONTDESC](/windows/win32/api/olectl/ns-olectl-fontdesc) yapısına işaretçi.

*pFontDispAmbient*<br/>
Yazı tipi `IFontDisp` özelliğinin varsayılan durumunu başlatmada kullanılacak bir yazı tipinin arabirimine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Yazı tipi özelliği ortamdan denetime yükleniyorsa, yazı tipinin özellikleri ortamdan `CFontHolder` alınır ve *yazı tipi* tarafından başvurulan nesne onlarla birlikte baş harfe çevrilir. Yazı tipi özelliği depolanıyorsa, yazı tipi nesnesindeki özellikler ortama yazılır.

`CArchivePropExchange::ExchangeFontProp`İşlevler `CResetPropExchange::ExchangeFontProp`, `CPropsetPropExchange::ExchangeFontProp` ve bu saf sanal işlevi geçersiz kılar.

## <a name="cpropexchangeexchangepersistentprop"></a><a name="exchangepersistentprop"></a>CpropExchange::ExchangePersistentProp

Denetim ve dosya arasında bir özellik alışverişi.

```
virtual BOOL ExchangePersistentProp(
    LPCTSTR pszPropName,
    LPUNKNOWN* ppUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault) = 0;
```

### <a name="parameters"></a>Parametreler

*pszPropName*<br/>
Değiştirilen mülkün adı.

*ppUnk*<br/>
Özelliğin `IUnknown` arabirimi için bir işaretçi içeren bir değişken için bir işaretçi (bu değişken genellikle sınıfının bir üyesidir).

*ııd*<br/>
Denetimin kullanacağı özellikteki arabirimin arabirim kimliği.

*pUnkVarsayılan*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özellik dosyadan denetime yükleniyorsa, özellik oluşturulur ve dosyadan parayla başolarak başolarak yüklenir. Özellik depolanıyorsa, değeri dosyaya yazılır.

`CArchivePropExchange::ExchangePersistentProp`İşlevler `CResetPropExchange::ExchangePersistentProp`, `CPropsetPropExchange::ExchangePersistentProp` ve bu saf sanal işlevi geçersiz kılar.

## <a name="cpropexchangeexchangeprop"></a><a name="exchangeprop"></a>CpropExchange::ExchangeProp

Bir depolama ortamı ile denetim arasında bir özellik değişimi.

```
virtual BOOL ExchangeProp(
    LPCTSTR pszPropName,
    VARTYPE vtProp,
    void* pvProp,
    const void* pvDefault = NULL) = 0 ;
```

### <a name="parameters"></a>Parametreler

*pszPropName*<br/>
Değiştirilen mülkün adı.

*vtProp*<br/>
Değiştirilen özelliğin türünü belirten bir sembol. Olası değerler şunlardır:

|Sembol|Özellik Türü|
|------------|-------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_BOOL|**Bool**|
|Vt_bstr|`CString`|
|Vt_cy|**CY**|
|VT_R4|**float**|
|VT_R8|**double**|

*pvProp*<br/>
Özelliğin değeriiçin bir işaretçi.

*pvVarsayılan*<br/>
Özellik için varsayılan değeri işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Değişim başarılı olsaydı sıfır olmayan; Başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özellik ortamdan denetime yükleniyorsa, özelliğin değeri ortamdan alınır ve *pvProp*tarafından işaret edilen nesnede depolanır. Özellik ortama depolanıyorsa, *pvProp* tarafından işaret edilen nesnenin değeri ortama yazılır.

`CArchivePropExchange::ExchangeProp`İşlevler `CResetPropExchange::ExchangeProp`, `CPropsetPropExchange::ExchangeProp` ve bu saf sanal işlevi geçersiz kılar.

## <a name="cpropexchangeexchangeversion"></a><a name="exchangeversion"></a>CpropExchange::ExchangeVersion

Bir sürüm numarasının kalıcılığını işlemek için çerçeve tarafından çağrılır.

```
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,
    DWORD dwVersionDefault,
    BOOL bConvert);
```

### <a name="parameters"></a>Parametreler

*dwVersionLoaded*<br/>
Yüklenen kalıcı verilerin sürüm numarasının depolandığı bir değişkene başvuru.

*dwVersionVarsayılan*<br/>
Denetimin geçerli sürüm numarası.

*bDönüştür*<br/>
Kalıcı verileri geçerli sürüme dönüştürüp dönüştürmeyecek lerini veya yüklenen sürümde tutup tutmayacağını gösterir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfırsız; 0 aksi takdirde.

## <a name="cpropexchangegetversion"></a><a name="getversion"></a>CpropExchange::GetVersion

Denetimin sürüm numarasını almak için bu işlevi arayın.

```
DWORD GetVersion();
```

### <a name="return-value"></a>Dönüş Değeri

Denetimin sürüm numarası.

## <a name="cpropexchangeisasynchronous"></a><a name="isasynchronous"></a>CPropExchange::IsAsynchronous

Özellik değişimlerinin eşzamanlı olarak yapIlip yapılmadığını belirler.

```
BOOL IsAsynchronous();
```

### <a name="return-value"></a>Dönüş Değeri

Özellikler eş senkronize olarak değiştirilirse DOĞRU döndürür, aksi takdirde FALSE.

## <a name="cpropexchangeisloading"></a><a name="isloading"></a>CpropExchange::Isloading

Özelliklerin denetime yüklenip yüklenmediğini veya denetimden kaydedilip kaydedilemediğini belirlemek için bu işlevi arayın.

```
BOOL IsLoading();
```

### <a name="return-value"></a>Dönüş Değeri

Özellikler yükleniyorsa sıfır olmayan; aksi takdirde 0.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleControl::DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)
