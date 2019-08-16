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
ms.openlocfilehash: e9ad7c363f2580200af20baeb0acd7a93c1f603b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502767"
---
# <a name="cpropexchange-class"></a>CPropExchange sınıfı

OLE Denetimleriniz için kalıcılık uygulamasını destekler.

## <a name="syntax"></a>Sözdizimi

```
class AFX_NOVTABLE CPropExchange
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CPropExchange:: ExchangeBlobProp](#exchangeblobprop)|İkili büyük nesne (BLOB) özelliğini değiş tokuş eder.|
|[CPropExchange:: ExchangeFontProp](#exchangefontprop)|Yazı tipi özelliğini değiş tokuş eder.|
|[CPropExchange:: ExchangePersistentProp](#exchangepersistentprop)|Denetim ve Dosya arasında bir özellik alışverişi yapın.|
|[CPropExchange:: ExchangeProp](#exchangeprop)|Herhangi bir yerleşik türün özelliklerini değiştirir.|
|[CPropExchange:: ExchangeVersion](#exchangeversion)|OLE denetiminin sürüm numarasını değiş tokuş eder.|
|[CPropExchange:: GetVersion](#getversion)|OLE denetiminin sürüm numarasını alır.|
|[CPropExchange:: IsAsynchronous](#isasynchronous)|Özellik değişimlerinin zaman uyumsuz olarak gerçekleştirilip yapılamayacağını belirler.|
|[CPropExchange:: ısyükleniyor](#isloading)|Özelliklerin denetime yüklenip yüklenmediğini veya sunucudan kaydedilip kaydedilmediğini gösterir.|

## <a name="remarks"></a>Açıklamalar

`CPropExchange`taban sınıfına sahip değildir.

Bir özellik değişiminin bağlamını ve yönünü belirler.

Kalıcılık, denetimin kendisi ve orta arasında, genellikle özellikleriyle temsil edilen, denetimin durum bilgilerinin alışverişinin kendisidir.

Framework, bir OLE denetimi özelliklerinin kalıcı `CPropExchange` depolama alanından yüklenebileceği veya kalıcı olarak depolanabileceği hakkında bildirim geldiğinde öğesinden türetilmiş bir nesne oluşturur.

Framework, `CPropExchange` `DoPropExchange` denetimin işlevine bu nesneye bir işaretçi geçirir. Denetiminiz için başlangıç dosyalarını oluşturmak üzere bir sihirbaz kullandıysanız, denetiminizin `DoPropExchange` işlevi çağırır. `COleControl::DoPropExchange` Temel sınıf sürüm, denetimin stok özelliklerini de değiş tokuş eder; türetilmiş sınıfınızın sürümünü, denetitiğiniz Exchange özelliklerine değiştirirsiniz.

`CPropExchange`bir denetimin özelliklerini seri hale getirmek veya bir denetimin yükleme veya oluşturma sırasında denetimin özelliklerini başlatmak için kullanılabilir. `ExchangeProp` Ve üyesi`ExchangeFontProp` işlevleri özellikleridepolayıp`CPropExchange` farklı medyalardan yükleyebilir.

Kullanma `CPropExchange`hakkında daha fazla bilgi için bkz [. MFC ActiveX denetimleri: Özellik sayfaları](../../mfc/mfc-activex-controls-property-pages.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CPropExchange`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxctl. h

##  <a name="exchangeblobprop"></a>CPropExchange:: ExchangeBlobProp

İkili büyük nesne (BLOB) verilerini depolayan bir özelliği seri hale getirir.

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
Özelliğin nerede depolandığını gösteren bir değişken işaretçisi (değişken genellikle sınıfınızın bir üyesidir).

*hBlobDefault*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Özelliğin değeri, uygun şekilde, *phBlob*tarafından başvurulan değişkene göre okunurdur veya yazılır. *HBlobDefault* belirtilmişse, özelliğin varsayılan değeri olarak kullanılır. Bu değer, herhangi bir nedenle denetimin serileştirilmesi başarısız olursa kullanılır.

, Ve `CArchivePropExchange::ExchangeBlobProp` işlevleri`CPropsetPropExchange::ExchangeBlobProp` bu saf sanal işlevi geçersiz kılar. `CResetPropExchange::ExchangeBlobProp`

##  <a name="exchangefontprop"></a>CPropExchange:: ExchangeFontProp

Bir depolama ortamı ve denetim arasında bir yazı tipi özelliği değiş tokuş eder.

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

*Yazý*<br/>
Yazı tipi özelliğini içeren bir [Cfontheski](../../mfc/reference/cfontholder-class.md) nesnesine başvuru.

*pFontDesc*<br/>
*Pfontdispambtıı* null olduğunda Font özelliğinin varsayılan durumunu başlatma değerlerini Içeren [fontdesc](/windows/win32/api/olectl/ns-olectl-fontdesc) yapısına yönelik bir işaretçi.

*Pfontdispambun*<br/>
Yazı tipi özelliğinin varsayılan `IFontDisp` durumunu başlatmak için kullanılacak yazı tipinin arabirimine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Yazı tipi özelliği ortamdan denetime yükleniyorsa, yazı tipinin özellikleri ortamdan alınır ve `CFontHolder` *yazı tipi* tarafından başvurulan nesne bunlar ile başlatılır. Yazı tipi özelliği depolanıyorsa, yazı tipi nesnesindeki Özellikler ortama yazılır.

, Ve `CArchivePropExchange::ExchangeFontProp` işlevleri`CPropsetPropExchange::ExchangeFontProp` bu saf sanal işlevi geçersiz kılar. `CResetPropExchange::ExchangeFontProp`

##  <a name="exchangepersistentprop"></a>CPropExchange:: ExchangePersistentProp

Denetim ve Dosya arasında bir özellik değiş tokuş eder.

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
Özelliğin `IUnknown` arabirimine bir işaretçi içeren bir değişken işaretçisi (Bu değişken, genellikle sınıfınızın bir üyesidir).

*'si*<br/>
Denetimin kullanacağı özelliğin arabirim KIMLIĞI.

*pUnkDefault*<br/>
Özellik için varsayılan değer.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Özellik dosyadan denetime yükleniyorsa, özelliği dosyasından oluşturulur ve başlatılır. Özellik depolanıyorsa, değeri dosyasına yazılır.

, Ve `CArchivePropExchange::ExchangePersistentProp` işlevleri`CPropsetPropExchange::ExchangePersistentProp` bu saf sanal işlevi geçersiz kılar. `CResetPropExchange::ExchangePersistentProp`

##  <a name="exchangeprop"></a>CPropExchange:: ExchangeProp

Bir depolama ortamı ve denetim arasında bir özellik değiş tokuş eder.

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
Değiştirilen özelliğin türünü belirten bir sembol. Olası değerler şunlardır:

|Sembol|Özellik türü|
|------------|-------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_BOOL|**BOOL**|
|VT_BSTR|`CString`|
|VT_CY|**LI**|
|VT_R4|**float**|
|VT_R8|**double**|

*pvProp*<br/>
Özelliğin değerine yönelik bir işaretçi.

*pvDefault*<br/>
Özellik için varsayılan değer işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Exchange başarılı olursa sıfır dışı; başarısız ise 0.

### <a name="remarks"></a>Açıklamalar

Özelliği ortamdan denetime yüklenemıyorsa, özelliğin değeri ortamdan alınır ve *pvProp*tarafından işaret edilen nesnede depolanır. Özellik ortamda depolanıyorsa, *pvProp* tarafından işaret edilen nesnenin değeri ortama yazılır.

, Ve `CArchivePropExchange::ExchangeProp` işlevleri`CPropsetPropExchange::ExchangeProp` bu saf sanal işlevi geçersiz kılar. `CResetPropExchange::ExchangeProp`

##  <a name="exchangeversion"></a>CPropExchange:: ExchangeVersion

Sürüm numarasının kalıcılığını işlemek için Framework tarafından çağırılır.

```
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,
    DWORD dwVersionDefault,
    BOOL bConvert);
```

### <a name="parameters"></a>Parametreler

*Dwversionyüklendi*<br/>
Yüklenmekte olan kalıcı verilerin sürüm numarasının depolanacağı bir değişkene başvuru.

*dwVersionDefault*<br/>
Denetimin geçerli sürüm numarası.

*bConvert*<br/>
Kalıcı verilerin geçerli sürüme mi dönüştürüleceğini yoksa aynı sürüme mi yüklendiğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

İşlev başarılı olursa sıfır dışı; 0 Aksi takdirde.

##  <a name="getversion"></a>CPropExchange:: GetVersion

Denetimin sürüm numarasını almak için bu işlevi çağırın.

```
DWORD GetVersion();
```

### <a name="return-value"></a>Dönüş Değeri

Denetimin sürüm numarası.

##  <a name="isasynchronous"></a>CPropExchange:: IsAsynchronous

Özellik değişimlerinin zaman uyumsuz olarak gerçekleştirilip yapılamayacağını belirler.

```
BOOL IsAsynchronous();
```

### <a name="return-value"></a>Dönüş Değeri

Özellikler zaman uyumsuz olarak alınıp eşitse TRUE, değilse FALSE döndürür.

##  <a name="isloading"></a>CPropExchange:: ısyükleniyor

Denetimin denetime yüklenip yüklenmediğini veya sunucudan kaydedilip kaydedilmediğini öğrenmek için bu işlevi çağırın.

```
BOOL IsLoading();
```

### <a name="return-value"></a>Dönüş Değeri

Özellikler yükleniyorsa sıfır dışı; Aksi takdirde 0.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleControl::DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)
