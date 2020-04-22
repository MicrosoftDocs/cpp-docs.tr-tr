---
title: CMFCMenuBar Sınıfı
ms.date: 10/18/2018
f1_keywords:
- CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar
- AFXMENUBAR/CMFCMenuBar::AdjustLocations
- AFXMENUBAR/CMFCMenuBar::AllowChangeTextLabels
- AFXMENUBAR/CMFCMenuBar::AllowShowOnPaneMenu
- AFXMENUBAR/CMFCMenuBar::CalcFixedLayout
- AFXMENUBAR/CMFCMenuBar::CalcLayout
- AFXMENUBAR/CMFCMenuBar::CalcMaxButtonHeight
- AFXMENUBAR/CMFCMenuBar::CanBeClosed
- AFXMENUBAR/CMFCMenuBar::CanBeRestored
- AFXMENUBAR/CMFCMenuBar::Create
- AFXMENUBAR/CMFCMenuBar::CreateEx
- AFXMENUBAR/CMFCMenuBar::CreateFromMenu
- AFXMENUBAR/CMFCMenuBar::EnableHelpCombobox
- AFXMENUBAR/CMFCMenuBar::EnableMenuShadows
- AFXMENUBAR/CMFCMenuBar::GetAvailableExpandSize
- AFXMENUBAR/CMFCMenuBar::GetColumnWidth
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenu
- AFXMENUBAR/CMFCMenuBar::GetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::GetFloatPopupDirection
- AFXMENUBAR/CMFCMenuBar::GetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::GetHelpCombobox
- AFXMENUBAR/CMFCMenuBar::GetHMenu
- AFXMENUBAR/CMFCMenuBar::GetMenuFont
- AFXMENUBAR/CMFCMenuBar::GetMenuItem
- AFXMENUBAR/CMFCMenuBar::GetRowHeight
- AFXMENUBAR/CMFCMenuBar::GetSystemButton
- AFXMENUBAR/CMFCMenuBar::GetSystemButtonsCount
- AFXMENUBAR/CMFCMenuBar::GetSystemMenu
- AFXMENUBAR/CMFCMenuBar::HighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsButtonExtraSizeAvailable
- AFXMENUBAR/CMFCMenuBar::IsHighlightDisabledItems
- AFXMENUBAR/CMFCMenuBar::IsMenuShadows
- AFXMENUBAR/CMFCMenuBar::IsRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommands
- AFXMENUBAR/CMFCMenuBar::IsShowAllCommandsDelay
- AFXMENUBAR/CMFCMenuBar::LoadState
- AFXMENUBAR/CMFCMenuBar::OnChangeHot
- AFXMENUBAR/CMFCMenuBar::OnDefaultMenuLoaded
- AFXMENUBAR/CMFCMenuBar::OnSendCommand
- AFXMENUBAR/CMFCMenuBar::OnSetDefaultButtonText
- AFXMENUBAR/CMFCMenuBar::OnToolHitTest
- AFXMENUBAR/CMFCMenuBar::PreTranslateMessage
- AFXMENUBAR/CMFCMenuBar::RestoreOriginalstate
- AFXMENUBAR/CMFCMenuBar::SaveState
- AFXMENUBAR/CMFCMenuBar::SetDefaultMenuResId
- AFXMENUBAR/CMFCMenuBar::SetForceDownArrows
- AFXMENUBAR/CMFCMenuBar::SetMaximizeMode
- AFXMENUBAR/CMFCMenuBar::SetMenuButtonRTC
- AFXMENUBAR/CMFCMenuBar::SetMenuFont
- AFXMENUBAR/CMFCMenuBar::SetRecentlyUsedMenus
- AFXMENUBAR/CMFCMenuBar::SetShowAllCommands
helpviewer_keywords:
- CMFCMenuBar [MFC], AdjustLocations
- CMFCMenuBar [MFC], AllowChangeTextLabels
- CMFCMenuBar [MFC], AllowShowOnPaneMenu
- CMFCMenuBar [MFC], CalcFixedLayout
- CMFCMenuBar [MFC], CalcLayout
- CMFCMenuBar [MFC], CalcMaxButtonHeight
- CMFCMenuBar [MFC], CanBeClosed
- CMFCMenuBar [MFC], CanBeRestored
- CMFCMenuBar [MFC], Create
- CMFCMenuBar [MFC], CreateEx
- CMFCMenuBar [MFC], CreateFromMenu
- CMFCMenuBar [MFC], EnableHelpCombobox
- CMFCMenuBar [MFC], EnableMenuShadows
- CMFCMenuBar [MFC], GetAvailableExpandSize
- CMFCMenuBar [MFC], GetColumnWidth
- CMFCMenuBar [MFC], GetDefaultMenu
- CMFCMenuBar [MFC], GetDefaultMenuResId
- CMFCMenuBar [MFC], GetFloatPopupDirection
- CMFCMenuBar [MFC], GetForceDownArrows
- CMFCMenuBar [MFC], GetHelpCombobox
- CMFCMenuBar [MFC], GetHMenu
- CMFCMenuBar [MFC], GetMenuFont
- CMFCMenuBar [MFC], GetMenuItem
- CMFCMenuBar [MFC], GetRowHeight
- CMFCMenuBar [MFC], GetSystemButton
- CMFCMenuBar [MFC], GetSystemButtonsCount
- CMFCMenuBar [MFC], GetSystemMenu
- CMFCMenuBar [MFC], HighlightDisabledItems
- CMFCMenuBar [MFC], IsButtonExtraSizeAvailable
- CMFCMenuBar [MFC], IsHighlightDisabledItems
- CMFCMenuBar [MFC], IsMenuShadows
- CMFCMenuBar [MFC], IsRecentlyUsedMenus
- CMFCMenuBar [MFC], IsShowAllCommands
- CMFCMenuBar [MFC], IsShowAllCommandsDelay
- CMFCMenuBar [MFC], LoadState
- CMFCMenuBar [MFC], OnChangeHot
- CMFCMenuBar [MFC], OnDefaultMenuLoaded
- CMFCMenuBar [MFC], OnSendCommand
- CMFCMenuBar [MFC], OnSetDefaultButtonText
- CMFCMenuBar [MFC], OnToolHitTest
- CMFCMenuBar [MFC], PreTranslateMessage
- CMFCMenuBar [MFC], RestoreOriginalstate
- CMFCMenuBar [MFC], SaveState
- CMFCMenuBar [MFC], SetDefaultMenuResId
- CMFCMenuBar [MFC], SetForceDownArrows
- CMFCMenuBar [MFC], SetMaximizeMode
- CMFCMenuBar [MFC], SetMenuButtonRTC
- CMFCMenuBar [MFC], SetMenuFont
- CMFCMenuBar [MFC], SetRecentlyUsedMenus
- CMFCMenuBar [MFC], SetShowAllCommands
ms.assetid: 8a3ce4c7-b012-4dc0-b4f8-53c10b4b86b8
ms.openlocfilehash: f25bff9564eb7a4290f958f0b7810cac8ef7e238
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749623"
---
# <a name="cmfcmenubar-class"></a>CMFCMenuBar Sınıfı

Yerleştirme uygulayan bir menü çubuğu.
Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Sözdizimi

```
class CMFCMenuBar : public CMFCToolbar
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCMenuBar::Konumları Ayarla](#adjustlocations)|(Geçersiz `CMFCToolBar::AdjustLocations`kılar .)|
|[CMFCMenuBar::ChangeTextLabels izin ver](#allowchangetextlabels)|Araç çubuğu düğmelerinde resimlerin altında metin etiketlerinin gösterip gösterilemeyeceğini belirtir. [(CMFCToolBar geçersiz kılar::AllowChangeTextLabels](../../mfc/reference/cmfctoolbar-class.md#allowchangetextlabels).)|
|[CMFCMenuBar::İzinShowOnPaneMenu](#allowshowonpanemenu)|(Geçersiz `CPane::AllowShowOnPaneMenu`kılar .)|
|[CMFCMenuBar::CalcFixedLayout](#calcfixedlayout)|Araç çubuğunun yatay boyutunu hesaplar. (Geçersiz Kılar [CMFCToolBar::CalcFixedLayout](../../mfc/reference/cmfctoolbar-class.md#calcfixedlayout).)|
|[CMFCMenuBar::CalcLayout](#calclayout)|(Geçersiz `CMFCToolBar::CalcLayout`kılar .)|
|[CMFCMenuBar::CalcMaxButtonHeight](#calcmaxbuttonheight)|Araç çubuğundaki düğmelerin maksimum yüksekliğini hesaplar. [(Üstyüklemeler CMFCToolBar::CalcMaxButtonHeight](../../mfc/reference/cmfctoolbar-class.md#calcmaxbuttonheight).)|
|[CMFCMenuBar::Canbeclosed](#canbeclosed)|Kullanıcının araç çubuğunu kapatıp kapatamayacağını belirtir. [(CmFCToolBar geçersiz kılar::CanBeClosed](../../mfc/reference/cmfctoolbar-class.md#canbeclosed).)|
|[CMFCMenuBar::CanBeRestored](#canberestored)|Sistemin özelleştirmeden sonra bir araç çubuğunu özgün durumuna geri yükleyip geri yükleyemeyeceğini belirler. [(CmFCToolBar geçersiz kılar::CanBeRestored](../../mfc/reference/cmfctoolbar-class.md#canberestored).)|
|[CMFCMenuBar::Oluştur](#create)|Menü denetimi oluşturur ve nesneye `CMFCMenuBar` bağlar.|
|[CMFCMenuBar::CreateEx](#createex)|Ek stil `CMFCMenuBar` seçenekleri olan bir nesne oluşturur.|
|[CMFCMenuBar::CreateFromMenu](#createfrommenu)|Bir `CMFCMenuBar` nesneyi başharfe alar. Doldurulan bir şablon gibi davranan bir HMENU `CMFCMenuBar`parametresi kabul eder.|
|[CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox)|Menü çubuğunun sağ tarafında bulunan **yardım** açılan kutusunu etkinleştirin.|
|[CMFCMenuBar::EnableMenuShadows](#enablemenushadows)|Açılır menüler için gölgelerin görüntülenip görüntülenip görüntülenmeyeceğini belirtir.|
|[CMFCMenuBar::GetAvailableExpandSize](#getavailableexpandsize)|[(CPane geçersiz kılar::GetAvailableExpandSize](../../mfc/reference/cpane-class.md#getavailableexpandsize).)|
|[CMFCMenuBar::GetColumnWidth](#getcolumnwidth)|Araç çubuğu düğmelerinin genişliğini verir. [(CMFCToolBar geçersiz kılar::GetColumnWidth](../../mfc/reference/cmfctoolbar-class.md#getcolumnwidth).)|
|[CMFCMenuBar::GetDefaultMenu](#getdefaultmenu)|Kaynak dosyasındaki özgün menüye bir tanıtıcı döndürür.|
|[CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid)|Kaynak dosyasındaki özgün menünün kaynak tanımlayıcısını döndürür.|
|[CMFCMenuBar::GetFloatPopupDirection](#getfloatpopupdirection)||
|[CMFCMenuBar::GetForceDownArrows](#getforcedownarrows)||
|[CMFCMenuBar::GetHelpCombobox](#gethelpcombobox)|Bir işaretçiyi **Yardım** açılan kutusuna döndürür.|
|[CMFCMenuBar::GetHMenu](#gethmenu)|Tutamacı `CMFCMenuBar` nesneye iliştirilen menüye döndürür.|
|[CMFCMenuBar::GetMenuFont](#getmenufont)|Menü nesneleri için geçerli genel yazı tipini döndürür.|
|[CMFCMenuBar::GetMenuItem](#getmenuitem)|Sağlanan madde diziniile ilişkili araç çubuğu düğmesini döndürür.|
|[CMFCMenuBar::GetRowHeight](#getrowheight)|Araç çubuğu düğmelerinin yüksekliğini verir. [(CMFCToolBar geçersiz kılar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|
|[CMFCMenuBar::GetSystemButton](#getsystembutton)||
|[CMFCMenuBar::GetSystemButtonsCount](#getsystembuttonscount)||
|[CMFCMenuBar::GetSystemMenu](#getsystemmenu)||
|[CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems)|Devre dışı bırakılmış menü öğelerinin vurgulanıp vurgulanmadığını gösterir.|
|[CMFCMenuBar::IsbuttonExtrasizeKullanılabilir](#isbuttonextrasizeavailable)|Araç çubuğunun kenarlıkları uzatan düğmeleri görüntüleyip görüntüleyemeyeceğini belirler. [(Overrides CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|
|[CMFCMenuBar::IsHighlightDisabledItems](#ishighlightdisableditems)|Devre dışı bırakılan öğelerin vurgulanıp vurgulanmadığını gösterir.|
|[CMFCMenuBar::IsMenuShadows](#ismenushadows)|Açılır menüler için gölgelerin çizilip çizilmediğini gösterir.|
|[CMFCMenuBar::IsRecentlyUsed Menüler](#isrecentlyusedmenus)|Menü çubuğunda son kullanılan menü komutlarının görüntülenip görüntülenmediğini gösterir.|
|[CMFCMenuBar::IsShowAllKomutları](#isshowallcommands)|Açılır menülerin tüm komutları gösterip göstermediğini gösterir.|
|[CMFCMenuBar::IsShowAllCommandsDelay](#isshowallcommandsdelay)|Menülerin kısa bir gecikmeden sonra tüm komutları gösterip göstermediğini gösterir.|
|[CMFCMenuBar::LoadState](#loadstate)|Kayıt defterinden `CMFCMenuBar` nesnenin durumunu yükler.|
|[CMFCMenuBar::Onchangehot](#onchangehot)|Kullanıcı araç çubuğundaki bir düğmeyi seçtiğinde çerçeve tarafından çağrılır. [(Overrides CMFCToolBar::OnChangeHot](../../mfc/reference/cmfctoolbar-class.md#onchangehot).)|
|[CMFCMenuBar::OnDefaultMenuLoaded](#ondefaultmenuloaded)|Çerçeve penceresi kaynak dosyasından varsayılan menüyü yüklendiğinde çerçeve tarafından çağrılır.|
|[CMFCMenuBar::OnSendKomutu](#onsendcommand)|(Geçersiz `CMFCToolBar::OnSendCommand`kılar .)|
|[CMFCMenuBar::OnsetDefaultButtonText](#onsetdefaultbuttontext)|Bir menü özelleştirme modundayken ve kullanıcı bir menü öğesinin metnini değiştirdiğinde çerçeve tarafından çağrılır.|
|[CMFCMenuBar::OnToolhitTest](#ontoolhittest)|(Geçersiz `CMFCToolBar::OnToolHitTest`kılar .)|
|[CMFCMenuBar::PreTranslateMessage](#pretranslatemessage)|(Geçersiz `CMFCToolBar::PreTranslateMessage`kılar .)|
|[CMFCMenuBar::RestoreOriginalstate](#restoreoriginalstate)|Bir menü özelleştirme modundayken ve kullanıcı menü çubuğu için **Sıfırla'yı** seçerken çerçeve tarafından çağrılır.|
|[CMFCMenuBar::SaveState](#savestate)|`CMFCMenuBar` Nesnenin durumunu kayıt defterine kaydeder.|
|[CMFCMenuBar::SetDefaultMenuResId](#setdefaultmenuresid)|Kaynak dosyasındaki özgün menüyü ayarlar.|
|[CMFCMenuBar::SetForceDownArrows](#setforcedownarrows)||
|[CMFCMenuBar::SetMaximizeMode](#setmaximizemode)|Bir MDI alt penceresi ekran modunu değiştirdiğinde çerçeve tarafından çağrılır. MDI alt penceresi yeni en üst düzeye çıkarsa veya artık en üst düzeye çıkarılamazsa, bu yöntem menü çubuğunu güncelleştirir.|
|[CMFCMenuBar::SetMenuButtonRTC](#setmenubuttonrtc)|Kullanıcı dinamik olarak menü düğmeleri oluşturduğunda oluşturulan çalışma zamanı sınıf bilgilerini ayarlar.|
|[CMFCMenuBar::SetMenuFont](#setmenufont)|Uygulamadaki tüm menüler için yazı tipini ayarlar.|
|[CMFCMenuBar::SetRecentlyUsed Menüler](#setrecentlyusedmenus)|Menü çubuğunun en son kullanılan menü komutlarını gösterip görüntülemediğini belirtir.|
|[CMFCMenuBar::SetShowAllKomutları](#setshowallcommands)|Menü çubuğunun tüm komutları gösterip göstermediğini belirtir.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `CMFCMenuBar` yerleştirme işlevini uygulayan bir menü çubuğudur. Kapatılamaz, ancak bir araç çubuğuna benzer - her zaman görüntülenir.

`CMFCMenuBar`en son kullanılan menü öğesi nesnelerini görüntüleme seçeneğini destekler. Bu seçenek etkinleştirilirse, `CMFCMenuBar` ilk görüntülemede kullanılabilir komutların yalnızca bir alt kümesi görüntülenir. Bundan sonra, son kullanılan komutlar özgün komut alt kümesiyle birlikte görüntülenir. Buna ek olarak, kullanıcı her zaman kullanılabilir tüm komutları görüntülemek için menüyü genişletebilirsiniz. Böylece, kullanılabilir her komut sürekli olarak görüntülenecek veya yalnızca yakın zamanda seçiliyse görüntülenecek şekilde yapılandırılır.

Bir `CMFCMenuBar` nesneyi kullanmak için, ana pencere çerçevesi nesnesine gömün. İletiyi `WM_CREATE` işlerken, `CMFCMenuBar::Create` `CMFCMenuBar::CreateEx`arama veya . Hangi oluşturma işlevini kullandığınızdan bağımsız olarak, ana çerçeve penceresine bir işaretçi geçirin. Ardından [CFrameWndEx'i arayarak yerleştirmeyi etkinleştirin::EtkinleştirDocking.](../../mfc/reference/cframewndex-class.md#enabledocking) [CFrameWndEx::DockPane' yi](../../mfc/reference/cframewndex-class.md#dockpane)arayarak bu menüyü sabitleyin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfta çeşitli yöntemlerin `CMFCMenuBar` nasıl kullanılacağını göstermektedir. Örnek, bölmenin stilini nasıl ayarlanacağını, özelleştirme düğmesini etkinleştirmeyi, Yardım kutusunu etkinleştirmeyi, açılır menüler için gölgeleri etkinleştirmeyi ve menü çubuğunu nasıl güncelleştireceklerini gösterir. Bu kod parçacığı [IE Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]
[!code-cpp[NVC_MFC_IEDemo#3](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[Cpane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[Cmfctoolbar](../../mfc/reference/cmfctoolbar-class.md)

`CMFCMenuBar`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxmenubar.h

## <a name="cmfcmenubaradjustlocations"></a><a name="adjustlocations"></a>CMFCMenuBar::Konumları Ayarla

Menü çubuğundaki menü öğelerinin konumlarını ayarlar.

```
virtual void AdjustLocations();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubarallowchangetextlabels"></a><a name="allowchangetextlabels"></a>CMFCMenuBar::ChangeTextLabels izin ver

Menü çubuğundaki resimlerin altında metin etiketlerine izin verilip verilmediğini belirler.

```
virtual BOOL AllowChangeTextLabels() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı resimlerin altında metin etiketleri göstermeyi seçebiliyorsa TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubarallowshowonpanemenu"></a><a name="allowshowonpanemenu"></a>CMFCMenuBar::İzinShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubarcalcfixedlayout"></a><a name="calcfixedlayout"></a>CMFCMenuBar::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parametreler

[içinde] *bStretch*<br/>

[içinde] *bHorz*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubarcalclayout"></a><a name="calclayout"></a>CMFCMenuBar::CalcLayout

```
virtual CSize CalcLayout(
    DWORD dwMode,
    int nLength = -1);
```

### <a name="parameters"></a>Parametreler

[içinde] *dwMode*<br/>

[içinde] *nUzunluk*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubarcalcmaxbuttonheight"></a><a name="calcmaxbuttonheight"></a>CMFCMenuBar::CalcMaxButtonHeight

```
virtual int CalcMaxButtonHeight();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubarcanbeclosed"></a><a name="canbeclosed"></a>CMFCMenuBar::Canbeclosed

```
virtual BOOL CanBeClosed() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubarcanberestored"></a><a name="canberestored"></a>CMFCMenuBar::CanBeRestored

```
virtual BOOL CanBeRestored() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubarcreate"></a><a name="create"></a>CMFCMenuBar::Oluştur

Menü denetimi oluşturur ve [cmfcMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesnesine bağlar.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,
    UINT nID = AFX_IDW_MENUBAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
[içinde] Yeni `CMFCMenuBar` nesne için ana pencereyi işaretçi.

*Dwstyle*<br/>
[içinde] Yeni menü çubuğunun tarzı.

*Nıd*<br/>
[içinde] Menü çubuğunun alt penceresinin kimliği.

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bir `CMFCMenuBar` nesne inşa ettikten sonra, çağırmalısınız. `Create` Bu yöntem `CMFCMenuBar` denetimi oluşturur ve `CMFCMenuBar` nesneye bağlar.

Araç çubuğu stilleri hakkında daha fazla bilgi için [Bkz. CBasePane::SetPaneStyle](../../mfc/reference/cbasepane-class.md#setpanestyle).

## <a name="cmfcmenubarcreateex"></a><a name="createex"></a>CMFCMenuBar::CreateEx

Belirtilen genişletilmiş stiller içeren bir [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesnesi oluşturur.

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = TBSTYLE_FLAT,
    DWORD dwStyle = AFX_DEFAULT_TOOLBAR_STYLE,
    CRect rcBorders = CRect(1,
    1,
    1,
    1),
    UINT nID =AFX_IDW_MENUBAR);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
[içinde] Yeni `CMFCMenuBar` nesnenin ana penceresine işaretçi.

*dwCtrlStyle*<br/>
[içinde] Yeni menü çubuğu için ek stiller.

*Dwstyle*<br/>
[içinde] Yeni menü çubuğunun ana tarzı.

*rcBorders*<br/>
[içinde] Nesnenin kenarlıkları için boyutlar belirten bir `CRect` parametre. `CMFCMenuBar`

*Nıd*<br/>
[içinde] Menü çubuğunun alt penceresinin kimliği.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[CMFCMenuBar](#create) yerine bu işlevi kullanmalısınız::Araç çubuğu stiline ek olarak stilleri belirtmek istediğinizde oluşturun. Sık kullanılan bazı ek stiller TBSTYLE_TRANSPARENT ve CBRS_TOP.

Ek stillerin listeleri [için, Bkz. Araç Çubuğu Denetimi ve Düğme Stilleri,](/windows/win32/Controls/toolbar-control-and-button-styles) [ortak denetim stilleri](/windows/win32/Controls/common-control-styles)ve ortak pencere [stilleri.](/windows/win32/winmsg/window-styles)

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın yönteminin `CreateEx` nasıl `CMFCMenuBar` kullanılacağını göstermektedir. Bu kod parçacığı [IE Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_IEDemo#1](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_1.h)]
[!code-cpp[NVC_MFC_IEDemo#2](../../mfc/reference/codesnippet/cpp/cmfcmenubar-class_3.cpp)]

## <a name="cmfcmenubarcreatefrommenu"></a><a name="createfrommenu"></a>CMFCMenuBar::CreateFromMenu

[CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesnesi başharflerini. Bu yöntem, `CMFCMenuBar` HMENU parametresi sonra nesne modelleri.

```
virtual void CreateFromMenu(
    HMENU hMenu,
    BOOL bDefaultMenu = FALSE,
    BOOL bForceUpdate = FALSE);
```

### <a name="parameters"></a>Parametreler

*Hmenu*<br/>
[içinde] Menü kaynağına bir tanıtıcı. `CreateFromMenu`için bir şablon olarak `CMFCMenuBar`bu kaynağı kullanır.

*bDefaultMenü*<br/>
[içinde] Yeni menünün varsayılan menü olup olmadığını belirten bir Boolean.

*bForceUpdate*<br/>
[içinde] Bu yöntemin menü güncelleştirmesi zorlayıp zorladığını belirten bir Boolean.

### <a name="remarks"></a>Açıklamalar

Menü denetiminin menü kaynağıyla aynı menü öğelerine sahip olmasını istiyorsanız bu yöntemi kullanın. [CMFCMenuBar'ı](#create) aradıktan sonra bu yöntemi ararsınız::Oluştur veya [CMFCMenuBar::CreateEx](#createex).

## <a name="cmfcmenubarenablehelpcombobox"></a><a name="enablehelpcombobox"></a>CMFCMenuBar::EnableHelpCombobox

Menü çubuğunun sağ tarafında bulunan **yardım** açılan kutusunu etkinleştirin.

```cpp
void EnableHelpCombobox(
    UINT uiID,
    LPCTSTR lpszPrompt = NULL,
    int nComboBoxWidth = 150);
```

### <a name="parameters"></a>Parametreler

*uiID*<br/>
[içinde] **Yardım** açılan kutusunun düğmesinin komut kimliği.

*lpszPrompt*<br/>
[içinde] Boş ve etkin değilse, çerçevenin açılan kutuda görüntülenebilen metni içeren dize. Örneğin, "Metni buraya girin".

*nComboBoxGenişliği*<br/>
[içinde] Piksellerde açılan kutu için düğmenin genişliği.

### <a name="remarks"></a>Açıklamalar

**Yardım** açılan kutusu, Microsoft Word'ün menü çubuğundaki **Yardım** açılan kutusunu andırır.

*UIID* kümesi 0 ile bu yöntemi çağırdığınızda, bu yöntem açılan kutuyu gizler. Aksi takdirde, bu yöntem menü çubuğunuzun sağ tarafında otomatik olarak açılan kutuyu görüntüler. Bu yöntemi aradıktan sonra [CMFCMenuBar::GetHelpCombobox'ı](#gethelpcombobox) arayarak eklenen [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) nesnesine işaretçi edinin.

## <a name="cmfcmenubarenablemenushadows"></a><a name="enablemenushadows"></a>CMFCMenuBar::EnableMenuShadows

Açılır menüler için gölgeler sağlar.

```
static void EnableMenuShadows(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] Açılır menüler için gölgelerin etkinlenip etkinleştirilmediğini belirten boolean parametresi.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin kullandığı algoritma karmaşıktır ve uygulamanızın daha yavaş sistemlerdeki performansını düşürebilir.

## <a name="cmfcmenubargetavailableexpandsize"></a><a name="getavailableexpandsize"></a>CMFCMenuBar::GetAvailableExpandSize

```
virtual int GetAvailableExpandSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubargetcolumnwidth"></a><a name="getcolumnwidth"></a>CMFCMenuBar::GetColumnWidth

```
virtual int GetColumnWidth() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubargetdefaultmenu"></a><a name="getdefaultmenu"></a>CMFCMenuBar::GetDefaultMenu

Orijinal menüye bir tanıtıcı alır. Çerçeve, kaynak dosyasından özgün menüyü yükler.

```
HMENU GetDefaultMenu() const;
```

### <a name="return-value"></a>Dönüş Değeri

Menü kaynağına bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Uygulamanız bir menü özelleştiriciyse, özgün menüye bir tanıtıcı almak için bu yöntemi kullanabilirsiniz.

## <a name="cmfcmenubargetdefaultmenuresid"></a><a name="getdefaultmenuresid"></a>CMFCMenuBar::GetDefaultMenuResId

Varsayılan menü için kaynak tanımlayıcısını alır.

```
UINT GetDefaultMenuResId() const;
```

### <a name="return-value"></a>Dönüş Değeri

Menü kaynak tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Çerçeve, kaynak dosyasından `CMFCMenuBar` nesnenin varsayılan menüsünü yükler.

## <a name="cmfcmenubargetfloatpopupdirection"></a><a name="getfloatpopupdirection"></a>CMFCMenuBar::GetFloatPopupDirection

```
int GetFloatPopupDirection(CMFCToolBarMenuButton* pButton);
```

### <a name="parameters"></a>Parametreler

[içinde] *pDüğme*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubargetforcedownarrows"></a><a name="getforcedownarrows"></a>CMFCMenuBar::GetForceDownArrows

```
BOOL GetForceDownArrows();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubargethelpcombobox"></a><a name="gethelpcombobox"></a>CMFCMenuBar::GetHelpCombobox

Bir işaretçiyi **Yardım** açılan kutusuna döndürür.

```
CMFCToolBarComboBoxButton* GetHelpCombobox();
```

### <a name="return-value"></a>Dönüş Değeri

**Yardım** açılan kutusuna bir işaretçi. **Yardım** açılan kutusu gizliyse veya etkin değilse NULL.

### <a name="remarks"></a>Açıklamalar

**Yardım** açılan kutusu menü çubuğunun sağ tarafında yer alır. Bu açılan kutuyu etkinleştirmek için [CMFCMenuBar::EnableHelpCombobox](#enablehelpcombobox) yöntemini arayın.

## <a name="cmfcmenubargethmenu"></a><a name="gethmenu"></a>CMFCMenuBar::GetHMenu

[CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesnesine iliştirilen menüye tutamacı alır.

```
HMENU GetHMenu() const;
```

## <a name="cmfcmenubargetmenufont"></a><a name="getmenufont"></a>CMFCMenuBar::GetMenuFont

Geçerli menü yazı tipini alır.

```
static const CFont& GetMenuFont(BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Parametreler

*bHorz*<br/>
[içinde] Yatay veya dikey yazı tipini döndürüp döndürmeyeceğini belirten bir Boolean parametresi. TRUE yatay yazı tipini gösterir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli menü çubuğu yazı tipini içeren bir [CFont](../../mfc/reference/cfont-class.md) parametresine işaretçi.

### <a name="remarks"></a>Açıklamalar

Döndürülen yazı tipi, uygulama için genel bir parametredir. Tüm `CMFCMenuBar` nesneler için iki genel yazı tipi korunur. Bu ayrı yazı tipleri yatay ve dikey menü çubukları için kullanılır.

## <a name="cmfcmenubargetmenuitem"></a><a name="getmenuitem"></a>CMFCMenuBar::GetMenuItem

Öğe dizini dayalı bir menü çubuğunda bir [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) nesnesi alır.

```
CMFCToolBarButton* GetMenuItem(int iItem) const;
```

### <a name="parameters"></a>Parametreler

*iÖğe*<br/>
[içinde] Döndürülecek menü öğesinin dizini.

### <a name="return-value"></a>Dönüş Değeri

*iItem*tarafından `CMFCToolBarButton` belirtilen dizinle eşleşen nesneye işaretçi. Dizin geçersizse NULL.

## <a name="cmfcmenubargetrowheight"></a><a name="getrowheight"></a>CMFCMenuBar::GetRowHeight

```
virtual int GetRowHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubargetsystembutton"></a><a name="getsystembutton"></a>CMFCMenuBar::GetSystemButton

```
CMFCToolBarMenuButtonsButton* GetSystemButton(
    UINT uiBtn,
    BOOL bByCommand = TRUE) const;
```

### <a name="parameters"></a>Parametreler

[içinde] *uiBtn*<br/>

[içinde] *bByCommand*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubargetsystembuttonscount"></a><a name="getsystembuttonscount"></a>CMFCMenuBar::GetSystemButtonsCount

```
int GetSystemButtonsCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubargetsystemmenu"></a><a name="getsystemmenu"></a>CMFCMenuBar::GetSystemMenu

```
CMFCToolBarSystemMenuButton* GetSystemMenu() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubarhighlightdisableditems"></a><a name="highlightdisableditems"></a>CMFCMenuBar::HighlightDisabledItems

Çerçevenin devre dışı bırakılan menü öğelerini vurgulayıp vurgulamadığını denetler.

```
static void HighlightDisabledItems(BOOL bHighlight = TRUE);
```

### <a name="parameters"></a>Parametreler

*bVurgu*<br/>
[içinde] Çerçevenin kullanılamayan menü öğelerini vurgulayıp vurgulamadığını gösteren bir Boolean parametresi.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, kullanıcı fare işaretçisini üzerlerine konumlandırdığında, çerçeve kullanılamayan menü öğelerini vurgulamaz.

## <a name="cmfcmenubarisbuttonextrasizeavailable"></a><a name="isbuttonextrasizeavailable"></a>CMFCMenuBar::IsbuttonExtrasizeKullanılabilir

```
virtual BOOL IsButtonExtraSizeAvailable() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubarishighlightdisableditems"></a><a name="ishighlightdisableditems"></a>CMFCMenuBar::IsHighlightDisabledItems

Çerçevenin kullanılamayan menü öğelerini vurgulayıp vurgulamadığını gösterir.

```
static BOOL IsHighlightDisabledItems();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanılamayan menü öğeleri vurgulanırsa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, kullanıcı fare işaretçisini üzerlerine konumlandırdığında, çerçeve kullanılamayan menü öğelerini vurgulamaz. Bu özelliği etkinleştirmek için [CMFCMenuBar::HighlightDisabledItems](#highlightdisableditems) yöntemini kullanın.

## <a name="cmfcmenubarismenushadows"></a><a name="ismenushadows"></a>CMFCMenuBar::IsMenuShadows

Çerçevenin açılır menüler için gölgeler çizip çizmeyeceğini gösterir.

```
static BOOL IsMenuShadows();
```

### <a name="return-value"></a>Dönüş Değeri

Çerçeve menü gölgelerini çekiyorsa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu özelliği etkinleştirmek veya devre dışı bırakmak için [CMFCMenuBar::EnableMenuShadows](#enablemenushadows) yöntemini kullanın.

## <a name="cmfcmenubarisrecentlyusedmenus"></a><a name="isrecentlyusedmenus"></a>CMFCMenuBar::IsRecentlyUsed Menüler

Menü çubuğunda son kullanılan menü komutlarının görüntülenip görüntülenmediğini gösterir.

```
static BOOL IsRecentlyUsedMenus();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne son `CMFCMenuBar` kullanılan menü komutlarını gösteriyorsa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Menü çubuğunun son kullanılan menü komutlarını gösterip göstermediğini denetlemek için [CMFCMenuBar::SetRecentlyUsedMenüs](#setrecentlyusedmenus) işlevini kullanın.

## <a name="cmfcmenubarisshowallcommands"></a><a name="isshowallcommands"></a>CMFCMenuBar::IsShowAllKomutları

Menülerin tüm komutları gösterip göstermediğini gösterir.

```
static BOOL IsShowAllCommands();
```

### <a name="return-value"></a>Dönüş Değeri

Tüm komutları `CMFCMenuBar` görüntülerse sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir `CMFCMenuBar` nesne, tüm komutları gösterecek veya yalnızca bir komut alt kümesini gösterecek şekilde yapılandırılabilir. Bu özellik hakkında daha fazla bilgi için [CMFCMenuBar Sınıfı'na](../../mfc/reference/cmfcmenubar-class.md)bakın.

`IsShowAllCommands`bu özelliğin `CMFCMenuBar` nesne için nasıl yapılandırıldığı size söyleyecektir. Hangi menü komutlarının gösterildiğini denetlemek için [CMFCMenuBar::SetShowAllKomutları](#setshowallcommands) ve [CMFCMenuBar::SetRecentlyUsedMenüs](#setrecentlyusedmenus)yöntemlerini kullanın.

## <a name="cmfcmenubarisshowallcommandsdelay"></a><a name="isshowallcommandsdelay"></a>CMFCMenuBar::IsShowAllCommandsDelay

[CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesnesinin kısa bir gecikmeden sonra tüm komutları gösterip görüntülemediğini gösterir.

```
static BOOL IsShowAllCommandsDelay();
```

### <a name="return-value"></a>Dönüş Değeri

Menü çubuğu kısa bir gecikmeden sonra tam menüler görüntülerse sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir menü çubuğunu son kullanılan öğeleri görüntülemek üzere yapılandırırken, menü çubuğu tüm menüyü iki şekilde görüntüler:

- Kullanıcı nın imleci menünün altındaki ok üzerinde gezinmesinden sonra programlanmış bir gecikmeden sonra tüm menüyü görüntüleyin.

- Kullanıcı menünün altındaki oku tıklattıktan sonra tüm menüyü görüntüleyin.

Varsayılan olarak, `CMFCMenuBar` tüm nesneler kısa bir gecikmeden sonra tam menüyü görüntülemek için bu seçeneği kullanır. Bu seçenek `CMFCMenuBar` sınıfta programlı olarak değiştirilemez. Ancak, kullanıcı **Özelleştir** iletişim kutusunu kullanarak araç çubuğu özelleştirme sırasında davranışı değiştirebilirsiniz...

## <a name="cmfcmenubarloadstate"></a><a name="loadstate"></a>CMFCMenuBar::LoadState

Windows kayıt defterinden menü çubuğunun durumunu yükler.

```
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT)-1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[içinde] Windows kayıt defteri anahtarının yolunu içeren dize.

*Nındex*<br/>
[içinde] Menü çubuğunun denetim kimliği.

*uiID*<br/>
[içinde] Ayrılmış bir değer.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olsaydı DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Menü çubuğunun durumunu kayıt defterine kaydetmek için [CMFCMenuBar::SaveState](#savestate) yöntemini kullanın. Kaydedilen bilgiler menü öğelerini, dock durumunu ve menü çubuğunun konumunu içerir.

Çoğu durumda uygulamanız aramaz. `LoadState` Çalışma alanını başlattığında çerçeve bu yöntemi çağırır.

## <a name="cmfcmenubaronchangehot"></a><a name="onchangehot"></a>CMFCMenuBar::Onchangehot

```
virtual void OnChangeHot(int iHot);
```

### <a name="parameters"></a>Parametreler

[içinde] *iSıcak*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubarondefaultmenuloaded"></a><a name="ondefaultmenuloaded"></a>CMFCMenuBar::OnDefaultMenuLoaded

Çerçeve, menü kaynağını kaynak dosyasından yüklerken bu yöntemi çağırır.

```
virtual void OnDefaultMenuLoaded(HMENU hMenu);
```

### <a name="parameters"></a>Parametreler

*Hmenu*<br/>
[içinde] `CMFCMenuBar` Nesneye iliştirilen menünün tutamacı.

### <a name="remarks"></a>Açıklamalar

Bu işlevin varsayılan uygulaması hiçbir şey yapmaz. Çerçeve kaynak dosyasından bir menü kaynağı yüklendikten sonra özel kodu yürütmek için bu işlevi geçersiz kılın.

## <a name="cmfcmenubaronsendcommand"></a><a name="onsendcommand"></a>CMFCMenuBar::OnSendKomutu

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Parametreler

[içinde] *pDüğme*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubaronsetdefaultbuttontext"></a><a name="onsetdefaultbuttontext"></a>CMFCMenuBar::OnsetDefaultButtonText

Kullanıcı menü çubuğundaki bir öğenin metnini değiştirdiğinde çerçeve bu yöntemi çağırır.

```
virtual BOOL OnSetDefaultButtonText(CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Parametreler

*pDüğme*<br/>
[içinde] [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) nesnesine kullanıcının özelleştirmek istediği bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Çerçeve menü çubuğuna kullanıcı değişiklikleri uygularsa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem için varsayılan uygulama, düğmenin metnini kullanıcının sağladığı metne değiştirir.

## <a name="cmfcmenubarontoolhittest"></a><a name="ontoolhittest"></a>CMFCMenuBar::OnToolhitTest

```
virtual INT_PTR OnToolHitTest(
    CPoint point,
    TOOLINFO* pTI) const;
```

### <a name="parameters"></a>Parametreler

[içinde] *nokta*<br/>

[içinde] *pTI*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubarpretranslatemessage"></a><a name="pretranslatemessage"></a>CMFCMenuBar::PreTranslateMessage

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>Parametreler

[içinde] *pMsg*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubarrestoreoriginalstate"></a><a name="restoreoriginalstate"></a>CMFCMenuBar::RestoreOriginalstate

Kullanıcı **Özelleştir** iletişim kutusundan **Sıfırla'yı** seçtiğinde çerçeve tarafından çağrılır.

```
virtual BOOL RestoreOriginalstate();
```

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kullanıcı özelleştirme menüsünden **Sıfırla'yı** seçtiğinde çağrılır. Menü çubuğunun durumunu programlı olarak sıfırlamak için bu yöntemi el ile de arayabilirsiniz. Bu yöntem, kaynak dosyasından özgün durumu yükler.

Kullanıcı **Sıfırla** seçeneğini seçtiğinde herhangi bir işlem yapmak istiyorsanız bu yöntemi geçersiz kılın.

## <a name="cmfcmenubarsavestate"></a><a name="savestate"></a>CMFCMenuBar::SaveState

[CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesnesinin durumunu Windows kayıt defterine kaydeder.

```
virtual BOOL SaveState (
    LPCTSTR lpszProfileName = NULL,
    int nIndex = -1,
    UINT uiID = (UINT)-1);
```

### <a name="parameters"></a>Parametreler

*lpszProfileName*<br/>
[içinde] Windows kayıt defteri anahtarının yolunu içeren dize.

*Nındex*<br/>
[içinde] Menü çubuğunun denetim kimliği.

*uiID*<br/>
[içinde] Ayrılmış bir değer.

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; aksi takdirde YANLIŞ;

### <a name="remarks"></a>Açıklamalar

Genellikle, uygulamaaramaz `SaveState`. Çalışma alanı seri hale geldiğinde çerçeve bu yöntemi çağırır. Daha fazla bilgi için [Bkz. CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate).

Kaydedilen bilgiler menü öğelerini, dock durumunu ve menü çubuğunun konumunu içerir.

## <a name="cmfcmenubarsetdefaultmenuresid"></a><a name="setdefaultmenuresid"></a>CMFCMenuBar::SetDefaultMenuResId

Kaynak kimliğine dayalı bir [CMFCMenuBar](../../mfc/reference/cmfcmenubar-class.md) nesnesinin varsayılan menüsünü ayarlar.

```cpp
void SetDefaultMenuResId(UINT uiResId);
```

### <a name="parameters"></a>Parametreler

*uiResId*<br/>
[içinde] Yeni varsayılan menü için kaynak kimliği.

### <a name="remarks"></a>Açıklamalar

[CMFCMenuBar::Geri YüklemeOriginalstate](#restoreoriginalstate) yöntemi kaynak dosyasından varsayılan menüyü geri yükler.

Varsayılan menüyü geri almadan almak için [CMFCMenuBar::GetDefaultMenuResId](#getdefaultmenuresid) yöntemini kullanın.

## <a name="cmfcmenubarsetforcedownarrows"></a><a name="setforcedownarrows"></a>CMFCMenuBar::SetForceDownArrows

```cpp
void SetForceDownArrows(BOOL bValue);
```

### <a name="parameters"></a>Parametreler

[içinde] *bDeğer*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcmenubarsetmaximizemode"></a><a name="setmaximizemode"></a>CMFCMenuBar::SetMaximizeMode

Çerçeve, bir MDI ekran modunu değiştirdiğinde ve menü çubuğu güncelleştirildiğinde bu yöntemi çağırır.

```cpp
void SetMaximizeMode(
    BOOL bMax,
    CWnd* pWnd = NULL,
    BOOL bRecalcLayout = TRUE);
```

### <a name="parameters"></a>Parametreler

*bMax*<br/>
[içinde] Modu belirten bir Boolean. Daha fazla bilgi için Açıklamalar bölümüne bakın.

*Pwnd*<br/>
[içinde] Değişen MDI alt penceresiiçin bir işaretçi.

*bRecalcLayout*<br/>
[içinde] Menü çubuğunun düzeninin hemen yeniden hesaplanıp yeniden hesaplanmaması gerektiğini belirten bir Boolean.

### <a name="remarks"></a>Açıklamalar

Bir MDI alt penceresi en üst düzeye çıkarıldığında, MDI ana çerçeve penceresine bağlı bir menü çubuğu sistem menüsünü ve **Simge durumuna küçült, Simgedurumuna Sökve** **kapat** düğmelerini görüntüler. **Maximize** *bMax* TRUE ise ve *pWnd* NULL değilse, MDI alt penceresi en üst düzeye çıkar ve menü çubuğu ek denetimleri dahil etmelidir. Aksi takdirde, menü çubuğu normal durumuna döner.

## <a name="cmfcmenubarsetmenubuttonrtc"></a><a name="setmenubuttonrtc"></a>CMFCMenuBar::SetMenuButtonRTC

Kullanıcı menü düğmeleri oluşturduğunda çerçevenin kullandığı çalışma zamanı sınıf bilgilerini ayarlar.

```cpp
void SetMenuButtonRTC(CRuntimeClass* pMenuButtonRTC);
```

### <a name="parameters"></a>Parametreler

*pMenuButtonRTC*<br/>
[içinde] [CMFCMenuButton Sınıfından](../../mfc/reference/cmfcmenubutton-class.md)türetilen bir sınıfın [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bilgileri.

### <a name="remarks"></a>Açıklamalar

Bir kullanıcı menü çubuğuna yeni düğmeler eklediğinde, çerçeve düğmeleri dinamik olarak oluşturur. Varsayılan olarak, `CMFCMenuButton` nesneler oluşturur. Çerçevenin oluşturduğu düğme nesnelerinin türünü değiştirmek için bu yöntemi geçersiz kılın.

## <a name="cmfcmenubarsetmenufont"></a><a name="setmenufont"></a>CMFCMenuBar::SetMenuFont

Uygulamanızdaki tüm menü çubuklarının yazı tipini ayarlar.

```
static BOOL SetMenuFont(
    LPLOGFONT lpLogFont,
    BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpLogFont*<br/>
[içinde] Ayarlayacak yazı tipini tanımlayan [LOGFONT](/windows/win32/api/dimm/ns-dimm-logfonta) yapısına işaretçi.

*bHorz*<br/>
[içinde] *LPLogFont* parametresinin dikey yazı tipi için kullanılmasını istiyorsanız DOĞRU, yatay yazı tipi için kullanılmasını istiyorsanız FALSE.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olsaydı DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Tüm `CMFCMenuBar` nesneler için iki yazı tipi kullanılır. Bu ayrı yazı tipleri yatay ve dikey menü çubukları için kullanılır.

Yazı tipi ayarları genel değişkenlerdir `CMFCMenuBar` ve tüm nesneleri etkiler.

## <a name="cmfcmenubarsetrecentlyusedmenus"></a><a name="setrecentlyusedmenus"></a>CMFCMenuBar::SetRecentlyUsed Menüler

Menü çubuğunun en son kullanılan menü komutlarını gösterip görüntülemediğini denetler.

```
static void SetRecentlyUsedMenus (BOOL bOn = TRUE);
```

### <a name="parameters"></a>Parametreler

*Bon*<br/>
[içinde] Son kullanılan menü komutlarının görüntülenip görüntülenmediğini kontrol eden bir Boolean.

## <a name="cmfcmenubarsetshowallcommands"></a><a name="setshowallcommands"></a>CMFCMenuBar::SetShowAllKomutları

Bir menünün tüm kullanılabilir komutları gösterip göstermediğini denetler.

```
static void SetShowAllCommands(BOOL bShowAllCommands = TRUE);
```

### <a name="parameters"></a>Parametreler

*bShowAllKomutları*<br/>
[içinde] Açılır menütüm menü komutlarını gösterip göstermediğini belirten bir Boolean parametresi.

### <a name="remarks"></a>Açıklamalar

Menü tüm menü komutlarını görüntülemiyorsa, nadiren kullanılan komutları gizler. Menü komutlarını görüntüleme hakkında daha fazla bilgi için [CMFCMenuBar Class'a](../../mfc/reference/cmfcmenubar-class.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)
