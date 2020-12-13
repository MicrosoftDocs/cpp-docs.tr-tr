---
description: 'Daha fazla bilgi edinin: CMFCPopupMenuBar sınıfı'
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
ms.openlocfilehash: 4db8c02ed92aec5243f9a2c7800c6fd1f9747751
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334744"
---
# <a name="cmfcpopupmenubar-class"></a>CMFCPopupMenuBar sınıfı

Açılır menüye eklenmiş bir menü çubuğu.

## <a name="syntax"></a>Syntax

```
class CMFCPopupMenuBar : public CMFCToolBar
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPopupMenuBar:: AdjustSizeImmediate](#adjustsizeimmediate)|Bir bölmenin yerleşimini hemen yeniden hesaplar. ( [CPane:: Adjustsizeımimmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate)geçersiz kılar.)|
|[CMFCPopupMenuBar:: BuildOrigItems](#buildorigitems)|Belirtilen menü kaynağından açılan menü öğelerini yükler.|
|[CMFCPopupMenuBar:: Closedelayedalt menüsü](#closedelayedsubmenu)|Gecikmeli açılan menü düğmesini kapatır.|
|[CMFCPopupMenuBar:: ExportToMenu](#exporttomenu)|Açılan menü düğmelerinden bir menü oluşturur.|
|[CMFCPopupMenuBar:: FindDestintationToolBar](#finddestintationtoolbar)|Belirtilen noktanın bulunduğu araç çubuğunu konumlandırır.|
|[CMFCPopupMenuBar:: GetCurrentMenuImageSize](#getcurrentmenuimagesize)|Menü düğmesi görüntülerinin boyutunu gösterir.|
|[CMFCPopupMenuBar:: GetDefaultMenuId](#getdefaultmenuid)|Varsayılan menü öğesinin tanımlayıcısını döndürür.|
|[CMFCPopupMenuBar:: Getlastcommandındex](#getlastcommandindex)|En son çağrılan menü komutunun dizinini alır.|
|[CMFCPopupMenuBar:: GetOffset](#getoffset)|Açılan menü çubuğunun satır konumunu alır.|
|[CMFCPopupMenuBar:: ımportfrommenu](#importfrommenu)|Belirtilen menüden açılan menü düğmelerini içeri aktarır.|
|[CMFCPopupMenuBar:: ısdropdownlistmode](#isdropdownlistmode)|Açılan menü çubuğunun açılan liste modunda olup olmadığını gösterir.|
|[CMFCPopupMenuBar:: ıspalettemode](#ispalettemode)|Açılan menü çubuğunun palet modunda olup olmadığını gösterir.|
|[CMFCPopupMenuBar:: ısribbonpanel](#isribbonpanel)|Bu bir şerit paneli (varsayılan olarak FALSE) olup olmadığını gösterir.|
|[CMFCPopupMenuBar:: ısribbonpanelınregularmode](#isribbonpanelinregularmode)|Bunun normal modda bir şerit paneli olup olmadığını gösterir (varsayılan olarak FALSE).|
|[CMFCPopupMenuBar:: LoadFromHash](#loadfromhash)|Arşivlenmiş bir menü yükler.|
|[CMFCPopupMenuBar:: Restoredelayedalt menü](#restoredelayedsubmenu)|Açılan menü çubuğunu kapatmak için geciken bir menü düğmesini geri yükler.|
|[CMFCPopupMenuBar:: SetButtonStyle](#setbuttonstyle)|Verilen dizindeki araç çubuğu düğmesinin stilini ayarlar. ( [CMFCToolBar:: SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle)geçersiz kılar.)|
|[CMFCPopupMenuBar:: SetOffset](#setoffset)|Açılan menü çubuğunun satır konumunu ayarlar.|
|[CMFCPopupMenuBar:: StartPopupMenuTimer](#startpopupmenutimer)|Belirtilen gecikmeli açılan menü düğmesi için süreölçeri başlatır.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCPopupMenuBar:: m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|Uygulamanın bir Windows XP görünümü olduğunda gri kenar çubuğunun görüntülenip görüntülenmeyeceğini belirtir.|

## <a name="remarks"></a>Açıklamalar

, `CMFCPopupMenuBar` Bir [CMFCPopupMenu sınıfı](../../mfc/reference/cmfcpopupmenu-class.md) ile aynı zamanda oluşturulur ve içine katıştırılır. , `CMFCPopupMenuBar` Nesnesinin istemci alanının tamamını içerir `CMFCPopupMenu` . Klavye ve fare girişini destekler. Ayrıca, bu girişi `CMFCPopupMenu` ve en üst düzey çerçeve penceresine da iletir.

## <a name="example"></a>Örnek

Aşağıdaki örnek bir nesnesinden bir nesnenin nasıl başlatılacağını gösterir `CMFCPopupMenuBar` `CMFCPopupMenu` . Bu kod parçacığı, [Çizim istemci örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

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

**Üstbilgi:** afxpopupmenubar. h

## <a name="cmfcpopupmenubaradjustsizeimmediate"></a><a name="adjustsizeimmediate"></a> CMFCPopupMenuBar:: AdjustSizeImmediate

Açılan menü çubuğu bölmesinin yerleşimini hemen yeniden hesaplar. ( [CPane:: Adjustsizeımimmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate)geçersiz kılar.

```
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```

### <a name="parameters"></a>Parametreler

*bRecalcLayout*<br/>
'ndaki Açılan menü çubuğu bölmesinin yerleşimini otomatik olarak yeniden hesaplamak için TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarbuildorigitems"></a><a name="buildorigitems"></a> CMFCPopupMenuBar:: BuildOrigItems

Belirtilen menü kaynağından açılan menü öğelerini yükler.

```
BOOL BuildOrigItems(UINT uiMenuResID);
```

### <a name="parameters"></a>Parametreler

*Uııd*<br/>
'ndaki Yüklenecek menü kaynağının menü KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE, değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarclosedelayedsubmenu"></a><a name="closedelayedsubmenu"></a> CMFCPopupMenuBar:: Closedelayedalt menüsü

Geciktirilen bir açılan menü düğmesini kapatır.

```
virtual void CloseDelayedSubMenu();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarexporttomenu"></a><a name="exporttomenu"></a> CMFCPopupMenuBar:: ExportToMenu

Açılan menü düğmelerinden bir menü oluşturur.

```
virtual HMENU ExportToMenu() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni menüye bir tanıtıcı döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarfinddestintationtoolbar"></a><a name="finddestintationtoolbar"></a> CMFCPopupMenuBar:: FindDestintationToolBar

Belirtilen noktanın bulunduğu araç çubuğunu konumlandırır.

```
CMFCToolBar* FindDestintationToolBar(CPoint point);
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
'ndaki Ekranda bir nokta.

### <a name="return-value"></a>Dönüş Değeri

Noktanın bulunduğu araç çubuğuna bir tutamaç, varsa, yoksa NULL değeri döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubargetcurrentmenuimagesize"></a><a name="getcurrentmenuimagesize"></a> CMFCPopupMenuBar:: GetCurrentMenuImageSize

Menü düğmesi görüntülerinin boyutunu gösterir.

```
virtual CSize GetCurrentMenuImageSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Araç çubuğundaki menü düğmesi görüntülerinin boyutunu döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubargetdefaultmenuid"></a><a name="getdefaultmenuid"></a> CMFCPopupMenuBar:: GetDefaultMenuId

Varsayılan menü öğesinin tanımlayıcısını döndürür.

```
UINT GetDefaultMenuId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan menü çubuğundaki varsayılan menü öğesinin tanımlayıcısını döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubargetlastcommandindex"></a><a name="getlastcommandindex"></a> CMFCPopupMenuBar:: Getlastcommandındex

En son çağrılan menü komutunun dizinini alır.

```
static int __stdcall GetLastCommandIndex();
```

### <a name="return-value"></a>Dönüş Değeri

Çağrılan son menü komutunun dizinini döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubargetoffset"></a><a name="getoffset"></a> CMFCPopupMenuBar:: GetOffset

Açılan menü çubuğunun satır konumunu alır.

```
int GetOffset() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan menü çubuğunun satır sapmasını döndürür.

### <a name="remarks"></a>Açıklamalar

Bu değer [CMFCPopupMenuBar:: SetOffset](#setoffset)kullanılarak ayarlanır.

## <a name="cmfcpopupmenubarimportfrommenu"></a><a name="importfrommenu"></a> CMFCPopupMenuBar:: ımportfrommenu

Belirtilen menüden açılan menü düğmelerini içeri aktarır.

```
virtual BOOL ImportFromMenu(
    HMENU hMenu,
    BOOL bShowAllCommands = FALSE);
```

### <a name="parameters"></a>Parametreler

*hMenu*<br/>
'ndaki Açılan menü düğmelerinin içeri aktarılacağı menü.

*bShowAllCommands*<br/>
'ndaki Menüdeki tüm komutlar içeri aktarılacaksa TRUE, nadiren kullanılırsa ise FALSE.

### <a name="return-value"></a>Dönüş Değeri

Menü düğmeleri menüden başarıyla içeri aktarıldıysa TRUE, değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarisdropdownlistmode"></a><a name="isdropdownlistmode"></a> CMFCPopupMenuBar:: ısdropdownlistmode

Açılan menü çubuğunun açılan liste modunda olup olmadığını gösterir.

```
BOOL IsDropDownListMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açılan menü çubuğu açılır liste modundaysa TRUE, değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarispalettemode"></a><a name="ispalettemode"></a> CMFCPopupMenuBar:: ıspalettemode

Açılan menü çubuğunun palet modunda olup olmadığını gösterir.

```
BOOL IsPaletteMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Palet modu etkinse TRUE, değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Menü çubuğu palet moduna ayarlandığında, menü öğeleri birden çok sütunda ve sınırlı sayıda satırda görüntülenir.

## <a name="cmfcpopupmenubarisribbonpanel"></a><a name="isribbonpanel"></a> CMFCPopupMenuBar:: ısribbonpanel

Bu bir şerit paneli (varsayılan olarak FALSE) olup olmadığını gösterir.

```
virtual BOOL IsRibbonPanel() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan olarak, bu bir şerit paneli olmadığını gösteren yanlış döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarisribbonpanelinregularmode"></a><a name="isribbonpanelinregularmode"></a> CMFCPopupMenuBar:: ısribbonpanelınregularmode

Bunun normal modda bir şerit paneli olup olmadığını gösterir (varsayılan olarak FALSE).

```
virtual BOOL IsRibbonPanelInRegularMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan olarak, bunun normal modda bir şerit paneli olmadığını gösteren yanlış döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarloadfromhash"></a><a name="loadfromhash"></a> CMFCPopupMenuBar:: LoadFromHash

Arşivlenmiş bir menü yükler.

```
BOOL LoadFromHash(HMENU hMenu);
```

### <a name="parameters"></a>Parametreler

*hMenu*<br/>
'ndaki Arşivlenen menüye yüklenecek bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Menü başarıyla yüklenirse TRUE, değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarm_bdisablesidebarinxpmode"></a><a name="m_bdisablesidebarinxpmode"></a> CMFCPopupMenuBar:: m_bDisableSideBarInXPMode

Uygulamanızın bir Windows XP görünümü olduğunda gri kenar çubuğu olup olmadığını belirten bir Boolean parametresi.

```
BOOL m_bDisableSideBarInXPMode;
```

### <a name="remarks"></a>Açıklamalar

Bu üye değişkeni yanlış olarak ayarlanırsa ve uygulamanızda bir Windows XP görünümü varsa, çerçeve uygulamanızda gri bir kenar çubuğu çizer.

Varsayılan değer FALSE 'dur.

## <a name="cmfcpopupmenubarrestoredelayedsubmenu"></a><a name="restoredelayedsubmenu"></a> CMFCPopupMenuBar:: Restoredelayedalt menü

Açılan menü çubuğunu kapatmak için geciken bir menü düğmesini geri yükler.

```
virtual void RestoreDelayedSubMenu();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarsetbuttonstyle"></a><a name="setbuttonstyle"></a> CMFCPopupMenuBar:: SetButtonStyle

Verilen dizindeki araç çubuğu düğmesinin stilini ayarlar. ( [CMFCToolBar:: SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle)geçersiz kılar.)

```
virtual void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
'ndaki Stili ayarlanacak olan araç çubuğu düğmesinin sıfır tabanlı dizini.

*nStyle*<br/>
'ndaki Düğmenin stili. Kullanılabilir araç çubuğu düğmesi stillerinin listesi için bkz. [ToolBar denetim stilleri](../../mfc/reference/toolbar-control-styles.md) .

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarsetoffset"></a><a name="setoffset"></a> CMFCPopupMenuBar:: SetOffset

Açılan menü çubuğunun satır konumunu ayarlar.

```cpp
void SetOffset(int iOffset);
```

### <a name="parameters"></a>Parametreler

*ıkayması*<br/>
'ndaki Açılan menü çubuğunun kaydırılacağı satır sayısı.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcpopupmenubarstartpopupmenutimer"></a><a name="startpopupmenutimer"></a> CMFCPopupMenuBar:: StartPopupMenuTimer

Belirtilen gecikmeli açılan menü düğmesi için süreölçeri başlatır.

```cpp
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,
    int nDelayFactor = 1);
```

### <a name="parameters"></a>Parametreler

*Pmenubtan*<br/>
'ndaki Gecikme süreölçeri ayarlanacak menü düğmesine yönelik işaretçi.

*nDelayFactor*<br/>
'ndaki Standart Menü gecikme süresi (genellikle yarım saniye ve beş saniye arasında) ile çarpmak için en az bir gecikme faktörü.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCPopupMenu sınıfı](../../mfc/reference/cmfcpopupmenu-class.md)
