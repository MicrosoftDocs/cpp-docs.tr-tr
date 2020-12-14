---
description: 'Daha fazla bilgi edinin: CRecentDockSiteInfo Sınıfı'
title: CRecentDockSiteInfo Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CRecentDockSiteInfo
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::CleanUp
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentDefaultPaneDivider
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentDockedPercent
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentDockedRect
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentListOfPanes
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentPaneContainer
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::GetRecentTabContainer
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::Init
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::IsRecentLeftPane
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::SaveListOfRecentPanes
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::SetInfo
- AFXRECENTDOCKSITEINFO/CRecentDockSiteInfo::StoreDockInfo
helpviewer_keywords:
- CRecentDockSiteInfo [MFC], CleanUp
- CRecentDockSiteInfo [MFC], GetRecentDefaultPaneDivider
- CRecentDockSiteInfo [MFC], GetRecentDockedPercent
- CRecentDockSiteInfo [MFC], GetRecentDockedRect
- CRecentDockSiteInfo [MFC], GetRecentListOfPanes
- CRecentDockSiteInfo [MFC], GetRecentPaneContainer
- CRecentDockSiteInfo [MFC], GetRecentTabContainer
- CRecentDockSiteInfo [MFC], Init
- CRecentDockSiteInfo [MFC], IsRecentLeftPane
- CRecentDockSiteInfo [MFC], SaveListOfRecentPanes
- CRecentDockSiteInfo [MFC], SetInfo
- CRecentDockSiteInfo [MFC], StoreDockInfo
ms.assetid: 2dd14f95-d5a2-4461-a7a5-2c6c36a3a165
ms.openlocfilehash: e33ef48be2b091477200f15a31c194d845693399
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343103"
---
# <a name="crecentdocksiteinfo-class"></a>CRecentDockSiteInfo Sınıfı

`CRecentDockSiteInfo`Sınıfı, [CPane sınıfı](../../mfc/reference/cpane-class.md)için son durum bilgilerini depolayan bir yardımcı sınıftır.

## <a name="syntax"></a>Syntax

```
class CRecentDockSiteInfo : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CRecentDockSiteInfo::CRecentDockSiteInfo`|Varsayılan Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRecentDockSiteInfo:: CleanUp](#cleanup)||
|[CRecentDockSiteInfo:: GetRecentDefaultPaneDivider](#getrecentdefaultpanedivider)||
|[CRecentDockSiteInfo:: GetRecentDockedPercent](#getrecentdockedpercent)||
|[CRecentDockSiteInfo:: GetRecentDockedRect](#getrecentdockedrect)||
|[CRecentDockSiteInfo:: Getrecentlıfbölmeler](#getrecentlistofpanes)||
|[CRecentDockSiteInfo:: Getrecentbölmesi kapsayıcısı](#getrecentpanecontainer)||
|[CRecentDockSiteInfo:: GetRecentTabContainer](#getrecenttabcontainer)||
|[CRecentDockSiteInfo:: Init](#init)||
|[CRecentDockSiteInfo:: ısrecentleftpane](#isrecentleftpane)||
|[CRecentDockSiteInfo:: operator =](#operator_eq)||
|[CRecentDockSiteInfo:: Savelıfrecentbölmeler](#savelistofrecentpanes)||
|[CRecentDockSiteInfo:: SetInfo](#setinfo)||
|[CRecentDockSiteInfo:: Storedockınfo](#storedockinfo)||

## <a name="remarks"></a>Açıklamalar

`CRecentDockSiteInfo`Sınıfı bir veri yönetimi sınıfıdır. `CPane`Sabitlenmiş ve kayan arasında geçiş yaparken, bir öğesinin son durumunu izler. Bir Kullanıcı, kayan bir yerleştirilebilir bölmesine çift tıkladığında yerleştirilmiş hale gelir. Yerleşik bölmeye çift tıklamak, önceki konumuna, boyutuna ve durumuna geri döner. Benzer şekilde, bölme yeniden yerleştirildiğinde, önceki yerleştirme konumuna geri döner. Bu veri sınıfı, mümkün olan şeydir. Bu sınıfın üyeleri yerleşik bölme için durum bilgilerini depoladığından, sizin uygulamanız tarafından doğrudan değiştirilmemelidir.

Bir `CRecentDockSiteInfo` bölme her oluşturulduğunda bir nesne oluşturulur. Her `CPane` nesnenin, bu bilgileri depolamak Için [CPane:: m_recentDockInfo](../../mfc/reference/cpane-class.md#m_recentdockinfo)üye değişkeni vardır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CRecentDockSiteInfo](../../mfc/reference/crecentdocksiteinfo-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxrecentDockSiteInfo. h

## <a name="crecentdocksiteinfocleanup"></a><a name="cleanup"></a> CRecentDockSiteInfo:: CleanUp

```cpp
void CleanUp();
```

### <a name="remarks"></a>Açıklamalar

## <a name="crecentdocksiteinfocrecentdocksiteinfo"></a><a name="crecentdocksiteinfo"></a> CRecentDockSiteInfo:: CRecentDockSiteInfo

```
CRecentDockSiteInfo(CPane* pBar);
```

### <a name="parameters"></a>Parametreler

'ndaki *pBar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="crecentdocksiteinfogetrecentdefaultpanedivider"></a><a name="getrecentdefaultpanedivider"></a> CRecentDockSiteInfo:: GetRecentDefaultPaneDivider

```
CPaneDivider* GetRecentDefaultPaneDivider();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="crecentdocksiteinfogetrecentdockedpercent"></a><a name="getrecentdockedpercent"></a> CRecentDockSiteInfo:: GetRecentDockedPercent

```
int GetRecentDockedPercent(BOOL bForSlider);
```

### <a name="parameters"></a>Parametreler

'ndaki *Bforslider*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="crecentdocksiteinfogetrecentdockedrect"></a><a name="getrecentdockedrect"></a> CRecentDockSiteInfo:: GetRecentDockedRect

```
CRect& GetRecentDockedRect(BOOL bForSlider);
```

### <a name="parameters"></a>Parametreler

'ndaki *Bforslider*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="crecentdocksiteinfogetrecentlistofpanes"></a><a name="getrecentlistofpanes"></a> CRecentDockSiteInfo:: Getrecentlıfbölmeler

```
CList<HWND, HWND>& GetRecentListOfPanes(BOOL bForSlider);
```

### <a name="parameters"></a>Parametreler

'ndaki *Bforslider*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="crecentdocksiteinfogetrecentpanecontainer"></a><a name="getrecentpanecontainer"></a> CRecentDockSiteInfo:: Getrecentbölmesi kapsayıcısı

```
CPaneContainer* GetRecentPaneContainer(BOOL bForSlider);
```

### <a name="parameters"></a>Parametreler

'ndaki *Bforslider*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="crecentdocksiteinfogetrecenttabcontainer"></a><a name="getrecenttabcontainer"></a> CRecentDockSiteInfo:: GetRecentTabContainer

```
CPaneContainer* GetRecentTabContainer(BOOL bForSlider);
```

### <a name="parameters"></a>Parametreler

'ndaki *Bforslider*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="crecentdocksiteinfoinit"></a><a name="init"></a> CRecentDockSiteInfo:: Init

```cpp
void Init();
```

### <a name="remarks"></a>Açıklamalar

## <a name="crecentdocksiteinfoisrecentleftpane"></a><a name="isrecentleftpane"></a> CRecentDockSiteInfo:: ısrecentleftpane

```
BOOL IsRecentLeftPane(BOOL bForSlider);
```

### <a name="parameters"></a>Parametreler

'ndaki *Bforslider*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="crecentdocksiteinfooperator-"></a><a name="operator_eq"></a> CRecentDockSiteInfo:: operator =

```
CRecentDockSiteInfo& operator=(CRecentDockSiteInfo& src);
```

### <a name="parameters"></a>Parametreler

'ndaki *src*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="crecentdocksiteinfosavelistofrecentpanes"></a><a name="savelistofrecentpanes"></a> CRecentDockSiteInfo:: Savelıfrecentbölmeler

```cpp
void SaveListOfRecentPanes(CList<HWND,
    HWND>& lstOrg,
    BOOL bForSlider);
```

### <a name="parameters"></a>Parametreler

'ndaki *CList<HWND*<br/>
'ndaki *Lstorg*<br/>
'ndaki *Bforslider*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="crecentdocksiteinfosetinfo"></a><a name="setinfo"></a> CRecentDockSiteInfo:: SetInfo

```
virtual void SetInfo(
    BOOL bForSlider,
    CRecentDockSiteInfo& srcInfo);
```

### <a name="parameters"></a>Parametreler

'ndaki *Bforslider*<br/>
'ndaki *srcInfo*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="crecentdocksiteinfostoredockinfo"></a><a name="storedockinfo"></a> CRecentDockSiteInfo:: Storedockınfo

```
virtual void StoreDockInfo(
    CPaneContainer* pRecentContainer,
    CDockablePane* pTabbedBar = NULL);
```

### <a name="parameters"></a>Parametreler

'ndaki *ön kapsayıcı*<br/>
'ndaki *Ptabbedbar*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CDockSite sınıfı](../../mfc/reference/cdocksite-class.md)
