---
description: 'Daha fazla bilgi edinin: CMFCRibbonMiniToolBar sınıfı'
title: CMFCRibbonMiniToolBar sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsContextMenuMode
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::SetCommands
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::Show
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::ShowWithContextMenu
helpviewer_keywords:
- CMFCRibbonMiniToolBar [MFC], IsContextMenuMode
- CMFCRibbonMiniToolBar [MFC], IsRibbonMiniToolBar
- CMFCRibbonMiniToolBar [MFC], SetCommands
- CMFCRibbonMiniToolBar [MFC], Show
- CMFCRibbonMiniToolBar [MFC], ShowWithContextMenu
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
ms.openlocfilehash: 7215349323f8039bccb24860e4e5ad663bd24bcd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273949"
---
# <a name="cmfcribbonminitoolbar-class"></a>CMFCRibbonMiniToolBar sınıfı

Bağlamsal açılan araç çubuğunu uygular.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|Varsayılan Oluşturucu.|
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|`CMFCRibbonMiniToolBar::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|`CMFCRibbonMiniToolBar::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCRibbonMiniToolBar:: ıscontextmenumode](#iscontextmenumode)||
|[CMFCRibbonMiniToolBar:: IsRibbonMiniToolBar](#isribbonminitoolbar)|(Geçersiz kılmalar `CMFCPopupMenu::IsRibbonMiniToolBar` .)|
|[CMFCRibbonMiniToolBar:: SetCommands](#setcommands)|Araç çubuğunda görüntülenecek komutların listesini ayarlar.|
|[Cmfcribbonmini araç çubuğu:: show](#show)|Belirtilen Ekran koordinatlarındaki Mini araç çubuğunu görüntüler.|
|[CMFCRibbonMiniToolBar:: ShowWithContextMenu](#showwithcontextmenu)|Mini araç çubuğunu bir bağlam menüsü ile birlikte görüntüler.|

## <a name="remarks"></a>Açıklamalar

Mini araç çubuğu, genellikle Kullanıcı belgedeki bir nesneyi seçtikten sonra görüntülenir. Örneğin, Kullanıcı bir sözcük işleme programında metin bloğunu seçtikten sonra, uygulama metin biçimlendirme komutlarını içeren bir mini araç çubuğunu görüntüler.

Mini araç çubuğu, fare işaretçisi Mini araç çubuğunun sınırları dışında olduğunda saydam hale gelir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

`CMFCRibbonPanelMenu`

[Cmfcribbonmini araç çubuğu](../../mfc/reference/cmfcribbonminitoolbar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRibbonMiniToolBar. h

## <a name="cmfcribbonminitoolbarsetcommands"></a><a name="setcommands"></a> CMFCRibbonMiniToolBar:: SetCommands

Araç çubuğunda görüntülenecek komutların listesini ayarlar.

```cpp
void SetCommands(
    CMFCRibbonBar* pRibbonBar,
    const CList<UINT,UINT>& lstCommands);
```

### <a name="parameters"></a>Parametreler

*Pribbonçubuğu*<br/>
'ndaki Mini araç çubuğunun görüntülenecek düğmeleri arayacağı şerit çubuğu.

*lstCommands*<br/>
'ndaki Mini araç çubuğunda görüntülenecek komutların listesi. Tüm Şerit kategorileri, ilişkili düğmeleri bulmak için aranır.

### <a name="remarks"></a>Açıklamalar

Mini araç çubuğunda görüntülenecek komutların listesini ayarlamak için bu işlevi kullanın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının yönteminin nasıl kullanılacağını gösterir `SetCommands` `CMFCRibbonMiniToolBar` . Bu kod parçacığı, [MS Office 2007 demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_MSOffice2007Demo#9](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]

## <a name="cmfcribbonminitoolbarshow"></a><a name="show"></a> Cmfcribbonmini araç çubuğu:: show

Belirtilen Ekran koordinatlarındaki Mini araç çubuğunu görüntüler.

```
BOOL Show(
    int x,
    int y);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Ekran koordinatlarındaki Mini araç çubuğunun yatay konumunu belirtir.

*Iz*<br/>
'ndaki Ekran koordinatlarındaki Mini araç çubuğunun dikey konumunu belirtir.

### <a name="return-value"></a>Dönüş Değeri

Mini araç çubuğu başarıyla görüntüleniyorsa doğru; Aksi takdirde, FALSE.

## <a name="cmfcribbonminitoolbarshowwithcontextmenu"></a><a name="showwithcontextmenu"></a> CMFCRibbonMiniToolBar:: ShowWithContextMenu

Mini araç çubuğunu bir bağlam menüsü ile birlikte görüntüler.

```
BOOL ShowWithContextMenu(
    int x,
    int y,
    UINT uiMenuResID,
    CWnd* pWndOwner);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Ekran koordinatlarındaki bağlam menüsünün yatay konumunu belirtir.

*Iz*<br/>
'ndaki Ekran koordinatlarındaki bağlam menüsünün dikey konumunu belirtir.

*Uııd*<br/>
'ndaki Görüntülenecek bağlam menüsünün kaynak KIMLIĞINI belirtir.

*pWndOwner*<br/>
'ndaki Bağlam menüsünden iletileri alan pencereyi tanımlar.

### <a name="return-value"></a>Dönüş Değeri

Bağlam menüsü başarıyla görüntüleniyorsa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bağlam menüsü olan Mini araç çubuğunu göstermek için bu işlevi kullanın. Bağlam menüsü, Mini araç çubuğunun altında 15 piksel konumlandırılır.

## <a name="cmfcribbonminitoolbariscontextmenumode"></a><a name="iscontextmenumode"></a> CMFCRibbonMiniToolBar:: ıscontextmenumode

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
BOOL IsContextMenuMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonminitoolbarisribbonminitoolbar"></a><a name="isribbonminitoolbar"></a> CMFCRibbonMiniToolBar:: IsRibbonMiniToolBar

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
virtual BOOL IsRibbonMiniToolBar() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
