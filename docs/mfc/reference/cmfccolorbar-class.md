---
title: CMFCColorBar Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCColorBar
- AFXCOLORBAR/CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::CMFCColorBar
- AFXCOLORBAR/CMFCColorBar::ContextToSize
- AFXCOLORBAR/CMFCColorBar::CreateControl
- AFXCOLORBAR/CMFCColorBar::Create
- AFXCOLORBAR/CMFCColorBar::EnableAutomaticButton
- AFXCOLORBAR/CMFCColorBar::EnableOtherButton
- AFXCOLORBAR/CMFCColorBar::GetColor
- AFXCOLORBAR/CMFCColorBar::GetCommandID
- AFXCOLORBAR/CMFCColorBar::GetHighlightedColor
- AFXCOLORBAR/CMFCColorBar::GetHorzMargin
- AFXCOLORBAR/CMFCColorBar::GetVertMargin
- AFXCOLORBAR/CMFCColorBar::IsTearOff
- AFXCOLORBAR/CMFCColorBar::SetColor
- AFXCOLORBAR/CMFCColorBar::SetColorName
- AFXCOLORBAR/CMFCColorBar::SetCommandID
- AFXCOLORBAR/CMFCColorBar::SetDocumentColors
- AFXCOLORBAR/CMFCColorBar::SetHorzMargin
- AFXCOLORBAR/CMFCColorBar::SetVertMargin
- AFXCOLORBAR/CMFCColorBar::AdjustLocations
- AFXCOLORBAR/CMFCColorBar::AllowChangeTextLabels
- AFXCOLORBAR/CMFCColorBar::AllowShowOnList
- AFXCOLORBAR/CMFCColorBar::CalcSize
- AFXCOLORBAR/CMFCColorBar::CreatePalette
- AFXCOLORBAR/CMFCColorBar::GetColorGridSize
- AFXCOLORBAR/CMFCColorBar::GetExtraHeight
- AFXCOLORBAR/CMFCColorBar::InitColors
- AFXCOLORBAR/CMFCColorBar::OnKey
- AFXCOLORBAR/CMFCColorBar::OnSendCommand
- AFXCOLORBAR/CMFCColorBar::OnUpdateCmdUI
- AFXCOLORBAR/CMFCColorBar::OpenColorDialog
- AFXCOLORBAR/CMFCColorBar::Rebuild
- AFXCOLORBAR/CMFCColorBar::SelectPalette
- AFXCOLORBAR/CMFCColorBar::SetPropList
- AFXCOLORBAR/CMFCColorBar::ShowCommandMessageString
helpviewer_keywords:
- CMFCColorBar [MFC], CMFCColorBar
- CMFCColorBar [MFC], ContextToSize
- CMFCColorBar [MFC], CreateControl
- CMFCColorBar [MFC], Create
- CMFCColorBar [MFC], EnableAutomaticButton
- CMFCColorBar [MFC], EnableOtherButton
- CMFCColorBar [MFC], GetColor
- CMFCColorBar [MFC], GetCommandID
- CMFCColorBar [MFC], GetHighlightedColor
- CMFCColorBar [MFC], GetHorzMargin
- CMFCColorBar [MFC], GetVertMargin
- CMFCColorBar [MFC], IsTearOff
- CMFCColorBar [MFC], SetColor
- CMFCColorBar [MFC], SetColorName
- CMFCColorBar [MFC], SetCommandID
- CMFCColorBar [MFC], SetDocumentColors
- CMFCColorBar [MFC], SetHorzMargin
- CMFCColorBar [MFC], SetVertMargin
- CMFCColorBar [MFC], AdjustLocations
- CMFCColorBar [MFC], AllowChangeTextLabels
- CMFCColorBar [MFC], AllowShowOnList
- CMFCColorBar [MFC], CalcSize
- CMFCColorBar [MFC], CreatePalette
- CMFCColorBar [MFC], GetColorGridSize
- CMFCColorBar [MFC], GetExtraHeight
- CMFCColorBar [MFC], InitColors
- CMFCColorBar [MFC], OnKey
- CMFCColorBar [MFC], OnSendCommand
- CMFCColorBar [MFC], OnUpdateCmdUI
- CMFCColorBar [MFC], OpenColorDialog
- CMFCColorBar [MFC], Rebuild
- CMFCColorBar [MFC], SelectPalette
- CMFCColorBar [MFC], SetPropList
- CMFCColorBar [MFC], ShowCommandMessageString
ms.assetid: 4756ee40-25a5-4cee-af7f-acab7993d1c7
ms.openlocfilehash: 7b63fb66b800bd758c7f4c89c553e857ad9bbfbc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367765"
---
# <a name="cmfccolorbar-class"></a>CMFCColorBar Sınıfı

Sınıf, `CMFCColorBar` belge veya uygulamada renkleri seçebilen bir yerleştirme denetim çubuğunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CMFCColorBar : public CMFCPopupMenuBar
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCColorBar::CMFCColorBar](#cmfccolorbar)|Bir `CMFCColorBar` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCColorBar::Contexttosize](#contexttosize)|Renk çubuğu denetimindeki düğmeleri içerecek şekilde gereken dikey ve yatay kenar boşluklarını hesaplar ve bu düğmelerin konumunu ayarlar.|
|[CMFCColorBar::Create Control](#createcontrol)|Renk çubuğu denetim penceresi oluşturur, `CMFCColorBar` nesneye bağlar ve denetimi belirtilen renk paletini içerecek şekilde yeniden boyutlandırır.|
|[CMFCColorBar::Oluştur](#create)|Renk çubuğu denetim penceresi oluşturur ve `CMFCColorBar` nesneye bağlar.|
|[CMFCColorBar::EnableAutomaticButton](#enableautomaticbutton)|Otomatik düğmeyi gösterir veya gizler.|
|[CMFCColorBar::EnableOtherButton](#enableotherbutton)|Kullanıcının daha fazla renk seçmesine olanak tanıyan bir iletişim kutusunun ekranını etkinleştirer veya devre dışı bırakırsa.|
|[CMFCColorBar::GetColor](#getcolor)|Şu anda seçili rengi alır.|
|[CMFCColorBar::GetCommandID](#getcommandid)|Geçerli renk çubuğu denetiminin komut kimliğini alır.|
|[CMFCColorBar::GetHighlightedColor](#gethighlightedcolor)|Bir renk düğmesinin odak noktası olduğunu belirten rengi alır; yani, düğme *sıcak*.|
|[CMFCColorBar::GetHorzMargin](#gethorzmargin)|Sol veya sağ renk hücresi ile istemci alanı sınırı arasındaki boşluk olan yatay kenar boşluğunu alır.|
|[CMFCColorBar::GetVertMargin](#getvertmargin)|Üst veya alt renk hücresi ile istemci alanı sınırı arasındaki boşluk olan dikey kenar boşluğunu alır.|
|[CMFCColorBar::Istearoff](#istearoff)|Geçerli renk çubuğunun sabitlenebilir olup olmadığını gösterir.|
|[CMFCColorBar::SetColor](#setcolor)|Şu anda seçili rengi ayarlar.|
|[CMFCColorBar::SetColorName](#setcolorname)|Belirli bir renk için yeni bir ad ayarlar.|
|[CMFCColorBar::SetCommandID](#setcommandid)|Renk çubuğu denetimi için yeni bir komut kimliği ayarlar.|
|[CMFCColorBar::SetDocumentColors](#setdocumentcolors)|Geçerli belgede kullanılan renklerin listesini ayarlar.|
|[CMFCColorBar::SetHorzMargin](#sethorzmargin)|Sol veya sağ renk hücresi ile istemci alanı sınırı arasındaki boşluk olan yatay kenar boşluğunu ayarlar.|
|[CMFCColorBar::SetVertMargin](#setvertmargin)|Üst veya alt renk hücresi ile istemci alanı sınırı arasındaki boşluk olan dikey kenar boşluğunu ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCColorBar::Konumları Ayarla](#adjustlocations)|Renk çubuğu denetimindeki renk düğmelerinin konumlarını ayarlar.|
|[CMFCColorBar::ChangeTextLabels izin](#allowchangetextlabels)|Renk düğmelerinin metin etiketinin değişip değişmeyeceğini gösterir.|
|[CMFCColorBar::İzin Showonlist](#allowshowonlist)|Özelleştirme işlemi sırasında renk çubuğu denetim nesnesinin araç çubuğu listesinde görünüp görünmeyeceğini gösterir.|
|[CMFCColorBar::CalcSize](#calcsize)|Düzen hesaplama işleminin bir parçası olarak çerçeve tarafından çağrılır.|
|[CMFCColorBar::CreatePalette](#createpalette)|Belirli bir renk dizisinde ki renklerle bir paleti başolarak alır.|
|[CMFCColorBar::GetColorGridSize](#getcolorgridsize)|Renk çubuğu denetiminin ızgarasındaki satır ve sütun sayısını hesaplar.|
|[CMFCColorBar::GetExtraHeight](#getextraheight)|Geçerli renk çubuğunun **Diğer** düğmesi, belge renkleri ve benzeri çeşitli kullanıcı arabirimi öğelerini görüntülemek için gerektirdiği ek yüksekliği hesaplar.|
|[CMFCColorBar::InitColors](#initcolors)|Belirli bir paletteki veya sistem varsayılan paletindeki renklerle bir renk dizisini başolarak karşılar.|
|[CMFCColorBar::OnKey](#onkey)|Bir kullanıcı klavye düğmesine bastığında çerçeve tarafından çağrılır.|
|[CMFCColorBar::OnSendKomutu](#onsendcommand)|Açılır pencere denetimleri hiyerarşisini kapatmak için çerçeve tarafından çağrılır.|
|[CMFCColorBar::OnUpdateCmdUI](#onupdatecmdui)|Öğe görüntülenmeden önce renk çubuğu denetiminin kullanıcı arabirimi öğesini etkinleştirmek veya devre dışı kılabilir.|
|[CMFCColorBar::OpenColorDialog](#opencolordialog)|Renk iletişim kutusunu açar.|
|[CMFCColorBar::Yeniden Oluşturma](#rebuild)|Renk çubuğu denetimini tamamen yeniden çizer.|
|[CMFCColorBar::SelectPalette](#selectpalette)|Belirtilen aygıt bağlamının mantıksal paletini geçerli renk çubuğu denetiminin üst düğmesinin paletine ayarlar.|
|[CMFCColorBar::SetPropList](#setproplist)|Korumalı `m_pWndPropList` veri üyesini bir özellik ızgara denetimi için belirtilen işaretçiye ayarlar.|
|[CMFCColorBar::ShowCommandMessageString](#showcommandmessagestring)|Durum çubuğundaki ileti satırını güncelleştirmek için renk çubuğu denetiminin sahibi olan çerçeve penceresini ister.|

### <a name="protected-data-members"></a>Korumalı Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|`m_bInternal`|Fare olaylarının işlenip işlenmediğini belirleyen bir Boolean alanı. Genellikle, bu alan TRUE ve özelleştirme modu FALSE olduğunda fare olayları işlenir.|
|`m_bIsEnabled`|Denetimin etkin olup olmadığını gösteren bir Boolean.|
|`m_bIsTearOff`|Renk çubuğu denetiminin kenetlenmeyi destekleyip desteklemediğini gösteren bir Boolean.|
|`m_BoxSize`|Renk çubuğu ızgarasındaki hücrenin boyutunu belirten bir [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.|
|`m_bShowDocColorsWhenDocked`|Renk çubuğu kenetlendiğinde belge renklerini gösterip göstermeyeceğini belirten bir Boolean. Daha fazla bilgi için [CMFCColorBar::SetDocumentColors'](#setdocumentcolors)a bakınız.|
|`m_bStdColorDlg`|Standart sistem renk iletişim kutusunu veya [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusunu gösterip göstermeyeceğini belirten bir Boolean. Daha fazla bilgi için [cmfccolorbar::EnableOtherButton'a](#enableotherbutton)bakın.|
|`m_ColorAutomatic`|Geçerli otomatik rengi depolayan bir [COLORREF.](/windows/win32/gdi/colorref) Daha fazla bilgi için [cmfccolorbar::EnableOtherButton'a](#enableotherbutton)bakın.|
|`m_ColorNames`|Bir Dizi RGB rengini adlarıyla ilişkilendiren bir [CMap](../../mfc/reference/cmap-class.md) nesnesi.|
|`m_colors`|Renk çubuğu denetiminde görüntülenen renkleri içeren [COLORREF](/windows/win32/gdi/colorref) değerlerinden oluşan [bir CArray.](../../mfc/reference/carray-class.md)|
|`m_ColorSelected`|Kullanıcının renk çubuğu denetiminden şu anda seçtiği renk olan [COLORREF](/windows/win32/gdi/colorref) değeri.|
|`m_lstDocColors`|Şu anda bir belgede kullanılan renkleri içeren [COLORREF](/windows/win32/gdi/colorref) değerlerinin [CList'i.](../../mfc/reference/clist-class.md)|
|`m_nCommandID`|Renk düğmesinin komut kimliği olan imzasız bir tamsayı.|
|`m_nHorzMargin`|Renk ızgarasındaki renk düğmeleri arasındaki yatay kenar boşluğu olan tamsayı.|
|`m_nHorzOffset`|Renk düğmesinin ortasına yatay ofset olan bir tümsek. Düğme bir renge ek olarak metin veya görüntü görüntülerse bu değer önemlidir.|
|`m_nNumColumns`|Renklerin renk çubuğu denetim ızgarasındaki sütun sayısı olan tamsayı.|
|`m_nNumColumnsVert`|Dikey olarak yönlendirilmiş bir renk ızgarasındaki sütun sayısı olan tamsayı.|
|`m_nNumRowsHorz`|Yatay olarak yönlendirilmiş bir renk ızgarasındaki sütun sayısı olan tamsayı.|
|`m_nRowHeight`|Renk ızgarasında bir sıra renk düğmesinin yüksekliği olan bir tamsayı.|
|`m_nVertMargin`|Renk ızgarasındaki renk düğmeleri arasındaki dikey kenar boşluğu olan tamsayı.|
|`m_nVertOffset`|Renk düğmesinin ortasına dikey ofset olan bir tümsek. Düğme bir renge ek olarak metin veya görüntü görüntülerse bu değer önemlidir.|
|`m_Palette`|Renk çubuğu denetiminde kullanılan renklerin [CPalette'si.](../../mfc/reference/cpalette-class.md)|
|`m_pParentBtn`|Geçerli düğmenin üst öğesi olan [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) nesnesine işaretçi. Renk düğmesi araç çubuğu denetimleri hiyerarşisindeyse veya renk özelliği ızgara denetimindeyse bu değer önemlidir.|
|`m_pParentRibbonBtn`|Şerit üzerinde olan ve geçerli düğmenin ana düğmesi olan [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md) nesnesine işaretçi. Renk düğmesi araç çubuğu denetimleri hiyerarşisindeyse veya renk özelliği ızgara denetimindeyse bu değer önemlidir.|
|`m_pWndPropList`|[CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) nesnesine işaretçi.|
|`m_strAutoColor`|**Otomatik** düğmede görüntülenen metin olan [bir CString.](../../atl-mfc-shared/reference/cstringt-class.md) Daha fazla bilgi için [cmfccolorbar::EnableAutomaticButton](#enableautomaticbutton)bakın.|
|`m_strDocColors`|Belge renkleri düğmesinde görüntülenen metin olan [bir CString.](../../atl-mfc-shared/reference/cstringt-class.md) Daha fazla bilgi için [CMFCColorBar::SetDocumentColors'](#setdocumentcolors)a bakınız.|
|`m_strOtherColor`|*Diğer* düğmede görüntülenen metin olan [bir CString.](../../atl-mfc-shared/reference/cstringt-class.md) Daha fazla bilgi için [cmfccolorbar::EnableOtherButton'a](#enableotherbutton)bakın.|

## <a name="remarks"></a>Açıklamalar

Genellikle, doğrudan bir `CMFCColorBar` nesne oluşturmuyorsunuz. Bunun yerine, [CMFCColorMenuButton Sınıfı](../../mfc/reference/cmfccolormenubutton-class.md) (menülerde ve araç çubuklarında kullanılır) veya `CMFCColorBar` [CMFCColorButton Sınıfı](../../mfc/reference/cmfccolorbutton-class.md) nesneyi oluşturur.

Sınıf `CMFCColorBar` aşağıdaki işlevselliği sağlar:

- Belge renkleri listesini otomatik olarak ayarlar.

- Belge durumuyla birlikte durumunu kaydeder ve geri yükler.

- "Otomatik" düğmesini yönetir.

- Özel bir renk seçmek için [CMFCColorPickerCtrl Sınıf](../../mfc/reference/cmfccolorpickerctrl-class.md) denetimini kullanır.

- Bir "yırtılma" durumunu destekler [(CMFCColorMenuButton Sınıfı](../../mfc/reference/cmfccolormenubutton-class.md)kullanılarak oluşturulursa).

`CMFCColorBar` İşlevselliği uygulamanıza dahil etmek için:

1. Normal bir menü düğmesi oluşturun ve ID_CHAR_COLOR gibi bir kimlik atayın.

1. Çerçeve penceresi sınıfınızda, [CFrameWndEx::OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) yöntemini geçersiz kılın ve normal menü düğmesini [CMFCColorMenuButton Sınıf](../../mfc/reference/cmfccolormenubutton-class.md) nesnesi ile değiştirin [(CMFCToolBar::ReplaceButton'u](../../mfc/reference/cmfctoolbar-class.md#replacebutton)arayarak).

1. [CMFCColorMenuButton Sınıf](../../mfc/reference/cmfccolormenubutton-class.md) oluşturma sırasında tüm `CMFCColorBar` stilleri ayarlayın ve nesnenin özelliklerini etkinleştirin veya devre dışı bırakın. Çerçeve `CMFCColorMenuButton` `CreatePopupMenu` yöntemi çağırdıktan `CMFCColorBar` sonra nesne dinamik olarak nesne oluşturur.

Kullanıcı bir renk çubuğu denetimi düğmesini tıklattığında, çerçeve `ON_COMMAND` üst renk çubuğu denetimi bildirmek için makroyu kullanır. Makroda komut kimliği parametresi, adım 1'deki (bu örnekte ID_CHAR_COLOR) renk çubuğu denetim düğmesine atadığınız değerdir. Daha fazla bilgi için [CMFCColorMenuButton Class,](../../mfc/reference/cmfccolormenubutton-class.md) [CMFCColorButton Class,](../../mfc/reference/cmfccolorbutton-class.md) [CMFCColorPickerCtrl Class,](../../mfc/reference/cmfccolorpickerctrl-class.md) [CFrameWndEx Class](../../mfc/reference/cframewndex-class.md)ve [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md) sınıfları'na bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCColorBar` sınıfta çeşitli yöntemler kullanarak bir renk çubuğunu nasıl yapılandırıştırılabildiğini gösterir. Yöntemler yatay ve dikey kenar boşluklarını ayarlar, diğer düğmeyi etkinleştirin, renk çubuğu denetim penceresi oluşturur ve şu anda seçili rengi ayarlar. Bu örnek, [Yeni Denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#1](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#2](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[Cpane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[Cmfctoolbar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCPopUpMenüBar](../../mfc/reference/cmfcpopupmenubar-class.md)

[Cmfccolorbar](../../mfc/reference/cmfccolorbar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcolorbar.h

## <a name="cmfccolorbaradjustlocations"></a><a name="adjustlocations"></a>CMFCColorBar::Konumları Ayarla

Renk çubuğu denetimindeki renk düğmelerinin konumlarını ayarlar.

```
virtual void AdjustLocations();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, WM_SIZE ileti işleme sırasında çerçeve tarafından çağrılır.

## <a name="cmfccolorbarallowchangetextlabels"></a><a name="allowchangetextlabels"></a>CMFCColorBar::ChangeTextLabels izin

Renk düğmelerinin metin etiketinin değişip değişmeyeceğini gösterir.

```
virtual BOOL AllowChangeTextLabels() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman FALSE.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem her zaman FALSE döndürür, bu da metin etiketlerinin değiştirilemeyeceği anlamına gelir. Metin etiketlerini değiştirmeyi etkinleştirmek için bu yöntemi geçersiz kılın.

## <a name="cmfccolorbarallowshowonlist"></a><a name="allowshowonlist"></a>CMFCColorBar::İzin Showonlist

Özelleştirme işlemi sırasında renk çubuğu denetim nesnesinin araç çubuğu listesinde görünüp görünmeyeceğini gösterir.

```
virtual BOOL AllowShowOnList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem her zaman TRUE döndürür, bu da çerçevenin özelleştirme işlemi sırasında renk çubuğu denetimini görüntüleyebileceği anlamına gelir. Farklı bir davranış uygulamak için bu yöntemi geçersiz kılın.

## <a name="cmfccolorbarcalcsize"></a><a name="calcsize"></a>CMFCColorBar::CalcSize

Düzen hesaplama işleminin bir parçası olarak çerçeve tarafından çağrılır.

```
virtual CSize CalcSize(BOOL bVertDock);
```

### <a name="parameters"></a>Parametreler

*bVertDock*<br/>
[içinde] Renk çubuğu denetiminin dikey olarak sabitlenmiş olduğunu belirtmek için TRUE; Renk çubuğu denetiminin yatay olarak sabitlenerek sabitlendiğini belirtmek için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Renk çubuğu denetimindeki renk düğmeleri dizisinin boyutu.

## <a name="cmfccolorbarcmfccolorbar"></a><a name="cmfccolorbar"></a>CMFCColorBar::CMFCColorBar

Bir `CMFCColorBar` nesne inşa eder.

```
CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors,
    CList<COLORREF,COLORREF>& lstDocColors,
    int nColumns,
    int nRowsDockHorz,
    int nColDockVert,
    COLORREF colorAutomatic,
    UINT nCommandID,
    CMFCColorButton* pParentBtn);

CMFCColorBar(
    const CArray<COLORREF,COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors,
    CList<COLORREF,COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic,
    UINT nCommandID,
    CMFCRibbonColorButton* pParentRibbonBtn);

CMFCColorBar(
    CMFCColorBar& src,
    UINT uiCommandID);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
[içinde] Çerçevenin renk çubuğu denetiminde görüntüleyen bir dizi renk.

*color*<br/>
[içinde] Başlangıçta seçilen renk.

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

*nRowsDockHorz*<br/>
[içinde] Renk çubuğuyatay olarak kenetlendiğinde sahip olduğu satır sayısı.

*nColDockVert*<br/>
[içinde] Renk çubuğudikey olarak kenetlendiğinde sahip olduğu sütun sayısı.

*Colorautomatic*<br/>
[içinde] Otomatik düğmeyi tıklattığınızda çerçevenin uyguladığı varsayılan renk.

*nCommandID*<br/>
[içinde] Renk çubuğu denetim komut kimliği.

*pParentBtn*<br/>
[içinde] Üst düğmeye işaretçi.

*src*<br/>
[içinde] Varolan `CMFCColorBar` bir nesne yeni `CMFCColorBar` nesneye kopyalanacak.

*uiCommandID*<br/>
[içinde] Komut kimliği.

## <a name="cmfccolorbarcontexttosize"></a><a name="contexttosize"></a>CMFCColorBar::Contexttosize

Renk çubuğu denetimindeki düğmeleri içerecek şekilde gereken dikey ve yatay kenar boşluklarını hesaplar ve bu düğmelerin konumunu ayarlar.

```
void ContextToSize(
    BOOL bSquareButtons = TRUE,
    BOOL bCenterButtons = TRUE);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*bSquareButtons*|[içinde] Renk çubuğu denetimindeki düğmelerin şeklinin kare olduğunu belirtmek için TRUE; aksi takdirde, YANLIŞ. Varsayılan değer TRUE'dur.|
|*bCenterButtons*|[içinde] Renk çubuğu denetim düğmesinin yüzündeki içeriğin ortalanmış olduğunu belirtmek için TRUE; aksi takdirde, YANLIŞ. Varsayılan değer TRUE'dur.|

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorbarcreate"></a><a name="create"></a>CMFCColorBar::Oluştur

Renk çubuğu denetim penceresi oluşturur ve `CMFCColorBar` nesneye bağlar.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle,
    UINT nID,
    CPalette* pPalette=NULL,
    int nColumns=0,
    int nRowsDockHorz=0,
    int nColDockVert=0);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
[içinde] Üst pencereye işaretçi.

*Dwstyle*<br/>
[içinde] [Pencere stillerinin](../../mfc/reference/styles-used-by-mfc.md#window-styles)bitwise kombinasyonu (VEYA) .

*Nıd*<br/>
[içinde] Komut kimliği.

*pPalette*<br/>
[içinde] Renk paletine işaretçi. Varsayılan değer NULL'dur.

*nSütunlar*<br/>
[içinde] Renk çubuğu denetimindeki sütun sayısı. Varsayılan değer, 0'dur.

*nRowsDockHorz*<br/>
[içinde] Yatay olarak kenetlendiğinde renk çubuğundaki satır sayısı denetimi. Varsayılan değer, 0'dur.

*nColDockVert*<br/>
[içinde] Dikey olarak kenetlendiğinde renk çubuğundaki sütun sayısı denetimi. Varsayılan değer, 0'dur.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bir `CMFCColorBar` nesne oluşturmak için, sınıf oluşturucusu sonra bu yöntemi arayın. Yöntem, `Create` Windows denetimini oluşturur ve bir renk listesini başharfe çeker.

## <a name="cmfccolorbarcreatecontrol"></a><a name="createcontrol"></a>CMFCColorBar::Create Control

Renk çubuğu denetim penceresi oluşturur, `CMFCColorBar` nesneye bağlar ve denetim penceresini belirtilen renk paletini içerecek şekilde yeniden boyutlandırır.

```
virtual BOOL CreateControl(
    CWnd* pParentWnd,
    const CRect& rect,
    UINT nID,
    int nColumns=-1,
    CPalette* pPalette=NULL);
```

### <a name="parameters"></a>Parametreler

*pParentWnd*<br/>
[içinde] Üst pencereye işaretçi. NULL olamaz.

*Rect*<br/>
[içinde] Renk çubuğu denetiminin nerede çizilen yeri belirten sınırlayıcı bir dikdörtgen.

*Nıd*<br/>
[içinde] Kontrol kimliği.

*nSütunlar*<br/>
[içinde] Renk çubuğu denetiminde ideal sütun sayısı. Bu yöntem, belirtilen renk paletine uyacak şekilde bu sayıyı değiştirir. Varsayılan değer -1'dir, bu da bu parametrenin belirtilmemiş olduğu anlamına gelir.

*pPalette*<br/>
[içinde] Renk paletine işaretçi veya NULL. Bu parametre NULL ise, bu yöntem renk çubuğu denetiminin boyutunu 20 renk belirtilmiş gibi hesaplar. Varsayılan değer NULL'dur.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, renk çubuğu denetiminde uygun sayı veya satır ve sütunları hesaplamak için *rekt,* *nColumns*ve *pPalette* parametrelerini kullanır ve sonra [CMFCColorBar çağırır::Oluşturma](#create) yöntemi.

## <a name="cmfccolorbarcreatepalette"></a><a name="createpalette"></a>CMFCColorBar::CreatePalette

Belirli bir renk dizisinde ki renklerle bir paleti başolarak alır.

```
static BOOL CreatePalette(
    const CArray<COLORREF, COLORREF>& arColors,
    CPalette& palette);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*arColors*|[içinde] Bir dizi renk.|
|*Palet*|[içinde] Bir renk paleti.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cmfccolorbarenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFCColorBar::EnableAutomaticButton

Otomatik düğmeyi gösterir veya gizler.

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszEtiket*<br/>
[içinde] *Otomatik* (varsayılan) renk düğmesinin metin etiketi veya NULL.

Otomatik düğme için standart etiket **Otomatiktir.**

*Colorautomatic*<br/>
[içinde] Otomatik düğmeyi tıklattığınızda çerçevenin uyguladığı varsayılan renk.

*bEtkinleştir*<br/>
[içinde] Otomatik düğmeyi etkinleştirmek için TRUE; Otomatik düğmeyi devre dışı etmek için FALSE. Varsayılan değer TRUE'dur.

### <a name="remarks"></a>Açıklamalar

*lpszLabel* parametresi NULL veya *bEnable* parametresi FALSE ise otomatik düğmenin metin etiketi silinir.

## <a name="cmfccolorbarenableotherbutton"></a><a name="enableotherbutton"></a>CMFCColorBar::EnableOtherButton

Kullanıcının daha fazla renk seçmesine olanak tanıyan bir iletişim kutusunun ekranını etkinleştirer veya devre dışı bırakırsa.

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszEtiket*<br/>
[içinde] Daha fazla renk seçeneği görüntüleyen *diğer* düğmenin metin etiketi veya NULL.

Bu düğmenin standart etiketi **Daha Fazla Renktir...**.

*bAltColorDlg*<br/>
[içinde] [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusunu görüntülemek için TRUE; Standart [CColorDialog](../../mfc/reference/ccolordialog-class.md) iletişim kutusunu görüntülemek için FALSE. Varsayılan değer TRUE'dur.

*bEtkinleştir*<br/>
[içinde] DÜĞMEYi etkinleştirmek için TRUE; Düğmeyi devre dışı etmek için FALSE. Varsayılan değer TRUE'dur.

## <a name="cmfccolorbargetcolor"></a><a name="getcolor"></a>CMFCColorBar::GetColor

Şu anda seçili rengi alır.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili renk.

## <a name="cmfccolorbargetcolorgridsize"></a><a name="getcolorgridsize"></a>CMFCColorBar::GetColorGridSize

Renk çubuğu denetiminin ızgarasındaki satır ve sütun sayısını hesaplar.

```
CSize GetColorGridSize(BOOL bVertDock) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*bVertDock*|[içinde] Dikey olarak sabitlenmiş renk çubuğu denetimi için hesaplamayı gerçekleştirmek için TRUE; aksi takdirde, yatay olarak sabitlenmiş bir denetim için hesaplamayı gerçekleştirin.|

### <a name="return-value"></a>Dönüş Değeri

Bileşeni sütun sayısını içeren ve `cy` bileşeni satır sayısını içeren bir [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi. `cx`

## <a name="cmfccolorbargetcommandid"></a><a name="getcommandid"></a>CMFCColorBar::GetCommandID

Geçerli renk çubuğu denetiminin komut kimliğini alır.

```
UINT GetCommandID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir komut kimliği.

### <a name="remarks"></a>Açıklamalar

Kullanıcı yeni bir renk seçtiğinde, çerçeve nesnenin üst `CMFCColorBar` bildirimini bildirmek için WM_COMMAND iletisinde komut kimliğini gönderir.

## <a name="cmfccolorbargetextraheight"></a><a name="getextraheight"></a>CMFCColorBar::GetExtraHeight

Geçerli renk çubuğunun **Diğer** düğme veya belge renkleri gibi çeşitli kullanıcı arabirimi öğelerini görüntülemek için gereken ek yüksekliği hesaplar.

```
int GetExtraHeight(int nNumColumns) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*nNumSütunlar*|[içinde] Renk çubuğu denetimi belge renkleri içeriyorsa, belge renklerinin ızgarasında görüntülenecek sütun sayısı. Aksi takdirde, bu değer kullanılmaz.|

### <a name="return-value"></a>Dönüş Değeri

Gerekli hesaplanan ekstra yükseklik.

## <a name="cmfccolorbargethighlightedcolor"></a><a name="gethighlightedcolor"></a>CMFCColorBar::GetHighlightedColor

Bir renk düğmesinin odak noktası olduğunu belirten rengi alır; yani, düğme *sıcak*.

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

RGB değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorbargethorzmargin"></a><a name="gethorzmargin"></a>CMFCColorBar::GetHorzMargin

Sol veya sağ renk hücresi ile istemci alanı sınırı arasındaki boşluk olan yatay kenar boşluğunu alır.

```
int GetHorzMargin();
```

### <a name="return-value"></a>Dönüş Değeri

Yatay kenar boşluğu.

## <a name="cmfccolorbargetvertmargin"></a><a name="getvertmargin"></a>CMFCColorBar::GetVertMargin

Üst veya alt renk hücresi ile istemci alanı sınırı arasındaki boşluk olan dikey kenar boşluğunu alır.

```
int GetVertMargin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dikey kenar boşluğu.

## <a name="cmfccolorbarinitcolors"></a><a name="initcolors"></a>CMFCColorBar::InitColors

Belirli bir paletteki renklerle veya sistem varsayılan paletiyle bir renk dizisini başolarak karşılar.

```
static int InitColors(
    CPalette* pPalette,
    CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pPalette*|[içinde] Bir palet nesnesi için bir işaretçi veya NULL. Bu parametre NULL ise, bu yöntem işletim sisteminin varsayılan paletini kullanır.|
|*arColors*|[içinde] Bir dizi renk.|

### <a name="return-value"></a>Dönüş Değeri

Renk dizisindeki öğelerin sayısı.

## <a name="cmfccolorbaristearoff"></a><a name="istearoff"></a>CMFCColorBar::Istearoff

Geçerli renk çubuğunun sabitlenebilir olup olmadığını gösterir.

```
BOOL IsTearOff() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli renk çubuğu denetimi takılabilirse DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Renk çubuğu denetimi takılabilirse, bir denetim çubuğundan koparılabilir ve başka bir konuma sabitlenebilir.

## <a name="cmfccolorbaronkey"></a><a name="onkey"></a>CMFCColorBar::OnKey

Bir kullanıcı klavye düğmesine bastığında çerçeve tarafından çağrılır.

```
virtual BOOL OnKey(UINT nChar);
```

### <a name="parameters"></a>Parametreler

*Nchar*<br/>
[içinde] Kullanıcının bastığı anahtarın sanal anahtar kodu.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem belirtilen anahtarı işlerse DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cmfccolorbaronsendcommand"></a><a name="onsendcommand"></a>CMFCColorBar::OnSendKomutu

Açılır pencereler hiyerarşisini kapatmak için çerçeve tarafından çağrılır.

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pDüğme*|[içinde] Araç çubuğunda bulunan bir denetimiçin işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cmfccolorbaronupdatecmdui"></a><a name="onupdatecmdui"></a>CMFCColorBar::OnUpdateCmdUI

Öğe görüntülenmeden önce renk çubuğu denetiminin kullanıcı arabirimi öğesini etkinleştirmek veya devre dışı kılabilir.

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Parametreler

*pTarget*<br/>
[içinde] Güncelleştirmek için kullanıcı arabirimi öğesi içeren bir pencereişaretçisi.

*bDisableIfNoHndler*<br/>
[içinde] İleti haritasında işleyici tanımlanmamışsa, kullanıcı arabirimi öğesini devre dışı bilebilir; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Uygulamanızın bir kullanıcısı bir kullanıcı arabirimi öğesini tıklattığında, öğenin etkin veya devre dışı bırakılmış olarak görüntülenip görüntülenmemesi gerektiğini bilmesi gerekir. Komut iletisinin hedefi, ON_UPDATE_COMMAND_UI komut işleyicisi uygulayarak bu bilgileri sağlar. Komutu işlemeye yardımcı olmak için bu yöntemi kullanın. Daha fazla bilgi için [CCmdUI Sınıfı'na](../../mfc/reference/ccmdui-class.md)bakın.

## <a name="cmfccolorbaropencolordialog"></a><a name="opencolordialog"></a>CMFCColorBar::OpenColorDialog

Renk iletişim kutusunu açar.

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>Parametreler

*colorDefault*<br/>
[içinde] Renk iletişim kutusu açıldığında varsayılan olarak seçilen renk.

*colorRes*<br/>
[çıkış] Kullanıcının seçtiği renk.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı bir renk seçiliyse TRUE; Kullanıcı renk iletişim kutusunu iptal ettiyse FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorbarrebuild"></a><a name="rebuild"></a>CMFCColorBar::Yeniden Oluşturma

Renk çubuğu denetimini tamamen yeniden çizer.

```
virtual void Rebuild();
```

## <a name="cmfccolorbarselectpalette"></a><a name="selectpalette"></a>CMFCColorBar::SelectPalette

Belirtilen aygıt bağlamının mantıksal paletini geçerli renk çubuğu denetiminin üst düğmesinin paletine ayarlar.

```
CPalette* SelectPalette(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Pdc*|[içinde] Geçerli renk çubuğu denetiminin üst düğmesinin aygıt bağlamını işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

Geçerli renk çubuğu denetiminin üst düğmesinin paletiyle değiştirilen palete işaretçi.

## <a name="cmfccolorbarsetcolor"></a><a name="setcolor"></a>CMFCColorBar::SetColor

Şu anda seçili rengi ayarlar.

```
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
[içinde] RGB renk değeri.

## <a name="cmfccolorbarsetcolorname"></a><a name="setcolorname"></a>CMFCColorBar::SetColorName

Belirli bir renk için yeni bir ad ayarlar.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
[içinde] Bir rengin RGB değeri.

*strName*<br/>
[içinde] Belirtilen renk için yeni ad.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, uygulamanızdaki tüm `CMFCColorBar` nesnelerde belirtilen rengin adını değiştirir.

## <a name="cmfccolorbarsetcommandid"></a><a name="setcommandid"></a>CMFCColorBar::SetCommandID

Renk çubuğu denetimi için yeni bir komut kimliği ayarlar.

```
void SetCommandID(UINT nCommandID);
```

### <a name="parameters"></a>Parametreler

*nCommandID*<br/>
[içinde] Bir komut kimliği.

### <a name="remarks"></a>Açıklamalar

Renk çubuğu denetiminin komut kimliğini değiştirmek ve kimliğin değiştiğini denetimin üst penceresine bildirmek için bu yöntemi arayın.

## <a name="cmfccolorbarsetdocumentcolors"></a><a name="setdocumentcolors"></a>CMFCColorBar::SetDocumentColors

Geçerli belgede kullanılan renklerin listesini ayarlar.

```
void SetDocumentColors(
    LPCTSTR lpszCaption,
    CList<COLORREF,COLORREF>& lstDocColors,
    BOOL bShowWhenDocked=FALSE);
```

### <a name="parameters"></a>Parametreler

*lpszCaption*<br/>
[içinde] Renk çubuğu denetimi kenetlenmediğinde görüntülenen resim yazısı.

*lstDocColors*<br/>
[içinde] Geçerli belge renklerinin yerini alan renklerin listesi.

*bShowWhenDocked*<br/>
[içinde] Renk çubuğu denetimi kenetlendiğinde belge renklerini göstermek için TRUE; aksi takdirde, YANLIŞ. Varsayılan değer FALSE'dur.

### <a name="remarks"></a>Açıklamalar

*Belge renkleri,* belgede şu anda kullanılan renklerdir. Çerçeve otomatik olarak belge renkleri listesini tutar, ancak listeyi değiştirmek için bu yöntemi kullanabilirsiniz.

## <a name="cmfccolorbarsethorzmargin"></a><a name="sethorzmargin"></a>CMFCColorBar::SetHorzMargin

Sol veya sağ renk hücresi ile istemci alanının sınırı arasındaki boşluk olan yatay kenar boşluğunu ayarlar.

```
void SetHorzMargin(int nHorzMargin);
```

### <a name="parameters"></a>Parametreler

*nHorzMargin*<br/>
[içinde] Yatay kenar boşluğu, piksel olarak.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [CMFCColorBar::CMFCColorBar](#cmfccolorbar) oluşturucu yatay kenar boşluğunu 4 piksele ayarlar.

## <a name="cmfccolorbarsetproplist"></a><a name="setproplist"></a>CMFCColorBar::SetPropList

Korumalı `m_pWndPropList` veri üyesini bir özellik ızgara denetimi için belirtilen işaretçiye ayarlar.

```
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pWndList*|[içinde] Özellik ızgara denetim nesnesine işaretçi.|

## <a name="cmfccolorbarsetvertmargin"></a><a name="setvertmargin"></a>CMFCColorBar::SetVertMargin

Üst veya alt renk hücresi ile istemci alanı sınırı arasındaki boşluk olan dikey kenar boşluğunu ayarlar.

```
void SetVertMargin(int nVertMargin);
```

### <a name="parameters"></a>Parametreler

*nVertMargin*<br/>
[içinde] Piksel olarak dikey kenar boşluğu.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [CMFCColorBar::CMFCColorBar](#cmfccolorbar) oluşturucu dikey kenar boşluğunu 4 piksele ayarlar.

## <a name="cmfccolorbarshowcommandmessagestring"></a><a name="showcommandmessagestring"></a>CMFCColorBar::ShowCommandMessageString

Durum çubuğundaki ileti satırını güncelleştirmek için renk çubuğu denetiminin sahibi olan çerçeve penceresini ister.

```
virtual void ShowCommandMessageString(UINT uiCmdId);
```

### <a name="parameters"></a>Parametreler

*uiCmdId*<br/>
[içinde] Bir komut kimliği. (Bu parametre yoksayılır.)

### <a name="remarks"></a>Açıklamalar

Bu yöntem, renk çubuğu denetiminin sahibine WM_SETMESSAGESTRING ileti gönderir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
