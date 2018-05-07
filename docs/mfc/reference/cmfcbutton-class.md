---
title: CMFCButton sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73a3bb877bec385a9f7e56191286c9b560da8610
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcbutton-class"></a>CMFCButton sınıfı
`CMFCButton` Sınıfı için işlevsellik ekler [CButton](../../mfc/reference/cbutton-class.md) düğme metni hizalama, düğme metin ve görüntü birleştirme, bir imleç seçerek ve araç ipucu belirterek gibi sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCButton : public CButton  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCButton::CMFCButton`|Varsayılan Oluşturucu.|  
|`CMFCButton::~CMFCButton`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCButton::CleanUp](#cleanup)|İç değişkenler sıfırlar ve resimler, bit eşlemler ve simgeler gibi ayrılan kaynakları serbest bırakır.|  
|`CMFCButton::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|`CMFCButton::DrawItem`|Sahip tarafından çizilmiş düğmenin görsel yönü değiştiğinde çerçevesi tarafından çağrılır. (Geçersiz kılmaları [CButton::DrawItem](../../mfc/reference/cbutton-class.md#drawitem).)|  
|[CMFCButton::EnableFullTextTooltip](#enablefulltexttooltip)|Tam bir araç ipucu metninin büyük araç ipucu penceresi veya metni küçük araç ipucu penceresinde kesilmiş bir sürümünü görüntülenip görüntülenmeyeceğini belirtir.|  
|[CMFCButton::EnableMenuFont](#enablemenufont)|Düğme metin yazı tipi yazı tipi uygulama menüsü ile aynı olup olmadığını belirtir.|  
|[CMFCButton::EnableWindowsTheming](#enablewindowstheming)|Düğme kenarlığın stili geçerli Windows teması karşılık gelen olup olmadığını belirtir.|  
|`CMFCButton::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCButton::GetToolTipCtrl](#gettooltipctrl)|Temel alınan araç ipucu denetimi için bir başvuru döndürür.|  
|[CMFCButton::IsAutoCheck](#isautocheck)|Bir onay kutusu veya radyo düğmesi otomatik düğmesi olup olmadığını gösterir.|  
|[CMFCButton::IsAutorepeatCommandMode](#isautorepeatcommandmode)|Bir düğme otomatik yineleme modu olarak ayarlanmış olup olmadığını gösterir.|  
|[CMFCButton::IsCheckBox](#ischeckbox)|Bir düğme bir onay kutusu düğmesi olup olmadığını gösterir.|  
|[CMFCButton::IsChecked](#ischecked)|Geçerli düğmenin işaretli olup olmadığını gösterir.|  
|[CMFCButton::IsHighlighted](#ishighlighted)|Bir düğmesi vurgulanmış olup olmadığını gösterir.|  
|[CMFCButton::IsPressed](#ispressed)|Bir düğme gönderilir mi, yoksa vurgulanır ve olup olmadığını gösterir.|  
|[CMFCButton::IsPushed](#ispushed)|Bir düğme gönderilen olup olmadığını gösterir.|  
|[CMFCButton::IsRadioButton](#isradiobutton)|Bir düğme radyo düğmesi olup olmadığını gösterir.|  
|[CMFCButton::IsWindowsThemingEnabled](#iswindowsthemingenabled)|Düğme kenarlığın stili geçerli Windows teması karşılık gelen olup olmadığını gösterir.|  
|`CMFCButton::OnDrawParentBackground`|Düğmenin üst arka planı, belirtilen bölgede çizer. (Geçersiz kılmaları [AFX_GLOBAL_DATA::DrawParentBackground](../../mfc/reference/afx-global-data-structure.md)|  
|`CMFCButton::PreTranslateMessage`|Pencere iletileri için gönderilen önce çevirir [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows çalışır. (Geçersiz kılmaları [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCButton::SetAutorepeatMode](#setautorepeatmode)|Bir düğme otomatik-repeat moduna ayarlar.|  
|[CMFCButton::SetCheckedImage](#setcheckedimage)|Checked düğme için resim ayarlar.|  
|[CMFCButton::SetFaceColor](#setfacecolor)|Düğme metni arka plan rengini belirler.|  
|[CMFCButton::SetImage](#setimage)|Düğme için resim ayarlar.|  
|[CMFCButton::SetMouseCursor](#setmousecursor)|İmleç görüntüyü ayarlar.|  
|[CMFCButton::SetMouseCursorHand](#setmousecursorhand)|İmleç el görüntüyü ayarlar.|  
|[CMFCButton::SetStdImage](#setstdimage)|Kullanan bir `CMenuImages` düğme resminin ayarlamak için nesne.|  
|[CMFCButton::SetTextColor](#settextcolor)|Seçili olmayan bir düğme düğmesi metin rengini belirler.|  
|[CMFCButton::SetTextHotColor](#settexthotcolor)|Seçili bir düğme düğmesi metin rengini belirler.|  
|[CMFCButton::SetTooltip](#settooltip)|Bir araç ipucu düğmesi ile ilişkilendirir.|  
|[CMFCButton::SizeToContent](#sizetocontent)|Düğme metni ve görüntü içerecek şekilde bir düğmeye yeniden boyutlandırır.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCButton::OnDraw](#ondraw)|Bir düğme çizmek için çerçevesi tarafından çağrılır.|  
|[CMFCButton::OnDrawBorder](#ondrawborder)|Bir düğme kenarlığı çizmek için çerçevesi tarafından çağrılır.|  
|[CMFCButton::OnDrawFocusRect](#ondrawfocusrect)|Düğme odak dikdörtgeni çizmek için çerçevesi tarafından çağrılır.|  
|[CMFCButton::OnDrawText](#ondrawtext)|Düğme metni çizmek için çerçevesi tarafından çağrılır.|  
|[CMFCButton::OnFillBackground](#onfillbackground)|Düğme metni arka planı çizmek için çerçevesi tarafından çağrılır.|  
|[CMFCButton::SelectFont](#selectfont)|Belirtilen aygıt bağlamla ilişkili yazı tipini alır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCButton::m_bDrawFocus](#m_bdrawfocus)|Odak dikdörtgeni bir düğme geçici çizileceğini gösterir.|  
|[CMFCButton::m_bHighlightChecked](#m_bhighlightchecked)|İmlecin üzerine geldiğinde BS_CHECKBOX stil düğmesi vurgulamak gösterir.|  
|[CMFCButton::m_bRightImage](#m_brightimage)|Düğme sağ tarafta bir görüntü görüntülenip görüntülenmeyeceğini gösterir.|  
|[CMFCButton::m_bTransparent](#m_btransparent)|Düğme saydam olup olmadığını gösterir.|  
|[CMFCButton::m_nAlignStyle](#m_nalignstyle)|Düğme metni hizalamasını belirtir.|  
|[CMFCButton::m_nFlatStyle](#m_nflatstyle)|Düğmenin Kenarlıksız, düz, noktalı düz veya 3B gibi stilini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Diğer türleri düğmelerinin türetilmiş `CMFCButton` gibi sınıfı [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md) köprüleri destekler, sınıf ve `CMFCColorButton` bir Renk Seçici iletişim kutusu destekleyen sınıfı.  
  
 Stilini bir `CMFCButton` nesnesi olabilir *3B*, *düz*, *noktalı düz* veya *hiçbir kenarlık*. Düğme metni sola, üst veya bir düğme ortasını hizalanabilir. Çalışma zamanında düğmesi metni, bir görüntü veya metin ve görüntü görüntüler olup olmadığını kontrol edebilirsiniz. Ayrıca, imleç düğmenin üzerine geldiğinde belirli imleç görüntü görüntüleneceğini belirtebilirsiniz.  
  
 Düğme denetimi kodunuzda doğrudan ya da kullanarak oluşturmak **MFC Sınıf Sihirbazı** aracı ve bir iletişim kutusu şablon. Düğme denetimi doğrudan oluşturursanız, ekleme bir `CMFCButton` uygulama ve ardından arama Oluşturucusu değişken ve `Create` yöntemlerinin `CMFCButton` nesnesi. Kullanırsanız **MFC Sınıf Sihirbazı**, ekleme bir `CButton` uygulamanıza değişken ve değişkeninden türünü değiştirme `CButton` için `CMFCButton`.  
  
 Bir iletişim kutusu uygulama bildirim iletilerini işlemek için bir ileti eşleme girişi ve her bir bildirim için bir olay işleyicisi ekleyin. Tarafından gönderilen bildirimler bir `CMFCButton` nesne aynıdır olanlar tarafından gönderilen bir `CButton` nesnesi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çeşitli yöntemlerle kullanarak düğmesinin özelliklerini yapılandırmak gösterilmiştir `CMFCButton` sınıfı. Örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
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
 **Başlık:** afxbutton.h  
  
##  <a name="cleanup"></a>  CMFCButton::CleanUp  
 İç değişkenler sıfırlar ve resimler, bit eşlemler ve simgeler gibi ayrılan kaynakları serbest bırakır.  
  
```  
virtual void CleanUp();
```  
  
##  <a name="enablefulltexttooltip"></a>  CMFCButton::EnableFullTextTooltip  
 Tam bir araç ipucu metninin büyük araç ipucu penceresi veya metni küçük araç ipucu penceresinde kesilmiş bir sürümünü görüntülenip görüntülenmeyeceğini belirtir.  
  
```  
void EnableFullTextTooltip(BOOL bOn=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bOn`  
 `TRUE` metnin tamamını görüntülemek için; `FALSE` kesilmiş görüntüleme metni için.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="enablemenufont"></a>  CMFCButton::EnableMenuFont  
 Düğme metin yazı tipi yazı tipi uygulama menüsü ile aynı olup olmadığını belirtir.  
  
```  
void EnableMenuFont(
    BOOL bOn=TRUE,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bOn`  
 `TRUE` yazı tipi uygulama menüsü düğmesi metin yazı tipi kullanmak için; `FALSE` sistem yazı tipi kullanılacak. Varsayılan, `TRUE` değeridir.  
  
 [in] `bRedraw`  
 `TRUE` hemen ekranı yeniden çizmek için; Aksi takdirde `FALSE`. Varsayılan, `TRUE` değeridir.  
  
### <a name="remarks"></a>Açıklamalar  
 Düğme metin yazı tipi belirtmek için bu yöntemi kullanmayın, birlikte yazı tipi belirtebilirsiniz [CWnd::SetFont](../../mfc/reference/cwnd-class.md#setfont) yöntemi. Hiç bir yazı tipi belirtmezseniz, varsayılan yazı tipi framework ayarlar.  
  
##  <a name="enablewindowstheming"></a>  CMFCButton::EnableWindowsTheming  
 Düğme kenarlığın stili geçerli Windows teması karşılık gelen olup olmadığını belirtir.  
  
```  
static void EnableWindowsTheming(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bEnable`  
 `TRUE` Geçerli Windows temasını düğmesi Kenarlıkları çizmek için kullanılacak; `FALSE` Windows teması kullanmayacak şekilde. Varsayılan, `TRUE` değeridir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem türetilmiş, uygulamanızdaki tüm düğmeleri etkiler `CMFCButton` sınıfı.  
  
##  <a name="gettooltipctrl"></a>  CMFCButton::GetToolTipCtrl  
 Temel alınan araç ipucu denetimi için bir başvuru döndürür.  
  
```  
CToolTipCtrl& GetToolTipCtrl();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Temel alınan araç ipucu denetimi referansı.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isautocheck"></a>  CMFCButton::IsAutoCheck  
 Bir onay kutusu veya radyo düğmesi otomatik düğmesi olup olmadığını gösterir.  
  
```  
BOOL IsAutoCheck() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` düğmesi varsa BS_AUTOCHECKBOX veya bs_autoradıobutton stil; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isautorepeatcommandmode"></a>  CMFCButton::IsAutorepeatCommandMode  
 Bir düğme otomatik yineleme modu olarak ayarlanmış olup olmadığını gösterir.  
  
```  
BOOL IsAutorepeatCommandMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme otomatik-repeat moduna ayarlandıysa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CMFCButton::SetAutorepeatMode](#setautorepeatmode) yöntemi bir düğme otomatik yineleme modu olarak ayarlanmış.  
  
##  <a name="ischeckbox"></a>  CMFCButton::IsCheckBox  
 Bir düğme bir onay kutusu düğmesi olup olmadığını gösterir.  
  
```  
BOOL IsCheckBox() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmesi BS_CHECKBOX veya BS_AUTOCHECKBOX stilini varsa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ischecked"></a>  CMFCButton::IsChecked  
 Geçerli düğmenin işaretli olup olmadığını gösterir.  
  
```  
BOOL IsChecked() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Geçerli düğmenin işaretli değilse; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve düğmeleri farklı türde denetlenir göstermek için farklı bir yol kullanır. Örneğin, bir nokta içerdiğinde radyo düğmesi denetlenir; Bunu içerdiğinde, onay kutusunun işaretli olduğundan bir **X**.  
  
##  <a name="ishighlighted"></a>  CMFCButton::IsHighlighted  
 Bir düğmesi vurgulanmış olup olmadığını gösterir.  
  
```  
BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmesi vurgulanmış TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Fare düğmenin üzerine geldiğinde bir düğmesi vurgulanmış haline gelir.  
  
##  <a name="ispressed"></a>  CMFCButton::IsPressed  
 Bir düğme gönderilir mi, yoksa vurgulanır ve olup olmadığını gösterir.  
  
```  
BOOL IsPressed() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmeye basıldığında TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ispushed"></a>  CMFCButton::IsPushed  
 Bir düğme gönderilen olup olmadığını gösterir.  
  
```  
BOOL IsPushed() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme gönderilen TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isradiobutton"></a>  CMFCButton::IsRadioButton  
 Bir düğme radyo düğmesi olup olmadığını gösterir.  
  
```  
BOOL IsRadioButton() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme stilini bs_radıobutton veya bs_autoradıobutton ise TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="iswindowsthemingenabled"></a>  CMFCButton::IsWindowsThemingEnabled  
 Düğme kenarlığın stili geçerli Windows teması karşılık gelen olup olmadığını gösterir.  
  
```  
static BOOL IsWindowsThemingEnabled();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Geçerli Windows teması düğmesi kenarlığın stili karşılık geliyorsa; Aksi takdirde `FALSE`.  
  
##  <a name="m_bdrawfocus"></a>  CMFCButton::m_bDrawFocus  
 Odak dikdörtgeni bir düğme geçici çizileceğini gösterir.  
  
```  
BOOL m_bDrawFocus;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlama `m_bDrawFocus` üyesine `TRUE` framework düğmenin metni etrafında odak dikdörtgen çizme ve düğme odak alırsa görüntü belirtmek için.  
  
 `CMFCButton` Oluşturucu, bu üye başlatır `TRUE`.  
  
##  <a name="m_bhighlightchecked"></a>  CMFCButton::m_bHighlightChecked  
 İmlecin üzerine geldiğinde BS_CHECKBOX stil düğmesi vurgulamak gösterir.  
  
```  
BOOL m_bHighlightChecked;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlama `m_bHighlightChecked` üyesine `TRUE` fare üzerine geldiğinde framework BS_CHECKBOX stil düğmesi vurgular belirtmek için.  
  
##  <a name="m_brightimage"></a>  CMFCButton::m_bRightImage  
 Düğme sağ tarafta bir görüntü görüntülenip görüntülenmeyeceğini gösterir.  
  
```  
BOOL m_bRightImage;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlama `m_bRightImage` üyesine `TRUE` framework düğmenin metin etiketi sağındaki düğmenin resmi görüntüle belirtmek için.  
  
##  <a name="m_btransparent"></a>  CMFCButton::m_bTransparent  
 Düğme saydam olup olmadığını gösterir.  
  
```  
BOOL m_bTransparent;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlama `m_bTransparent` üyesine `TRUE` framework düğmesi saydam yapar belirtmek için. `CMFCButton` Oluşturucu, bu üye başlatır `FALSE`.  
  
##  <a name="m_nalignstyle"></a>  CMFCButton::m_nAlignStyle  
 Düğme metni hizalamasını belirtir.  
  
```  
AlignStyle m_nAlignStyle;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdakilerden birini kullanmak `CMFCButton::AlignStyle` numaralandırma değerlerinin düğmesi metin hizalamasını belirtin:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|ALIGN_CENTER|(Varsayılan) Düğmenin merkezine düğmesi metni hizalar.|  
|ALIGN_LEFT|Düğme metni düğme sol tarafına hizalar.|  
|ALIGN_RIGHT|Düğmenin sağ tarafındaki düğmesi metni hizalar.|  
  
 `CMFCButton` Oluşturucu, bu üye için ALIGN_CENTER başlatır.  
  
##  <a name="m_nflatstyle"></a>  CMFCButton::m_nFlatStyle  
 Düğmenin Kenarlıksız, düz, noktalı düz veya 3B gibi stilini belirtir.  
  
```  
FlatStyle  m_nFlatStyle;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki tabloda `CMFCButton::m_nFlatStyle` düğme görünümünü belirten numaralandırma değerleri.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|BUTTONSTYLE_3D|(Varsayılan) Yüksek, üç boyutlu kenara olmasını düğmesi görünür. Düğme tıklatıldığında derin girinti basılması için düğmesi görünür.|  
|BUTTONSTYLE_FLAT|Fare düğmesini duraklatmak değil, düğme iki boyutlu gibi görünüyor ve yükseltilmiş kenara sahip değil. Fare düğmesini duraklatır, düşük, üç boyutlu kenara olmasını düğmesi görünür. Düğme tıklatıldığında yüzeysel girinti basılması için düğmesi görünür.|  
|BUTTONSTYLE_SEMIFLAT|Düşük, üç boyutlu kenara olmasını düğmesi görünür. Düğme tıklatıldığında derin girinti basılması için düğmesi görünür.|  
|BUTTONSTYLE_NOBORDERS|Düğme sahip oluşmaz yanları ve her zaman iki boyutlu görünür. Düğmesine tıklandığında girinti basılması görünmüyor.|  
  
 `CMFCButton` Oluşturucu, bu üye başlatır `BUTTONSTYLE_3D`.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, değerlerini ayarlamak gösterilmiştir `m_nFlatStyle` üye değişkeni `CMFCButton` sınıfı. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#29](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_5.cpp)]  
  
##  <a name="ondraw"></a>  CMFCButton::OnDraw  
 Bir düğme çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `rect`  
 Düğme bounds dikdörtgene referansı.  
  
 [in] `uiState`  
 Geçerli düğme durumu. Daha fazla bilgi için bkz: `itemState` üyesi [DRAWITEMSTRUCT yapısı](../../mfc/reference/drawitemstruct-structure.md) konu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir düğme çizmek için kendi kodunuzu kullanmak için bu yöntemi geçersiz kılın.  
  
##  <a name="ondrawborder"></a>  CMFCButton::OnDrawBorder  
 Bir düğme kenarlığı çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `rectClient`  
 Düğme bounds dikdörtgene referansı.  
  
 [in] `uiState`  
 Geçerli düğme durumu. Daha fazla bilgi için bkz: `itemState` üyesi [DRAWITEMSTRUCT yapısı](../../mfc/reference/drawitemstruct-structure.md) konu.  
  
### <a name="remarks"></a>Açıklamalar  
 Kenarlık çizmek için kendi kodunuzu kullanmak için bu yöntemi geçersiz kılın.  
  
##  <a name="ondrawfocusrect"></a>  CMFCButton::OnDrawFocusRect  
 Düğme odak dikdörtgeni çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `rectClient`  
 Düğme bounds dikdörtgene referansı.  
  
### <a name="remarks"></a>Açıklamalar  
 Odak dikdörtgeni çizmek için kendi kodunuzu kullanmak için bu yöntemi geçersiz kılın.  
  
##  <a name="ondrawtext"></a>  CMFCButton::OnDrawText  
 Düğme metni çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDrawText(
    CDC* pDC,  
    const CRect& rect,  
    const CString& strText,  
    UINT uiDTFlags,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `rect`  
 Düğme bounds dikdörtgene referansı.  
  
 [in] `strText`  
 Çizmek için metin.  
  
 [in] `uiDTFlags`  
 Metni Biçimlendirme belirtin bayraklar. Daha fazla bilgi için bkz: `nFormat` parametresinin [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext) yöntemi.  
  
 [in] `uiState`  
 (Ayrılmıştır.)  
  
### <a name="remarks"></a>Açıklamalar  
 Düğme metni çizmek için kendi kodunuzu kullanmak için bu yöntemi geçersiz kılın.  
  
##  <a name="onfillbackground"></a>  CMFCButton::OnFillBackground  
 Düğme metni arka planı çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnFillBackground(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `rectClient`  
 Düğme bounds dikdörtgene referansı.  
  
### <a name="remarks"></a>Açıklamalar  
 Düğmenin arka planının çizmek için kendi kodunuzu kullanmak için bu yöntemi geçersiz kılın.  
  
##  <a name="selectfont"></a>  CMFCButton::SelectFont  
 Belirtilen aygıt bağlamla ilişkili yazı tipini alır.  
  
```  
virtual CFont* SelectFont(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazı tipi almak amacıyla kendi kodunuzu kullanmak için bu yöntemi geçersiz kılın.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setautorepeatmode"></a>  CMFCButton::SetAutorepeatMode  
 Bir düğme otomatik-repeat moduna ayarlar.  
  
```  
void SetAutorepeatMode(int nTimeDelay=500);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nTimeDelay`  
 Üst penceresine gönderilen iletileri arasındaki aralığı belirtir negatif olmayan bir sayı. Aralık milisaniye cinsinden ölçülür ve varsayılan değer 500 milisaniyedir. Otomatik yineleme ileti modu devre dışı bırakmak için sıfır belirtin.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem düğme düğmesi serbest kadar üst penceresine sürekli WM_COMMAND iletileri göndermek neden veya `nTimeDelay` parametresini sıfır olarak ayarlayın.  
  
##  <a name="setcheckedimage"></a>  CMFCButton::SetCheckedImage  
 Checked düğme için resim ayarlar.  
  
```  
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
 [in] `hIcon`  
 Bit eşlem ve yeni görüntüyü maskesini içeren simge için işleyin.  
  
 [in] `bAutoDestroy`  
 `TRUE` bit eşlem kaynakları otomatik olarak; yok edilmesi belirtmek için Aksi takdirde `FALSE`. Varsayılan, `TRUE` değeridir.  
  
 [in] `hIconHot`  
 Seçilen durumu için görüntüyü içeren simge için işleyin.  
  
 [in] `hBitmap`  
 Seçili olmayan durumu için görüntüsünü içeren bit eşlem için işleyin.  
  
 [in] `hBitmapHot`  
 Seçili durum görüntüsünü içeren bit eşlem için işleyin.  
  
 [in] `bMap3dColors`  
 Düğme arka planını saydam rengini belirtir. diğer bir deyişle, düğme yüzü. `TRUE` (192, 192, 192); RGB renk değeri kullanmak için `FALSE` tarafından tanımlanan renk değeri kullanmak için `AFX_GLOBAL_DATA::clrBtnFace`.  
  
 [in] `uiBmpResId`  
 Seçili olmayan görüntü kaynak kimliği.  
  
 [in] `uiBmpHotResId`  
 Seçilen görüntü kaynak kimliği.  
  
 [in] `hIconDisabled`  
 Devre dışı görüntü simgesi için işleyin.  
  
 [in] `hBitmapDisabled`  
 Devre dışı görüntüsünü içeren bit eşlem işleyin.  
  
 [in] `uiBmpDsblResID`  
 Bit eşlem'i devre dışı bırakılmış kaynak kimliği.  
  
 [in] `bAlphaBlend`  
 `TRUE` alfa kanal kullanmak yalnızca 32-bit görüntüleri kullanmak için; `FALSE`, yalnızca alfa kanal görüntüleri kullanmayacak şekilde. Varsayılan, `FALSE` değeridir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setfacecolor"></a>  CMFCButton::SetFaceColor  
 Düğme metni arka plan rengini belirler.  
  
```  
void SetFaceColor(
    COLORREF crFace,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `crFace`  
 RGB renk değeri.  
  
 [in] `bRedraw`  
 `TRUE` Ekran hemen yeniden çizmek için; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Düğme arka planını (yüz) için yeni bir dolgu rengi tanımlamak için bu yöntemi kullanın. Arka plan olmadığına dikkat edin doldurulmuş [CMFCButton::m_bTransparent](#m_btransparent) üye değişkeni `TRUE`.  
  
##  <a name="setimage"></a>  CMFCButton::SetImage  
 Düğme için resim ayarlar.  
  
```  
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
 [in] `hIcon`  
 Bit eşlem ve yeni görüntüyü maskesini içeren simge için işleyin.  
  
 [in] `bAutoDestroy`  
 `TRUE` bit eşlem kaynakları otomatik olarak; yok edilmesi belirtmek için Aksi takdirde `FALSE`. Varsayılan, `TRUE` değeridir.  
  
 [in] `hIconHot`  
 Seçilen durumu için görüntüyü içeren simge için işleyin.  
  
 [in] `hBitmap`  
 Seçili olmayan durumu için görüntüsünü içeren bit eşlem için işleyin.  
  
 [in] `hBitmapHot`  
 Seçili durum görüntüsünü içeren bit eşlem için işleyin.  
  
 [in] `uiBmpResId`  
 Seçili olmayan görüntü kaynak kimliği.  
  
 [in] `uiBmpHotResId`  
 Seçilen görüntü kaynak kimliği.  
  
 [in] `bMap3dColors`  
 Düğme arka planını saydam rengini belirtir. diğer bir deyişle, düğme yüzü. `TRUE` (192, 192, 192); RGB renk değeri kullanmak için `FALSE` tarafından tanımlanan renk değeri kullanmak için `AFX_GLOBAL_DATA::clrBtnFace`.  
  
 [in] `hIconDisabled`  
 Devre dışı görüntü simgesi için işleyin.  
  
 [in] `hBitmapDisabled`  
 Devre dışı görüntüsünü içeren bit eşlem işleyin.  
  
 [in] `uiBmpDsblResID`  
 Bit eşlem'i devre dışı bırakılmış kaynak kimliği.  
  
 [in] `bAlphaBlend`  
 `TRUE` alfa kanal kullanmak yalnızca 32-bit görüntüleri kullanmak için; `FALSE`, yalnızca alfa kanal görüntüleri kullanmayacak şekilde. Varsayılan, `FALSE` değeridir.  
  
### <a name="remarks"></a>Açıklamalar  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, çeşitli sürümlerini gösterilmiştir `SetImage` yönteminde `CMFCButton` sınıfı. Örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]  
  
##  <a name="setmousecursor"></a>  CMFCButton::SetMouseCursor  
 İmleç görüntüyü ayarlar.  
  
```  
void SetMouseCursor(HCURSOR hcursor);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `hcursor`  
 Bir imleç işleci.  
  
### <a name="remarks"></a>Açıklamalar  
 Elle imleci gibi bir imleç görüntüsü düğmesi ile ilişkilendirmek için bu yöntemi kullanın. İmleç uygulama kaynaklarından yüklenir.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `SetMouseCursor` yönteminde `CMFCButton` sınıfı. Örneğin kodda bir parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#30](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_6.cpp)]  
  
##  <a name="setmousecursorhand"></a>  CMFCButton::SetMouseCursorHand  
 İmleç el görüntüyü ayarlar.  
  
```  
void SetMouseCursorHand();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir yandan imleç görüntüsü düğmesi ile ilişkilendirmek için bu yöntemi kullanın. İmleç uygulama kaynaklarından yüklenir.  
  
##  <a name="setstdimage"></a>  CMFCButton::SetStdImage  
 Kullanan bir `CMenuImages` düğme resminin ayarlamak için nesne.  
  
```  
void SetStdImage(
    CMenuImages::IMAGES_IDS id,  
    CMenuImages::IMAGE_STATE state=CMenuImages::ImageBlack,  
    CMenuImages::IMAGES_IDS idDisabled=(CMenuImages::IMAGES_IDS)0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `id`  
 Tanımlanan düğmesi görüntü tanımlayıcıları birini `CMenuImage::IMAGES_IDS` numaralandırması. Resim değerleri oklar, PIN ve radyo düğmeleri gibi yansımalarını belirtin.  
  
 [in] `state`  
 Tanımlanan düğmesi görüntü durumu tanımlayıcıları birini `CMenuImages::IMAGE_STATE` numaralandırması. Görüntü durumları düğme renkleri siyah, gri, açık gri beyaz ve koyu gri gibi belirtin. Varsayılan değer `CMenuImages::ImageBlack` şeklindedir.  
  
 [in] `idDisabled`  
 Tanımlanan düğmesi görüntü tanımlayıcıları birini `CMenuImage::IMAGES_IDS` numaralandırması. Görüntü düğmesi devre dışı olduğunu belirtir. İlk düğme resminin varsayılan değerdir ( `CMenuImages::IdArrowDown`).  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="settextcolor"></a>  CMFCButton::SetTextColor  
 Seçili olmayan bir düğme düğmesi metin rengini belirler.  
  
```  
void SetTextColor(COLORREF clrText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `clrText`  
 RGB renk değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="settexthotcolor"></a>  CMFCButton::SetTextHotColor  
 Seçili bir düğme düğmesi metin rengini belirler.  
  
```  
void SetTextHotColor(COLORREF clrTextHot);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `clrTextHot`  
 RGB renk değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="settooltip"></a>  CMFCButton::SetTooltip  
 Bir araç ipucu düğmesi ile ilişkilendirir.  
  
```  
void SetTooltip(LPCTSTR lpszToolTipText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszToolTipText`  
 Araç ipucu metnini işaretçi. Araç İpucu devre dışı bırakmak için NULL belirtin.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="sizetocontent"></a>  CMFCButton::SizeToContent  
 Düğme metni ve görüntü içerecek şekilde bir düğmeye yeniden boyutlandırır.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bCalcOnly`  
 `TRUE` hesaplar, ancak, yeni boyut düğmesinin değiştirmemeniz için; `FALSE` düğmenin boyutunu değiştirmek için. Varsayılan, `FALSE` değeridir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CSize` düğmenin yeni boyutunu içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntem 10 piksel yatay kenar boşluğu ve dikey boşluğu 5 piksel içeren yeni bir boyutu hesaplar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCLinkCtrl sınıfı](../../mfc/reference/cmfclinkctrl-class.md)   
 [CMFCColorButton sınıfı](../../mfc/reference/cmfccolorbutton-class.md)   
 [CMFCMenuButton Sınıfı](../../mfc/reference/cmfcmenubutton-class.md)
