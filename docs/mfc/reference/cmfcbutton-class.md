---
description: 'Daha fazla bilgi edinin: CMFCButton sınıfı'
title: CMFCButton sınıfı
ms.date: 08/28/2018
f1_keywords:
- CMFCButton
- AFXBUTTON/CMFCButton
- AFXBUTTON/CMFCButton::CleanUp
- AFXBUTTON/CMFCButton::EnableFullTextTooltip
- AFXBUTTON/CMFCButton::EnableMenuFont
- AFXBUTTON/CMFCButton::EnableWindowsTheming
- AFXBUTTON/CMFCButton::GetToolTipCtrl
- AFXBUTTON/CMFCButton::IsAutoCheck
- AFXBUTTON/CMFCButton::IsAutorepeatCommandMode
- AFXBUTTON/CMFCButton::IsCheckBox
- AFXBUTTON/CMFCButton::IsChecked
- AFXBUTTON/CMFCButton::IsHighlighted
- AFXBUTTON/CMFCButton::IsPressed
- AFXBUTTON/CMFCButton::IsPushed
- AFXBUTTON/CMFCButton::IsRadioButton
- AFXBUTTON/CMFCButton::IsWindowsThemingEnabled
- AFXBUTTON/CMFCButton::SetAutorepeatMode
- AFXBUTTON/CMFCButton::SetCheckedImage
- AFXBUTTON/CMFCButton::SetFaceColor
- AFXBUTTON/CMFCButton::SetImage
- AFXBUTTON/CMFCButton::SetMouseCursor
- AFXBUTTON/CMFCButton::SetMouseCursorHand
- AFXBUTTON/CMFCButton::SetStdImage
- AFXBUTTON/CMFCButton::SetTextColor
- AFXBUTTON/CMFCButton::SetTextHotColor
- AFXBUTTON/CMFCButton::SetTooltip
- AFXBUTTON/CMFCButton::SizeToContent
- AFXBUTTON/CMFCButton::OnDraw
- AFXBUTTON/CMFCButton::OnDrawBorder
- AFXBUTTON/CMFCButton::OnDrawFocusRect
- AFXBUTTON/CMFCButton::OnDrawText
- AFXBUTTON/CMFCButton::OnFillBackground
- AFXBUTTON/CMFCButton::SelectFont
- AFXBUTTON/CMFCButton::m_bDrawFocus
- AFXBUTTON/CMFCButton::m_bHighlightChecked
- AFXBUTTON/CMFCButton::m_bRightImage
- AFXBUTTON/CMFCButton::m_bTransparent
- AFXBUTTON/CMFCButton::m_nAlignStyle
- AFXBUTTON/CMFCButton::m_nFlatStyle
helpviewer_keywords:
- CMFCButton [MFC], CleanUp
- CMFCButton [MFC], EnableFullTextTooltip
- CMFCButton [MFC], EnableMenuFont
- CMFCButton [MFC], EnableWindowsTheming
- CMFCButton [MFC], GetToolTipCtrl
- CMFCButton [MFC], IsAutoCheck
- CMFCButton [MFC], IsAutorepeatCommandMode
- CMFCButton [MFC], IsCheckBox
- CMFCButton [MFC], IsChecked
- CMFCButton [MFC], IsHighlighted
- CMFCButton [MFC], IsPressed
- CMFCButton [MFC], IsPushed
- CMFCButton [MFC], IsRadioButton
- CMFCButton [MFC], IsWindowsThemingEnabled
- CMFCButton [MFC], SetAutorepeatMode
- CMFCButton [MFC], SetCheckedImage
- CMFCButton [MFC], SetFaceColor
- CMFCButton [MFC], SetImage
- CMFCButton [MFC], SetMouseCursor
- CMFCButton [MFC], SetMouseCursorHand
- CMFCButton [MFC], SetStdImage
- CMFCButton [MFC], SetTextColor
- CMFCButton [MFC], SetTextHotColor
- CMFCButton [MFC], SetTooltip
- CMFCButton [MFC], SizeToContent
- CMFCButton [MFC], OnDraw
- CMFCButton [MFC], OnDrawBorder
- CMFCButton [MFC], OnDrawFocusRect
- CMFCButton [MFC], OnDrawText
- CMFCButton [MFC], OnFillBackground
- CMFCButton [MFC], SelectFont
- CMFCButton [MFC], m_bDrawFocus
- CMFCButton [MFC], m_bHighlightChecked
- CMFCButton [MFC], m_bRightImage
- CMFCButton [MFC], m_bTransparent
- CMFCButton [MFC], m_nAlignStyle
- CMFCButton [MFC], m_nFlatStyle
ms.assetid: 4b32f57c-7a53-4734-afb9-d47e3359f62e
ms.openlocfilehash: 4e75d5238dc427b4a6543b7bc6c1c3345f0df532
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327769"
---
# <a name="cmfcbutton-class"></a>CMFCButton sınıfı

`CMFCButton`Sınıfı, düğme metnini hizalama, düğme metnini ve görüntüyü birleştirme, imleç seçme ve araç ipucu belirtme gibi [CButton](../../mfc/reference/cbutton-class.md) sınıfına işlevsellik ekler.

## <a name="syntax"></a>Syntax

```
class CMFCButton : public CButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|`CMFCButton::CMFCButton`|Varsayılan Oluşturucu.|
|`CMFCButton::~CMFCButton`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCButton:: CleanUp](#cleanup)|İç değişkenleri sıfırlar ve görüntüler, bit eşlemler ve simgeler gibi ayrılmış kaynakları serbest bırakır.|
|`CMFCButton::CreateObject`|Framework tarafından bu sınıf türünün dinamik bir örneğini oluşturmak için kullanılır.|
|`CMFCButton::DrawItem`|Sahip tarafından çizilmiş bir düğmenin görsel bir yönü değiştiğinde Framework tarafından çağırılır. (Geçersiz kılmalar [CButton::D rawitem](../../mfc/reference/cbutton-class.md#drawitem).)|
|[CMFCButton:: EnableFullTextTooltip](#enablefulltexttooltip)|Bir araç ipucunun tam metninin büyük bir araç ipucu penceresinde mi yoksa küçük bir araç çubuğu penceresinde metnin kesilmiş bir sürümünde mi görüntüleneceğini belirtir.|
|[CMFCButton:: EnableMenuFont](#enablemenufont)|Düğme metni yazı tipinin, uygulama menüsü yazı tipiyle aynı olup olmadığını belirtir.|
|[CMFCButton:: Enablewindowstema](#enablewindowstheming)|Düğme kenarlığının stilinin geçerli Windows temasına karşılık gelmesi gerekip gerekmediğini belirtir.|
|`CMFCButton::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine bir işaretçi almak için Framework tarafından kullanılır.|
|[CMFCButton:: GetToolTipCtrl](#gettooltipctrl)|Temel araç ipucu denetimine bir başvuru döndürür.|
|[CMFCButton:: ısoto denetimi](#isautocheck)|Bir onay kutusunun veya radyo düğmesinin otomatik düğme olup olmayacağını gösterir.|
|[CMFCButton:: ısoto Repeatcommandmode](#isautorepeatcommandmode)|Bir düğmenin otomatik yineleme moduna ayarlanmış olup olmadığını gösterir.|
|[CMFCButton:: ıscheckbox](#ischeckbox)|Bir düğmenin onay kutusu düğmesi olup olmadığını gösterir.|
|[CMFCButton:: IsChecked](#ischecked)|Geçerli düğmenin işaretli olup olmadığını gösterir.|
|[CMFCButton:: ısvurgulu](#ishighlighted)|Bir düğmenin vurgulanıp vurgulanmadığını gösterir.|
|[CMFCButton:: ısbastı](#ispressed)|Bir düğmenin gönderilip ayrılmadığını ve vurgulanmayacağını gösterir.|
|[CMFCButton:: ısitilmiş](#ispushed)|Bir düğmenin gönderilip atılmadığını gösterir.|
|[CMFCButton:: IsRadioButton](#isradiobutton)|Bir düğmenin radyo düğmesi olup olmadığını gösterir.|
|[CMFCButton:: IsWindowsThemingEnabled](#iswindowsthemingenabled)|Düğme kenarlığının stilinin geçerli Windows temasına karşılık geldiğini gösterir.|
|`CMFCButton::OnDrawParentBackground`|Belirtilen alanda bir düğmenin üstünün arka planını çizer. (Geçersiz kılmalar [AFX_GLOBAL_DATA::D rawParentBackground](../../mfc/reference/afx-global-data-structure.md)|
|`CMFCButton::PreTranslateMessage`|[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine dağıtılmadan önce pencere iletilerini çevirir. ( [CWnd::P reTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)geçersiz kılar.)|
|[CMFCButton:: SetAutorepeatMode](#setautorepeatmode)|Otomatik yineleme moduna bir düğme ayarlar.|
|[CMFCButton:: Setcheckedımage](#setcheckedimage)|İşaretli bir düğmenin görüntüsünü ayarlar.|
|[CMFCButton:: SetFaceColor](#setfacecolor)|Düğme metni için arka plan rengini ayarlar.|
|[CMFCButton:: SetImage](#setimage)|Bir düğmenin görüntüsünü ayarlar.|
|[CMFCButton:: Setmousecurcursor](#setmousecursor)|İmleç resmini ayarlar.|
|[CMFCButton:: SetMouseCursorHand](#setmousecursorhand)|İmleci bir el resmine ayarlar.|
|[CMFCButton:: Setstdımage](#setstdimage)|`CMenuImages`Düğme görüntüsünü ayarlamak için bir nesnesi kullanır.|
|[CMFCButton:: SetTextColor](#settextcolor)|Seçili olmayan bir düğme için düğme metninin rengini ayarlar.|
|[CMFCButton:: SetTextHotColor](#settexthotcolor)|Seçilen bir düğme için düğme metninin rengini ayarlar.|
|[CMFCButton:: SetTooltip](#settooltip)|Araç ipucunu bir düğmeyle ilişkilendirir.|
|[CMFCButton:: SizeToContent](#sizetocontent)|Bir düğmeyi düğme metnini ve görüntüsünü içerecek şekilde yeniden boyutlandırır.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCButton:: OnDraw](#ondraw)|Bir düğme çizmek için Framework tarafından çağırılır.|
|[CMFCButton:: OnDrawBorder](#ondrawborder)|Bir düğmenin kenarlığını çizmek için Framework tarafından çağırılır.|
|[CMFCButton:: OnDrawFocusRect](#ondrawfocusrect)|Düğme için odak dikdörtgeni çizmek üzere Framework tarafından çağırılır.|
|[CMFCButton:: OnDrawText](#ondrawtext)|Düğme metnini çizmek için Framework tarafından çağırılır.|
|[CMFCButton:: OnFillBackground](#onfillbackground)|Düğme metninin arka planını çizmek için Framework tarafından çağırılır.|
|[CMFCButton:: SelectFont](#selectfont)|Belirtilen cihaz içeriğiyle ilişkili yazı tipini alır.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCButton:: m_nAlignStyle](#m_nalignstyle)|Düğme metninin hizalamasını belirtir.|
|[CMFCButton:: m_bDontUseWinXPTheme](#m_bDontUseWinXPTheme)|Windows XP temaları 'nın kullanılıp kullanılmayacağını belirtir.|
|[CMFCButton:: m_bDrawFocus](#m_bdrawfocus)|Düğme etrafında bir odak dikdörtgeni çizip çizmeyeceğinizi gösterir.|
|[CMFCButton:: m_nFlatStyle](#m_nflatstyle)|Düğme stilini belirtir (örneğin, Kenarlıksız, düz, yarı düz veya 3B).|
|[CMFCButton:: m_bGrayDisabled](#m_bGrayDisabled)|DOĞRU olduğunda, devre dışı bir düğmenin gri çizili olarak çizilmesini sağlar.|
|[CMFCButton:: m_bHighlightChecked](#m_bhighlightchecked)|İmleç üzerine geldiğinde BS_CHECKBOX stili bir düğmenin vurgulanmasını belirtir.|
|[CMFCButton:: m_bResponseOnButtonDown](#m_bResponseOnButtonDown)|Düğme azaltma olaylarına yanıt verilip verilmeyeceğini gösterir.|
|[CMFCButton:: m_bRightImage](#m_brightimage)|Düğmenin sağ tarafında bir görüntünün görüntülenip görüntülenmeyeceğini gösterir.|
|[CMFCButton:: m_bTopImage](#m_bTopImage)| Resmin düğmenin üstünde olup olmadığını gösterir.|
|[CMFCButton:: m_bTransparent](#m_btransparent)|Düğmenin saydam olup olmadığını gösterir.|
|[CMFCButton:: m_bWasDblClk](#m_bWasDblClk)| Son tıklama olayının çift tıkladığını gösterir.|

## <a name="remarks"></a>Açıklamalar

Diğer düğme türleri `CMFCButton` ,, köprüleri destekleyen [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md) sınıfı ve `CMFCColorButton` Renk Seçici iletişim kutusunu destekleyen sınıfı gibi sınıftan türetilir.

Bir `CMFCButton` nesnenin stili *3B*, *düz*, *yarı düz* veya *kenarlık yok* olabilir. Düğme metni, bir düğmenin sol, üst veya merkezinde hizalanabilir. Çalışma zamanında, düğmenin metin, resim veya metin ve görüntü görüntüleyip görüntülemediğini denetleyebilirsiniz. İmleç bir düğmenin üzerine geldiğinde belirli bir imleç resminin görüntülenmesini de belirtebilirsiniz.

Doğrudan kodunuzda veya **MFC sınıf Sihirbazı** aracını ve bir iletişim kutusu şablonunu kullanarak bir düğme denetimi oluşturun. Doğrudan bir düğme denetimi oluşturursanız `CMFCButton` uygulamanıza bir değişken ekleyin ve ardından nesnenin oluşturucusunu ve `Create` yöntemlerini çağırın `CMFCButton` . **MFC sınıf Sihirbazı 'nı** kullanırsanız `CButton` uygulamanıza bir değişken ekleyin ve sonra değişkenin türünü `CButton` olarak değiştirin `CMFCButton` .

Bir iletişim kutusu uygulamasında bildirim iletilerini işlemek için her bildirim için bir ileti eşleme girişi ve bir olay işleyicisi ekleyin. Bir nesne tarafından gönderilen bildirimler `CMFCButton` bir nesne tarafından gönderilen olanlarla aynıdır `CButton` .

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında çeşitli yöntemler kullanarak düğmenin özelliklerinin nasıl yapılandırılacağını gösterir `CMFCButton` . Örnek, [Yeni denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]
[!code-cpp[NVC_MFC_NewControls#32](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_3.cpp)]
[!code-cpp[NVC_MFC_NewControls#33](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_4.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxbutton. h

## <a name="cmfcbuttoncleanup"></a><a name="cleanup"></a> CMFCButton:: CleanUp

İç değişkenleri sıfırlar ve görüntüler, bit eşlemler ve simgeler gibi ayrılmış kaynakları serbest bırakır.

```
virtual void CleanUp();
```

## <a name="cmfcbuttonenablefulltexttooltip"></a><a name="enablefulltexttooltip"></a> CMFCButton:: EnableFullTextTooltip

Bir araç ipucunun tam metninin büyük bir araç ipucu penceresinde mi yoksa küçük bir araç çubuğu penceresinde metnin kesilmiş bir sürümünde mi görüntüleneceğini belirtir.

```cpp
void EnableFullTextTooltip(BOOL bOn=TRUE);
```

### <a name="parameters"></a>Parametreler

*Um*<br/>
'ndaki Metnin tümünü göstermek için TRUE; Kesilen metni göstermek için FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonenablemenufont"></a><a name="enablemenufont"></a> CMFCButton:: EnableMenuFont

Düğme metni yazı tipinin, uygulama menüsü yazı tipiyle aynı olup olmadığını belirtir.

```cpp
void EnableMenuFont(
    BOOL bOn=TRUE,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parametreler

*Um*<br/>
'ndaki Düğme metin yazı tipi olarak uygulama menüsü yazı tipini kullanmak için TRUE. Sistem yazı tipini kullanmak için FALSE. Varsayılan değer TRUE 'dur.

*bRedraw*<br/>
'ndaki Ekranın hemen yeniden çizilebilmesi için TRUE. Aksi takdirde, FALSE. Varsayılan değer TRUE 'dur.

### <a name="remarks"></a>Açıklamalar

Düğme metni yazı tipini belirtmek için bu yöntemi kullanmazsanız, yazı tipini [CWnd:: SetFont](../../mfc/reference/cwnd-class.md#setfont) yöntemiyle belirtebilirsiniz. Bir yazı tipi belirtmezseniz, çerçeve varsayılan bir yazı tipi ayarlar.

## <a name="cmfcbuttonenablewindowstheming"></a><a name="enablewindowstheming"></a> CMFCButton:: Enablewindowstema

Düğme kenarlığının stilinin geçerli Windows temasına karşılık gelmesi gerekip gerekmediğini belirtir.

```
static void EnableWindowsTheming(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Düğme kenarlıklarını çizmek için geçerli Windows temasını kullanmak için TRUE; Windows temasını kullanmadan önce FALSE. Varsayılan değer TRUE 'dur.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, uygulamanızdaki sınıfından türetilmiş tüm düğmeleri etkiler `CMFCButton` .

## <a name="cmfcbuttongettooltipctrl"></a><a name="gettooltipctrl"></a> CMFCButton:: GetToolTipCtrl

Temel araç ipucu denetimine bir başvuru döndürür.

```
CToolTipCtrl& GetToolTipCtrl();
```

### <a name="return-value"></a>Dönüş Değeri

Temel araç ipucu denetimine başvuru.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonisautocheck"></a><a name="isautocheck"></a> CMFCButton:: ısoto denetimi

Bir onay kutusunun veya radyo düğmesinin otomatik düğme olup olmayacağını gösterir.

```
BOOL IsAutoCheck() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme stil BS_AUTOCHECKBOX veya BS_AUTORADIOBUTTON içeriyorsa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonisautorepeatcommandmode"></a><a name="isautorepeatcommandmode"></a> CMFCButton:: ısoto Repeatcommandmode

Bir düğmenin otomatik yineleme moduna ayarlanmış olup olmadığını gösterir.

```
BOOL IsAutorepeatCommandMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme otomatik yineleme moduna ayarlandıysa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Otomatik yineleme moduna bir düğme ayarlamak için [CMFCButton:: SetAutorepeatMode](#setautorepeatmode) metodunu kullanın.

## <a name="cmfcbuttonischeckbox"></a><a name="ischeckbox"></a> CMFCButton:: ıscheckbox

Bir düğmenin onay kutusu düğmesi olup olmadığını gösterir.

```
BOOL IsCheckBox() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme BS_CHECKBOX ya da BS_AUTOCHECKBOX stiline sahipse TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonischecked"></a><a name="ischecked"></a> CMFCButton:: IsChecked

Geçerli düğmenin işaretli olup olmadığını gösterir.

```
BOOL IsChecked() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli düğme işaretliyse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Çerçeve, farklı düğme türlerinin denetlendiğini göstermek için farklı yollar kullanır. Örneğin, bir nokta içerdiğinde radyo düğmesi işaretlenir; bir onay kutusu **X** içerdiğinde denetlenir.

## <a name="cmfcbuttonishighlighted"></a><a name="ishighlighted"></a> CMFCButton:: ısvurgulu

Bir düğmenin vurgulanıp vurgulanmadığını gösterir.

```
BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme vurgulanmışsa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Fare düğmenin üzerine geldiğinde düğme vurgulanır.

## <a name="cmfcbuttonispressed"></a><a name="ispressed"></a> CMFCButton:: ısbastı

Bir düğmenin gönderilip ayrılmadığını ve vurgulanmayacağını gösterir.

```
BOOL IsPressed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmeye basıldığında doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonispushed"></a><a name="ispushed"></a> CMFCButton:: ısitilmiş

Bir düğmenin gönderilip atılmadığını gösterir.

```
BOOL IsPushed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme itilliyse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonisradiobutton"></a><a name="isradiobutton"></a> CMFCButton:: IsRadioButton

Bir düğmenin radyo düğmesi olup olmadığını gösterir.

```
BOOL IsRadioButton() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme stili BS_RADIOBUTTON veya BS_AUTORADIOBUTTON ise doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttoniswindowsthemingenabled"></a><a name="iswindowsthemingenabled"></a> CMFCButton:: IsWindowsThemingEnabled

Düğme kenarlığının stilinin geçerli Windows temasına karşılık geldiğini gösterir.

```
static BOOL IsWindowsThemingEnabled();
```

### <a name="return-value"></a>Dönüş Değeri

Düğme kenarlığının stili geçerli Windows temasına karşılık geliyorsa doğru; Aksi takdirde, FALSE.

## <a name="cmfcbuttonm_bdontusewinxptheme"></a><a name="m_bDontUseWinXPTheme"/> CMFCButton:: m_bDontUseWinXPTheme

Düğme çizerken Windows XP temalarını kullanıp kullanmayacağınızı belirtir.

```
BOOL m_bDontUseWinXPTheme;
```

## <a name="cmfcbuttonm_bdrawfocus"></a><a name="m_bdrawfocus"></a> CMFCButton:: m_bDrawFocus

Düğme etrafında bir odak dikdörtgeni çizip çizmeyeceğinizi gösterir.

```
BOOL m_bDrawFocus;
```

### <a name="remarks"></a>Açıklamalar

`m_bDrawFocus`Düğmenin odak alırsa düğmenin metin ve görüntüsünün etrafında bir odak dikdörtgeni çizileceğini belirtmek için üyeyı true olarak ayarlayın.

`CMFCButton`Oluşturucu bu üyeyı doğru olarak başlatır.

## <a name="cmfcbuttonm_bgraydisabled"></a><a name="m_bGrayDisabled"></a> CMFCButton:: m_bGrayDisabled

DOĞRU olduğunda, devre dışı bir düğmenin gri çizili olarak çizilmesini sağlar.

```
BOOL m_bGrayDisabled;
```

## <a name="cmfcbuttonm_bhighlightchecked"></a><a name="m_bhighlightchecked"></a> CMFCButton:: m_bHighlightChecked

İmleç üzerine geldiğinde BS_CHECKBOX stili bir düğmenin vurgulanmasını belirtir.

```
BOOL m_bHighlightChecked;
```

### <a name="remarks"></a>Açıklamalar

`m_bHighlightChecked`Farenin üzerine geldiğinde BS_CHECKBOX stili bir düğme vurgulayamadığını belirtmek için üyeyı true olarak ayarlayın.

## <a name="cmfcbuttonm_bresponseonbuttondown"></a><a name="m_bResponseOnButtonDown"></a> CMFCButton:: m_bResponseOnButtonDown

Düğme azaltma olaylarına yanıt verilip verilmeyeceğini gösterir.

```
BOOL m_bResponseOnButtonDown;
```

## <a name="cmfcbuttonm_brightimage"></a><a name="m_brightimage"></a> CMFCButton:: m_bRightImage

Düğmenin sağ tarafında bir görüntünün görüntülenip görüntülenmeyeceğini gösterir.

```
BOOL m_bRightImage;
```

## <a name="cmfcbuttonm_btopimagem_btopimage"></a><a name="m_bTopImage"></a> CMFCButton:: m_bTopImage] (#m_bTopImage)

Resmin düğmenin üstünde olup olmadığını gösterir.

```
BOOL m_bTopImage;
```

### <a name="remarks"></a>Açıklamalar

`m_bRightImage`Çerçevenin düğmenin metin etiketinin sağında düğme görüntüsünü göstermesini belirtmek için üyeyı doğru olarak ayarlayın.

## <a name="cmfcbuttonm_btransparent"></a><a name="m_btransparent"></a> CMFCButton:: m_bTransparent

Düğmenin saydam olup olmadığını gösterir.

```
BOOL m_bTransparent;
```

### <a name="remarks"></a>Açıklamalar

`m_bTransparent`Çerçevenin düğmeyi saydam hale ayarlayabelirtmesini belirtmek için üyeyı true olarak ayarlayın. `CMFCButton`Oluşturucu bu üyeyı false olarak başlatır.

## <a name="cmfcbuttonm_nalignstyle"></a><a name="m_nalignstyle"></a> CMFCButton:: m_nAlignStyle

Düğme metninin hizalamasını belirtir.

```
AlignStyle m_nAlignStyle;
```

### <a name="remarks"></a>Açıklamalar

`CMFCButton::AlignStyle`Düğme metninin hizalamasını belirtmek için aşağıdaki sabit listesi değerlerinden birini kullanın:

|Değer|Açıklama|
|-----------|-----------------|
|ALIGN_CENTER|Varsayılanını Düğme metnini düğmenin ortasına hizalar.|
|ALIGN_LEFT|Düğme metnini düğmenin sol tarafına hizalar.|
|ALIGN_RIGHT|Düğme metnini düğmenin sağ tarafına hizalar.|

`CMFCButton`Oluşturucu bu üyeyi ALIGN_CENTER için başlatır.

## <a name="cmfcbuttonm_bwasdblclkm_bwasdblclk"></a><a name="m_bWasDblClk"></a> CMFCButton:: m_bWasDblClk] (#m_bWasDblClk) |

Son tıklama olayının çift tıkladığını gösterir. |

```
BOOL m_bWasDblClk;
```

## <a name="cmfcbuttonm_nflatstyle"></a><a name="m_nflatstyle"></a> CMFCButton:: m_nFlatStyle

Düğme stilini belirtir (örneğin, Kenarlıksız, düz, yarı düz veya 3B).

```
FlatStyle  m_nFlatStyle;
```

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda `CMFCButton::m_nFlatStyle` bir düğmenin görünümünü belirten numaralandırma değerleri listelenmektedir.

|Değer|Açıklama|
|-----------|-----------------|
|BUTTONSTYLE_3D|Varsayılanını Düğme, büyük ve üç boyutlu kenarları olan bir şekilde görünür. Düğmeye tıklandığında düğme, derinlemesine bir girintiye basıldığında görüntülenir.|
|BUTTONSTYLE_FLAT|Fare düğme üzerinde duraklatamaktığında, düğme iki boyutlu gibi görünür ve kabarık yanları yoktur. Fare düğme üzerinde durakladığında, düğme az, üç boyutlu taraflara sahip olacak şekilde görünür. Düğmeye tıklandığında düğme, bir basit girintiye basıldığında görüntülenir.|
|BUTTONSTYLE_SEMIFLAT|Düğme az, üç boyutlu kenarlara sahip gibi görünür. Düğmeye tıklandığında düğme, derinlemesine bir girintiye basıldığında görüntülenir.|
|BUTTONSTYLE_NOBORDERS|Düğme, kabarık yanlara sahip değildir ve her zaman iki boyutlu görünür. Düğme tıklandığında bir girintiye basılmamış gibi görünmüyor.|

`CMFCButton`Oluşturucu bu üyeyi BUTTONSTYLE_3D için başlatır.

### <a name="example"></a>Örnek

Aşağıdaki örnekte, sınıfındaki üye değişkeni değerlerinin nasıl ayarlanacağı gösterilmektedir `m_nFlatStyle` `CMFCButton` . Bu örnek, [Yeni denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#29](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_5.cpp)]

## <a name="cmfcbuttonondraw"></a><a name="ondraw"></a> CMFCButton:: OnDraw

Bir düğme çizmek için Framework tarafından çağırılır.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*Rect*<br/>
'ndaki Düğmeyi sınıralan bir dikdörtgene başvuru.

*uiState*<br/>
'ndaki Geçerli düğme durumu. Daha fazla bilgi için `itemState` [Drawitemstruct yapısı](/windows/win32/api/winuser/ns-winuser-drawitemstruct) konusunun üyesine bakın.

### <a name="remarks"></a>Açıklamalar

Bir düğme çizmek için kendi kodunuzu kullanmak üzere bu yöntemi geçersiz kılın.

## <a name="cmfcbuttonondrawborder"></a><a name="ondrawborder"></a> CMFCButton:: OnDrawBorder

Bir düğmenin kenarlığını çizmek için Framework tarafından çağırılır.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*rectClient*<br/>
'ndaki Düğmeyi sınıralan bir dikdörtgene başvuru.

*uiState*<br/>
'ndaki Geçerli düğme durumu. Daha fazla bilgi için `itemState` [Drawitemstruct yapısı](/windows/win32/api/winuser/ns-winuser-drawitemstruct) konusunun üyesine bakın.

### <a name="remarks"></a>Açıklamalar

Kenarlık çizmek için kendi kodunuzu kullanmak üzere bu yöntemi geçersiz kılın.

## <a name="cmfcbuttonondrawfocusrect"></a><a name="ondrawfocusrect"></a> CMFCButton:: OnDrawFocusRect

Düğme için odak dikdörtgeni çizmek üzere Framework tarafından çağırılır.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*rectClient*<br/>
'ndaki Düğmeyi sınıralan bir dikdörtgene başvuru.

### <a name="remarks"></a>Açıklamalar

Odak dikdörtgenini çizmek için kendi kodunuzu kullanmak üzere bu yöntemi geçersiz kılın.

## <a name="cmfcbuttonondrawtext"></a><a name="ondrawtext"></a> CMFCButton:: OnDrawText

Düğme metnini çizmek için Framework tarafından çağırılır.

```
virtual void OnDrawText(
    CDC* pDC,
    const CRect& rect,
    const CString& strText,
    UINT uiDTFlags,
    UINT uiState);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*Rect*<br/>
'ndaki Düğmeyi sınıralan bir dikdörtgene başvuru.

*strText*<br/>
'ndaki Çizilecek metin.

*Uııdtflags*<br/>
'ndaki Metnin nasıl biçimlendirileceğini belirten bayraklar. Daha fazla bilgi için bkz. [CDC::D rawText](../../mfc/reference/cdc-class.md#drawtext) yönteminin *nFormat* parametresi.

*uiState*<br/>
'ndaki Ayrılamadı.

### <a name="remarks"></a>Açıklamalar

Düğme metnini çizmek için kendi kodunuzu kullanmak üzere bu yöntemi geçersiz kılın.

## <a name="cmfcbuttononfillbackground"></a><a name="onfillbackground"></a> CMFCButton:: OnFillBackground

Düğme metninin arka planını çizmek için Framework tarafından çağırılır.

```
virtual void OnFillBackground(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*rectClient*<br/>
'ndaki Düğmeyi sınıralan bir dikdörtgene başvuru.

### <a name="remarks"></a>Açıklamalar

Bir düğmenin arka planını çizmek üzere kendi kodunuzu kullanmak için bu yöntemi geçersiz kılın.

## <a name="cmfcbuttonselectfont"></a><a name="selectfont"></a> CMFCButton:: SelectFont

Belirtilen cihaz içeriğiyle ilişkili yazı tipini alır.

```
virtual CFont* SelectFont(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yazı tipini almak için kendi kodunuzu kullanmak üzere bu yöntemi geçersiz kılın.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonsetautorepeatmode"></a><a name="setautorepeatmode"></a> CMFCButton:: SetAutorepeatMode

Otomatik yineleme moduna bir düğme ayarlar.

```cpp
void SetAutorepeatMode(int nTimeDelay=500);
```

### <a name="parameters"></a>Parametreler

*nTimeDelay*<br/>
'ndaki Ana pencereye gönderilen iletiler arasındaki aralığı belirten negatif olmayan bir sayı. Aralık milisaniye cinsinden ölçülür ve varsayılan değeri 500 milisaniyedir. Otomatik tekrarlanacak ileti modunu devre dışı bırakmak için sıfır değerini belirtin.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, düğme serbest bırakılana kadar veya *nTimeDelay* parametresi sıfır olarak ayarlandığında düğmenin ana pencereye sürekli olarak WM_COMMAND iletileri göndermesini sağlar.

## <a name="cmfcbuttonsetcheckedimage"></a><a name="setcheckedimage"></a> CMFCButton:: Setcheckedımage

İşaretli bir düğmenin görüntüsünü ayarlar.

```cpp
void SetCheckedImage(
    HICON hIcon,
    BOOL bAutoDestroy=TRUE,
    HICON hIconHot=NULL,
    HICON hIconDisabled=NULL,
    BOOL bAlphaBlend=FALSE);

void SetCheckedImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy=TRUE,
    HBITMAP hBitmapHot=NULL,
    BOOL bMap3dColors=TRUE,
    HBITMAP hBitmapDisabled=NULL);

void SetCheckedImage(
    UINT uiBmpResId,
    UINT uiBmpHotResId=0,
    UINT uiBmpDsblResID=0);
```

### <a name="parameters"></a>Parametreler

*HICON*<br/>
'ndaki Yeni görüntünün bit eşlemini ve maskesini içeren simgeye yönelik işleme.

*bAutoDestroy*<br/>
'ndaki Bit eşlem kaynaklarının otomatik olarak yok edileceği belirtmek için TRUE; Aksi takdirde, FALSE. Varsayılan değer TRUE 'dur.

*hIconHot*<br/>
'ndaki Seçili durum için görüntüyü içeren simgeye yönelik işleyici.

*HBITMAP*<br/>
'ndaki Seçili olmayan durumun görüntüsünü içeren bit eşlemle işleme.

*hBitmapHot*<br/>
'ndaki Seçili durum için görüntüyü içeren bit eşlem için tanıtıcı.

*bMap3dColors*<br/>
'ndaki Düğme arka planı için saydam bir renk belirtir; diğer bir deyişle, düğmenin yüzü. RGB renk değerini kullanmak için TRUE (192, 192, 192); Tarafından tanımlanan renk değerini kullanmak için FALSE `AFX_GLOBAL_DATA::clrBtnFace` .

*Uıımpresd*<br/>
'ndaki Seçili olmayan görüntünün kaynak KIMLIĞI.

*Uıımphotresd*<br/>
'ndaki Seçili görüntü için kaynak KIMLIĞI.

*hIconDisabled*<br/>
'ndaki Devre dışı bırakılan görüntünün simgesine yönelik işleç.

*Hbitmapdevre dışı*<br/>
'ndaki Devre dışı bırakılan görüntüyü içeren bit eşlemle işleme.

*Uıımpdsblresd*<br/>
'ndaki Devre dışı bitmapin kaynak KIMLIĞI.

*bAlphaBlend*<br/>
'ndaki Yalnızca alfa kanalını kullanan 32 bitlik görüntüleri kullanmak için TRUE; Yalnızca alfa kanal görüntülerini kullanmak için FALSE. Varsayılan değer FALSE 'dur.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonsetfacecolor"></a><a name="setfacecolor"></a> CMFCButton:: SetFaceColor

Düğme metni için arka plan rengini ayarlar.

```cpp
void SetFaceColor(
    COLORREF crFace,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parametreler

*crFace*<br/>
'ndaki Bir RGB renk değeri.

*bRedraw*<br/>
'ndaki Ekranı hemen yeniden çizmek için TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Düğme arka planı (yüz) için yeni bir doldur rengi tanımlamak üzere bu yöntemi kullanın. [CMFCButton:: m_bTransparent](#m_btransparent) üye değişkeni true olduğunda arka planın doldurulmadığını unutmayın.

## <a name="cmfcbuttonsetimage"></a><a name="setimage"></a> CMFCButton:: SetImage

Bir düğmenin görüntüsünü ayarlar.

```cpp
void SetImage(
    HICON hIcon,
    BOOL bAutoDestroy=TRUE,
    HICON hIconHot=NULL,
    HICON hIconDisabled=NULL,
    BOOL bAlphaBlend=FALSE);

void SetImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy=TRUE,
    HBITMAP hBitmapHot=NULL,
    BOOL bMap3dColors=TRUE,
    HBITMAP hBitmapDisabled=NULL);

void SetImage(
    UINT uiBmpResId,
    UINT uiBmpHotResId=0,
    UINT uiBmpDsblResID=0);
```

### <a name="parameters"></a>Parametreler

*HICON*<br/>
'ndaki Yeni görüntünün bit eşlemini ve maskesini içeren simgeye yönelik işleme.

*bAutoDestroy*<br/>
'ndaki Bit eşlem kaynaklarının otomatik olarak yok edileceği belirtmek için TRUE; Aksi takdirde, FALSE. Varsayılan değer TRUE 'dur.

*hIconHot*<br/>
'ndaki Seçili durum için görüntüyü içeren simgeye yönelik işleyici.

*HBITMAP*<br/>
'ndaki Seçili olmayan durumun görüntüsünü içeren bit eşlemle işleme.

*hBitmapHot*<br/>
'ndaki Seçili durum için görüntüyü içeren bit eşlem için tanıtıcı.

*Uıımpresd*<br/>
'ndaki Seçili olmayan görüntünün kaynak KIMLIĞI.

*Uıımphotresd*<br/>
'ndaki Seçili görüntü için kaynak KIMLIĞI.

*bMap3dColors*<br/>
'ndaki Düğme arka planı için saydam bir renk belirtir; diğer bir deyişle, düğmenin yüzü. RGB renk değerini kullanmak için TRUE (192, 192, 192); Tarafından tanımlanan renk değerini kullanmak için FALSE `AFX_GLOBAL_DATA::clrBtnFace` .

*hIconDisabled*<br/>
'ndaki Devre dışı bırakılan görüntünün simgesine yönelik işleç.

*Hbitmapdevre dışı*<br/>
'ndaki Devre dışı bırakılan görüntüyü içeren bit eşlemle işleme.

*Uıımpdsblresd*<br/>
'ndaki Devre dışı bitmapin kaynak KIMLIĞI.

*bAlphaBlend*<br/>
'ndaki Yalnızca alfa kanalını kullanan 32 bitlik görüntüleri kullanmak için TRUE; Yalnızca alfa kanal görüntülerini kullanmak için FALSE. Varsayılan değer FALSE 'dur.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında yönteminin çeşitli sürümlerini nasıl kullanacağınızı gösterir `SetImage` `CMFCButton` . Örnek, [Yeni denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]

## <a name="cmfcbuttonsetmousecursor"></a><a name="setmousecursor"></a> CMFCButton:: Setmousecurcursor

İmleç resmini ayarlar.

```cpp
void SetMouseCursor(HCURSOR hcursor);
```

### <a name="parameters"></a>Parametreler

*hCursor*<br/>
'ndaki İmlecin tutamacı.

### <a name="remarks"></a>Açıklamalar

Düğme ile imleç gibi bir imleç görüntüsünü ilişkilendirmek için bu yöntemi kullanın. İmleç uygulama kaynaklarından yüklenir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfında yönteminin nasıl kullanılacağını gösterir `SetMouseCursor` `CMFCButton` . Örnek, [Yeni denetimler örneğindeki](../../overview/visual-cpp-samples.md)kodun bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#30](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_6.cpp)]

## <a name="cmfcbuttonsetmousecursorhand"></a><a name="setmousecursorhand"></a> CMFCButton:: SetMouseCursorHand

İmleci bir el resmine ayarlar.

```cpp
void SetMouseCursorHand();
```

### <a name="remarks"></a>Açıklamalar

Bir Hand 'in imleç resmini düğme ile ilişkilendirmek için bu yöntemi kullanın. İmleç uygulama kaynaklarından yüklenir.

## <a name="cmfcbuttonsetstdimage"></a><a name="setstdimage"></a> CMFCButton:: Setstdımage

`CMenuImages`Düğme görüntüsünü ayarlamak için bir nesnesi kullanır.

```cpp
void SetStdImage(
    CMenuImages::IMAGES_IDS id,
    CMenuImages::IMAGE_STATE state=CMenuImages::ImageBlack,
    CMenuImages::IMAGES_IDS idDisabled=(CMenuImages::IMAGES_IDS)0);
```

### <a name="parameters"></a>Parametreler

*id*<br/>
'ndaki Numaralandırmada tanımlanan düğme görüntüsü tanımlayıcılarından biri `CMenuImage::IMAGES_IDS` . Görüntü değerleri oklar, PIN 'ler ve radyo düğmeleri gibi görüntüleri belirler.

*durumunda*<br/>
'ndaki Sabit listesi içinde tanımlanan düğme görüntüsü durum tanımlayıcılarından biri `CMenuImages::IMAGE_STATE` . Görüntü durumları siyah, gri, açık gri, beyaz ve koyu gri gibi düğme renklerini belirtir. `CMenuImages::ImageBlack` varsayılan değerdir.

*ıddisabled*<br/>
'ndaki Numaralandırmada tanımlanan düğme görüntüsü tanımlayıcılarından biri `CMenuImage::IMAGES_IDS` . Resim, düğmenin devre dışı olduğunu gösterir. Varsayılan değer, ilk düğme görüntüsüdür ( `CMenuImages::IdArrowDown` ).

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonsettextcolor"></a><a name="settextcolor"></a> CMFCButton:: SetTextColor

Seçili olmayan bir düğme için düğme metninin rengini ayarlar.

```cpp
void SetTextColor(COLORREF clrText);
```

### <a name="parameters"></a>Parametreler

*clrText*<br/>
'ndaki Bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonsettexthotcolor"></a><a name="settexthotcolor"></a> CMFCButton:: SetTextHotColor

Seçilen bir düğme için düğme metninin rengini ayarlar.

```cpp
void SetTextHotColor(COLORREF clrTextHot);
```

### <a name="parameters"></a>Parametreler

*clrTextHot*<br/>
'ndaki Bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonsettooltip"></a><a name="settooltip"></a> CMFCButton:: SetTooltip

Araç ipucunu bir düğmeyle ilişkilendirir.

```cpp
void SetTooltip(LPCTSTR lpszToolTipText);
```

### <a name="parameters"></a>Parametreler

*lpszToolTipText*<br/>
'ndaki Araç ipucu için metin işaretçisi. Araç ipucunu devre dışı bırakmak için NULL değerini belirtin.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonsizetocontent"></a><a name="sizetocontent"></a> CMFCButton:: SizeToContent

Bir düğmeyi düğme metnini ve görüntüsünü içerecek şekilde yeniden boyutlandırır.

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>Parametreler

*bCalcOnly*<br/>
'ndaki Düğmenin yeni boyutunu hesaplamak, ancak değiştirmek için TRUE; Düğmenin boyutunu değiştirmek için FALSE. Varsayılan değer FALSE 'dur.

### <a name="return-value"></a>Dönüş Değeri

`CSize`Düğmenin yeni boyutunu içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem 10 piksellik yatay bir kenar boşluğu ve 5 piksellik dikey bir kenar boşluğu içeren yeni bir boyut hesaplar.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCLinkCtrl sınıfı](../../mfc/reference/cmfclinkctrl-class.md)<br/>
[CMFCColorButton sınıfı](../../mfc/reference/cmfccolorbutton-class.md)<br/>
[Cmfcmenubtan sınıfı](../../mfc/reference/cmfcmenubutton-class.md)
