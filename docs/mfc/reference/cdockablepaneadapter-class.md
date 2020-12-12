---
description: 'Daha fazla bilgi edinin: CDockablePaneAdapter sınıfı'
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
ms.openlocfilehash: 0a46ef15d35194203d6e5c035555de0d80b63c72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185043"
---
# <a name="cdockablepaneadapter-class"></a>CDockablePaneAdapter sınıfı

İle türetilmiş bölmeler için yerleştirme desteği sağlar `CWnd` .

## <a name="syntax"></a>Syntax

```
class CDockablePaneAdapter : public CDockablePane
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDockablePaneAdapter:: GetWrappedWnd](#getwrappedwnd)|Sarmalanan pencereyi döndürür.|
|[CDockablePaneAdapter:: LoadState](#loadstate)|( [CDockablePane:: LoadState](cdockablepane-class.md#loadstate)geçersiz kılar)|
|[CDockablePaneAdapter:: Savemlak](#savestate)|( [CDockablePane:: sav,](cdockablepane-class.md)geçersiz kılar.)|
|[CDockablePaneAdapter:: SetWrappedWnd](#setwrappedwnd)||

## <a name="remarks"></a>Açıklamalar

Genellikle, [CMFCBaseTabCtrl:: AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab) veya [CMFCBaseTabCtrl:: InsertTab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab) yöntemlerini kullandığınızda Framework bu sınıfın nesnelerini başlatır.

Davranışı özelleştirmek istiyorsanız `CDockablePaneAdapter` , bundan yeni bir sınıf türetirsiniz ve çalışma zamanı sınıfı bilgilerini, [CMFCBaseTabCtrl:: SetDockingBarWrapperRTC](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc)kullanarak bir sekmeli pencereye ayarlamanız yeterlidir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)\
└ &nbsp; [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CWnd](../../mfc/reference/cwnd-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CBasePane](../../mfc/reference/cbasepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CPane](../../mfc/reference/cpane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CDockablePane](../../mfc/reference/cdockablepane-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxDockablePaneAdapter. h

## <a name="cdockablepaneadaptergetwrappedwnd"></a><a name="getwrappedwnd"></a> CDockablePaneAdapter:: GetWrappedWnd

Yerleştirilebilir bölmesi bağdaştırıcısı için temeldeki pencereyi döndürür.

```
virtual CWnd* GetWrappedWnd() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sarmalanan pencereye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Sarmalanan pencereye erişmek için bu işlevi kullanın.

## <a name="cdockablepaneadapterloadstate"></a><a name="loadstate"></a> CDockablePaneAdapter:: LoadState

Bölme durumunu kayıt defterinden yükler.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
'ndaki Profil adı.

*nDizin*<br/>
'ndaki Profil dizini.

*Uııd*<br/>
'ndaki Bölme KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockablepaneadaptersavestate"></a><a name="savestate"></a> CDockablePaneAdapter:: Savemlak

Bölmenin durumunu kayıt defterine kaydeder.

```
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT) -1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
'ndaki Profil adı.

*nDizin*<br/>
'ndaki Profil dizini (varsayılan olarak pencerenin Denetim KIMLIĞI olur).

*Uııd*<br/>
'ndaki Bölme KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cdockablepaneadaptersetwrappedwnd"></a><a name="setwrappedwnd"></a> CDockablePaneAdapter:: SetWrappedWnd

Yerleştirilebilir bölmesi bağdaştırıcısı için temeldeki pencereyi ayarlar.

```
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
'ndaki Bölme bağdaştırıcısının sarılacağı pencerenin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md)
