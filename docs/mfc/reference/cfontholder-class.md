---
title: CFontHolder sınıfı
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
ms.openlocfilehash: 623ce5da46716e3f9a562862fc0375fb8704bb21
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57297885"
---
# <a name="cfontholder-class"></a>CFontHolder sınıfı

Stok yazı tipi özelliğini uygular ve bir Windows yazı tipi nesnesinin işlevselliğini kapsüller ve `IFont` arabirimi.

## <a name="syntax"></a>Sözdizimi

```
class CFontHolder
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFontHolder::CFontHolder](#cfontholder)|Oluşturur bir `CFontHolder` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFontHolder::GetDisplayString](#getdisplaystring)|Bir kapsayıcının özelliği tarayıcıda görüntülenen dizeyi alır.|
|[CFontHolder::GetFontDispatch](#getfontdispatch)|Yazı tipinin döndürür `IDispatch` arabirimi.|
|[CFontHolder::GetFontHandle](#getfonthandle)|Bir Windows yazı tipi için bir tanıtıcı döndürür.|
|[CFontHolder::InitializeFont](#initializefont)|Başlatan bir `CFontHolder` nesne.|
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|İlgili yazı tipi için bilgileri alır.|
|[CFontHolder::ReleaseFont](#releasefont)|Keser `CFontHolder` nesnesinden `IFont` ve `IFontNotification` arabirimleri.|
|[CFontHolder::Select](#select)|Bir yazı tipi kaynak cihaz bağlamına seçer.|
|[CFontHolder::SetFont](#setfont)|Bağlanan `CFontHolder` nesnesini bir `IFont` arabirimi.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CFontHolder::m_pFont](#m_pfont)|Bir işaretçi `CFontHolder` nesnenin `IFont` arabirimi.|

## <a name="remarks"></a>Açıklamalar

`CFontHolder` bir temel sınıfa sahip değil.

Bu sınıf, özel yazı tipi özellikleri denetlemek için uygulamak için kullanın. Tür özellikleri oluşturma hakkında daha fazla bilgi için bkz [ActiveX denetimleri: Yazı tiplerini kullanma](../../mfc/mfc-activex-controls-using-fonts.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CFontHolder`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxctl.h

##  <a name="cfontholder"></a>  CFontHolder::CFontHolder

Oluşturur bir `CFontHolder` nesne.

```
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```

### <a name="parameters"></a>Parametreler

*pNotify*<br/>
Yazı tipinin işaretçisine `IPropertyNotifySink` arabirimi.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız `InitializeFont` kullanmadan önce elde edilen nesnenin başlatılamadı.

##  <a name="getdisplaystring"></a>  CFontHolder::GetDisplayString

Bir kapsayıcının özelliği tarayıcıda görüntülenen bir dize alır.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>Parametreler

*strValue*<br/>
Başvuru [CString](../../atl-mfc-shared/reference/cstringt-class.md) görüntü dizesini tutacak olmasıdır.

### <a name="return-value"></a>Dönüş Değeri

Dize başarıyla aldı olursa sıfır dışı; Aksi durumda 0.

##  <a name="getfontdispatch"></a>  CFontHolder::GetFontDispatch

Bir işaretçi yazıtipinin gönderme arabirimi almak için bu işlevi çağırın.

```
LPFONTDISP GetFontDispatch();
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi `CFontHolder` nesnenin `IFontDisp` arabirimi. İşlev çağrılarının Not `GetFontDispatch` çağırmalıdır `IUnknown::Release` üzerinde ile işiniz bittiğinde bu arabirim işaretçisi.

### <a name="remarks"></a>Açıklamalar

Çağrı `InitializeFont` çağırmadan önce `GetFontDispatch`.

##  <a name="getfonthandle"></a>  CFontHolder::GetFontHandle

Bir Windows yazı tipi için bir tanıtıcı almak için bu işlevi çağırın.

```
HFONT GetFontHandle();

HFONT GetFontHandle(
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>Parametreler

*cyLogical*<br/>
Mantıksal birimi, denetimin çizilen dikdörtgenin yüksekliği.

*cyHimetric*<br/>
MM_HIMETRIC birimi, denetimin yüksekliği.

### <a name="return-value"></a>Dönüş Değeri

Yazı tipi nesnesi için bir tanıtıcı; bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

Oranını *cyLogical* ve *cyHimetric* MM_HIMETRIC birimleri ifade fontun punto boyutu için mantıksal birimler cinsinden uygun görüntü boyutunu hesaplamak için kullanılır:

Görüntü boyutu = ( *cyLogical* / *cyHimetric*) X yazı tipi boyutu

Sürüm parametresi olmayan ekran için doğru boyutta bir yazı tipi için bir tanıtıcı döndürür.

##  <a name="initializefont"></a>  CFontHolder::InitializeFont

Başlatan bir `CFontHolder` nesne.

```
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,
    LPDISPATCH pFontDispAmbient = NULL);
```

### <a name="parameters"></a>Parametreler

*pFontDesc*<br/>
Bir yazı tipi açıklama yapıya yönelik işaretçi ( [FONTDESC](/windows/desktop/api/olectl/ns-olectl-tagfontdesc)) yazı tipinin özelliklerini belirtir.

*pFontDispAmbient*<br/>
Kapsayıcının ortam yazı tipi özelliğini işaretçisi.

### <a name="remarks"></a>Açıklamalar

Varsa *pFontDispAmbient* NULL değil `CFontHolder` nesne için bir kopyasını bağlı `IFont` kapsayıcının ortam yazı tipi özelliği tarafından kullanılan arabirim.

Varsa *pFontDispAmbient* NULL, yeni bir yazı nesnesine oluşturulduğu ya da işaret ettiği yazı tipi açıklamasından *pFontDesc* veya *pFontDesc* bir varsayılan NULL ise açıklaması.

Oluşturduktan sonra bu işlevi çağırın bir `CFontHolder` nesne.

##  <a name="m_pfont"></a>  CFontHolder::m_pFont

Bir işaretçi `CFontHolder` nesnenin `IFont` arabirimi.

```
LPFONT m_pFont;
```

##  <a name="querytextmetrics"></a>  CFontHolder::QueryTextMetrics

Tarafından temsil edilen fiziksel yazı tipi hakkında bilgi alır `CFontHolder` nesne.

```
void QueryTextMetrics(LPTEXTMETRIC lptm);
```

### <a name="parameters"></a>Parametreler

*lptm*<br/>
Bir işaretçi bir [TEXTMETRIC](/windows/desktop/api/wingdi/ns-wingdi-tagtextmetrica) bilgi alacak yapısı.

##  <a name="releasefont"></a>  CFontHolder::ReleaseFont

Bu işlev bağlantısı kesildiğinde `CFontHolder` nesnesinin kendi `IFont` arabirimi.

```
void ReleaseFont();
```

##  <a name="select"></a>  CFontHolder::Select

Belirtilen bir cihaz bağlamına denetiminizin yazı tipi seçmek için bu işlevi çağırın.

```
CFont* Select(
    CDC* pDC,
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
Cihaz bağlamı içine yazı seçilir.

*cyLogical*<br/>
Mantıksal birimi, denetimin çizilen dikdörtgenin yüksekliği.

*cyHimetric*<br/>
MM_HIMETRIC birimi, denetimin yüksekliği.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilmekte olan yazı tipi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bkz: [GetFontHandle](#getfonthandle) bir irdelemesi *cyLogical* ve *cyHimetric* parametreleri.

##  <a name="setfont"></a>  CFontHolder::SetFont

Mevcut bir yazı tipi serbest bırakır ve bağlanan `CFontHolder` nesnesini bir `IFont` arabirimi.

```
void SetFont(LPFONT pNewFont);
```

### <a name="parameters"></a>Parametreler

*pNewFont*<br/>
İşaretçi yeni `IFont` arabirimi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPropExchange Sınıfı](../../mfc/reference/cpropexchange-class.md)
