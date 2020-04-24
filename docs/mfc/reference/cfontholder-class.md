---
title: Cfontholder Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CFontHolder
- AFXCTL/CFontHolder
- AFXCTL/CFontHolder::CFontHolder
- AFXCTL/CFontHolder::GetDisplayString
- AFXCTL/CFontHolder::GetFontDispatch
- AFXCTL/CFontHolder::GetFontHandle
- AFXCTL/CFontHolder::InitializeFont
- AFXCTL/CFontHolder::QueryTextMetrics
- AFXCTL/CFontHolder::ReleaseFont
- AFXCTL/CFontHolder::Select
- AFXCTL/CFontHolder::SetFont
- AFXCTL/CFontHolder::m_pFont
helpviewer_keywords:
- CFontHolder [MFC], CFontHolder
- CFontHolder [MFC], GetDisplayString
- CFontHolder [MFC], GetFontDispatch
- CFontHolder [MFC], GetFontHandle
- CFontHolder [MFC], InitializeFont
- CFontHolder [MFC], QueryTextMetrics
- CFontHolder [MFC], ReleaseFont
- CFontHolder [MFC], Select
- CFontHolder [MFC], SetFont
- CFontHolder [MFC], m_pFont
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
ms.openlocfilehash: 36fbebc39101c5534bd52d4f79fee5286487a6e0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754989"
---
# <a name="cfontholder-class"></a>Cfontholder Sınıfı

Stok Font özelliğini uygular ve Windows yazı tipi nesnesinin ve `IFont` arabirimin işlevselliğini kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CFontHolder
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CFontHolder::CFontholder](#cfontholder)|Bir `CFontHolder` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFontHolder::GetDisplayString](#getdisplaystring)|Kapsayıcının özellik tarayıcısında görüntülenen dizeyi alır.|
|[CFontHolder::GetFontDispatch](#getfontdispatch)|Yazı tipinin `IDispatch` arabirimini döndürür.|
|[CFontHolder::GetFontHandle](#getfonthandle)|Bir tanıtıcıyı Windows yazı tipine döndürür.|
|[CFontHolder::InitializeFont](#initializefont)|Bir `CFontHolder` nesneyi başharfe alar.|
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|İlgili yazı tipi için bilgi alır.|
|[CFontHolder::ReleaseFont](#releasefont)|Nesneyi `CFontHolder` `IFont` ve `IFontNotification` arabirimlerini keser.|
|[CFontHolder::Seç](#select)|Bir yazı tipi kaynağını aygıt bağlamına seçer.|
|[CFontHolder::SetFont](#setfont)|Nesneyi `CFontHolder` bir `IFont` arabirime bağlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CFontHolder::m_pFont](#m_pfont)|Nesnenin `CFontHolder` `IFont` arabirimine işaretçi.|

## <a name="remarks"></a>Açıklamalar

`CFontHolder`taban sınıfa sahip değildir.

Denetiminiz için özel yazı tipi özelliklerini uygulamak için bu sınıfı kullanın. Bu tür özellikleri oluşturma hakkında daha fazla bilgi için [ActiveX Denetimleri makalesine bakın: Yazı Tiplerini Kullanma.](../../mfc/mfc-activex-controls-using-fonts.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CFontHolder`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxctl.h

## <a name="cfontholdercfontholder"></a><a name="cfontholder"></a>CFontHolder::CFontholder

Bir `CFontHolder` nesne inşa eder.

```
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```

### <a name="parameters"></a>Parametreler

*pNotify*<br/>
Yazı tipinin `IPropertyNotifySink` arabirimini işaretçi.

### <a name="remarks"></a>Açıklamalar

Kullanmadan `InitializeFont` önce ortaya çıkan nesneyi başlatmayı aramalısınız.

## <a name="cfontholdergetdisplaystring"></a><a name="getdisplaystring"></a>CFontHolder::GetDisplayString

Kapsayıcının özellik tarayıcısında görüntülenebilen bir dize alır.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>Parametreler

*strValue*<br/>
Ekran dizesini tutmak için [CString'e](../../atl-mfc-shared/reference/cstringt-class.md) başvuru.

### <a name="return-value"></a>Dönüş Değeri

Dize başarıyla alınırsa sıfırsız; aksi takdirde 0.

## <a name="cfontholdergetfontdispatch"></a><a name="getfontdispatch"></a>CFontHolder::GetFontDispatch

Yazı tipinin gönderme arabirimine bir işaretçi almak için bu işlevi arayın.

```
LPFONTDISP GetFontDispatch();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin `CFontHolder` `IFontDisp` arabirimine işaretçi. Çağıran `GetFontDispatch` işlevin bu arabirim işaretçisini araması gerektiğini `IUnknown::Release` unutmayın.

### <a name="remarks"></a>Açıklamalar

Aramadan `GetFontDispatch`önce arayın. `InitializeFont`

## <a name="cfontholdergetfonthandle"></a><a name="getfonthandle"></a>CFontHolder::GetFontHandle

Bir Windows yazı tipine tanıtıcı almak için bu işlevi arayın.

```
HFONT GetFontHandle();

HFONT GetFontHandle(
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>Parametreler

*cyLogical*<br/>
Yükseklik, mantıksal birimler, denetim çizilir dikdörtgen.

*cyHimetric*<br/>
Yükseklik, MM_HIMETRIC ünitelerde, kontrolün.

### <a name="return-value"></a>Dönüş Değeri

Yazı tipi nesnesine bir tutamaç; aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

*SIMetrik* ve *sihimetrik* oranı, MM_HIMETRIC birimlerde ifade edilen yazı tipinin nokta boyutu için mantıksal birimlerde uygun görüntü boyutunu hesaplamak için kullanılır:

Ekran boyutu = ( *cyLogical* / *cyHimetric*) X yazı tipi boyutu

Parametreleri olmayan sürüm, ekran için doğru boyutlandırılmış bir yazı tipine bir tutamacı döndürür.

## <a name="cfontholderinitializefont"></a><a name="initializefont"></a>CFontHolder::InitializeFont

Bir `CFontHolder` nesneyi başharfe alar.

```cpp
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,
    LPDISPATCH pFontDispAmbient = NULL);
```

### <a name="parameters"></a>Parametreler

*pFontDesc*<br/>
Yazı tipinin özelliklerini belirten bir yazı tipi açıklama yapısı [(FONTDESC)](/windows/win32/api/olectl/ns-olectl-fontdesc)işaretçisi.

*pFontDispAmbient*<br/>
Kapsayıcının ortam Yazı Tipi özelliğini işaretleyin.

### <a name="remarks"></a>Açıklamalar

*pFontDispAmbient* NULL değilse, `CFontHolder` nesne kapsayıcının `IFont` ortam Font özelliği tarafından kullanılan arabirimin bir klonuna bağlanır.

*pFontDispAmbient* NULL ise, *pFontDesc* tarafından işaret edilen yazı tipi açıklamasından veya *pFontDesc* NULL ise varsayılan bir açıklamadan yeni bir Font nesnesi oluşturulur.

Bir `CFontHolder` nesne yaptıktan sonra bu işlevi çağırın.

## <a name="cfontholderm_pfont"></a><a name="m_pfont"></a>CFontHolder::m_pFont

Nesnenin `CFontHolder` `IFont` arabirimine işaretçi.

```
LPFONT m_pFont;
```

## <a name="cfontholderquerytextmetrics"></a><a name="querytextmetrics"></a>CFontHolder::QueryTextMetrics

Nesne tarafından temsil edilen fiziksel yazı `CFontHolder` tipindeki bilgileri alır.

```cpp
void QueryTextMetrics(LPTEXTMETRIC lptm);
```

### <a name="parameters"></a>Parametreler

*lptm*<br/>
Bilgileri alacak [textmetric](/windows/win32/api/wingdi/ns-wingdi-textmetricw) yapısına işaretçi.

## <a name="cfontholderreleasefont"></a><a name="releasefont"></a>CFontHolder::ReleaseFont

Bu işlev, `CFontHolder` nesneyi `IFont` arabiriminden keser.

```cpp
void ReleaseFont();
```

## <a name="cfontholderselect"></a><a name="select"></a>CFontHolder::Seç

Denetiminizin yazı tipini belirtilen aygıt bağlamına seçmek için bu işlevi arayın.

```
CFont* Select(
    CDC* pDC,
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
Yazı tipinin seçildiği aygıt bağlamı.

*cyLogical*<br/>
Yükseklik, mantıksal birimler, denetim çizilir dikdörtgen.

*cyHimetric*<br/>
Yükseklik, MM_HIMETRIC ünitelerde, kontrolün.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilen yazı tipiiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

*CyLogical* ve *cyHimetric* parametrelerinin tartışılması için [GetFontHandle'a](#getfonthandle) bakın.

## <a name="cfontholdersetfont"></a><a name="setfont"></a>CFontHolder::SetFont

Varolan herhangi bir yazı `CFontHolder` tipini `IFont` serbest bırakır ve nesneyi bir arabirime bağlar.

```cpp
void SetFont(LPFONT pNewFont);
```

### <a name="parameters"></a>Parametreler

*pNewFont*<br/>
Yeni `IFont` arabirimi işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CpropExchange Sınıfı](../../mfc/reference/cpropexchange-class.md)
