---
title: CPropExchange sınıfı
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
ms.openlocfilehash: 4210399e32c2bb39008afa75b787c19e3338a7d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372432"
---
# <a name="cpropexchange-class"></a>CPropExchange sınıfı

OLE denetimleriniz için sürekliliğin uygulanmasını destekler.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CPropExchange
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPropExchange::ExchangeBlobProp](#exchangeblobprop)|İkili büyük nesne (BLOB) özelliğini değiştirir.|
|[CPropExchange::ExchangeFontProp](#exchangefontprop)|Font özelliği birbiriyle değiştirir.|
|[CPropExchange::ExchangePersistentProp](#exchangepersistentprop)|Bir dosya ile Denetim arasındaki bir özellik birbiriyle değiştirir.|
|[CPropExchange::ExchangeProp](#exchangeprop)|Herhangi bir yerleşik tür özelliklerini değiştirir.|
|[CPropExchange::ExchangeVersion](#exchangeversion)|Bir OLE denetim sürüm numarasını değiştirir.|
|[CPropExchange::GetVersion](#getversion)|Bir OLE denetim sürüm numarasını alır.|
|[CPropExchange::IsAsynchronous](#isasynchronous)|Özellik değişimleri zaman uyumsuz olarak gerçekleştirilir, belirler.|
|[CPropExchange::IsLoading](#isloading)|Özellikleri gönderildiğini belirten denetimine atanan veya ondan kaydedildi.|

## <a name="remarks"></a>Açıklamalar

`CPropExchange` bir temel sınıfa sahip değil.

Bir özellik değişiminin yönünü ve bağlam oluşturur.

Kalıcılık, genellikle bir ortam ile Denetim arasındaki özellikleri tarafından temsil edilen denetim durumu bilgi alışverişi olur.

Framework türetilen bir nesne oluşturur `CPropExchange` bir OLE denetim özelliklerini yüklenmesini olduğunu ne zaman bildirim veya depolanan kalıcı depolama ortamı.

Çerçeve işaretçisi için geçirir `CPropExchange` denetiminizin nesnesine `DoPropExchange` işlevi. Denetim için Denetim başlangıç dosyaları oluşturmak için bir sihirbaz kullandıysanız `DoPropExchange` işlev çağrılarında `COleControl::DoPropExchange`. Temel sınıf sürüm denetim stok özelliklerini değiştirir; exchange özellikleri türetilmiş sınıfınızın sürüm denetiminize eklediğiniz değiştirin.

`CPropExchange` bir denetimin özelliklerini serileştirmek veya bir denetim oluşturma ve yükleme sırasında bir denetimin özelliklerini başlatmak için kullanılabilir. `ExchangeProp` Ve `ExchangeFontProp` üye işlevleri `CPropExchange` özelliklerini depolamak ve bunları farklı medyadan yükle.

Kullanma hakkında daha fazla bilgi için `CPropExchange`, makaleye göz atın [MFC ActiveX denetimleri: Özellik sayfaları](../../mfc/mfc-activex-controls-property-pages.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CPropExchange`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxctl.h

##  <a name="exchangeblobprop"></a>  CPropExchange::ExchangeBlobProp

İkili büyük nesne (BLOB) veri depolayan bir özellik serileştirir.

```
virtual BOOL ExchangeBlobProp(
    LPCTSTR pszPropName,
    HGLOBAL* phBlob,
    HGLOBAL hBlobDefault = NULL) = 0;
```

### <a name="parameters"></a>Parametreler

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*phBlob*<br/>
Özellik depolandığı işaret eden bir değişken işaretçisi (değişken, genellikle sınıfınıza üyesi).

*hBlobDefault*<br/>
Bir özellik için varsayılan değeri.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri okunan veya için uygun şekilde tarafından başvurulan değişken yazılan *phBlob*. Varsa *hBlobDefault* belirtilirse, bu kullanılacak özelliğin varsayılan değer olarak. Denetimin serileştirme herhangi bir nedenle başarısız olursa, bu değer kullanılır.

İşlevleri `CArchivePropExchange::ExchangeBlobProp`, `CResetPropExchange::ExchangeBlobProp`, ve `CPropsetPropExchange::ExchangeBlobProp` bu saf sanal işlevi geçersiz.

##  <a name="exchangefontprop"></a>  CPropExchange::ExchangeFontProp

Font özelliği bir depolama ortamına ile Denetim arasındaki birbiriyle değiştirir.

```
virtual BOOL ExchangeFontProp(
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC* pFontDesc,
    LPFONTDISP pFontDispAmbient) = 0;
```

### <a name="parameters"></a>Parametreler

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*Yazı tipi*<br/>
Bir başvuru bir [CFontHolder](../../mfc/reference/cfontholder-class.md) font özelliği içeren nesne.

*pFontDesc*<br/>
Bir işaretçi bir [FONTDESC](/windows/desktop/api/olectl/ns-olectl-tagfontdesc) font özelliğinin varsayılan durumu için değerleri içeren yapı olduğunda *pFontDispAmbient* null.

*pFontDispAmbient*<br/>
Bir işaretçi `IFontDisp` font özelliğinin varsayılan durum başlatmak için kullanılacak bir yazı tipi arabirimi.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Font özelliği denetime ortamdan yüklendiğinden, yazıtipinin özellikleri ortamından alınır ve `CFontHolder` tarafından başvurulan nesne *yazı tipi* ile başlatılır. Font özelliği depolanan özellikleri font nesnede Orta yazılır.

İşlevleri `CArchivePropExchange::ExchangeFontProp`, `CResetPropExchange::ExchangeFontProp`, ve `CPropsetPropExchange::ExchangeFontProp` bu saf sanal işlevi geçersiz.

##  <a name="exchangepersistentprop"></a>  CPropExchange::ExchangePersistentProp

Bir dosya ile Denetim arasındaki bir özellik birbiriyle değiştirir.

```
virtual BOOL ExchangePersistentProp(
    LPCTSTR pszPropName,
    LPUNKNOWN* ppUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault) = 0;
```

### <a name="parameters"></a>Parametreler

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*ppUnk*<br/>
Özelliğin bir işaretçi içeren bir değişken işaretçisi `IUnknown` arabirimi (Bu değişken, genellikle sınıfınıza üyesi).

*IID*<br/>
Denetimin kullanıp kullanmayacağını özelliği arabirimi arabirim kimliği.

*pUnkDefault*<br/>
Bir özellik için varsayılan değeri.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Denetime özellik dosyasından yüklenirken, özelliği oluşturulur ve dosyasından başlatıldı. Özellik depolanan, değeri dosyasına yazılır.

İşlevleri `CArchivePropExchange::ExchangePersistentProp`, `CResetPropExchange::ExchangePersistentProp`, ve `CPropsetPropExchange::ExchangePersistentProp` bu saf sanal işlevi geçersiz.

##  <a name="exchangeprop"></a>  CPropExchange::ExchangeProp

Bir özelliği bir depolama ortamına ile Denetim arasındaki birbiriyle değiştirir.

```
virtual BOOL ExchangeProp(
    LPCTSTR pszPropName,
    VARTYPE vtProp,
    void* pvProp,
    const void* pvDefault = NULL) = 0 ;
```

### <a name="parameters"></a>Parametreler

*pszPropName*<br/>
Değiştirilen özelliğin adı.

*vtProp*<br/>
Değiştirilen özelliğin türünü belirten bir simge. Olası değerler şunlardır:

|Sembol|Özellik türü|
|------------|-------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_BOOL|**BOOL**|
|VT_BSTR|`CString`|
|VT_CY|**CY**|
|VT_R4|**float**|
|VT_R8|**double**|

*pvProp*<br/>
Özelliğin değeri için bir işaretçi.

*pvDefault*<br/>
Varsayılan değer özelliği için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; işlem başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Denetime özellik ortamından yüklenirken, özelliğin değerini ortamından alındığında ve tarafından işaret edilen nesnede depolanan *pvProp*. Özelliği Orta depolanıyorsa, nesnenin değeri tarafından işaret edilen *pvProp* Orta yazılır.

İşlevleri `CArchivePropExchange::ExchangeProp`, `CResetPropExchange::ExchangeProp`, ve `CPropsetPropExchange::ExchangeProp` bu saf sanal işlevi geçersiz.

##  <a name="exchangeversion"></a>  CPropExchange::ExchangeVersion

Sürüm numarasının Kalıcılık işlemek için framework tarafından çağırılır.

```
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,
    DWORD dwVersionDefault,
    BOOL bConvert);
```

### <a name="parameters"></a>Parametreler

*dwVersionLoaded*<br/>
Yüklenmekte olan kalıcı veri sürüm numarasını depolanacağı bir değişken başvuru.

*dwVersionDefault*<br/>
Geçerli sürüm numarası denetimi.

*bConvert*<br/>
Geçerli sürüme kalıcı verileri dönüştürebilir veya yüklenen aynı sürümde tutmak görüntülenip görüntülenmeyeceğini gösterir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; Aksi durumda 0.

##  <a name="getversion"></a>  CPropExchange::GetVersion

Denetim sürüm numarasını almak için bu işlevi çağırın.

```
DWORD GetVersion();
```

### <a name="return-value"></a>Dönüş Değeri

Denetim sürüm numarası.

##  <a name="isasynchronous"></a>  CPropExchange::IsAsynchronous

Özellik değişimleri zaman uyumsuz olarak gerçekleştirilir, belirler.

```
BOOL IsAsynchronous();
```

### <a name="return-value"></a>Dönüş Değeri

Özellikleri ise TRUE döndürür, aksi takdirde FALSE zaman uyumsuz olarak değiş tokuş.

##  <a name="isloading"></a>  CPropExchange::IsLoading

Özellikler yükleniyor olup olmadığını belirlemek için bu işlevi çağırın denetime yüklendi ya da ondan kaydedildi.

```
BOOL IsLoading();
```

### <a name="return-value"></a>Dönüş Değeri

Özellikler yükleniyor olursa sıfır dışı; Aksi durumda 0.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleControl::DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)
