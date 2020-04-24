---
title: CMFCColorPopupMenü Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CreateTearOffBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::GetMenuBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::SetPropList
helpviewer_keywords:
- CMFCColorPopupMenu [MFC], CMFCColorPopupMenu
- CMFCColorPopupMenu [MFC], CreateTearOffBar
- CMFCColorPopupMenu [MFC], GetMenuBar
- CMFCColorPopupMenu [MFC], SetPropList
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
ms.openlocfilehash: 901a44c8f5fdecd1b277ebdecc995722a3afe9a3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752499"
---
# <a name="cmfccolorpopupmenu-class"></a>CMFCColorPopupMenü Sınıfı

Kullanıcıların belge veya uygulamada renkleri seçmek için kullandıkları açılır menüyü temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CMFCColorPopupMenu : public CMFCPopupMenu
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Adı|Açıklama|
|[CMFCColorPopUpMenü::CMFCColorPopupMenü](#cmfccolorpopupmenu)|Bir `CMFCColorPopupMenu` nesne inşa eder.|
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Adı|Açıklama|
|[CMFCColorPopupMenu::CreateTearOffBar](#createtearoffbar)|Sabitlenebilir bir yırtılma renk çubuğu oluşturur. [(CMFCPopUpMenu geçersiz kılar::CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar).)|
|[CMFCColorPopupMenü::GetMenuBar](#getmenubar)|Açılır menüye katıştırılmış [CMFCPopUpMenuBar'ı](../../mfc/reference/cmfcpopupmenubar-class.md) döndürür. [(CMFCPopUpMenu geçersiz kılar::GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar).)|
|`CMFCColorPopupMenu::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCColorPopUpMenu::SetPropList](#setproplist)|Katıştınesnenin `CMFCColorBar` özellik ızgara denetim nesnesini ayarlar.|

### <a name="data-members"></a>Veri Üyeleri

|||
|-|-|
|Adı|Açıklama|
|`m_bEnabledInCustomizeMode`|Renk çubuğunu gösterip göstermeyeceğini belirleyen boolean değeri.|
|`m_wndColorBar`|Renk `CMFCColorBar` seçimi sağlayan nesne.|

### <a name="remarks"></a>Açıklamalar

Bu sınıf, `CMFCPopupMenu` sınıfın açılır menü işlevini devralır ve `CMFCColorBar` renk seçimi sağlayan bir nesneyi yönetir. Araç çubuğu çerçevesi özelleştirme modunda yken `m_bEnabledInCustomizeMode` ve üye FALSE olarak ayarlandığında, renk çubuğu nesnesi gösterilmez. Özelleştirme modu hakkında daha fazla bilgi için [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)

Hakkında `CMFCColorBar`daha fazla bilgi için [CMFCColorBar Sınıfı'na](../../mfc/reference/cmfccolorbar-class.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[Cmfcpopupmenu](../../mfc/reference/cmfcpopupmenu-class.md)

[CMFCColorPopupMenü](../../mfc/reference/cmfccolorpopupmenu-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcolorpopupmenu.h

## <a name="cmfccolorpopupmenucmfccolorpopupmenu"></a><a name="cmfccolorpopupmenu"></a>CMFCColorPopUpMenü::CMFCColorPopupMenü

Bir `CMFCColorPopupMenu` nesne inşa eder.

```
CMFCColorPopupMenu(
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    int nHorzDockRows,
    int nVertDockColumns,
    COLORREF colorAutomatic,
    UINT uiCommandID,
    BOOL bStdColorDlg = FALSE);

CMFCColorPopupMenu(
    CMFCColorButton* pParentBtn,
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic);

CMFCColorPopupMenu(
    CMFCRibbonColorButton* pParentBtn,
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
[içinde] Çerçevenin açılır menüde görüntülenebilen bir dizi renk.

*color*<br/>
[içinde] Varsayılan seçili renk.

*lpszAutoColor*<br/>
[içinde] *Otomatik* (varsayılan) renk düğmesinin metin etiketi veya NULL.

Otomatik düğme için standart etiket **Otomatiktir.**

*lpszOtherColor*<br/>
[içinde] Daha fazla renk seçeneği görüntüleyen *diğer* düğmenin metin etiketi veya NULL.

Diğer düğme için standart etiket **Daha Fazla Renk...**.

*lpszDocColors*<br/>
[içinde] Belge renkleri düğmesinin metin etiketi. Belge renkleri paleti, belgenin şu anda kullandığı tüm renkleri listeler.

*lstDocColors*<br/>
[içinde] Belgenin şu anda kullandığı renklerin listesi.

*nSütunlar*<br/>
[içinde] Renk dizisinin sahip olduğu sütun sayısı.

*nHorzDockRows*<br/>
[içinde] Renk çubuğuyatay olarak kenetlendiğinde sahip olduğu satır sayısı.

*nVertDockSütunlar*<br/>
[içinde] Renk çubuğudikey olarak kenetlendiğinde sahip olduğu sütun sayısı.

*Colorautomatic*<br/>
[içinde] Otomatik düğmeyi tıklattığınızda çerçevenin uyguladığı varsayılan renk.

*uiCommandID*<br/>
[içinde] Renk çubuğu denetim komut kimliği.

*bStdColorDlg*<br/>
[içinde] Standart sistem renk iletişim kutusunu veya [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusunu gösterip göstermeyeceğini belirten bir Boolean.

*pParentBtn*<br/>
[içinde] Üst düğmeye işaretçi.

*Nıd*<br/>
[içinde] Komut kimliği.

### <a name="remarks"></a>Açıklamalar

Aşırı yüklü her yapı `m_bEnabledInCustomizeMode` yapıcı üyeyi FALSE'a ayarlar.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCColorPopupMenu` nesnenin nasıl inşa edilebildiğini gösterir.

[!code-cpp[NVC_MFC_RibbonApp#34](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]

## <a name="cmfccolorpopupmenucreatetearoffbar"></a><a name="createtearoffbar"></a>CMFCColorPopupMenu::CreateTearOffBar

Sabitlenebilir bir yırtılma renk çubuğu oluşturur.

```
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,
    UINT uiID,
    LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pWndMain*|[içinde] Yırtılma çubuğunun üst penceresine işaretçi.|
|*uiID*|[içinde] Yırtılma çubuğunun komut kimliği.|
|*Lpszname*|[içinde] Yırtılma çubuğunun pencere metni.|

### <a name="return-value"></a>Dönüş Değeri

Yeni yırtılma denetim çubuğu nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir [CMFCColorBar Sınıfı](../../mfc/reference/cmfccolorbar-class.md) nesnesi oluşturur ve [cpane sınıfı](../../mfc/reference/cpane-class.md) işaretçisine atar. [MFC Sınıf Nesnelerinin Tür](../../mfc/reference/type-casting-of-mfc-class-objects.md)Döküm'ünde açıklanan döküm makrolarından birini kullanarak bu değeri [CMFCColorBar Sınıfı](../../mfc/reference/cmfccolorbar-class.md) işaretçisine geri atabilirsiniz.

## <a name="cmfccolorpopupmenugetmenubar"></a><a name="getmenubar"></a>CMFCColorPopupMenü::GetMenuBar

Açılır menüye katıştırılmış [CMFCPopUpMenuBar'ı](../../mfc/reference/cmfcpopupmenubar-class.md) döndürür.

```
virtual CMFCPopupMenuBar* GetMenuBar();
```

### <a name="return-value"></a>Dönüş Değeri

Katıştılmış `CMFCPopupMenuBar`bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Renk açılır menüsünde gömülü [cmfcpopupMenuBar Sınıf](../../mfc/reference/cmfcpopupmenubar-class.md) nesnesi vardır. Uygulamanız farklı bir katışma türü kullanıyorsa, türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfccolorpopupmenusetproplist"></a><a name="setproplist"></a>CMFCColorPopUpMenu::SetPropList

Katıştınesnenin `CMFCColorBar` özellik ızgara denetim nesnesini ayarlar.

```cpp
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>Parametreler

*pWndList*<br/>
[içinde] Özellik ızgara denetim nesnesine işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
