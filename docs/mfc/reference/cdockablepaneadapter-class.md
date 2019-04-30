---
title: CDockablePaneAdapter sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::GetWrappedWnd
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::LoadState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SaveState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SetWrappedWnd
helpviewer_keywords:
- CDockablePaneAdapter [MFC], GetWrappedWnd
- CDockablePaneAdapter [MFC], LoadState
- CDockablePaneAdapter [MFC], SaveState
- CDockablePaneAdapter [MFC], SetWrappedWnd
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
ms.openlocfilehash: 8f184bab564b4867138608b735c67b328e1a21cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391250"
---
# <a name="cdockablepaneadapter-class"></a>CDockablePaneAdapter sınıfı

İçin yerleştirme desteği sağlar `CWnd`-bölmeler.

## <a name="syntax"></a>Sözdizimi

```
class CDockablePaneAdapter : public CDockablePane
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDockablePaneAdapter::GetWrappedWnd](#getwrappedwnd)|Sarmalanan pencereyi döndürür.|
|[CDockablePaneAdapter::LoadState](#loadstate)|(Geçersiz kılmaları [CDockablePane::LoadState](cdockablepane-class.md#loadstate).)|
|[CDockablePaneAdapter::SaveState](#savestate)|(Geçersiz kılmaları [CDockablePane::SaveState](cdockablepane-class.md).)|
|[CDockablePaneAdapter::SetWrappedWnd](#setwrappedwnd)||

## <a name="remarks"></a>Açıklamalar

Genellikle, framework kullandığınızda bu sınıfın nesneleri başlatır [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) veya [CMFCBaseTabCtrl::InsertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) yöntemleri.

Özelleştirmek istiyorsanız `CDockablePaneAdapter` davranışı, yalnızca yeni bir sınıf türetmeniz ve çalışma zamanı sınıf bilgileri kullanarak sekmeli pencere ayarlamak [CMFCBaseTabCtrl::SetDockingBarWrapperRTC](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxDockablePaneAdapter.h

##  <a name="getwrappedwnd"></a>  CDockablePaneAdapter::GetWrappedWnd

Yerleştirilebilir bölmesinde bağdaştırıcısı için temel alınan pencereyi döndürür.

```
virtual CWnd* GetWrappedWnd() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sarmalanan penceresine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Sarmalanan penceresine erişmek için bu işlevi kullanın.

##  <a name="loadstate"></a>  CDockablePaneAdapter::LoadState

Kayıt defterinden bölmesinde durumunu yükler.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[in] Profil adı.

*nIndex*<br/>
[in] Profili dizini.

*uiID*<br/>
[in] Bölmesinde kimliği.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="savestate"></a>  CDockablePaneAdapter::SaveState

Kayıt defterine bölmesinde durumunu kaydeder.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[in] Profil adı.

*nIndex*<br/>
[in] Profili dizini (varsayılan pencere denetim kimliği olarak).

*uiID*<br/>
[in] Bölmesinde kimliği.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="setwrappedwnd"></a>  CDockablePaneAdapter::SetWrappedWnd

Alttaki pencerenin yerleştirilebilir bölmesinde bağdaştırıcı için ayarlar.

```
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
[in] Sarılacak bölmesinde bağdaştırıcısı penceresine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane Sınıfı](../../mfc/reference/cdockablepane-class.md)
