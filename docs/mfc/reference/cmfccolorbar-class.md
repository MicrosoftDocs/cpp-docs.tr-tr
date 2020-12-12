---
description: 'Daha fazla bilgi edinin: CMFCColorBar sınıfı'
title: CMFCColorBar sınıfı
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
ms.openlocfilehash: 5a2935c71a5579dddb2133f2ac6589a6bd447ef6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327715"
---
# <a name="cmfccolorbar-class"></a>CMFCColorBar sınıfı

`CMFCColorBar`Sınıfı, bir belge veya uygulamadaki renkleri seçebileceğiniz bir yerleştirme denetim çubuğunu temsil eder.

## <a name="syntax"></a>Syntax

```
class CMFCColorBar : public CMFCPopupMenuBar
```

## <a name="members"></a>Üyeler

### <a name="protected-constructors"></a>Korumalı Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCColorBar:: CMFCColorBar](#cmfccolorbar)|Bir `CMFCColorBar` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCColorBar:: ContextToSize](#contexttosize)|Renk çubuğu denetimindeki düğmeleri içermesi için gereken dikey ve yatay kenar boşluklarını hesaplar ve ardından bu düğmelerin konumunu ayarlar.|
|[CMFCColorBar:: CreateControl](#createcontrol)|Bir renk çubuğu denetim penceresi oluşturur, `CMFCColorBar` nesneye iliştirir ve belirtilen renk paletini içerecek şekilde denetimi yeniden boyutlandırır.|
|[CMFCColorBar:: Create](#create)|Bir renk çubuğu denetim penceresi oluşturur ve `CMFCColorBar` nesneye ekler.|
|[CMFCColorBar:: EnableAutomaticButton](#enableautomaticbutton)|Otomatik düğmesini gösterir veya gizler.|
|[CMFCColorBar:: EnableOtherButton](#enableotherbutton)|Kullanıcının daha fazla renk seçmesini sağlayan bir iletişim kutusunun görüntülenmesini sağlar veya devre dışı bırakır.|
|[CMFCColorBar:: GetColor](#getcolor)|Şu anda seçili rengi alır.|
|[CMFCColorBar:: Getcommandıd](#getcommandid)|Geçerli renk çubuğu denetiminin komut KIMLIĞINI alır.|
|[CMFCColorBar:: Gethighaçıklatedcolor](#gethighlightedcolor)|Bir renk düğmesinin odağa sahip olduğunu belirten rengi alır; diğer bir deyişle, düğme *sıcak* olur.|
|[CMFCColorBar:: GetHorzMargin](#gethorzmargin)|Sol veya sağ renk hücresi ile istemci alanı sınırı arasındaki boşluk olan yatay boşluğu alır.|
|[CMFCColorBar:: GetVertMargin](#getvertmargin)|Üst veya alt renk hücresi ile istemci alanı sınırı arasındaki boşluk olan dikey boşluğu alır.|
|[CMFCColorBar:: Isteyoff](#istearoff)|Geçerli renk çubuğunun dockable olup olmadığını gösterir.|
|[CMFCColorBar:: SetColor](#setcolor)|Şu anda seçili olan rengi ayarlar.|
|[CMFCColorBar:: SetColorName](#setcolorname)|Belirtilen renk için yeni bir ad ayarlar.|
|[CMFCColorBar:: Setcommandıd](#setcommandid)|Renk çubuğu denetimi için yeni bir komut KIMLIĞI ayarlar.|
|[CMFCColorBar:: SetDocumentColors](#setdocumentcolors)|Geçerli belgede kullanılan renklerin listesini ayarlar.|
|[CMFCColorBar:: SetHorzMargin](#sethorzmargin)|Sol veya sağ renk hücresi ile istemci alanı sınırı arasındaki boşluk olan yatay boşluğu ayarlar.|
|[CMFCColorBar:: SetVertMargin](#setvertmargin)|Üst veya alt renk hücresi ile istemci alanı sınırı arasındaki boşluk olan dikey boşluğu ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCColorBar:: AdjustLocations](#adjustlocations)|Renk çubuğu denetimindeki renk düğmelerinin konumlarını ayarlar.|
|[CMFCColorBar:: AllowChangeTextLabels](#allowchangetextlabels)|Renk düğmelerinin metin etiketinin değişebilir olup olmadığını gösterir.|
|[CMFCColorBar:: AllowShowOnList](#allowshowonlist)|Özelleştirme işlemi sırasında renk çubuğu Denetim nesnesinin bir araç çubuğu listesinde görünüp görünmeyeceğini gösterir.|
|[CMFCColorBar:: CalcSize](#calcsize)|Düzen hesaplama sürecinin bir parçası olarak Framework tarafından çağırılır.|
|[CMFCColorBar:: CreatePalette](#createpalette)|Belirtilen renk dizisindeki renklerle bir palet başlatır.|
|[CMFCColorBar:: GetColorGridSize](#getcolorgridsize)|Renk çubuğu denetiminin kılavuzundaki satır ve sütun sayısını hesaplar.|
|[CMFCColorBar:: GetExtraHeight](#getextraheight)|Geçerli renk çubuğunun **diğer** düğme, belge renkleri vb. gibi çeşitli kullanıcı arabirimi öğelerini görüntülemesi için gereken ek yüksekliği hesaplar.|
|[CMFCColorBar:: ınitcolors](#initcolors)|Belirtilen bir paletteki renklerle veya sistem varsayılan paletinde renkler dizisini başlatır.|
|[CMFCColorBar:: OnKey](#onkey)|Kullanıcı bir klavye düğmesine bastığında Framework tarafından çağırılır.|
|[CMFCColorBar:: OnSendCommand](#onsendcommand)|Bir açılır denetim hiyerarşisini kapatmak için Framework tarafından çağırılır.|
|[CMFCColorBar:: OnUpdateCmdUI](#onupdatecmdui)|Öğe görüntülenmeden önce bir renk çubuğu denetiminin Kullanıcı arabirimi öğesini etkinleştirmek veya devre dışı bırakmak için Framework tarafından çağırılır.|
|[CMFCColorBar:: OpenColorDialog](#opencolordialog)|Bir renk iletişim kutusu açar.|
|[CMFCColorBar:: Rebuild](#rebuild)|Renk çubuğu denetimini tamamen yeniden çizer.|
|[CMFCColorBar:: SelectPalette](#selectpalette)|Belirtilen cihaz bağlamının mantıksal paletini geçerli renk çubuğu denetiminin ana düğmesinin paleti olarak ayarlar.|
|[CMFCColorBar:: SetPropList](#setproplist)|`m_pWndPropList`Korumalı veri üyesini bir özellik Kılavuzu denetimine belirtilen işaretçiye ayarlar.|
|[CMFCColorBar:: ShowCommandMessageString](#showcommandmessagestring)|Durum çubuğundaki ileti satırını güncelleştirmek için renk çubuğu denetiminin sahibi olan çerçeve penceresini ister.|

### <a name="protected-data-members"></a>Korumalı veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|`m_bInternal`|Fare olaylarının işlenip işlenmediğini belirleyen bir Boole alanı. Genellikle, bu alan TRUE olduğunda ve özelleştirme modu FALSE olduğunda fare olayları işlenir.|
|`m_bIsEnabled`|Bir denetimin etkin olup olmadığını gösteren bir Boole değeri.|
|`m_bIsTearOff`|Renk çubuğu denetiminin yerleştirmeyi destekleyip desteklemediğini gösteren bir Boole değeri.|
|`m_BoxSize`|Bir renk çubuğu kılavuzundaki bir hücrenin boyutunu belirten [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.|
|`m_bShowDocColorsWhenDocked`|Renk çubuğu yerleştirildiğinde belge renklerinin gösterilip gösterilmeyeceğini belirten bir Boole değeri. Daha fazla bilgi için bkz. [CMFCColorBar:: SetDocumentColors](#setdocumentcolors).|
|`m_bStdColorDlg`|Standart sistem rengi iletişim kutusunun mi yoksa [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusunun mi gösterileceğini belirten bir Boole değeri. Daha fazla bilgi için bkz. [CMFCColorBar:: EnableOtherButton](#enableotherbutton).|
|`m_ColorAutomatic`|Geçerli otomatik rengi depolayan bir [colorref](/windows/win32/gdi/colorref) . Daha fazla bilgi için bkz. [CMFCColorBar:: EnableOtherButton](#enableotherbutton).|
|`m_ColorNames`|Bir RGB renkleri kümesini adlarıyla ilişkilendiren [CMap](../../mfc/reference/cmap-class.md) nesnesi.|
|`m_colors`|Renk çubuğu denetiminde görüntülenen renkleri içeren [colorref](/windows/win32/gdi/colorref) değerlerinin bir [CArray](../../mfc/reference/carray-class.md) değeri.|
|`m_ColorSelected`|Kullanıcının renk çubuğu denetiminden Şu anda seçtiği renk olan [colorref](/windows/win32/gdi/colorref) değeri.|
|`m_lstDocColors`|Bir belgede Şu anda kullanılan renkleri içeren [colorref](/windows/win32/gdi/colorref) değerlerinin [CList](../../mfc/reference/clist-class.md) 'i.|
|`m_nCommandID`|Bir renk düğmesinin komut KIMLIĞI olan işaretsiz bir tamsayı.|
|`m_nHorzMargin`|Renklerin kılavuzundaki renk düğmeleri arasındaki yatay kenar boşluğu olan bir tamsayı.|
|`m_nHorzOffset`|Renk düğmesinin merkezinin yatay olarak kaydırılacağı bir tamsayı. Düğme, bir renge ek olarak metin veya görüntü görüntülüyorsa bu değer önemlidir.|
|`m_nNumColumns`|Renk çubuğu denetim kılavuzundaki renklerin içindeki sütun sayısı olan bir tamsayı.|
|`m_nNumColumnsVert`|Dikey olarak yönelimli renklerin bir kılavuzundaki sütun sayısı olan bir tamsayı.|
|`m_nNumRowsHorz`|Yatay olarak yönelimli renklerin bir kılavuzundaki sütun sayısı olan bir tamsayı.|
|`m_nRowHeight`|Renklerin kılavuzundaki renk düğmelerinin bir satırının yüksekliği olan bir tamsayı.|
|`m_nVertMargin`|Renklerin kılavuzundaki renk düğmeleri arasındaki dikey kenar boşluğu olan bir tamsayı.|
|`m_nVertOffset`|Renk düğmesinin ortasına dikey olan bir tamsayı. Düğme, bir renge ek olarak metin veya görüntü görüntülüyorsa bu değer önemlidir.|
|`m_Palette`|Renk çubuğu denetiminde kullanılan renklerin [Cpaleti](../../mfc/reference/cpalette-class.md) .|
|`m_pParentBtn`|Geçerli düğmenin üst öğesi olan [CMFCColorButton](../../mfc/reference/cmfccolorbutton-class.md) nesnesine yönelik bir işaretçi. Bu değer, Color düğmesi bir araç çubuğu denetimlerinin hiyerarşisinde ise veya Color özelliği kılavuz denetiminde olduğunda önemlidir.|
|`m_pParentRibbonBtn`|Şeritte bulunan [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md) nesnesine yönelik bir işaretçi ve geçerli düğmenin ana düğmesi. Bu değer, Color düğmesi bir araç çubuğu denetimlerinin hiyerarşisinde ise veya Color özelliği kılavuz denetiminde olduğunda önemlidir.|
|`m_pWndPropList`|[CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md) nesnesine yönelik bir işaretçi.|
|`m_strAutoColor`|**Otomatik** düğmesinde görüntülenen metin olan bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) . Daha fazla bilgi için bkz. [CMFCColorBar:: EnableAutomaticButton](#enableautomaticbutton).|
|`m_strDocColors`|Belge Renkleri düğmesinde görüntülenen metin olan bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) . Daha fazla bilgi için bkz. [CMFCColorBar:: SetDocumentColors](#setdocumentcolors).|
|`m_strOtherColor`|*Diğer* düğmede görüntülenen metin olan bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) . Daha fazla bilgi için bkz. [CMFCColorBar:: EnableOtherButton](#enableotherbutton).|

## <a name="remarks"></a>Açıklamalar

Genellikle doğrudan bir nesne oluşturmayın `CMFCColorBar` . Bunun yerine, [Cmfccolormenubtan sınıfı](../../mfc/reference/cmfccolormenubutton-class.md) (menülerde ve araç çubuklarında kullanılır) veya [CMFCColorButton sınıfı](../../mfc/reference/cmfccolorbutton-class.md) `CMFCColorBar` nesnesini oluşturur.

`CMFCColorBar`Sınıfı aşağıdaki işlevleri sağlar:

- Belge renklerinin listesini otomatik olarak ayarlar.

- Belge durumuyla birlikte durumunu kaydeder ve geri yükler.

- "Otomatik" düğmesini yönetir.

- Özel bir renk seçmek için [CMFCColorPickerCtrl sınıf](../../mfc/reference/cmfccolorpickerctrl-class.md) denetimini kullanır.

- Bir "Tear" durumunu destekler ( [Cmfccolormenubtan sınıfı](../../mfc/reference/cmfccolormenubutton-class.md)kullanılarak oluşturulduysa).

`CMFCColorBar`İşlevi uygulamanıza eklemek için:

1. Normal bir menü düğmesi oluşturun ve buna bir KIMLIK atayın, örneğin ID_CHAR_COLOR.

1. Çerçeve pencere sınıfınıza [CFrameWndEx:: OnShowPopupMenu](../../mfc/reference/cframewndex-class.md#onshowpopupmenu) yöntemini geçersiz kılın ve normal menü düğmesini bir [Cmfccolormenubtan Class](../../mfc/reference/cmfccolormenubutton-class.md) nesnesiyle değiştirin ( [CMFCToolBar:: ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)çağırarak).

1. Tüm stilleri ayarlayın ve `CMFCColorBar` [Cmfccolormenubtan sınıfı](../../mfc/reference/cmfccolormenubutton-class.md) oluşturma sırasında nesnenin özelliklerini etkinleştirin veya devre dışı bırakın. `CMFCColorMenuButton`Nesne, `CMFCColorBar` Framework yöntemini çağırdıktan sonra nesneyi dinamik olarak oluşturur `CreatePopupMenu` .

Kullanıcı bir renk çubuğu denetim düğmesine tıkladığında, çerçeve, `ON_COMMAND` renk çubuğu denetiminin üst öğesini bilgilendirmek için makroyu kullanır. Makroda komut KIMLIĞI parametresi, adım 1 ' deki (Bu örnekte ID_CHAR_COLOR) renk çubuğu denetim düğmesine atadığınız değerdir. Daha fazla bilgi için bkz. [Cmfccolormenubtan Class](../../mfc/reference/cmfccolormenubutton-class.md), [CMFCColorButton Class](../../mfc/reference/cmfccolorbutton-class.md), [CMFCColorPickerCtrl Class](../../mfc/reference/cmfccolorpickerctrl-class.md), [CFrameWndEx Class](../../mfc/reference/cframewndex-class.md)ve [CMFCToolBar sınıf](../../mfc/reference/cmfctoolbar-class.md) sınıfları.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında çeşitli yöntemler kullanarak bir renk çubuğunun nasıl yapılandırılacağını gösterir `CMFCColorBar` . Yatay ve dikey kenar boşluklarını ayarlayan Yöntemler, diğer düğmeyi etkinleştirir, bir renk çubuğu denetim penceresi oluşturur ve şu anda seçili rengi ayarlar. Bu örnek, [Yeni denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#1](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#2](../../mfc/reference/codesnippet/cpp/cmfccolorbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)

[CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcolorbar. h

## <a name="cmfccolorbaradjustlocations"></a><a name="adjustlocations"></a> CMFCColorBar:: AdjustLocations

Renk çubuğu denetimindeki renk düğmelerinin konumlarını ayarlar.

```
virtual void AdjustLocations();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, WM_SIZE ileti işleme sırasında çerçeve tarafından çağırılır.

## <a name="cmfccolorbarallowchangetextlabels"></a><a name="allowchangetextlabels"></a> CMFCColorBar:: AllowChangeTextLabels

Renk düğmelerinin metin etiketinin değişebilir olup olmadığını gösterir.

```
virtual BOOL AllowChangeTextLabels() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman FALSE.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem her zaman FALSE döndürür, bu da metin etiketlerinin değiştirilemediği anlamına gelir. Metin etiketlerinin değiştirilmesini etkinleştirmek için bu yöntemi geçersiz kılın.

## <a name="cmfccolorbarallowshowonlist"></a><a name="allowshowonlist"></a> CMFCColorBar:: AllowShowOnList

Özelleştirme işlemi sırasında renk çubuğu Denetim nesnesinin bir araç çubuğu listesinde görünüp görünmeyeceğini gösterir.

```
virtual BOOL AllowShowOnList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem her zaman TRUE değerini döndürür; bu, Framework 'ün özelleştirme süreci sırasında renk çubuğu denetimini görüntülemesi anlamına gelir. Farklı bir davranış uygulamak için bu yöntemi geçersiz kılın.

## <a name="cmfccolorbarcalcsize"></a><a name="calcsize"></a> CMFCColorBar:: CalcSize

Düzen hesaplama sürecinin bir parçası olarak Framework tarafından çağırılır.

```
virtual CSize CalcSize(BOOL bVertDock);
```

### <a name="parameters"></a>Parametreler

*bVertDock*<br/>
'ndaki Renk çubuğu denetiminin dikey olarak yerleştirilmiş olduğunu belirtmek için TRUE; Renk çubuğu denetiminin yatay olarak yerleştirilmiş olduğunu belirtmek için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Renk çubuğu denetimindeki renk düğmeleri dizisinin boyutu.

## <a name="cmfccolorbarcmfccolorbar"></a><a name="cmfccolorbar"></a> CMFCColorBar:: CMFCColorBar

Bir `CMFCColorBar` nesnesi oluşturur.

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

*lerde*<br/>
'ndaki Çerçevenin renk çubuğu denetiminde görüntülediği renk dizisi.

*Renk*<br/>
'ndaki Başlangıçta seçilen renk.

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

*nRowsDockHorz*<br/>
'ndaki Yatay yerleştirilmiş olan renk çubuğunun satır sayısı.

*nColDockVert*<br/>
'ndaki Renk çubuğunun dikey yerleştirilmiş olduğu sütun sayısı.

*colorAutomatic*<br/>
'ndaki Otomatik düğmesine tıkladığınızda çerçevenin geçerli olduğu varsayılan renk.

*nCommandID*<br/>
'ndaki Renk çubuğu denetim komut KIMLIĞI.

*pParentBtn*<br/>
'ndaki Üst düğmeye yönelik bir işaretçi.

*src*<br/>
'ndaki `CMFCColorBar` Yeni nesneye Kopyalanacak varolan bir nesne `CMFCColorBar` .

*Uııommandıd*<br/>
'ndaki Komut KIMLIĞI.

## <a name="cmfccolorbarcontexttosize"></a><a name="contexttosize"></a> CMFCColorBar:: ContextToSize

Renk çubuğu denetimindeki düğmeleri içermesi için gereken dikey ve yatay kenar boşluklarını hesaplar ve bu düğmelerin konumunu ayarlar.

```cpp
void ContextToSize(
    BOOL bSquareButtons = TRUE,
    BOOL bCenterButtons = TRUE);
```

### <a name="parameters"></a>Parametreler

*Bsquaredüğmeleri*\
'ndaki Bir renk çubuğu denetimindeki düğmelerin şeklinin kare olduğunu belirtmek için TRUE; Aksi takdirde, FALSE. Varsayılan değer TRUE 'dur.

*bCenterButtons*\
'ndaki Bir renk çubuğu denetim düğmesinin yüzdeki içeriğin ortalanmasını belirtmek için TRUE; Aksi takdirde, FALSE. Varsayılan değer TRUE 'dur.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorbarcreate"></a><a name="create"></a> CMFCColorBar:: Create

Bir renk çubuğu denetim penceresi oluşturur ve `CMFCColorBar` nesneye ekler.

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
'ndaki Ana pencerenin işaretçisi.

*dwStyle*<br/>
'ndaki [Pencere stillerinin](../../mfc/reference/styles-used-by-mfc.md#window-styles)bit tabanlı BIRLEŞIMI (veya).

*NID*<br/>
'ndaki Komut KIMLIĞI.

*pPalette*<br/>
'ndaki Renk paleti işaretçisi. Varsayılan değer NULL.

*nColumns*<br/>
'ndaki Renk çubuğu denetimindeki sütun sayısı. Varsayılan değer, 0'dur.

*nRowsDockHorz*<br/>
'ndaki Yatay yerleştirilmiş olan renk çubuğu denetimindeki satır sayısı. Varsayılan değer, 0'dur.

*nColDockVert*<br/>
'ndaki Dikey olarak yerleştirilmiş olan renk çubuğu denetimindeki sütun sayısı. Varsayılan değer, 0'dur.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bir nesne oluşturmak için `CMFCColorBar` , bu yöntemi ve sonra sınıf oluşturucusunu çağırın. `Create`Yöntemi Windows denetimini oluşturur ve renklerin bir listesini başlatır.

## <a name="cmfccolorbarcreatecontrol"></a><a name="createcontrol"></a> CMFCColorBar:: CreateControl

Bir renk çubuğu denetim penceresi oluşturur, `CMFCColorBar` nesneye iliştirir ve belirtilen renk paletini içerecek şekilde denetim penceresini yeniden boyutlandırır.

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
'ndaki Ana pencerenin işaretçisi. NULL olamaz.

*Rect*<br/>
'ndaki Renk çubuğu denetiminin nerede çizileceğini belirten bir sınırlayıcı dikdörtgen.

*NID*<br/>
'ndaki Denetim KIMLIĞI.

*nColumns*<br/>
'ndaki Renk çubuğu denetimindeki ideal sütun sayısı. Bu yöntem, belirtilen renk paletine uyacak şekilde bu sayıyı değiştirir. Varsayılan değer-1 ' dir, bu parametrenin belirtilmemiş olması anlamına gelir.

*pPalette*<br/>
'ndaki Renk paleti işaretçisi veya NULL. Bu parametre NULL ise, bu yöntem, 20 renk belirtilmiş gibi renk çubuğu denetiminin boyutunu hesaplar. Varsayılan değer NULL.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, renk çubuğu denetimindeki uygun sayıyı veya satırları ve sütunları hesaplamak için *Rect*, *nColumns* ve *pPalette* parametrelerini kullanır ve ardından [CMFCColorBar:: Create](#create) yöntemini çağırır.

## <a name="cmfccolorbarcreatepalette"></a><a name="createpalette"></a> CMFCColorBar:: CreatePalette

Belirtilen renk dizisindeki renklerle bir palet başlatır.

```
static BOOL CreatePalette(
    const CArray<COLORREF, COLORREF>& arColors,
    CPalette& palette);
```

### <a name="parameters"></a>Parametreler

*Arrenkler*\
'ndaki Renk dizisi.

*inizdeki*\
'ndaki Renk paleti.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

## <a name="cmfccolorbarenableautomaticbutton"></a><a name="enableautomaticbutton"></a> CMFCColorBar:: EnableAutomaticButton

Otomatik düğmesini gösterir veya gizler.

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
'ndaki *Otomatik* (varsayılan) renk DÜĞMESININ veya null alanının metin etiketi.

Otomatik düğmenin standart etiketi **otomatiktir**.

*colorAutomatic*<br/>
'ndaki Otomatik düğmesine tıkladığınızda çerçevenin geçerli olduğu varsayılan renk.

*bEnable*<br/>
'ndaki Otomatik düğmeyi etkinleştirmek için TRUE; Otomatik düğmeyi devre dışı bırakmak için FALSE. Varsayılan değer TRUE 'dur.

### <a name="remarks"></a>Açıklamalar

*LpszLabel* parametresi null ise ya da *BENABLE* parametresi false olduğunda otomatik düğmenin metin etiketi silinir.

## <a name="cmfccolorbarenableotherbutton"></a><a name="enableotherbutton"></a> CMFCColorBar:: EnableOtherButton

Kullanıcının daha fazla renk seçmesini sağlayan bir iletişim kutusunun görüntülenmesini sağlar veya devre dışı bırakır.

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
'ndaki *Diğer* düğmenin, daha fazla renk SEÇIMI veya null görüntüleyen metin etiketi.

Bu düğmenin standart etiketi **daha fazla renk...**.

*bAltColorDlg*<br/>
'ndaki [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusunu göstermek için true; Standart [CColorDialog](../../mfc/reference/ccolordialog-class.md) iletişim kutusunu göstermek için false. Varsayılan değer TRUE 'dur.

*bEnable*<br/>
'ndaki Düğmeyi etkinleştirmek için TRUE; Düğmeyi devre dışı bırakmak için FALSE. Varsayılan değer TRUE 'dur.

## <a name="cmfccolorbargetcolor"></a><a name="getcolor"></a> CMFCColorBar:: GetColor

Şu anda seçili rengi alır.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda seçili olan renk.

## <a name="cmfccolorbargetcolorgridsize"></a><a name="getcolorgridsize"></a> CMFCColorBar:: GetColorGridSize

Renk çubuğu denetiminin kılavuzundaki satır ve sütun sayısını hesaplar.

```
CSize GetColorGridSize(BOOL bVertDock) const;
```

### <a name="parameters"></a>Parametreler

*bVertDock*\
'ndaki Dikey olarak yerleştirilmiş bir renk çubuğu denetimi için hesaplamayı gerçekleştirmek üzere doğru; Aksi takdirde, yatay olarak yerleştirilmiş bir denetim için hesaplamayı gerçekleştirin.

### <a name="return-value"></a>Dönüş Değeri

[](../../atl-mfc-shared/reference/csize-class.md) `cx` Bileşeni sütun sayısını ve `cy` Bileşen satır sayısını içeren bir CSize nesnesi.

## <a name="cmfccolorbargetcommandid"></a><a name="getcommandid"></a> CMFCColorBar:: Getcommandıd

Geçerli renk çubuğu denetiminin komut KIMLIĞINI alır.

```
UINT GetCommandID() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir komut KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Kullanıcı yeni bir renk seçtiğinde, çerçeve nesnenin üst öğesini bilgilendirmek için komut KIMLIĞINI bir WM_COMMAND iletisinde gönderir `CMFCColorBar` .

## <a name="cmfccolorbargetextraheight"></a><a name="getextraheight"></a> CMFCColorBar:: GetExtraHeight

Geçerli renk çubuğunun **diğer** düğme veya belge renkleri gibi çeşitli kullanıcı arabirimi öğelerini görüntülemesi için gereken ek yüksekliği hesaplar.

```
int GetExtraHeight(int nNumColumns) const;
```

### <a name="parameters"></a>Parametreler

*nNumColumns*\
'ndaki Renk çubuğu denetimi belge renkleri içeriyorsa, belge renklerinin kılavuzunda görüntülenecek sütun sayısı. Aksi takdirde, bu değer kullanılmaz.

### <a name="return-value"></a>Dönüş Değeri

Gerekli olan hesaplanmış ek yükseklik.

## <a name="cmfccolorbargethighlightedcolor"></a><a name="gethighlightedcolor"></a> CMFCColorBar:: Gethighaçıklatedcolor

Bir renk düğmesinin odağa sahip olduğunu belirten rengi alır; diğer bir deyişle, düğme *sıcak* olur.

```
COLORREF GetHighlightedColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir RGB değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorbargethorzmargin"></a><a name="gethorzmargin"></a> CMFCColorBar:: GetHorzMargin

Sol veya sağ renk hücresi ile istemci alanı sınırı arasındaki boşluk olan yatay boşluğu alır.

```
int GetHorzMargin();
```

### <a name="return-value"></a>Dönüş Değeri

Yatay kenar boşluğu.

## <a name="cmfccolorbargetvertmargin"></a><a name="getvertmargin"></a> CMFCColorBar:: GetVertMargin

Üst veya alt renk hücresi ile istemci alanı sınırı arasındaki boşluk olan dikey boşluğu alır.

```
int GetVertMargin() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dikey kenar boşluğu.

## <a name="cmfccolorbarinitcolors"></a><a name="initcolors"></a> CMFCColorBar:: ınitcolors

Belirli bir paletteki renklerle veya sistem varsayılan paleti ile bir renk dizisini başlatır.

```
static int InitColors(
    CPalette* pPalette,
    CArray<COLORREF, COLORREF>& arColors);
```

### <a name="parameters"></a>Parametreler

*pPalette*\
'ndaki Palet nesnesine yönelik bir işaretçi veya NULL. Bu parametre NULL ise, bu yöntem işletim sisteminin varsayılan paletini kullanır.

*Arrenkler*\
'ndaki Renk dizisi.

### <a name="return-value"></a>Dönüş Değeri

Renk dizisindeki öğelerin sayısı.

## <a name="cmfccolorbaristearoff"></a><a name="istearoff"></a> CMFCColorBar:: Isteyoff

Geçerli renk çubuğunun dockable olup olmadığını gösterir.

```
BOOL IsTearOff() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli renk çubuğu denetimi dockable ise doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Renk çubuğu denetimi dockable ise, bir denetim çubuğu bozulmuş olabilir ve başka bir konuma yerleştirilebilir.

## <a name="cmfccolorbaronkey"></a><a name="onkey"></a> CMFCColorBar:: OnKey

Kullanıcı bir klavye düğmesine bastığında Framework tarafından çağırılır.

```
virtual BOOL OnKey(UINT nChar);
```

### <a name="parameters"></a>Parametreler

*nChar*<br/>
'ndaki Bir kullanıcıya basılan anahtar için sanal anahtar kodu.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem belirtilen anahtarı işliyorsa doğru; Aksi takdirde, FALSE.

## <a name="cmfccolorbaronsendcommand"></a><a name="onsendcommand"></a> CMFCColorBar:: OnSendCommand

Bir açılır denetimlerin hiyerarşisini kapatmak için Framework tarafından çağırılır.

```
virtual BOOL OnSendCommand(const CMFCToolBarButton* pButton);
```

### <a name="parameters"></a>Parametreler

*pButton*\
'ndaki Bir araç çubuğunda bulunan denetimin işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

## <a name="cmfccolorbaronupdatecmdui"></a><a name="onupdatecmdui"></a> CMFCColorBar:: OnUpdateCmdUI

Öğe görüntülenmeden önce bir renk çubuğu denetiminin Kullanıcı arabirimi öğesini etkinleştirmek veya devre dışı bırakmak için Framework tarafından çağırılır.

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler);
```

### <a name="parameters"></a>Parametreler

*pTarget*<br/>
'ndaki Güncelleştirilecek bir kullanıcı arabirimi öğesi içeren pencerenin işaretçisi.

*bDisableIfNoHndler*<br/>
'ndaki İleti eşlemesinde hiçbir işleyici tanımlanmamışsa Kullanıcı arabirimi öğesini devre dışı bırakmak için TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Uygulamanızın bir kullanıcısı bir kullanıcı arabirimi öğesine tıkladığında, öğenin etkin veya devre dışı olarak görüntülenmesi gerekip gerekmediğini bilmelidir. Komut iletisinin hedefi, bir ON_UPDATE_COMMAND_UI komut işleyicisi uygulayarak bu bilgileri sağlar. Komutu işlemeye yardımcı olması için bu yöntemi kullanın. Daha fazla bilgi için bkz. [CCmdUI sınıfı](../../mfc/reference/ccmdui-class.md).

## <a name="cmfccolorbaropencolordialog"></a><a name="opencolordialog"></a> CMFCColorBar:: OpenColorDialog

Bir renk iletişim kutusu açar.

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>Parametreler

*colorDefault*<br/>
'ndaki Renk iletişim kutusu açıldığında varsayılan olarak seçilen renk.

*colorRes*<br/>
dışı Bir kullanıcının seçtiği renk.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı bir renk seçse doğru; Kullanıcı Color iletişim kutusunu iptal edildiyse FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolorbarrebuild"></a><a name="rebuild"></a> CMFCColorBar:: Rebuild

Renk çubuğu denetimini tamamen yeniden çizer.

```
virtual void Rebuild();
```

## <a name="cmfccolorbarselectpalette"></a><a name="selectpalette"></a> CMFCColorBar:: SelectPalette

Belirtilen cihaz bağlamının mantıksal paletini geçerli renk çubuğu denetiminin ana düğmesinin paleti olarak ayarlar.

```
CPalette* SelectPalette(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*\
'ndaki Geçerli renk çubuğu denetiminin ana düğmesinin cihaz bağlamı işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Geçerli renk çubuğu denetiminin üst düğmesinin paleti ile değiştirilmiş palet işaretçisi.

## <a name="cmfccolorbarsetcolor"></a><a name="setcolor"></a> CMFCColorBar:: SetColor

Şu anda seçili olan rengi ayarlar.

```cpp
void SetColor(COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
'ndaki Bir RGB renk değeri.

## <a name="cmfccolorbarsetcolorname"></a><a name="setcolorname"></a> CMFCColorBar:: SetColorName

Belirtilen renk için yeni bir ad ayarlar.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
'ndaki Rengin RGB değeri.

*strName*<br/>
'ndaki Belirtilen rengin yeni adı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, uygulamanızdaki tüm nesnelerde belirtilen rengin adını değiştirir `CMFCColorBar` .

## <a name="cmfccolorbarsetcommandid"></a><a name="setcommandid"></a> CMFCColorBar:: Setcommandıd

Renk çubuğu denetimi için yeni bir komut KIMLIĞI ayarlar.

```cpp
void SetCommandID(UINT nCommandID);
```

### <a name="parameters"></a>Parametreler

*nCommandID*<br/>
'ndaki Bir komut KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Bir renk çubuğu denetiminin komut KIMLIĞINI değiştirmek ve KIMLIğIN değiştiği denetimin üst penceresine bildirmek için bu yöntemi çağırın.

## <a name="cmfccolorbarsetdocumentcolors"></a><a name="setdocumentcolors"></a> CMFCColorBar:: SetDocumentColors

Geçerli belgede kullanılan renklerin listesini ayarlar.

```cpp
void SetDocumentColors(
    LPCTSTR lpszCaption,
    CList<COLORREF,COLORREF>& lstDocColors,
    BOOL bShowWhenDocked=FALSE);
```

### <a name="parameters"></a>Parametreler

*lpszCaption*<br/>
'ndaki Renk çubuğu denetimi yuvalandığında görüntülenen bir resim yazısı.

*lstDocColors*<br/>
'ndaki Geçerli belge renklerinin yerini alan renklerin bir listesi.

*Bshowwhensabitlenmiş*<br/>
'ndaki Renk çubuğu denetimi yerleştirildiğinde belge renklerini göstermek için TRUE; Aksi takdirde, FALSE. Varsayılan değer FALSE 'dur.

### <a name="remarks"></a>Açıklamalar

*Belge renkleri* , bir belgede Şu anda kullanılan renklerdir. Çerçeve, belge renklerinin bir listesini otomatik olarak tutar, ancak bu yöntemi listeyi değiştirmek için kullanabilirsiniz.

## <a name="cmfccolorbarsethorzmargin"></a><a name="sethorzmargin"></a> CMFCColorBar:: SetHorzMargin

Sol veya sağ renk hücresi ile istemci alanının sınırı arasındaki boşluk olan yatay boşluğu ayarlar.

```cpp
void SetHorzMargin(int nHorzMargin);
```

### <a name="parameters"></a>Parametreler

*nHorzMargin*<br/>
'ndaki Piksel cinsinden yatay kenar boşluğu.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [CMFCColorBar:: CMFCColorBar](#cmfccolorbar) Oluşturucu yatay kenar boşluğunu 4 piksel olarak ayarlar.

## <a name="cmfccolorbarsetproplist"></a><a name="setproplist"></a> CMFCColorBar:: SetPropList

`m_pWndPropList`Korumalı veri üyesini bir özellik Kılavuzu denetimine belirtilen işaretçiye ayarlar.

```cpp
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>Parametreler

*pWndList*\
'ndaki Özellik kılavuzu denetim nesnesine yönelik işaretçi.

## <a name="cmfccolorbarsetvertmargin"></a><a name="setvertmargin"></a> CMFCColorBar:: SetVertMargin

Üst veya alt renk hücresi ile istemci alanı sınırı arasındaki boşluk olan dikey boşluğu ayarlar.

```cpp
void SetVertMargin(int nVertMargin);
```

### <a name="parameters"></a>Parametreler

*nVertMargin*<br/>
'ndaki Piksel cinsinden dikey kenar boşluğu.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [CMFCColorBar:: CMFCColorBar](#cmfccolorbar) Oluşturucu dikey boşluğu 4 piksel olarak ayarlar.

## <a name="cmfccolorbarshowcommandmessagestring"></a><a name="showcommandmessagestring"></a> CMFCColorBar:: ShowCommandMessageString

Durum çubuğundaki ileti satırını güncelleştirmek için renk çubuğu denetiminin sahibi olan çerçeve penceresini ister.

```
virtual void ShowCommandMessageString(UINT uiCmdId);
```

### <a name="parameters"></a>Parametreler

*Uıımıdıd*<br/>
'ndaki Bir komut KIMLIĞI. (Bu parametre yok sayılır.)

### <a name="remarks"></a>Açıklamalar

Bu yöntem WM_SETMESSAGESTRING iletisini renk çubuğu denetiminin sahibine gönderir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)
