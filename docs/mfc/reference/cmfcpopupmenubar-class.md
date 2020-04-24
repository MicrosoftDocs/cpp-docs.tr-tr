---
title: CMFCPopUpMenuBar Sınıfı
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
ms.openlocfilehash: c0ba90246d19e8dd07c856eec6a518a8513ee665
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751927"
---
# <a name="cmfcpopupmenubar-class"></a>CMFCPopUpMenuBar Sınıfı

Açılır menüye gömülü bir menü çubuğu.

## <a name="syntax"></a>Sözdizimi

```
class CMFCPopupMenuBar : public CMFCToolBar
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCPopUpMenuBar::AdjustSizeImmediate](#adjustsizeimmediate)|Bölmenin düzenini hemen yeniden hesaplar. [(CPane geçersiz kılar::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).)|
|[CMFCPopUpMenuBar::BuildOrigItems](#buildorigitems)|Belirtilen menü kaynağından açılır menü öğeleriyükler.|
|[CMFCPopUpMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|Gecikmiş açılır menü düğmesini kapatır.|
|[CMFCPopUpMenuBar::ExportToMenu](#exporttomenu)|Açılır menü düğmelerinden bir menü oluşturur.|
|[CMFCPopUpMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|Belirtilen noktanın bulunduğu araç çubuğunu bulur.|
|[CMFCPopUpMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|Menü düğmesi görüntülerinin boyutunu gösterir.|
|[CMFCPopUpMenuBar::GetDefaultMenuId](#getdefaultmenuid)|Varsayılan menü öğesinin tanımlayıcısını döndürür.|
|[CMFCPopUpMenuBar::GetLastCommandIndex](#getlastcommandindex)|En son çağrılan menü komutunun dizinini alır.|
|[CMFCPopUpMenuBar::GetOffset](#getoffset)|Açılır menü çubuğunun satır ofsetini alır.|
|[CMFCPopUpMenuBar::ImportFromMenu](#importfrommenu)|Belirtilen menüden açılır menü düğmelerini içeri akteder.|
|[CMFCPopUpMenuBar::IsDropDownListMode](#isdropdownlistmode)|Açılır menü çubuğunun açılır liste modunda olup olmadığını gösterir.|
|[CMFCPopUpMenuBar::IsPaletteMode](#ispalettemode)|Açılır menü çubuğunun palet modunda olup olmadığını gösterir.|
|[CMFCPopUpMenuBar::IsRibbonPanel](#isribbonpanel)|Bunun bir şerit paneli olup olmadığını gösterir (varsayılan olarak FALSE).|
|[CMFCPopUpMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|Bunun normal modda bir şerit paneli olup olmadığını gösterir (varsayılan olarak FALSE).|
|[CMFCPopUpMenüBar::LoadFromHash](#loadfromhash)|Arşivlenmiş bir menü yükler.|
|[CMFCPopUpMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|Açılır menü çubuğunu kapatmak için gecikmiş bir menü düğmesini geri yükler.|
|[CMFCPopUpMenuBar::SetButtonStyle](#setbuttonstyle)|Verilen dizindeki araç çubuğu düğmesinin stilini ayarlar. [(CMFCToolBar geçersiz kılar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)|
|[CMFCPopUpMenuBar::SetOffset](#setoffset)|Açılır menü çubuğunun satır ofsetini ayarlar.|
|[CMFCPopUpMenüBar::BaşlangıçPopupMenuTimer](#startpopupmenutimer)|Belirtilen gecikmeli açılır menü düğmesi için zamanlayıcıyı başlatır.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CMFCPopUpMenüBar::m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|Uygulama Windows XP görünümüne sahip olduğunda gri kenar çubuğunun görüntülenip görüntülenmeyeceğini belirtir.|

## <a name="remarks"></a>Açıklamalar

`CMFCPopupMenuBar` [CmFCPopUpMenu Sınıfı](../../mfc/reference/cmfcpopupmenu-class.md) ile aynı anda oluşturulur ve içine gömülüdür. Nesnenin `CMFCPopupMenuBar` tüm istemci alanını `CMFCPopupMenu` kapsar. Klavye ve fare girişini destekler. Ayrıca, bu girişi üst `CMFCPopupMenu` düzey çerçeve penceresine de ileter.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCPopupMenuBar` `CMFCPopupMenu` nesnenin bir nesneden nasıl başharfe atınır olduğunu gösterir. Bu kod snippet [Çekme İstemci örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_DrawClient#7](../../mfc/reference/codesnippet/cpp/cmfcpopupmenubar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[Cpane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[Cmfctoolbar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCPopUpMenüBar](../../mfc/reference/cmfcpopupmenubar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxpopupmenubar.h

## <a name="cmfcpopupmenubaradjustsizeimmediate"></a><a name="adjustsizeimmediate"></a>CMFCPopUpMenuBar::AdjustSizeImmediate

Hemen açılır menü çubuğu bölmesinin düzenini yeniden hesaplar. [(CPane geçersiz kılar::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate).

```
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```

### <a name="parameters"></a>Parametreler

*bRecalcLayout*<br/>
[içinde] Pop-up menü çubuğu bölmesinin düzenini otomatik olarak yeniden hesaplamak için TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarbuildorigitems"></a><a name="buildorigitems"></a>CMFCPopUpMenuBar::BuildOrigItems

Belirtilen menü kaynağından açılır menü öğeleriyükler.

```
BOOL BuildOrigItems(UINT uiMenuResID);
```

### <a name="parameters"></a>Parametreler

*uiMenuResID*<br/>
[içinde] Yüklenmesi gereken menü kaynağının menü kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı ysa TRUE veya FALSE değilse TRUE'yı döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarclosedelayedsubmenu"></a><a name="closedelayedsubmenu"></a>CMFCPopUpMenuBar::CloseDelayedSubMenu

Gecikmiş bir açılır menü düğmesini kapatır.

```
virtual void CloseDelayedSubMenu();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarexporttomenu"></a><a name="exporttomenu"></a>CMFCPopUpMenuBar::ExportToMenu

Açılır menü düğmelerinden bir menü oluşturur.

```
virtual HMENU ExportToMenu() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni menüye bir tanıtıcı döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarfinddestintationtoolbar"></a><a name="finddestintationtoolbar"></a>CMFCPopUpMenuBar::FindDestintationToolBar

Belirtilen noktanın bulunduğu araç çubuğunu bulur.

```
CMFCToolBar* FindDestintationToolBar(CPoint point);
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
[içinde] Ekranda bir nokta.

### <a name="return-value"></a>Dönüş Değeri

Bir tutamacı, noktanın bulunduğu araç çubuğuna, varsa bir veya yoksa NULL'a döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubargetcurrentmenuimagesize"></a><a name="getcurrentmenuimagesize"></a>CMFCPopUpMenuBar::GetCurrentMenuImageSize

Menü düğmesi görüntülerinin boyutunu gösterir.

```
virtual CSize GetCurrentMenuImageSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Araç çubuğundaki menü düğmesi görüntülerinin boyutunu döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubargetdefaultmenuid"></a><a name="getdefaultmenuid"></a>CMFCPopUpMenuBar::GetDefaultMenuId

Varsayılan menü öğesinin tanımlayıcısını döndürür.

```
UINT GetDefaultMenuId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılır menü çubuğundaki varsayılan menü öğesinin tanımlayıcısını döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubargetlastcommandindex"></a><a name="getlastcommandindex"></a>CMFCPopUpMenuBar::GetLastCommandIndex

En son çağrılan menü komutunun dizinini alır.

```
static int __stdcall GetLastCommandIndex();
```

### <a name="return-value"></a>Dönüş Değeri

Çağrılan son menü komutunun dizinini döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubargetoffset"></a><a name="getoffset"></a>CMFCPopUpMenuBar::GetOffset

Açılır menü çubuğunun satır ofsetini alır.

```
int GetOffset() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılır menü çubuğunun satır ofsetini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu değer [CMFCPopUpMenuBar::SetOffset](#setoffset)kullanılarak ayarlanır.

## <a name="cmfcpopupmenubarimportfrommenu"></a><a name="importfrommenu"></a>CMFCPopUpMenuBar::ImportFromMenu

Belirtilen menüden açılır menü düğmelerini içeri akteder.

```
virtual BOOL ImportFromMenu(
    HMENU hMenu,
    BOOL bShowAllCommands = FALSE);
```

### <a name="parameters"></a>Parametreler

*Hmenu*<br/>
[içinde] Açılır menü düğmelerini almak için menü.

*bShowAllKomutları*<br/>
[içinde] Menüdeki tüm komutlar içe aktarılacaksa DOĞRU veya nadiren kullanılan komutlar gizlenecekse FALSE.

### <a name="return-value"></a>Dönüş Değeri

Menü düğmeleri menüden başarıyla içe aktarıldıysa TRUE'yu döndürür veya değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarisdropdownlistmode"></a><a name="isdropdownlistmode"></a>CMFCPopUpMenuBar::IsDropDownListMode

Açılır menü çubuğunun açılır liste modunda olup olmadığını gösterir.

```
BOOL IsDropDownListMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılır menü çubuğu açılır listeden açılan listedeyse TRUE'yu döndürür veya değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarispalettemode"></a><a name="ispalettemode"></a>CMFCPopUpMenuBar::IsPaletteMode

Açılır menü çubuğunun palet modunda olup olmadığını gösterir.

```
BOOL IsPaletteMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Palet modu etkinse TRUE'yı döndürür veya değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Menü çubuğu palet moduna ayarlandığında, menü öğeleri birden çok sütunda ve sınırlı sayıda satırda görünür.

## <a name="cmfcpopupmenubarisribbonpanel"></a><a name="isribbonpanel"></a>CMFCPopUpMenuBar::IsRibbonPanel

Bunun bir şerit paneli olup olmadığını gösterir (varsayılan olarak FALSE).

```
virtual BOOL IsRibbonPanel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan olarak FALSE döndürür, bu bir şerit paneli olmadığını gösterir.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarisribbonpanelinregularmode"></a><a name="isribbonpanelinregularmode"></a>CMFCPopUpMenuBar::IsRibbonPanelInRegularMode

Bunun normal modda bir şerit paneli olup olmadığını gösterir (varsayılan olarak FALSE).

```
virtual BOOL IsRibbonPanelInRegularMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bunun normal modda bir şerit paneli olmadığını belirten FALSE varsayılan olarak döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarloadfromhash"></a><a name="loadfromhash"></a>CMFCPopUpMenüBar::LoadFromHash

Arşivlenmiş bir menü yükler.

```
BOOL LoadFromHash(HMENU hMenu);
```

### <a name="parameters"></a>Parametreler

*Hmenu*<br/>
[içinde] Yüklenmesi için arşivlenmiş menüye bir tutamaç.

### <a name="return-value"></a>Dönüş Değeri

Menü başarıyla yüklenirse DOĞRU'yu döndürür veya yüklenmezse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarm_bdisablesidebarinxpmode"></a><a name="m_bdisablesidebarinxpmode"></a>CMFCPopUpMenüBar::m_bDisableSideBarInXPMode

Uygulamanızın Windows XP görünümünde gri bir kenar çubuğuolup olmadığını gösteren boolean parametresi.

```
BOOL m_bDisableSideBarInXPMode;
```

### <a name="remarks"></a>Açıklamalar

Bu üye değişken FALSE olarak ayarlanmışsa ve uygulamanızda Windows XP görünümü varsa, çerçeve uygulamanızda gri bir kenar çubuğu çizer.

Varsayılan değer FALSE'dur.

## <a name="cmfcpopupmenubarrestoredelayedsubmenu"></a><a name="restoredelayedsubmenu"></a>CMFCPopUpMenuBar::RestoreDelayedSubMenu

Açılır menü çubuğunu kapatmak için gecikmiş bir menü düğmesini geri yükler.

```
virtual void RestoreDelayedSubMenu();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarsetbuttonstyle"></a><a name="setbuttonstyle"></a>CMFCPopUpMenuBar::SetButtonStyle

Verilen dizindeki araç çubuğu düğmesinin stilini ayarlar. [(CMFCToolBar geçersiz kılar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle).)

```
virtual void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
[içinde] Stili ayarlanacak araç çubuğu düğmesinin sıfır tabanlı dizin.

*nStyle*<br/>
[içinde] Düğmenin stili. Kullanılabilir araç çubuğu düğmesi stilleri listesi için [Araç Çubuğu Denetim Stilleri'ne](../../mfc/reference/toolbar-control-styles.md) bakın.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarsetoffset"></a><a name="setoffset"></a>CMFCPopUpMenuBar::SetOffset

Açılır menü çubuğunun satır ofsetini ayarlar.

```cpp
void SetOffset(int iOffset);
```

### <a name="parameters"></a>Parametreler

*iOffset*<br/>
[içinde] Açılır menü çubuğunun dengelenmesi gereken satır sayısı.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarstartpopupmenutimer"></a><a name="startpopupmenutimer"></a>CMFCPopUpMenüBar::BaşlangıçPopupMenuTimer

Belirtilen gecikmeli açılır menü düğmesi için zamanlayıcıyı başlatır.

```cpp
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,
    int nDelayFactor = 1);
```

### <a name="parameters"></a>Parametreler

*pMenuButton*<br/>
[içinde] Gecikme zamanlayıcısını ayarlamak için menü düğmesini işaretleyin.

*nDelayFactor*<br/>
[içinde] Standart menü gecikme süresiyle (genellikle yarım saniye ile beş saniye arasında) çarpılması gereken en az bir gecikme faktörü.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorBar Sınıfı](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCPopUpMenü Sınıfı](../../mfc/reference/cmfcpopupmenu-class.md)
