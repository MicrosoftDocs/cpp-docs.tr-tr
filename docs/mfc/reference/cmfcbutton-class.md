---
title: CMFCButton Sınıfı
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
ms.openlocfilehash: e949feaaac3570e1518cfb488cc1c42a471a1c46
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754876"
---
# <a name="cmfcbutton-class"></a>CMFCButton Sınıfı

Sınıf, `CMFCButton` düğme metnini hizalama, düğme metni ve görüntüyü birleştirme, imleç seçme ve bir araç ipucu belirtme gibi [CButton](../../mfc/reference/cbutton-class.md) sınıfına işlevsellik ekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCButton : public CButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CMFCButton::CMFCButton`|Varsayılan oluşturucu.|
|`CMFCButton::~CMFCButton`|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCButton::Temizleme](#cleanup)|İç değişkenleri sıfırlar ve görüntüler, bit eşlemler ve simgeler gibi ayrılan kaynakları serbest sağlar.|
|`CMFCButton::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için çerçeve tarafından kullanılır.|
|`CMFCButton::DrawItem`|Sahip tarafından çizilen düğmenin görsel yönü değiştiğinde çerçeve tarafından çağrılır. [(Overrides CButton::DrawItem](../../mfc/reference/cbutton-class.md#drawitem).)|
|[CMFCButton::EnableFullTextTooltip](#enablefulltexttooltip)|Bir araç ucunun tam metnini büyük bir araç ucu penceresinde mi yoksa küçük bir araç ucu penceresinde metnin kesilmiş bir sürümünde mi gösterin;|
|[CMFCButton::EnableMenuFont](#enablemenufont)|Düğme metin yazı tipinin uygulama menüsü yazı tipiyle aynı olup olmadığını belirtir.|
|[CMFCButton::WindowsTheming etkinleştirme](#enablewindowstheming)|Düğme kenarlığı stilinin geçerli Windows temasıyla eş eyılup uymadığını belirtir.|
|`CMFCButton::GetThisClass`|Bu sınıf türüyle ilişkili [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) nesnesine işaretçi almak için çerçeve tarafından kullanılır.|
|[CMFCButton::GetToolTipCtrl](#gettooltipctrl)|Altta yatan araç ipucu denetimine bir başvuru verir.|
|[CMFCButton::IsAutoCheck](#isautocheck)|Onay kutusunun veya radyo düğmesinin otomatik bir düğme olup olmadığını gösterir.|
|[CMFCButton::IsAutorepeatCommandMode](#isautorepeatcommandmode)|Düğmenin otomatik yineleme moduna ayarlanıp ayarlanıp ayarlmadığını gösterir.|
|[CMFCButton::Ischeckbox](#ischeckbox)|Düğmenin onay kutusu düğmesi olup olmadığını gösterir.|
|[CMFCButton::Kontrol Edildi](#ischecked)|Geçerli düğmenin işaretlenip işaretlenmediğini gösterir.|
|[CMFCButton::Vurgulanmış](#ishighlighted)|Düğmenin vurgulanıp vurgulanmadığını gösterir.|
|[CMFCButton::Basılı](#ispressed)|Düğmeye basılıp basılı paçatır ı gösterir.|
|[CMFCButton::Itit](#ispushed)|Düğmeye basılıp itilip itilen olmadığını gösterir.|
|[CMFCButton::IsRadioButton](#isradiobutton)|Düğmenin radyo düğmesi olup olmadığını gösterir.|
|[CMFCButton::IsWindowsThemingEtkin](#iswindowsthemingenabled)|Düğme kenarlığı stilinin geçerli Windows temaya uygun olup olmadığını gösterir.|
|`CMFCButton::OnDrawParentBackground`|Belirtilen alanda bir düğmenin üst arka planını çizer. [(Overrides AFX_GLOBAL_DATA::DrawParentBackground](../../mfc/reference/afx-global-data-structure.md)|
|`CMFCButton::PreTranslateMessage`|Pencere iletilerini [Çeviri İletisi](/windows/win32/api/winuser/nf-winuser-translatemessage) ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows işlevlerine gönderilmeden önce çevirir. [(CWnd geçersiz kılar::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|
|[CMFCButton::SetAutorepeatMode](#setautorepeatmode)|Otomatik yineleme moduna bir düğme ayarlar.|
|[CMFCButton::SetCheckedImage](#setcheckedimage)|Görüntüyü işaretli bir düğme için ayarlar.|
|[CMFCButton:SetFaceColor](#setfacecolor)|Düğme metninin arka plan rengini ayarlar.|
|[CMFCButton::SetImage](#setimage)|Görüntüyü bir düğme için ayarlar.|
|[CMFCButton::SetMouseCursor](#setmousecursor)|İmleç görüntüsünü ayarlar.|
|[CMFCButton::SetMouseCursorHand](#setmousecursorhand)|İmleci bir elin görüntüsüne ayarlar.|
|[CMFCButton::SetStdImage](#setstdimage)|Düğme `CMenuImages` görüntüsünü ayarlamak için bir nesne kullanır.|
|[CMFCButton::SetTextColor](#settextcolor)|Seçili olmayan bir düğme için düğme metninin rengini ayarlar.|
|[CMFCButton:SetTextHotColor](#settexthotcolor)|Seçili bir düğme için düğme metninin rengini ayarlar.|
|[CMFCButton::SetTooltip](#settooltip)|Bir araç ucunu bir düğmeyle ilişkilendirir.|
|[CMFCButton::SizetoContent](#sizetocontent)|Düğme metnini ve görüntüsünü içerecek şekilde düğmeyi yeniden boyutlandırın.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCButton::Ondraw](#ondraw)|Bir düğme çizmek için çerçeve tarafından çağrıldı.|
|[CMFCButton::OnDrawBorder](#ondrawborder)|Bir düğmenin kenarlığı çizmek için çerçeve tarafından çağrıldı.|
|[CMFCButton::OnDrawFocusRect](#ondrawfocusrect)|Bir düğme için odak dikdörtgeni çizmek için çerçeve tarafından çağrılır.|
|[CMFCButton::OndrawText](#ondrawtext)|Düğme metnini çizmek için çerçeve tarafından çağrılır.|
|[CMFCButton::OnFillBackground](#onfillbackground)|Düğme metninin arka planını çizmek için çerçeve tarafından çağrılır.|
|[CMFCButton::SelectFont](#selectfont)|Belirtilen aygıt bağlamıyla ilişkili yazı tipini alır.|

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CMFCButton::m_nAlignStyle](#m_nalignstyle)|Düğme metninin hizalanmasını belirtir.|
|[CMFCButton::m_bDontUseWinXPTheme](#m_bDontUseWinXPTheme)|Windows XP temalarının kullanılıp kullanılmayacağını belirtir.|
|[CMFCButton:m_bDrawFocus](#m_bdrawfocus)|Bir düğmenin etrafına odak dikdörtgeni çizip çizmeyeceğini gösterir.|
|[CMFCButton:m_nFlatStyle](#m_nflatstyle)|Kenarlıksız, düz, yarı düz veya 3D gibi düğmenin stilini belirtir.|
|[CMFCButton::m_bGrayDisabled](#m_bGrayDisabled)|TRUE olduğunda, devre dışı bırakılmış bir düğmenin gri renkte olarak çizilmesini sağlar.|
|[CMFCButton::m_bHighlightChecked](#m_bhighlightchecked)|İmleç üzerinde gezinirken BS_CHECKBOX stili bir düğmeyi vurgulayıp vurgulamayacağını gösterir.|
|[CMFCButton::m_bResponseOnButtonDown](#m_bResponseOnButtonDown)|Düğme aşağı olayları yanıtlayıp yanıtlamamayı gösterir.|
|[CMFCButton::m_bRightImage](#m_brightimage)|Düğmenin sağ tarafında görüntü gösterip göstermeyeceğini gösterir.|
|[CMFCButton::m_bTopImage](#m_bTopImage)| Görüntünün düğmenin üstünde olup olmadığını gösterir.|
|[CMFCButton:m_bTransparent](#m_btransparent)|Düğmenin saydam olup olmadığını gösterir.|
|[CMFCButton::m_bWasDblClk](#m_bWasDblClk)| Son tıklama olayının çift tıklatma olup olmadığını gösterir.|

## <a name="remarks"></a>Açıklamalar

Diğer düğme türleri, köprüleri `CMFCButton` destekleyen [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md) sınıfı ve renk seçici iletişim `CMFCColorButton` kutusunu destekleyen sınıf gibi sınıftan türetilmiştir.

Bir `CMFCButton` nesnenin stili *3D,* *düz,* *yarı düz* veya *kenarlıksız*olabilir. Düğme metni bir düğmenin solunda, üstünde veya ortasında hizalanabilir. Çalışma zamanında, düğmenin metin, görüntü veya metin ve görüntü gösterip görüntülemediğini denetleyebilirsiniz. İmleç bir düğmenin üzerinde gezindiğinde belirli bir imleç görüntüsünün görüntüleneceğini de belirtebilirsiniz.

Doğrudan kodunuzda veya **MFC Sınıf Sihirbazı** aracını ve iletişim kutusu şablonunu kullanarak bir düğme denetimi oluşturun. Doğrudan bir düğme denetimi oluşturursanız, uygulamanıza bir `CMFCButton` değişken ekleyin ve `Create` nesnenin `CMFCButton` oluşturucusu ve yöntemlerini arayın. **MFC Sınıf Sihirbazı**kullanıyorsanız, `CButton` uygulamanıza bir değişken ekleyin ve sonra `CButton` değişkenin türünü 'den ' e `CMFCButton`değiştirin

Bildirim iletilerini bir iletişim kutusu uygulamasında işlemek için, her bildirim için bir ileti eşlemi girişi ve olay işleyicisi ekleyin. Bir `CMFCButton` nesne tarafından gönderilen bildirimler, bir `CButton` nesne tarafından gönderilenlerle aynıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCButton` sınıfta çeşitli yöntemler kullanarak düğmenin özelliklerini nasıl yapılandırılabildiğini göstermektedir. Örnek, [Yeni Denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]
[!code-cpp[NVC_MFC_NewControls#32](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_3.cpp)]
[!code-cpp[NVC_MFC_NewControls#33](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_4.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Cbutton](../../mfc/reference/cbutton-class.md)

[CMFCDüğmesi](../../mfc/reference/cmfcbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxbutton.h

## <a name="cmfcbuttoncleanup"></a><a name="cleanup"></a>CMFCButton::Temizleme

İç değişkenleri sıfırlar ve görüntüler, bit eşlemler ve simgeler gibi ayrılan kaynakları serbest sağlar.

```
virtual void CleanUp();
```

## <a name="cmfcbuttonenablefulltexttooltip"></a><a name="enablefulltexttooltip"></a>CMFCButton::EnableFullTextTooltip

Bir araç ucunun tam metnini büyük bir araç ucu penceresinde mi yoksa küçük bir araç ucu penceresinde metnin kesilmiş bir sürümünde mi gösterin;

```cpp
void EnableFullTextTooltip(BOOL bOn=TRUE);
```

### <a name="parameters"></a>Parametreler

*Bon*<br/>
[içinde] METNin tümünün görüntülenmesi için TRUE; Kesilen metni görüntülemek için YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonenablemenufont"></a><a name="enablemenufont"></a>CMFCButton::EnableMenuFont

Düğme metin yazı tipinin uygulama menüsü yazı tipiyle aynı olup olmadığını belirtir.

```cpp
void EnableMenuFont(
    BOOL bOn=TRUE,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parametreler

*Bon*<br/>
[içinde] UYGULAMA menüsü yazı tipini düğme metin yazı tipi olarak kullanmak için TRUE; Sistem yazı tipini kullanmak için FALSE. Varsayılan TRUE'dur.

*bRedraw*<br/>
[içinde] EKRANI HEMEN YENIDEN ÇIZMEK IÇIN DOĞRU; aksi takdirde, YANLIŞ. Varsayılan TRUE'dur.

### <a name="remarks"></a>Açıklamalar

Düğme metin yazı tipini belirtmek için bu yöntemi kullanmazsanız, [CWnd:SetFont](../../mfc/reference/cwnd-class.md#setfont) yöntemiyle yazı tipini belirtebilirsiniz. Bir yazı tipi belirtmezseniz, çerçeve varsayılan bir yazı tipi ayarlar.

## <a name="cmfcbuttonenablewindowstheming"></a><a name="enablewindowstheming"></a>CMFCButton::WindowsTheming etkinleştirme

Düğme kenarlığı stilinin geçerli Windows temasıyla eş eyılup uymadığını belirtir.

```
static void EnableWindowsTheming(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] DÜĞME kenarlıkları çizmek için geçerli Windows temasını kullanmak için TRUE; Windows temasını kullanmamak için YANLIŞ. Varsayılan TRUE'dur.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, uygulamanızdaki `CMFCButton` sınıftan türetilen tüm düğmeleri etkiler.

## <a name="cmfcbuttongettooltipctrl"></a><a name="gettooltipctrl"></a>CMFCButton::GetToolTipCtrl

Altta yatan araç ipucu denetimine bir başvuru verir.

```
CToolTipCtrl& GetToolTipCtrl();
```

### <a name="return-value"></a>Dönüş Değeri

Altta yatan araç ucu denetimine bir başvuru.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonisautocheck"></a><a name="isautocheck"></a>CMFCButton::IsAutoCheck

Onay kutusunun veya radyo düğmesinin otomatik bir düğme olup olmadığını gösterir.

```
BOOL IsAutoCheck() const;
```

### <a name="return-value"></a>Dönüş Değeri

DOĞRU düğmenin stili BS_AUTOCHECKBOX veya BS_AUTORADIOBUTTON varsa; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonisautorepeatcommandmode"></a><a name="isautorepeatcommandmode"></a>CMFCButton::IsAutorepeatCommandMode

Düğmenin otomatik yineleme moduna ayarlanıp ayarlanıp ayarlmadığını gösterir.

```
BOOL IsAutorepeatCommandMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme otomatik yineleme moduna ayarlanırsa TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bir düğmeyi otomatik yineleme moduna ayarlamak için [CMFCButton:SetAutorepeatMode](#setautorepeatmode) yöntemini kullanın.

## <a name="cmfcbuttonischeckbox"></a><a name="ischeckbox"></a>CMFCButton::Ischeckbox

Düğmenin onay kutusu düğmesi olup olmadığını gösterir.

```
BOOL IsCheckBox() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmede BS_CHECKBOX veya BS_AUTOCHECKBOX tarzı varsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonischecked"></a><a name="ischecked"></a>CMFCButton::Kontrol Edildi

Geçerli düğmenin işaretlenip işaretlenmediğini gösterir.

```
BOOL IsChecked() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli düğme işaretlenirse DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Çerçeve, farklı türde düğmelerin denetlendiğini belirtmek için farklı yollar kullanır. Örneğin, bir radyo düğmesi nokta içerdiğinde denetlenir; bir x içerdiğinde bir onay **X**kutusu işaretlenir.

## <a name="cmfcbuttonishighlighted"></a><a name="ishighlighted"></a>CMFCButton::Vurgulanmış

Düğmenin vurgulanıp vurgulanmadığını gösterir.

```
BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme vurgulanırsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Fare düğmenin üzerinde gezindiğinde bir düğme vurgulanır.

## <a name="cmfcbuttonispressed"></a><a name="ispressed"></a>CMFCButton::Basılı

Düğmeye basılıp basılı paçatır ı gösterir.

```
BOOL IsPressed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmeye basıldığında DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonispushed"></a><a name="ispushed"></a>CMFCButton::Itit

Düğmeye basılıp itilip itilen olmadığını gösterir.

```
BOOL IsPushed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmeye basılırsa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonisradiobutton"></a><a name="isradiobutton"></a>CMFCButton::IsRadioButton

Düğmenin radyo düğmesi olup olmadığını gösterir.

```
BOOL IsRadioButton() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme stili BS_RADIOBUTTON veya BS_AUTORADIOBUTTON gerçekse; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttoniswindowsthemingenabled"></a><a name="iswindowsthemingenabled"></a>CMFCButton::IsWindowsThemingEtkin

Düğme kenarlığı stilinin geçerli Windows temaya uygun olup olmadığını gösterir.

```
static BOOL IsWindowsThemingEnabled();
```

### <a name="return-value"></a>Dönüş Değeri

Düğme kenarlığı stili geçerli Windows temaya karşılık gelirse DOĞRU; aksi takdirde, YANLIŞ.

## <a name="cmfcbuttonm_bdontusewinxptheme"></a><a name="m_bDontUseWinXPTheme"/>CMFCButton::m_bDontUseWinXPTheme

Düğmeyi çizerken Windows XP temalarının kullanılıp kullanılmayacağını belirtir.

```
BOOL m_bDontUseWinXPTheme;
```

## <a name="cmfcbuttonm_bdrawfocus"></a><a name="m_bdrawfocus"></a>CMFCButton:m_bDrawFocus

Bir düğmenin etrafına odak dikdörtgeni çizip çizmeyeceğini gösterir.

```
BOOL m_bDrawFocus;
```

### <a name="remarks"></a>Açıklamalar

Düğme `m_bDrawFocus` odak aldığında, çerçevenin düğmenin metni ve resminin etrafına bir odak dikdörtgeni çizeceğini belirtmek için üyeyi TRUE olarak ayarlayın.

Oluşturucu `CMFCButton` bu üyeyi TRUE'ya başharfletir.

## <a name="cmfcbuttonm_bgraydisabled"></a><a name="m_bGrayDisabled"></a>CMFCButton::m_bGrayDisabled

TRUE olduğunda, devre dışı bırakılmış bir düğmenin gri renkte olarak çizilmesini sağlar.

```
BOOL m_bGrayDisabled;
```

## <a name="cmfcbuttonm_bhighlightchecked"></a><a name="m_bhighlightchecked"></a>CMFCButton::m_bHighlightChecked

İmleç üzerinde gezinirken BS_CHECKBOX stili bir düğmeyi vurgulayıp vurgulamayacağını gösterir.

```
BOOL m_bHighlightChecked;
```

### <a name="remarks"></a>Açıklamalar

Fare `m_bHighlightChecked` üzerinde gezinirken çerçevenin BS_CHECKBOX stili bir düğmeyi vurgulayacağını belirtmek için üyeyi TRUE olarak ayarlayın.

## <a name="cmfcbuttonm_bresponseonbuttondown"></a><a name="m_bResponseOnButtonDown"></a>CMFCButton::m_bResponseOnButtonDown

Düğme aşağı olayları yanıtlayıp yanıtlamamayı gösterir.

```
BOOL m_bResponseOnButtonDown;
```

## <a name="cmfcbuttonm_brightimage"></a><a name="m_brightimage"></a>CMFCButton::m_bRightImage

Düğmenin sağ tarafında görüntü gösterip göstermeyeceğini gösterir.

```
BOOL m_bRightImage;
```

## <a name="cmfcbuttonm_btopimagem_btopimage"></a><a name="m_bTopImage"></a>CMFCButton::m_bTopImage](#m_bTopImage)

Görüntünün düğmenin üstünde olup olmadığını gösterir.

```
BOOL m_bTopImage;
```

### <a name="remarks"></a>Açıklamalar

Çerçevenin `m_bRightImage` düğmenin metin etiketinin sağındaki görüntüyü göstereceğini belirtmek için üyeyi TRUE olarak ayarlayın.

## <a name="cmfcbuttonm_btransparent"></a><a name="m_btransparent"></a>CMFCButton:m_bTransparent

Düğmenin saydam olup olmadığını gösterir.

```
BOOL m_bTransparent;
```

### <a name="remarks"></a>Açıklamalar

Çerçevenin `m_bTransparent` düğmeyi saydam hale getireceğini belirtmek için üyeyi TRUE olarak ayarlayın. Oluşturucu `CMFCButton` bu üyeyi FALSE'a başharfletir.

## <a name="cmfcbuttonm_nalignstyle"></a><a name="m_nalignstyle"></a>CMFCButton::m_nAlignStyle

Düğme metninin hizalanmasını belirtir.

```
AlignStyle m_nAlignStyle;
```

### <a name="remarks"></a>Açıklamalar

Düğme metninin `CMFCButton::AlignStyle` hizalanmasını belirtmek için aşağıdaki numaralandırma değerlerinden birini kullanın:

|Değer|Açıklama|
|-----------|-----------------|
|ALIGN_CENTER|(Varsayılan) Düğme metnini düğmenin ortasına hizalar.|
|ALIGN_LEFT|Düğme metnini düğmenin sol tarafına hizalar.|
|ALIGN_RIGHT|Düğme metnini düğmenin sağ tarafına hizalar.|

Yapıcı `CMFCButton` bu üyeyi ALIGN_CENTER.

## <a name="cmfcbuttonm_bwasdblclkm_bwasdblclk"></a><a name="m_bWasDblClk"></a>CMFCButton::m_bWasDblClk](#m_bWasDblClk)|

Son tıklama olayının çift tıklatma olup olmadığını gösterir.|

```
BOOL m_bWasDblClk;
```

## <a name="cmfcbuttonm_nflatstyle"></a><a name="m_nflatstyle"></a>CMFCButton:m_nFlatStyle

Kenarlıksız, düz, yarı düz veya 3D gibi düğmenin stilini belirtir.

```
FlatStyle  m_nFlatStyle;
```

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda, `CMFCButton::m_nFlatStyle` bir düğmenin görünümünü belirten numaralandırma değerleri listelenistır.

|Değer|Açıklama|
|-----------|-----------------|
|BUTTONSTYLE_3D|(Varsayılan) Düğmenin yüksek, üç boyutlu kenarları var gibi görünüyor. Düğme tıklatıldığında, düğmeye derin bir girinti içine basıldığında görünür.|
|BUTTONSTYLE_FLAT|Fare düğme üzerinde duraklamadığınızda, düğme iki boyutlu gibi görünür ve kenarları yükseltilmiş değildir. Fare düğmenin üzerinde durakladığında, düğmenin düşük, üç boyutlu kenarları vardır. Düğme tıklatıldığında, düğme sığ bir girintiye basılmış gibi görünür.|
|BUTTONSTYLE_SEMIFLAT|Düğmenin düşük, üç boyutlu kenarları var gibi görünüyor. Düğme tıklatıldığında, düğmeye derin bir girinti içine basıldığında görünür.|
|BUTTONSTYLE_NOBORDERS|Düğmenin kenarları yükseltilmiş değildir ve her zaman iki boyutlu görünür. Düğmeye tıklandığında girintiye basılmış gibi görünmüyor.|

Yapıcı `CMFCButton` bu üyeyi BUTTONSTYLE_3D.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `m_nFlatStyle` `CMFCButton` sınıftaki üye değişkenin değerlerinin nasıl ayarlandığını göstermektedir. Bu örnek, [Yeni Denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#29](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_5.cpp)]

## <a name="cmfcbuttonondraw"></a><a name="ondraw"></a>CMFCButton::Ondraw

Bir düğme çizmek için çerçeve tarafından çağrıldı.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    UINT uiState);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*Rect*<br/>
[içinde] Düğmeyi sınırlayan bir dikdörtgen için bir başvuru.

*uiState*<br/>
[içinde] Geçerli düğme durumu. Daha fazla bilgi `itemState` için [DRAWITEMSTRUCT Yapısı](/windows/win32/api/winuser/ns-winuser-drawitemstruct) konusunun üyesine bakın.

### <a name="remarks"></a>Açıklamalar

Bir düğme çizmek için kendi kodunuzu kullanmak için bu yöntemi geçersiz kılın.

## <a name="cmfcbuttonondrawborder"></a><a name="ondrawborder"></a>CMFCButton::OnDrawBorder

Bir düğmenin kenarlığı çizmek için çerçeve tarafından çağrıldı.

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect& rectClient,
    UINT uiState);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*rectClient*<br/>
[içinde] Düğmeyi sınırlayan bir dikdörtgen için bir başvuru.

*uiState*<br/>
[içinde] Geçerli düğme durumu. Daha fazla bilgi `itemState` için [DRAWITEMSTRUCT Yapısı](/windows/win32/api/winuser/ns-winuser-drawitemstruct) konusunun üyesine bakın.

### <a name="remarks"></a>Açıklamalar

Kenarlığı çizmek için kendi kodunuzu kullanmak için bu yöntemi geçersiz kılın.

## <a name="cmfcbuttonondrawfocusrect"></a><a name="ondrawfocusrect"></a>CMFCButton::OnDrawFocusRect

Bir düğme için odak dikdörtgeni çizmek için çerçeve tarafından çağrılır.

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*rectClient*<br/>
[içinde] Düğmeyi sınırlayan bir dikdörtgen için bir başvuru.

### <a name="remarks"></a>Açıklamalar

Odak dikdörtgeni çizmek için kendi kodunuzu kullanmak için bu yöntemi geçersiz kılın.

## <a name="cmfcbuttonondrawtext"></a><a name="ondrawtext"></a>CMFCButton::OndrawText

Düğme metnini çizmek için çerçeve tarafından çağrılır.

```
virtual void OnDrawText(
    CDC* pDC,
    const CRect& rect,
    const CString& strText,
    UINT uiDTFlags,
    UINT uiState);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*Rect*<br/>
[içinde] Düğmeyi sınırlayan bir dikdörtgen için bir başvuru.

*strText*<br/>
[içinde] Çizecek metin.

*uiDTBayraklar*<br/>
[içinde] Metnin nasıl biçimlendirilenini belirten bayraklar. Daha fazla bilgi için [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext) yönteminin *nFormat* parametresini görün.

*uiState*<br/>
[içinde] Saklı -dır.

### <a name="remarks"></a>Açıklamalar

Düğme metnini çizmek için kendi kodunuzu kullanmak için bu yöntemi geçersiz kılın.

## <a name="cmfcbuttononfillbackground"></a><a name="onfillbackground"></a>CMFCButton::OnFillBackground

Düğme metninin arka planını çizmek için çerçeve tarafından çağrılır.

```
virtual void OnFillBackground(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*rectClient*<br/>
[içinde] Düğmeyi sınırlayan bir dikdörtgen için bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bir düğmenin arka planını çizmek için kendi kodunuzu kullanmak için bu yöntemi geçersiz kılın.

## <a name="cmfcbuttonselectfont"></a><a name="selectfont"></a>CMFCButton::SelectFont

Belirtilen aygıt bağlamıyla ilişkili yazı tipini alır.

```
virtual CFont* SelectFont(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yazı tipini almak için kendi kodunuzu kullanmak için bu yöntemi geçersiz kılın.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonsetautorepeatmode"></a><a name="setautorepeatmode"></a>CMFCButton::SetAutorepeatMode

Otomatik yineleme moduna bir düğme ayarlar.

```cpp
void SetAutorepeatMode(int nTimeDelay=500);
```

### <a name="parameters"></a>Parametreler

*nTimeDelay*<br/>
[içinde] Üst pencereye gönderilen iletiler arasındaki aralığı belirten negatif olmayan bir sayı. Aralık milisaniye cinsinden ölçülür ve varsayılan değeri 500 milisaniyedir. Otomatik yineleme ileti modunu devre dışı kalmak için sıfır belirtin.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, düğme serbest bırakılana veya *nTimeDelay* parametresi sıfıra ayarlanana kadar düğmenin sürekli olarak ana pencereye WM_COMMAND ileti göndermesine neden olur.

## <a name="cmfcbuttonsetcheckedimage"></a><a name="setcheckedimage"></a>CMFCButton::SetCheckedImage

Görüntüyü işaretli bir düğme için ayarlar.

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

*Hıcon*<br/>
[içinde] Yeni görüntü için bit eşlemi ve maskeiçeren simgeye işleyin.

*bAutoDestroy*<br/>
[içinde] Bitmap kaynaklarının otomatik olarak yok edildiğini belirtmek için TRUE; aksi takdirde, YANLIŞ. Varsayılan TRUE'dur.

*hIconHot*<br/>
[içinde] Seçili durum için görüntü içeren simgeye tanıtın.

*Hbıtmap*<br/>
[içinde] Seçili olmayan durum için görüntü içeren bit eşlemi.

*hBitmapSıcak*<br/>
[içinde] Seçili durum için görüntü içeren bit eşlemi.

*bMap3dColors*<br/>
[içinde] Düğme arka planı için saydam bir renk belirtir; yani, düğmenin yüzü. RGB renk değerini kullanmak için DOĞRU(192, 192, 192); tarafından tanımlanan `AFX_GLOBAL_DATA::clrBtnFace`renk değerini kullanmak için FALSE

*uiBmpResId*<br/>
[içinde] Seçili olmayan görüntü için kaynak kimliği.

*uiBmpHotResId*<br/>
[içinde] Seçili resim için kaynak kimliği.

*hIconDisabled*<br/>
[içinde] Devre dışı bırakılmış görüntü için simgeye işleyin.

*hBitmapDevre Dışı*<br/>
[içinde] Devre dışı bırakılmış görüntüyü içeren bit eşlemi'ne işleyin.

*uiBmpDsblResID*<br/>
[içinde] Devre dışı bırakılan bit eşlemikaynak kimliği.

*bAlphaBlend*<br/>
[içinde] TRUE alfa kanalını kullanan sadece 32-bit görüntüleri kullanmak için; FALSE, sadece alfa kanal görüntüleri kullanmamak için. Varsayılan FALSE'dır.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonsetfacecolor"></a><a name="setfacecolor"></a>CMFCButton:SetFaceColor

Düğme metninin arka plan rengini ayarlar.

```cpp
void SetFaceColor(
    COLORREF crFace,
    BOOL bRedraw=TRUE);
```

### <a name="parameters"></a>Parametreler

*crYüz*<br/>
[içinde] RGB renk değeri.

*bRedraw*<br/>
[içinde] EKRANI hemen yeniden çizmek için TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Düğme arka planı (yüz) için yeni bir dolgu rengi tanımlamak için bu yöntemi kullanın. [CMFCButton::m_bTransparent](#m_btransparent) üye değişken doğru olduğunda arka planın dolmadığını unutmayın.

## <a name="cmfcbuttonsetimage"></a><a name="setimage"></a>CMFCButton::SetImage

Görüntüyü bir düğme için ayarlar.

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

*Hıcon*<br/>
[içinde] Yeni görüntü için bit eşlemi ve maskeiçeren simgeye işleyin.

*bAutoDestroy*<br/>
[içinde] Bitmap kaynaklarının otomatik olarak yok edildiğini belirtmek için TRUE; aksi takdirde, YANLIŞ. Varsayılan TRUE'dur.

*hIconHot*<br/>
[içinde] Seçili durum için görüntü içeren simgeye tanıtın.

*Hbıtmap*<br/>
[içinde] Seçili olmayan durum için görüntü içeren bit eşlemi.

*hBitmapSıcak*<br/>
[içinde] Seçili durum için görüntü içeren bit eşlemi.

*uiBmpResId*<br/>
[içinde] Seçili olmayan görüntü için kaynak kimliği.

*uiBmpHotResId*<br/>
[içinde] Seçili resim için kaynak kimliği.

*bMap3dColors*<br/>
[içinde] Düğme arka planı için saydam bir renk belirtir; yani, düğmenin yüzü. RGB renk değerini kullanmak için DOĞRU(192, 192, 192); tarafından tanımlanan `AFX_GLOBAL_DATA::clrBtnFace`renk değerini kullanmak için FALSE

*hIconDisabled*<br/>
[içinde] Devre dışı bırakılmış görüntü için simgeye işleyin.

*hBitmapDevre Dışı*<br/>
[içinde] Devre dışı bırakılmış görüntüyü içeren bit eşlemi'ne işleyin.

*uiBmpDsblResID*<br/>
[içinde] Devre dışı bırakılan bit eşlemikaynak kimliği.

*bAlphaBlend*<br/>
[içinde] TRUE alfa kanalını kullanan sadece 32-bit görüntüleri kullanmak için; FALSE, sadece alfa kanal görüntüleri kullanmamak için. Varsayılan FALSE'dır.

### <a name="remarks"></a>Açıklamalar

### <a name="example"></a>Örnek

Aşağıdaki örnek, yöntemin sınıftaki çeşitli `SetImage` sürümlerinin `CMFCButton` nasıl kullanılacağını göstermektedir. Örnek, [Yeni Denetimler örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]

## <a name="cmfcbuttonsetmousecursor"></a><a name="setmousecursor"></a>CMFCButton::SetMouseCursor

İmleç görüntüsünü ayarlar.

```cpp
void SetMouseCursor(HCURSOR hcursor);
```

### <a name="parameters"></a>Parametreler

*hcursor*<br/>
[içinde] İmleç sapı.

### <a name="remarks"></a>Açıklamalar

El imleci gibi imleç görüntüsünü düğmeyle ilişkilendirmek için bu yöntemi kullanın. İmleç uygulama kaynaklarından yüklenir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, yöntemin sınıfta `SetMouseCursor` nasıl `CMFCButton` kullanılacağını göstermektedir. Örnek, [Yeni Denetimler örneğindeki](../../overview/visual-cpp-samples.md)kodun bir parçasıdır.

[!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#30](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_6.cpp)]

## <a name="cmfcbuttonsetmousecursorhand"></a><a name="setmousecursorhand"></a>CMFCButton::SetMouseCursorHand

İmleci bir elin görüntüsüne ayarlar.

```cpp
void SetMouseCursorHand();
```

### <a name="remarks"></a>Açıklamalar

Bir elin imleç görüntüsünü düğmeyle ilişkilendirmek için bu yöntemi kullanın. İmleç uygulama kaynaklarından yüklenir.

## <a name="cmfcbuttonsetstdimage"></a><a name="setstdimage"></a>CMFCButton::SetStdImage

Düğme `CMenuImages` görüntüsünü ayarlamak için bir nesne kullanır.

```cpp
void SetStdImage(
    CMenuImages::IMAGES_IDS id,
    CMenuImages::IMAGE_STATE state=CMenuImages::ImageBlack,
    CMenuImages::IMAGES_IDS idDisabled=(CMenuImages::IMAGES_IDS)0);
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
[içinde] `CMenuImage::IMAGES_IDS` Numaralandırmada tanımlanan düğme görüntü tanımlayıcılarından biri. Görüntü değerleri oklar, iğneler ve radyo düğmeleri gibi görüntüleri belirtir.

*durum*<br/>
[içinde] Numaralandırmada `CMenuImages::IMAGE_STATE` tanımlanan düğme görüntü durum tanımlayıcılarından biri. Görüntü durumları, siyah, gri, açık gri, beyaz ve koyu gri gibi düğme renklerini belirtir. Varsayılan değer: `CMenuImages::ImageBlack`.

*idDevre dışı*<br/>
[içinde] `CMenuImage::IMAGES_IDS` Numaralandırmada tanımlanan düğme görüntü tanımlayıcılarından biri. Görüntü, düğmenin devre dışı bırakıldığını gösterir. Varsayılan değer ilk düğme görüntüsüdür ( `CMenuImages::IdArrowDown`).

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonsettextcolor"></a><a name="settextcolor"></a>CMFCButton::SetTextColor

Seçili olmayan bir düğme için düğme metninin rengini ayarlar.

```cpp
void SetTextColor(COLORREF clrText);
```

### <a name="parameters"></a>Parametreler

*clrMetin*<br/>
[içinde] RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonsettexthotcolor"></a><a name="settexthotcolor"></a>CMFCButton:SetTextHotColor

Seçili bir düğme için düğme metninin rengini ayarlar.

```cpp
void SetTextHotColor(COLORREF clrTextHot);
```

### <a name="parameters"></a>Parametreler

*clrTextHot*<br/>
[içinde] RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonsettooltip"></a><a name="settooltip"></a>CMFCButton::SetTooltip

Bir araç ucunu bir düğmeyle ilişkilendirir.

```cpp
void SetTooltip(LPCTSTR lpszToolTipText);
```

### <a name="parameters"></a>Parametreler

*lpszToolTipText*<br/>
[içinde] Araç ipucu için metne işaretçi. Araç ipucunu devre dışı ksaymak için NULL belirtin.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcbuttonsizetocontent"></a><a name="sizetocontent"></a>CMFCButton::SizetoContent

Düğme metnini ve görüntüsünü içerecek şekilde düğmeyi yeniden boyutlandırın.

```
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```

### <a name="parameters"></a>Parametreler

*bCalcSadece*<br/>
[içinde] DOĞRU hesaplamak için, ama değiştirmek değil, düğmenin yeni boyutu; DÜĞMENIn boyutunu değiştirmek için FALSE. Varsayılan FALSE'dır.

### <a name="return-value"></a>Dönüş Değeri

Düğmenin yeni boyutunu içeren bir `CSize` nesne.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem 10 piksel yatay kenar boşluğu ve 5 piksel dikey kenar boşluğu içeren yeni bir boyut hesaplar.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCLinkCtrl Sınıfı](../../mfc/reference/cmfclinkctrl-class.md)<br/>
[CMFCColorButton Sınıfı](../../mfc/reference/cmfccolorbutton-class.md)<br/>
[CMFCMenuButton Sınıfı](../../mfc/reference/cmfcmenubutton-class.md)
