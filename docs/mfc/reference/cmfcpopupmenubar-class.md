---
title: CMFCPopupMenuBar sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::AdjustSizeImmediate
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::BuildOrigItems
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::CloseDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ExportToMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::FindDestintationToolBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetCurrentMenuImageSize
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetDefaultMenuId
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetLastCommandIndex
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ImportFromMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsDropDownListMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsPaletteMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanel
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanelInRegularMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::LoadFromHash
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::RestoreDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetButtonStyle
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::StartPopupMenuTimer
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::m_bDisableSideBarInXPMode
helpviewer_keywords:
- CMFCPopupMenuBar [MFC], AdjustSizeImmediate
- CMFCPopupMenuBar [MFC], BuildOrigItems
- CMFCPopupMenuBar [MFC], CloseDelayedSubMenu
- CMFCPopupMenuBar [MFC], ExportToMenu
- CMFCPopupMenuBar [MFC], FindDestintationToolBar
- CMFCPopupMenuBar [MFC], GetCurrentMenuImageSize
- CMFCPopupMenuBar [MFC], GetDefaultMenuId
- CMFCPopupMenuBar [MFC], GetLastCommandIndex
- CMFCPopupMenuBar [MFC], GetOffset
- CMFCPopupMenuBar [MFC], ImportFromMenu
- CMFCPopupMenuBar [MFC], IsDropDownListMode
- CMFCPopupMenuBar [MFC], IsPaletteMode
- CMFCPopupMenuBar [MFC], IsRibbonPanel
- CMFCPopupMenuBar [MFC], IsRibbonPanelInRegularMode
- CMFCPopupMenuBar [MFC], LoadFromHash
- CMFCPopupMenuBar [MFC], RestoreDelayedSubMenu
- CMFCPopupMenuBar [MFC], SetButtonStyle
- CMFCPopupMenuBar [MFC], SetOffset
- CMFCPopupMenuBar [MFC], StartPopupMenuTimer
- CMFCPopupMenuBar [MFC], m_bDisableSideBarInXPMode
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
ms.openlocfilehash: acb1e2be7d40e5e0c569fffcc92c57c750be8f91
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374031"
---
# <a name="cmfcpopupmenubar-class"></a>CMFCPopupMenuBar sınıfı

Bir menü çubuğu açılır menüde gömülü.

## <a name="syntax"></a>Sözdizimi

```
class CMFCPopupMenuBar : public CMFCToolBar
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPopupMenuBar::AdjustSizeImmediate](#adjustsizeimmediate)|Hemen bir bölme düzenini yeniden hesaplar. (Geçersiz kılmaları [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).)|
|[CMFCPopupMenuBar::BuildOrigItems](#buildorigitems)|Açılan menü öğelerinin belirtilen menü kaynağı yükler.|
|[CMFCPopupMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|Gecikmeli açılan menü düğmesine kapatır.|
|[CMFCPopupMenuBar::ExportToMenu](#exporttomenu)|Bir menü açılır menü düğmelerle oluşturur.|
|[CMFCPopupMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|Araç, belirli bir noktaya nereden kaynaklandığını bulur.|
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|Menü düğmesine resimlerin boyutunu gösterir.|
|[CMFCPopupMenuBar::GetDefaultMenuId](#getdefaultmenuid)|Varsayılan menü öğesi tanımlayıcısını döndürür.|
|[CMFCPopupMenuBar::GetLastCommandIndex](#getlastcommandindex)|En son çağırılan menü komutunu dizinini alır.|
|[CMFCPopupMenuBar::GetOffset](#getoffset)|Açılan menü çubuğunun satır uzaklığı alır.|
|[CMFCPopupMenuBar::ImportFromMenu](#importfrommenu)|Açılan menü düğmesi belirtilen menüsünden içeri aktarır.|
|[CMFCPopupMenuBar::IsDropDownListMode](#isdropdownlistmode)|Açılan menü çubuğu aşağı açılan liste modunda olup olmadığını belirtir.|
|[CMFCPopupMenuBar::IsPaletteMode](#ispalettemode)|Açılan menü çubuğu paletinden modunda olup olmadığını gösterir.|
|[CMFCPopupMenuBar::IsRibbonPanel](#isribbonpanel)|Bu Şerit paneline (varsayılan olarak FALSE) olup olmadığını gösterir.|
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|Bu Şerit paneline normal modunda (varsayılan olarak FALSE) olup olmadığını gösterir.|
|[CMFCPopupMenuBar::LoadFromHash](#loadfromhash)|Arşivlenen bir menü yükler.|
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|Açılan menü çubuğu kapatma Gecikmeli menü düğmesine geri yükler.|
|[CMFCPopupMenuBar::SetButtonStyle](#setbuttonstyle)|Belirtilen dizindeki araç çubuğu düğmesini stilini ayarlar. (Geçersiz kılmaları [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)|
|[CMFCPopupMenuBar::SetOffset](#setoffset)|Açılan menü çubuğunun satır uzaklığı ayarlar.|
|[CMFCPopupMenuBar::StartPopupMenuTimer](#startpopupmenutimer)|Belirtilen Gecikmeli açılan menü düğmesi süreölçer başlatır.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPopupMenuBar::m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|Uygulamayı bir Windows XP görünümü olduğunda gri kenar görüntülenip görüntülenmeyeceğini belirtir.|

## <a name="remarks"></a>Açıklamalar

`CMFCPopupMenuBar` Aynı zamanda oluşturulmuş bir [CMFCPopupMenu sınıfı](../../mfc/reference/cmfcpopupmenu-class.md) ve içine katıştırılmış. `CMFCPopupMenuBar` Tüm istemci alanını kapsayan `CMFCPopupMenu` nesne. Bu, klavye ve fare girişi destekler. Ayrıca, giriş iletişim `CMFCPopupMenu` ve üst düzey bir çerçeve penceresi.

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl başlatılacağını gösterir. bir `CMFCPopupMenuBar` nesnesinden bir `CMFCPopupMenu` nesne. Bu kod parçacığı parçasıdır [çizmek istemci örneği](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#7](../../mfc/reference/codesnippet/cpp/cmfcpopupmenubar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxpopupmenubar.h

##  <a name="adjustsizeimmediate"></a>  CMFCPopupMenuBar::AdjustSizeImmediate

Hemen açılan menü çubuğu bölmesinin düzenini yeniden hesaplar. (Geçersiz kılmaları [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).

```
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```

### <a name="parameters"></a>Parametreler

*bRecalcLayout*<br/>
[in] Otomatik olarak açılan menü çubuğu bölmesinin düzenini yeniden hesapla için TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="buildorigitems"></a>  CMFCPopupMenuBar::BuildOrigItems

Açılan menü öğelerinin belirtilen menü kaynağı yükler.

```
BOOL BuildOrigItems(UINT uiMenuResID);
```

### <a name="parameters"></a>Parametreler

*uiMenuResID*<br/>
[in] Yüklemek için menü kaynağı menü Kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE ya da aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="closedelayedsubmenu"></a>  CMFCPopupMenuBar::CloseDelayedSubMenu

Ertelendi bir açılan menü düğmesi kapatır.

```
virtual void CloseDelayedSubMenu();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="exporttomenu"></a>  CMFCPopupMenuBar::ExportToMenu

Bir menü açılır menü düğmelerle oluşturur.

```
virtual HMENU ExportToMenu() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni menüsüne bir tanıtıcı döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="finddestintationtoolbar"></a>  CMFCPopupMenuBar::FindDestintationToolBar

Araç, belirli bir noktaya nereden kaynaklandığını bulur.

```
CMFCToolBar* FindDestintationToolBar(CPoint point);
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
[in] Ekranda bir nokta.

### <a name="return-value"></a>Dönüş Değeri

Varsa bir tanıtıcı araç çubuğuna burada noktası olduğunda, döndürür veya yoksa NULL.

### <a name="remarks"></a>Açıklamalar

##  <a name="getcurrentmenuimagesize"></a>  CMFCPopupMenuBar::GetCurrentMenuImageSize

Menü düğmesine resimlerin boyutunu gösterir.

```
virtual CSize GetCurrentMenuImageSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Araç çubuğundaki menü düğmesine resimlerin boyutunu döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="getdefaultmenuid"></a>  CMFCPopupMenuBar::GetDefaultMenuId

Varsayılan menü öğesi tanımlayıcısını döndürür.

```
UINT GetDefaultMenuId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan menü çubuğundaki varsayılan menü öğesi tanımlayıcısını döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="getlastcommandindex"></a>  CMFCPopupMenuBar::GetLastCommandIndex

En son çağırılan menü komutunu dizinini alır.

```
static int __stdcall GetLastCommandIndex();
```

### <a name="return-value"></a>Dönüş Değeri

Çağrıldıktan son menü komutunu dizinini döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="getoffset"></a>  CMFCPopupMenuBar::GetOffset

Açılan menü çubuğunun satır uzaklığı alır.

```
int GetOffset() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan menü çubuğunun satır uzaklığı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu değer kullanılarak ayarlanan [CMFCPopupMenuBar::SetOffset](#setoffset).

##  <a name="importfrommenu"></a>  CMFCPopupMenuBar::ImportFromMenu

Açılan menü düğmesi belirtilen menüsünden içeri aktarır.

```
virtual BOOL ImportFromMenu(
    HMENU hMenu,
    BOOL bShowAllCommands = FALSE);
```

### <a name="parameters"></a>Parametreler

*hMenu*<br/>
[in] Açılan menü düğmeleri alınacağı menüsü.

*bShowAllCommands*<br/>
[in] İçeri aktarılan veya yanlış nadiren kullanılan olanları gizlenebilir menüsünde TRUE tüm komutları olacak.

### <a name="return-value"></a>Dönüş Değeri

Menü veya FALSE ise düğmeleri başarıyla alınamadı, TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="isdropdownlistmode"></a>  CMFCPopupMenuBar::IsDropDownListMode

Açılan menü çubuğu aşağı açılan liste modunda olup olmadığını belirtir.

```
BOOL IsDropDownListMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan menü çubuğu aşağı açılan liste modu veya FALSE ise değilse true değer döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="ispalettemode"></a>  CMFCPopupMenuBar::IsPaletteMode

Açılan menü çubuğu paletinden modunda olup olmadığını gösterir.

```
BOOL IsPaletteMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Palet modu etkinse TRUE, değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Menü çubuğu paletinden moduna ayarlandığında menü öğeleri birden çok sütun ve sınırlı sayıda satır görüntülenir.

##  <a name="isribbonpanel"></a>  CMFCPopupMenuBar::IsRibbonPanel

Bu Şerit paneline (varsayılan olarak FALSE) olup olmadığını gösterir.

```
virtual BOOL IsRibbonPanel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bunun bir Şerit paneli olmadığını belirten, varsayılan olarak false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="isribbonpanelinregularmode"></a>  CMFCPopupMenuBar::IsRibbonPanelInRegularMode

Bu Şerit paneline normal modunda (varsayılan olarak FALSE) olup olmadığını gösterir.

```
virtual BOOL IsRibbonPanelInRegularMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu Şerit paneline normal modda olduğunu belirten, varsayılan olarak false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="loadfromhash"></a>  CMFCPopupMenuBar::LoadFromHash

Arşivlenen bir menü yükler.

```
BOOL LoadFromHash(HMENU hMenu);
```

### <a name="parameters"></a>Parametreler

*hMenu*<br/>
[in] Arşivlenen menüsüne yüklemek için bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Menü başarıyla yüklendi ya da aksi takdirde FALSE ise true değeri döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="m_bdisablesidebarinxpmode"></a>  CMFCPopupMenuBar::m_bDisableSideBarInXPMode

Bir Windows XP görünümü sahip olduğunda, uygulamanızın gri kenar çubuğu olup olmadığını belirten bir Boole parametresi.

```
BOOL m_bDisableSideBarInXPMode;
```

### <a name="remarks"></a>Açıklamalar

Bu üye değişkeni FALSE olarak ayarlanır ve bir Windows XP görünümü uygulamanız varsa, framework uygulamanızda gri kenar çizer.

Varsayılan değer FALSE olur.

##  <a name="restoredelayedsubmenu"></a>  CMFCPopupMenuBar::RestoreDelayedSubMenu

Açılan menü çubuğu kapatma Gecikmeli menü düğmesine geri yükler.

```
virtual void RestoreDelayedSubMenu();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="setbuttonstyle"></a>  CMFCPopupMenuBar::SetButtonStyle

Belirtilen dizindeki araç çubuğu düğmesini stilini ayarlar. (Geçersiz kılmaları [CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)

```
virtual void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
[in] Ayarlanacak stilini olan araç çubuğu düğmesini sıfır tabanlı dizini.

*nStyle*<br/>
[in] Düğmenin stili. Bkz: [ToolBar denetim stilleri](../../mfc/reference/toolbar-control-styles.md) kullanılabilir araç çubuğu düğmesi stilleri listesi.

### <a name="remarks"></a>Açıklamalar

##  <a name="setoffset"></a>  CMFCPopupMenuBar::SetOffset

Açılan menü çubuğunun satır uzaklığı ayarlar.

```
void SetOffset(int iOffset);
```

### <a name="parameters"></a>Parametreler

*iOffset*<br/>
[in] Açılan menü çubuğu uzaklığı, satır sayısı.

### <a name="remarks"></a>Açıklamalar

##  <a name="startpopupmenutimer"></a>  CMFCPopupMenuBar::StartPopupMenuTimer

Belirtilen Gecikmeli açılan menü düğmesi süreölçer başlatır.

```
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,
    int nDelayFactor = 1);
```

### <a name="parameters"></a>Parametreler

*pMenuButton*<br/>
[in] Menü düğmesine gecikme Zamanlayıcı ayarlanacak işaretçisi.

*nDelayFactor*<br/>
[in] Bir gecikme faktörü, en az bir standart menü gecikme süresini (genellikle yarım saniye arasında arama ve beş saniye) tarafından çarpmak için eşittir.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorBar Sınıfı](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCPopupMenu Sınıfı](../../mfc/reference/cmfcpopupmenu-class.md)
