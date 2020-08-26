---
title: CMFCColorPopupMenu sınıfı
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
ms.openlocfilehash: 2964f250b25ad6c77c70e8f10cd92cca0c7d11da
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844567"
---
# <a name="cmfccolorpopupmenu-class"></a>CMFCColorPopupMenu sınıfı

Kullanıcıların bir belge veya uygulamadaki renkleri seçmek için kullandığı bir açılır menüyü temsil eder.

## <a name="syntax"></a>Syntax

```
class CMFCColorPopupMenu : public CMFCPopupMenu
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|-|-|
|[CMFCColorPopupMenu:: CMFCColorPopupMenu](#cmfccolorpopupmenu)|Bir `CMFCColorPopupMenu` nesnesi oluşturur.|
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|-|-|
|[CMFCColorPopupMenu:: CreateTearOffBar](#createtearoffbar)|Yerleştirilebilir bir renk çubuğu oluşturur. ( [CMFCPopupMenu:: Createtearoff çubuğunu](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar)geçersiz kılar.)|
|[CMFCColorPopupMenu:: GetMenuBar](#getmenubar)|Açılan menünün içine katıştırılmış [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) öğesini döndürür. ( [CMFCPopupMenu:: GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar).) öğesini geçersiz kılar|
|`CMFCColorPopupMenu::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCColorPopupMenu:: SetPropList](#setproplist)|Katıştırılmış nesnenin özellik Kılavuzu denetim nesnesini ayarlar `CMFCColorBar` .|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|-|-|
|`m_bEnabledInCustomizeMode`|Renk çubuğunu gösterip göstermeyeceğinizi belirleyen bir Boolean değer.|
|`m_wndColorBar`|`CMFCColorBar`Renk seçimi sağlayan nesne.|

### <a name="remarks"></a>Açıklamalar

Bu sınıf, sınıfının açılır menü işlevselliğini devralır `CMFCPopupMenu` ve `CMFCColorBar` renk seçimi sağlayan bir nesneyi yönetir. Araç çubuğu çerçevesi özelleştirme modundayken ve `m_bEnabledInCustomizeMode` üye false olarak ayarlandığında, renk çubuğu nesnesi gösterilmez. Özelleştirme modu hakkında daha fazla bilgi için bkz [. CMFCToolBar:: IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)

Hakkında daha fazla bilgi için `CMFCColorBar` bkz. [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

[CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcolorpopupmenu. h

## <a name="cmfccolorpopupmenucmfccolorpopupmenu"></a><a name="cmfccolorpopupmenu"></a> CMFCColorPopupMenu:: CMFCColorPopupMenu

Bir `CMFCColorPopupMenu` nesnesi oluşturur.

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

*lerde*<br/>
'ndaki Çerçevenin açılır menüde görüntülediği renk dizisi.

*Renk*<br/>
'ndaki Varsayılan seçili renk.

*lpszAutoColor*<br/>
'ndaki *Otomatik* (varsayılan) renk DÜĞMESININ veya null alanının metin etiketi.

Otomatik düğmenin standart etiketi **otomatiktir**.

*lpszOtherColor*<br/>
'ndaki *Diğer* düğmenin, daha fazla renk SEÇIMI veya null görüntüleyen metin etiketi.

Diğer düğmenin standart etiketi **daha fazla renklerdir...**.

*lpszDocColors*<br/>
'ndaki Belge renkleri düğmesinin metin etiketi. Belge renkleri paleti, belgenin şu anda kullandığı tüm renkleri listeler.

*lstDocColors*<br/>
'ndaki Belgenin şu anda kullandığı renklerin listesi.

*nColumns*<br/>
'ndaki Renklerin dizisinin sahip olduğu sütun sayısı.

*nHorzDockRows*<br/>
'ndaki Yatay yerleştirilmiş olan renk çubuğunun satır sayısı.

*nVertDockColumns*<br/>
'ndaki Renk çubuğunun dikey yerleştirilmiş olduğu sütun sayısı.

*colorAutomatic*<br/>
'ndaki Otomatik düğmesine tıkladığınızda çerçevenin geçerli olduğu varsayılan renk.

*Uııommandıd*<br/>
'ndaki Renk çubuğu denetim komut KIMLIĞI.

*bStdColorDlg*<br/>
'ndaki Standart sistem rengi iletişim kutusunun mi yoksa [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusunun mi gösterileceğini belirten bir Boole değeri.

*pParentBtn*<br/>
'ndaki Üst düğmeye yönelik bir işaretçi.

*NID*<br/>
'ndaki Komut KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Her aşırı yüklenmiş Oluşturucu `m_bEnabledInCustomizeMode` üyeyı false olarak ayarlar.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnesinin nasıl oluşturulduğunu gösterir `CMFCColorPopupMenu` .

[!code-cpp[NVC_MFC_RibbonApp#34](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]

## <a name="cmfccolorpopupmenucreatetearoffbar"></a><a name="createtearoffbar"></a> CMFCColorPopupMenu:: CreateTearOffBar

Yerleştirilebilir bir renk çubuğu oluşturur.

```
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,
    UINT uiID,
    LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*pWndMain*\
'ndaki Koparma çubuğunun üst penceresine yönelik işaretçi.

*Uııd*\
'ndaki Yırma çubuğunun komut KIMLIĞI.

*lpszName*\
'ndaki Yırma çubuğunun pencere metni.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir yırt denetim çubuğu nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir [CMFCColorBar sınıf](../../mfc/reference/cmfccolorbar-class.md) nesnesi oluşturur ve bunu bir [CPane sınıfı](../../mfc/reference/cpane-class.md) işaretçisine yayınlar. Bu değeri, [MFC sınıf nesnelerinin tür ataması](../../mfc/reference/type-casting-of-mfc-class-objects.md)bölümünde açıklanan atama makrolarından birini kullanarak bir [CMFCColorBar sınıf](../../mfc/reference/cmfccolorbar-class.md) işaretçisine geri çevirebilirsiniz.

## <a name="cmfccolorpopupmenugetmenubar"></a><a name="getmenubar"></a> CMFCColorPopupMenu:: GetMenuBar

Açılan menünün içine katıştırılmış [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) öğesini döndürür.

```
virtual CMFCPopupMenuBar* GetMenuBar();
```

### <a name="return-value"></a>Dönüş Değeri

Katıştırılmış için bir işaretçi `CMFCPopupMenuBar` .

### <a name="remarks"></a>Açıklamalar

Renk açılır menüsünde gömülü bir [CMFCPopupMenuBar sınıfı](../../mfc/reference/cmfcpopupmenubar-class.md) nesnesi vardır. Uygulamanız farklı bir katıştırılmış tür kullanıyorsa türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfccolorpopupmenusetproplist"></a><a name="setproplist"></a> CMFCColorPopupMenu:: SetPropList

Katıştırılmış nesnenin özellik Kılavuzu denetim nesnesini ayarlar `CMFCColorBar` .

```cpp
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>Parametreler

*pWndList*<br/>
'ndaki Özellik kılavuzu denetim nesnesine yönelik işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
