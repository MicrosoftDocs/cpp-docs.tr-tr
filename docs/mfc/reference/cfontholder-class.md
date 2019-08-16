---
title: Cfontheski sınıfı
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
ms.openlocfilehash: 04de8141469f82bdd1fbb6adc1bae94d6026324c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506441"
---
# <a name="cfontholder-class"></a>Cfontheski sınıfı

Hisse senedi yazı tipi özelliğini uygular ve bir Windows yazı tipi nesnesinin ve `IFont` arabiriminin işlevselliğini Kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class CFontHolder
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cfonthdaha eski:: Cfonthdaha eski](#cfontholder)|Bir `CFontHolder` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cfonthdaha eski:: GetDisplayString](#getdisplaystring)|Kapsayıcının özellik tarayıcısında görünen dizeyi alır.|
|[Cfonthdaha eski:: GetFontDispatch](#getfontdispatch)|Yazı tipinin `IDispatch` arabirimini döndürür.|
|[Cfonthdaha eski:: GetFontHandle](#getfonthandle)|Windows yazı tipine yönelik bir tanıtıcı döndürür.|
|[Cfontheski:: InitializeFont](#initializefont)|Bir `CFontHolder` nesnesi başlatır.|
|[Cfonthdaha eski:: Querytextölçümleri](#querytextmetrics)|İlgili yazı tipine ilişkin bilgileri alır.|
|[Cfonthdaha eski:: ReleaseFont](#releasefont)|`CFontHolder` Nesnesinin vearabirimlerinden`IFontNotification`bağlantısınıkeser. `IFont`|
|[Cfonthdaha eski:: Select](#select)|Bir cihaz bağlamında bir yazı tipi kaynağı seçer.|
|[Cfonthdaha eski:: SetFont](#setfont)|`CFontHolder` Nesnesini bir`IFont` arabirime bağlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Cfonthdaha eski:: m_pFont](#m_pfont)|`CFontHolder` Nesnenin arabirimineyönelikbirişaretçi.`IFont`|

## <a name="remarks"></a>Açıklamalar

`CFontHolder`taban sınıfına sahip değildir.

Denetiminizin özel yazı tipi özelliklerini uygulamak için bu sınıfı kullanın. Bu tür özellikler oluşturma hakkında bilgi için bkz [. ActiveX denetimleri: Yazı tiplerini](../../mfc/mfc-activex-controls-using-fonts.md)kullanma.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CFontHolder`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxctl. h

##  <a name="cfontholder"></a>Cfonthdaha eski:: Cfonthdaha eski

Bir `CFontHolder` nesnesi oluşturur.

```
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```

### <a name="parameters"></a>Parametreler

*pNotify*<br/>
Yazı tipinin `IPropertyNotifySink` arabirimine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Elde edilen nesneyi `InitializeFont` kullanmadan önce başlatmak için öğesini çağırmanız gerekir.

##  <a name="getdisplaystring"></a>Cfonthdaha eski:: GetDisplayString

Kapsayıcının özellik tarayıcısında görüntülenebilen bir dize alır.

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>Parametreler

*strValue*<br/>
Görüntüleme dizesini tutan [CString](../../atl-mfc-shared/reference/cstringt-class.md) başvurusu.

### <a name="return-value"></a>Dönüş Değeri

Dize başarıyla alınırsa sıfır dışı; Aksi takdirde 0.

##  <a name="getfontdispatch"></a>Cfonthdaha eski:: GetFontDispatch

Yazı tipinin gönderme arabirimine bir işaretçi almak için bu işlevi çağırın.

```
LPFONTDISP GetFontDispatch();
```

### <a name="return-value"></a>Dönüş Değeri

`CFontHolder` Nesnenin arabirimineyönelikbirişaretçi.`IFontDisp` Çağıran `GetFontDispatch` işlevin, ile işiniz bittiğinde bu arabirim `IUnknown::Release` İşaretçisinde çağrı gerektiğini unutmayın.

### <a name="remarks"></a>Açıklamalar

`InitializeFont` Çağrılmadan`GetFontDispatch`önce çağırın.

##  <a name="getfonthandle"></a>Cfonthdaha eski:: GetFontHandle

Windows yazı tipine yönelik bir tanıtıcı almak için bu işlevi çağırın.

```
HFONT GetFontHandle();

HFONT GetFontHandle(
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>Parametreler

*cyLogical*<br/>
Denetimin çizildiği dikdörtgenin, mantıksal birimlerde yükseklik.

*Cyhimetrik*<br/>
Denetimin MM_HIMETRIC birim cinsinden yüksekliği.

### <a name="return-value"></a>Dönüş Değeri

Yazı tipi nesnesine yönelik bir tanıtıcı; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

MM_HIMETRIC birimlerinde ifade edilen yazı tipi boyutu için, mantıksal birimlerde uygun görüntüleme boyutunu hesaplamak için *cyLogical* ve *cyhimetrlik* oranı kullanılır:

Görüntü boyutu = ( *cyLogical* / *cyhihmetrik*) X yazı tipi boyutu

Parametresi olmayan sürüm, ekran için doğru şekilde boyutlandırılmış bir yazı tipine yönelik bir tanıtıcı döndürür.

##  <a name="initializefont"></a>Cfontheski:: InitializeFont

Bir `CFontHolder` nesnesi başlatır.

```
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,
    LPDISPATCH pFontDispAmbient = NULL);
```

### <a name="parameters"></a>Parametreler

*pFontDesc*<br/>
Yazı tipinin özelliklerini belirten bir yazı tipi açıklama yapısına ( [fontdesc](/windows/win32/api/olectl/ns-olectl-fontdesc)) yönelik işaretçi.

*Pfontdispambun*<br/>
Kapsayıcının çevresel yazı tipi özelliğine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

*Pfontdispambköpek* null değilse, `CFontHolder` nesne kapsayıcının çevresel yazı tipi özelliği tarafından kullanılan `IFont` arabirimin kopyasına bağlanır.

*Pfontdispambköpek* null Ise, *pFontDesc* tarafından Işaret edilen ya da *pFontDesc* değeri null ise, varsayılan bir açıklamadan yeni bir yazı tipi nesnesi oluşturulur.

Bir `CFontHolder` nesne oluşturulduktan sonra bu işlevi çağırın.

##  <a name="m_pfont"></a>Cfonthdaha eski:: m_pFont

`CFontHolder` Nesnenin arabirimineyönelikbirişaretçi.`IFont`

```
LPFONT m_pFont;
```

##  <a name="querytextmetrics"></a>Cfonthdaha eski:: Querytextölçümleri

`CFontHolder` Nesnenin gösterdiği fiziksel yazı tipiyle ilgili bilgileri alır.

```
void QueryTextMetrics(LPTEXTMETRIC lptm);
```

### <a name="parameters"></a>Parametreler

*lptm*<br/>
Bilgileri alacak [Textmetric](/windows/win32/api/wingdi/ns-wingdi-textmetricw) yapısına yönelik bir işaretçi.

##  <a name="releasefont"></a>Cfonthdaha eski:: ReleaseFont

Bu işlev, `CFontHolder` nesnesinin `IFont` arabiriminden bağlantısını keser.

```
void ReleaseFont();
```

##  <a name="select"></a>Cfonthdaha eski:: Select

Denetimin yazı tipini belirtilen cihaz bağlamında seçmek için bu işlevi çağırın.

```
CFont* Select(
    CDC* pDC,
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
Yazı tipinin seçildiği cihaz bağlamı.

*cyLogical*<br/>
Denetimin çizildiği dikdörtgenin, mantıksal birimlerde yükseklik.

*Cyhimetrik*<br/>
Denetimin MM_HIMETRIC birim cinsinden yüksekliği.

### <a name="return-value"></a>Dönüş Değeri

Değiştirilmekte olan yazı tipine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

*CyLogical* ve *cyhimetra* parametreleri hakkında bir tartışma Için bkz. [GetFontHandle](#getfonthandle) .

##  <a name="setfont"></a>Cfonthdaha eski:: SetFont

Var olan tüm yazı tiplerini serbest bırakır `CFontHolder` ve nesneyi bir `IFont` arabirime bağlar.

```
void SetFont(LPFONT pNewFont);
```

### <a name="parameters"></a>Parametreler

*pNewFont*<br/>
Yeni `IFont` arabirime yönelik işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPropExchange Sınıfı](../../mfc/reference/cpropexchange-class.md)
