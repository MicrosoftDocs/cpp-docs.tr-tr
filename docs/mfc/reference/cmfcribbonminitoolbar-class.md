---
title: CMFCRibbonMiniToolTa Bar Sınıfı
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
ms.openlocfilehash: 10b1d35c331df6563d09be0bea3c97c73e89acaa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375085"
---
# <a name="cmfcribbonminitoolbar-class"></a>CMFCRibbonMiniToolTa Bar Sınıfı

Bağlamsal açılır pencere araç çubuğu uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|Varsayılan oluşturucu.|
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|`CMFCRibbonMiniToolBar::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|`CMFCRibbonMiniToolBar::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCRibbonMiniToolBar::IscontextMenuMode](#iscontextmenumode)||
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](#isribbonminitoolbar)|(Geçersiz `CMFCPopupMenu::IsRibbonMiniToolBar`kılar .)|
|[CMFCRibbonMiniToolBar::SetKomutları](#setcommands)|Araç çubuğunda görüntülenecek komutların listesini ayarlar.|
|[CMFCRibbonMiniToolBar::Göster](#show)|Mini araç çubuğunu belirtilen ekran koordinatlarında görüntüler.|
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](#showwithcontextmenu)|Mini araç çubuğunu bağlam menüsüyle birlikte görüntüler.|

## <a name="remarks"></a>Açıklamalar

Mini araç çubuğu genellikle kullanıcı bir belgedeki bir nesneyi seçtikten sonra görüntülenir. Örneğin, kullanıcı bir sözcük işleme programında bir metin bloğu seçtikten sonra, uygulama metin biçimlendirme komutları içeren bir mini araç çubuğu görüntüler.

Fare işaretçisi mini araç çubuğunun sınırları dışında olduğunda mini araç çubuğu saydam hale gelir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[Cmfcpopupmenu](../../mfc/reference/cmfcpopupmenu-class.md)

`CMFCRibbonPanelMenu`

[CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRibbonMiniToolBar.h

## <a name="cmfcribbonminitoolbarsetcommands"></a><a name="setcommands"></a>CMFCRibbonMiniToolBar::SetKomutları

Araç çubuğunda görüntülenecek komutların listesini ayarlar.

```
void SetCommands(
    CMFCRibbonBar* pRibbonBar,
    const CList<UINT,UINT>& lstCommands);
```

### <a name="parameters"></a>Parametreler

*pRibbonBar*<br/>
[içinde] Mini araç çubuğunun görüntülenecek düğmeleri aradığı şerit çubuğu.

*lstKomutlar*<br/>
[içinde] Mini araç çubuğunda görüntülenecek komutların listesi. İlişkili düğmeleri bulmak için tüm şerit kategorileri aranır.

### <a name="remarks"></a>Açıklamalar

Mini araç çubuğunda görüntülenecek komutların listesini ayarlamak için bu işlevi kullanın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın yönteminin `SetCommands` nasıl `CMFCRibbonMiniToolBar` kullanılacağını göstermektedir. Bu kod parçacığı MS Office [2007 Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_MSOffice2007Demo#9](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]

## <a name="cmfcribbonminitoolbarshow"></a><a name="show"></a>CMFCRibbonMiniToolBar::Göster

Mini araç çubuğunu belirtilen ekran koordinatlarında görüntüler.

```
BOOL Show(
    int x,
    int y);
```

### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Ekran koordinatlarında mini araç çubuğunun yatay konumunu belirtir.

*Y*<br/>
[içinde] Ekran koordinatlarında mini araç çubuğunun dikey konumunu belirtir.

### <a name="return-value"></a>Dönüş Değeri

Mini araç çubuğu başarıyla görüntülendiyse DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cmfcribbonminitoolbarshowwithcontextmenu"></a><a name="showwithcontextmenu"></a>CMFCRibbonMiniToolBar::ShowWithContextMenu

Mini araç çubuğunu bağlam menüsüyle birlikte görüntüler.

```
BOOL ShowWithContextMenu(
    int x,
    int y,
    UINT uiMenuResID,
    CWnd* pWndOwner);
```

### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Ekran koordinatlarında bağlam menüsünün yatay konumunu belirtir.

*Y*<br/>
[içinde] Ekran koordinatlarında bağlam menüsünün dikey konumunu belirtir.

*uiMenuResID*<br/>
[içinde] Görüntülenecek bağlam menüsünün kaynak kimliğini belirtir.

*pWndSahibi*<br/>
[içinde] Bağlam menüsünden ileti alan pencereyi tanımlar.

### <a name="return-value"></a>Dönüş Değeri

Bağlam menüsü başarıyla görüntülendiyse DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bağlam menüsü olan bir mini araç çubuğu görüntülemek için bu işlevi kullanın. Bağlam menüsü mini araç çubuğunun 15 piksel altında konumlandırılmış.

## <a name="cmfcribbonminitoolbariscontextmenumode"></a><a name="iscontextmenumode"></a>CMFCRibbonMiniToolBar::IscontextMenuMode

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
BOOL IsContextMenuMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonminitoolbarisribbonminitoolbar"></a><a name="isribbonminitoolbar"></a>CMFCRibbonMiniToolBar::IsRibbonMiniToolBar

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
virtual BOOL IsRibbonMiniToolBar() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
