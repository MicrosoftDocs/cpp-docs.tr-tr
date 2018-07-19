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
ms.openlocfilehash: e50f48ad935e74bff05fe41dd77a0b17c0bd26ed
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337313"
---
# <a name="cmfcbutton-class"></a>CMFCButton sınıfı
`CMFCButton` Sınıfı işlevsellik ekler [CButton](../../mfc/reference/cbutton-class.md) düğme metnini hizalama, düğme metni ve görüntüyü birleştirme, imleç seçme ve araç ipuçları belirleme gibi sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
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
|[CMFCButton::CleanUp](#cleanup)|İç değişkenler sıfırlar ve görüntüler, bit eşlemler ve simgeler gibi ayrılan kaynakları serbest bırakır.|  
|`CMFCButton::CreateObject`|Bu sınıf türünün dinamik bir örneğini oluşturmak için framework tarafından kullanılır.|  
|`CMFCButton::DrawItem`|Sahip tarafından çizilmiş bir düğmenin görsel bir özelliği değiştiğinde framework tarafından çağırılır. (Geçersiz kılmaları [CButton::DrawItem](../../mfc/reference/cbutton-class.md#drawitem).)|  
|[CMFCButton::EnableFullTextTooltip](#enablefulltexttooltip)|Tam bir araç ipucu metninin büyük araç ipucu penceresi veya metinde küçük bir araç ipucu penceresi kesilmiş sürümünün görüntülenip görüntülenmeyeceğini belirtir.|  
|[CMFCButton::EnableMenuFont](#enablemenufont)|Düğme metin yazı tipi uygulama menüsünden yazı tipi ile aynı olup olmadığını belirtir.|  
|[CMFCButton::EnableWindowsTheming](#enablewindowstheming)|Düğme kenarlığın stili geçerli Windows teması için karşılık gelen olup olmadığını belirtir.|  
|`CMFCButton::GetThisClass`|Bir işaretçi alma için framework tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) bu sınıfı türü ile ilişkilendirilmiş nesne.|  
|[CMFCButton::GetToolTipCtrl](#gettooltipctrl)|Temel alınan araç ipucu denetimi için bir başvuru döndürür.|  
|[CMFCButton::IsAutoCheck](#isautocheck)|Onay kutusunun veya radyo düğmesinin bir otomatik düğmenin olup olmadığını belirtir.|  
|[CMFCButton::IsAutorepeatCommandMode](#isautorepeatcommandmode)|Bir düğme otomatik yineleme moduna ayarlanmış olup olmadığını gösterir.|  
|[CMFCButton::IsCheckBox](#ischeckbox)|Bir düğme, onay kutusu düğmesi olup olmadığını gösterir.|  
|[CMFCButton::IsChecked](#ischecked)|Geçerli düğmenin işaretli olup olmadığını gösterir.|  
|[CMFCButton::IsHighlighted](#ishighlighted)|Bir düğme vurgulanmış olup olmadığını gösterir.|  
|[CMFCButton::IsPressed](#ispressed)|Bir düğme gönderildi mi, yoksa vurgulanır ve olup olmadığını gösterir.|  
|[CMFCButton::IsPushed](#ispushed)|Bir düğme gönderildiğinde olup olmadığını gösterir.|  
|[CMFCButton::IsRadioButton](#isradiobutton)|Bir düğmeye bir radyo düğmesi olup olmadığını belirtir.|  
|[CMFCButton::IsWindowsThemingEnabled](#iswindowsthemingenabled)|Düğme kenarlığın stili geçerli Windows teması için karşılık gelen olup olmadığını gösterir.|  
|`CMFCButton::OnDrawParentBackground`|Belirtilen alanda bir düğmenin üst arka planı çizer. (Geçersiz kılmaları [AFX_GLOBAL_DATA::DrawParentBackground](../../mfc/reference/afx-global-data-structure.md)|  
|`CMFCButton::PreTranslateMessage`|Pencere iletileri için dağıtılmadan önce çevirir [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) ve [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows işlevleri. (Geçersiz kılmaları [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCButton::SetAutorepeatMode](#setautorepeatmode)|Bir düğme otomatik yineleme modunu ayarlar.|  
|[CMFCButton::SetCheckedImage](#setcheckedimage)|İşaretli bir düğme için resim ayarlar.|  
|[CMFCButton::SetFaceColor](#setfacecolor)|Düğme metnini arka plan rengini ayarlar.|  
|[CMFCButton::SetImage](#setimage)|Bir düğme için resim ayarlar.|  
|[CMFCButton::SetMouseCursor](#setmousecursor)|İmleç görüntü ayarlar.|  
|[CMFCButton::SetMouseCursorHand](#setmousecursorhand)|İmleç el görüntüyü ayarlar.|  
|[CMFCButton::SetStdImage](#setstdimage)|Kullanan bir `CMenuImages` nesne düğmesi ayarlayın.|  
|[CMFCButton::SetTextColor](#settextcolor)|Seçili olmayan bir düğmenin düğme metni rengini ayarlar.|  
|[CMFCButton::SetTextHotColor](#settexthotcolor)|Seçilen bir düğmenin düğme metni rengini ayarlar.|  
|[CMFCButton::SetTooltip](#settooltip)|Bir araç ipucu, bir düğme ile ilişkilendirir.|  
|[CMFCButton::SizeToContent](#sizetocontent)|Bir düğme, düğme metni ve görüntüyü içerecek şekilde yeniden boyutlandırır.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCButton::OnDraw](#ondraw)|Bir düğme çizmek için framework tarafından çağırılır.|  
|[CMFCButton::OnDrawBorder](#ondrawborder)|Düğmenin kenarlık çizmek için framework tarafından çağırılır.|  
|[CMFCButton::OnDrawFocusRect](#ondrawfocusrect)|Bir düğme odak dikdörtgeni çizilmesi gerektiğinde framework tarafından çağırılır.|  
|[CMFCButton::OnDrawText](#ondrawtext)|Düğme metnini çizmek için framework tarafından çağırılır.|  
|[CMFCButton::OnFillBackground](#onfillbackground)|Düğme metnini arka planının çizilmesi gerektiğinde framework tarafından çağırılır.|  
|[CMFCButton::SelectFont](#selectfont)|Belirtilen bir cihaz bağlamı ile ilişkili olan yazı tipini alır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCButton::m_bDrawFocus](#m_bdrawfocus)|Geçici bir düğme odak dikdörtgen çizmek görüntülenip görüntülenmeyeceğini gösterir.|  
|[CMFCButton::m_bHighlightChecked](#m_bhighlightchecked)|İmleci üzerine geldiğinde bir BS_CHECKBOX stili düğme vurgulamak görüntülenip görüntülenmeyeceğini gösterir.|  
|[CMFCButton::m_bRightImage](#m_brightimage)|Düğmenin sağ tarafında bir görüntü görüntülenip görüntülenmeyeceğini gösterir.|  
|[CMFCButton::m_bTransparent](#m_btransparent)|Düğme saydam olup olmadığını belirtir.|  
|[CMFCButton::m_nAlignStyle](#m_nalignstyle)|Düğme metnini hizalamasını belirtir.|  
|[CMFCButton::m_nFlatStyle](#m_nflatstyle)|Kenarlıksız, düz, noktalı düz veya 3B gibi bir düğmenin stilini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Düğmeleri diğer tür türetilir `CMFCButton` gibi sınıf [CMFCURLLinkButton](../../mfc/reference/cmfclinkctrl-class.md) köprüler destekleyen bir sınıf ve `CMFCColorButton` sınıfını, bir Renk Seçici iletişim kutusunu destekler.  
  
 Stilini bir `CMFCButton` nesnesi olabilir *3B*, *düz*, *noktalı sabit* veya *hiçbir kenarlık*. Düğme metnini, sol, üst veya merkezi bir düğmeye hizalanabilir. Çalışma zamanında, düğme metin, görüntü veya metin ve resim görüntüler kontrol edebilirsiniz. Ayrıca, belirli bir imleç görüntü İmleç bir düğmenin üzerine getirildiğinde gösterilecek belirtebilirsiniz.  
  
 Kodunuzda doğrudan veya kullanarak bir düğme denetimi oluşturmak **MFC Sınıf Sihirbazı** aracı ve bir iletişim kutusu şablonu. Bir düğme denetimi doğrudan oluşturursanız, ekleme bir `CMFCButton` uygulama ve sonra çağrı Oluşturucu değişken ve `Create` yöntemlerinin `CMFCButton` nesne. Kullanırsanız **MFC Sınıf Sihirbazı**, ekleme bir `CButton` değişken, uygulamanıza ve ardından değişkenin türünü değiştirme `CButton` için `CMFCButton`.  
  
 Bir iletişim kutusu uygulama bildirim iletilerini işlemek için bir ileti eşleme girişi ve her uyarı için bir olay işleyicisi ekleyin. Tarafından gönderilen bildirimleri bir `CMFCButton` nesne tarafından gönderilen bu aynı olan bir `CButton` nesne.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, çeşitli yöntemlerle kullanarak düğmesi özelliklerini yapılandırma işlemi gösterilmektedir `CMFCButton` sınıfı. Bir örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
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
 İç değişkenler sıfırlar ve görüntüler, bit eşlemler ve simgeler gibi ayrılan kaynakları serbest bırakır.  
  
```  
virtual void CleanUp();
```  
  
##  <a name="enablefulltexttooltip"></a>  CMFCButton::EnableFullTextTooltip  
 Tam bir araç ipucu metninin büyük araç ipucu penceresi veya metinde küçük bir araç ipucu penceresi kesilmiş sürümünün görüntülenip görüntülenmeyeceğini belirtir.  
  
```  
void EnableFullTextTooltip(BOOL bOn=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iyi*  
 Metnin tamamını görüntülemek için TRUE; Kesilmiş görüntüleme metni için FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="enablemenufont"></a>  CMFCButton::EnableMenuFont  
 Düğme metin yazı tipi uygulama menüsünden yazı tipi ile aynı olup olmadığını belirtir.  
  
```  
void EnableMenuFont(
    BOOL bOn=TRUE,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *iyi*  
 Uygulama menüsü yazı tipi düğme metin yazı tipi kullanmak için TRUE; Sistem yazı tipini kullan için FALSE. Varsayılan değer True'dur.  
  
 [in] *bRedraw*  
 Hemen ekranı yeniden çizmek için TRUE; Aksi takdirde FALSE. Varsayılan değer True'dur.  
  
### <a name="remarks"></a>Açıklamalar  
 Düğme metin yazı tipi belirtmek için bu yöntemi kullanmayın, yazı tipiyle belirtebilirsiniz [CWnd::SetFont](../../mfc/reference/cwnd-class.md#setfont) yöntemi. Bir yazı tipi hiç belirtmezseniz varsayılan yazı tipi framework ayarlar.  
  
##  <a name="enablewindowstheming"></a>  CMFCButton::EnableWindowsTheming  
 Düğme kenarlığın stili geçerli Windows teması için karşılık gelen olup olmadığını belirtir.  
  
```  
static void EnableWindowsTheming(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bSistemlerde*  
 Düğme Kenarlıkları çizmek için geçerli Windows teması kullanmak için TRUE; Windows teması kullanmak için FALSE. Varsayılan değer True'dur.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem türetilmiş uygulamanızdaki tüm düğmeleri etkiler `CMFCButton` sınıfı.  
  
##  <a name="gettooltipctrl"></a>  CMFCButton::GetToolTipCtrl  
 Temel alınan araç ipucu denetimi için bir başvuru döndürür.  
  
```  
CToolTipCtrl& GetToolTipCtrl();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Temel alınan araç ipucu denetimi için bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isautocheck"></a>  CMFCButton::IsAutoCheck  
 Onay kutusunun veya radyo düğmesinin bir otomatik düğmenin olup olmadığını belirtir.  
  
```  
BOOL IsAutoCheck() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmeyi bir stile sahipse TRUE BS_AUTOCHECKBOX veya bs_autoradıobutton; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isautorepeatcommandmode"></a>  CMFCButton::IsAutorepeatCommandMode  
 Bir düğme otomatik yineleme moduna ayarlanmış olup olmadığını gösterir.  
  
```  
BOOL IsAutorepeatCommandMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme otomatik yineleme moduna olarak ayarlanmışsa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [CMFCButton::SetAutorepeatMode](#setautorepeatmode) otomatik yineleme moduna bir düğme ayarlamak için yöntemi.  
  
##  <a name="ischeckbox"></a>  CMFCButton::IsCheckBox  
 Bir düğme, onay kutusu düğmesi olup olmadığını gösterir.  
  
```  
BOOL IsCheckBox() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme BS_CHECKBOX ya da BS_AUTOCHECKBOX bir stile sahipse TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ischecked"></a>  CMFCButton::IsChecked  
 Geçerli düğmenin işaretli olup olmadığını gösterir.  
  
```  
BOOL IsChecked() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli bir düğme işaretlendiğinde TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Çerçeve farklı türde düğmeleri seçili olduğunu göstermek için farklı yöntemler kullanır. Örneğin, bir nokta içeren bir radyo düğmesi denetlenir; içerdiği durumlarda bir onay kutusu işaretli bir **X**.  
  
##  <a name="ishighlighted"></a>  CMFCButton::IsHighlighted  
 Bir düğme vurgulanmış olup olmadığını gösterir.  
  
```  
BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğmesi vurgulanmış TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Düğmenin üzerine fare geldiğinde bir düğme vurgulanmış olur.  
  
##  <a name="ispressed"></a>  CMFCButton::IsPressed  
 Bir düğme gönderildi mi, yoksa vurgulanır ve olup olmadığını gösterir.  
  
```  
BOOL IsPressed() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme denetimine basıldıysa TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ispushed"></a>  CMFCButton::IsPushed  
 Bir düğme gönderildiğinde olup olmadığını gösterir.  
  
```  
BOOL IsPushed() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme gönderildiğinde TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isradiobutton"></a>  CMFCButton::IsRadioButton  
 Bir düğmeye bir radyo düğmesi olup olmadığını belirtir.  
  
```  
BOOL IsRadioButton() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme stilini bs_radıobutton veya bs_autoradıobutton ise TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="iswindowsthemingenabled"></a>  CMFCButton::IsWindowsThemingEnabled  
 Düğme kenarlığın stili geçerli Windows teması için karşılık gelen olup olmadığını gösterir.  
  
```  
static BOOL IsWindowsThemingEnabled();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme kenarlığın stili karşılık gelen geçerli Windows teması için TRUE; Aksi takdirde FALSE.  
  
##  <a name="m_bdrawfocus"></a>  CMFCButton::m_bDrawFocus  
 Geçici bir düğme odak dikdörtgen çizmek görüntülenip görüntülenmeyeceğini gösterir.  
  
```  
BOOL m_bDrawFocus;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlama `m_bDrawFocus` framework düğmenin metninin çevresindeki odak dikdörtgen çizme ve düğme odak alırsa görüntü belirtmek için true üyesi.  
  
 `CMFCButton` Oluşturucu, bu üye true başlatır.  
  
##  <a name="m_bhighlightchecked"></a>  CMFCButton::m_bHighlightChecked  
 İmleci üzerine geldiğinde bir BS_CHECKBOX stili düğme vurgulamak görüntülenip görüntülenmeyeceğini gösterir.  
  
```  
BOOL m_bHighlightChecked;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlama `m_bHighlightChecked` üye üzerine fare geldiğinde framework BS_CHECKBOX stili düğme vurgular belirtmek için true.  
  
##  <a name="m_brightimage"></a>  CMFCButton::m_bRightImage  
 Düğmenin sağ tarafında bir görüntü görüntülenip görüntülenmeyeceğini gösterir.  
  
```  
BOOL m_bRightImage;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlama `m_bRightImage` üye düğmenin resim framework tarafından düğmenin metin etiketinin sağında görüntüleneceğini belirtmek için true.  
  
##  <a name="m_btransparent"></a>  CMFCButton::m_bTransparent  
 Düğme saydam olup olmadığını belirtir.  
  
```  
BOOL m_bTransparent;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlama `m_bTransparent` üye framework düğme saydam yapar belirtmek için true. `CMFCButton` Oluşturucu, bu üye yanlış başlatır.  
  
##  <a name="m_nalignstyle"></a>  CMFCButton::m_nAlignStyle  
 Düğme metnini hizalamasını belirtir.  
  
```  
AlignStyle m_nAlignStyle;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdakilerden birini kullanın `CMFCButton::AlignStyle` numaralandırma değerlerinin düğme metnini hizalama belirtmek için:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|ALIGN_CENTER|(Varsayılan) Orta düğmenin düğme metnini hizalar.|  
|ALIGN_LEFT|Düğme metnini düğmenin sol tarafıyla hizalar.|  
|ALIGN_RIGHT|Düğmenin sağ tarafında düğme metnini hizalar.|  
  
 `CMFCButton` Oluşturucu bu üyeye ALIGN_CENTER başlatır.  
  
##  <a name="m_nflatstyle"></a>  CMFCButton::m_nFlatStyle  
 Kenarlıksız, düz, noktalı düz veya 3B gibi bir düğmenin stilini belirtir.  
  
```  
FlatStyle  m_nFlatStyle;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki tabloda `CMFCButton::m_nFlatStyle` bir düğmenin görünümünü belirten sabit listesi değerleri.  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|BUTTONSTYLE_3D|(Varsayılan) Yüksek, üç boyutlu yüz için düğmesi görünür. Düğmesine tıklandığında, derin bir girinti basılmasını düğmesi görünür.|  
|BUTTONSTYLE_FLAT|Düğmenin üzerine fare duraklamamasını, düğmenin iki boyutlu gibi görünüyor ve yükseltilmiş yüz sahip değil. Düğmenin üzerine fare duraklatır, düşük, üç boyutlu yüz için düğmesi görünür. Düğmesine tıklandığında, basit bir girinti basılmasını düğmesi görünür.|  
|BUTTONSTYLE_SEMIFLAT|Düşük, üç boyutlu yüz için düğmesi görünür. Düğmesine tıklandığında, derin bir girinti basılmasını düğmesi görünür.|  
|BUTTONSTYLE_NOBORDERS|Düğme sahip oluşmaz yüz ve her zaman iki boyutlu görünür. Düğme tıklandığında bir girinti basıldığında görünmüyor.|  
  
 `CMFCButton` Oluşturucu bu üyeye BUTTONSTYLE_3D başlatır.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, değerlerini ayarlamak gösterilmiştir `m_nFlatStyle` üye değişkeni `CMFCButton` sınıfı. Bu örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#29](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_5.cpp)]  
  
##  <a name="ondraw"></a>  CMFCButton::OnDraw  
 Bir düğme çizmek için framework tarafından çağırılır.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] *dikdörtgen*  
 Düğme sınırların bir dikdörtgen bir başvuru.  
  
 [in] *uiState*  
 Geçerli düğme durumu. Daha fazla bilgi için `itemState` üyesi [DRAWITEMSTRUCT yapısı](../../mfc/reference/drawitemstruct-structure.md) konu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir düğme çizmek için kendi kodunuzu kullanmak için bu yöntemi yok sayın.  
  
##  <a name="ondrawborder"></a>  CMFCButton::OnDrawBorder  
 Düğmenin kenarlık çizmek için framework tarafından çağırılır.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect& rectClient,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] *rectClient*  
 Düğme sınırların bir dikdörtgen bir başvuru.  
  
 [in] *uiState*  
 Geçerli düğme durumu. Daha fazla bilgi için `itemState` üyesi [DRAWITEMSTRUCT yapısı](../../mfc/reference/drawitemstruct-structure.md) konu.  
  
### <a name="remarks"></a>Açıklamalar  
 Kenarlık çizmek için kendi kodunuzu kullanmak için bu yöntemi yok sayın.  
  
##  <a name="ondrawfocusrect"></a>  CMFCButton::OnDrawFocusRect  
 Bir düğme odak dikdörtgeni çizilmesi gerektiğinde framework tarafından çağırılır.  
  
```  
virtual void OnDrawFocusRect(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] *rectClient*  
 Düğme sınırların bir dikdörtgen bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Odak dikdörtgen çizmek için kendi kodunuzu kullanmak için bu yöntemi yok sayın.  
  
##  <a name="ondrawtext"></a>  CMFCButton::OnDrawText  
 Düğme metnini çizmek için framework tarafından çağırılır.  
  
```  
virtual void OnDrawText(
    CDC* pDC,  
    const CRect& rect,  
    const CString& strText,  
    UINT uiDTFlags,  
    UINT uiState);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] *dikdörtgen*  
 Düğme sınırların bir dikdörtgen bir başvuru.  
  
 [in] *strText*  
 Çizmek için metin.  
  
 [in] *uiDTFlags*  
 Metnin nasıl biçimlendirileceğini belirten bayraklar. Daha fazla bilgi için *nFormat* parametresinin [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext) yöntemi.  
  
 [in] *uiState*  
 (Ayrılmış)  
  
### <a name="remarks"></a>Açıklamalar  
 Düğme metnini çizmek için kendi kodunuzu kullanmak için bu yöntemi yok sayın.  
  
##  <a name="onfillbackground"></a>  CMFCButton::OnFillBackground  
 Düğme metnini arka planının çizilmesi gerektiğinde framework tarafından çağırılır.  
  
```  
virtual void OnFillBackground(
    CDC* pDC,  
    const CRect& rectClient);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] *rectClient*  
 Düğme sınırların bir dikdörtgen bir başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir düğmenin arka planı çizmek için kendi kodunuzu kullanmak için bu yöntemi yok sayın.  
  
##  <a name="selectfont"></a>  CMFCButton::SelectFont  
 Belirtilen bir cihaz bağlamı ile ilişkili olan yazı tipini alır.  
  
```  
virtual CFont* SelectFont(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDC*  
 Bir cihaz bağlamı için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yazı tipi almak için kendi kodunuzu kullanmak için bu yöntemi yok sayın.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setautorepeatmode"></a>  CMFCButton::SetAutorepeatMode  
 Bir düğme otomatik yineleme modunu ayarlar.  
  
```  
void SetAutorepeatMode(int nTimeDelay=500);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nTimeDelay*  
 Üst penceresine gönderilen iletiler arasındaki zaman aralığını belirten negatif olmayan bir sayı. Aralığı milisaniye cinsinden ölçülür ve varsayılan değer 500 milisaniyedir. Otomatik-repeat mesajı modunu devre dışı bırakmak için sıfır belirtin.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem düğmesi serbest bırakıldığında kadar üst penceresine sürekli WM_COMMAND ileti göndermek düğme neden veya *nTimeDelay* parametresi, sıfır olarak ayarlanır.  
  
##  <a name="setcheckedimage"></a>  CMFCButton::SetCheckedImage  
 İşaretli bir düğme için resim ayarlar.  
  
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
 [in] *hIcon*  
 Bit eşlem ve yeni görüntüyü maskesinin içeren simgesine işleyin.  
  
 [in] *bAutoDestroy*  
 Bit eşlem kaynakları otomatik olarak yok edilecek belirtmek için TRUE; Aksi takdirde FALSE. Varsayılan değer True'dur.  
  
 [in] *hIconHot*  
 Seçilen durum görüntüsünü içeren simgesine işleyin.  
  
 [in] *Hbıtmap*  
 Seçili olmayan durum görüntüsünü içeren bir bit eşlemi işleyin.  
  
 [in] *hBitmapHot*  
 Seçilen durum görüntüsünü içeren bir bit eşlemi işleyin.  
  
 [in] *bMap3dColors*  
 Bir düğme arka saydam rengini belirtir. diğer bir deyişle, yüz tanıma düğmesi. (192, 192, 192); RGB renk değeri TRUE Tarafından tanımlanan renk değeri FALSE `AFX_GLOBAL_DATA::clrBtnFace`.  
  
 [in] *uiBmpResId*  
 Görüntü seçildi kaynak kimliği.  
  
 [in] *uiBmpHotResId*  
 Seçili görüntü için kaynak kimliği.  
  
 [in] *hIconDisabled*  
 Devre dışı görüntü için simgesine işleyin.  
  
 [in] *hBitmapDisabled*  
 Devre dışı görüntüsünü içeren bir bit eşlem için işler.  
  
 [in] *uiBmpDsblResID*  
 Devre dışı bırakılmış bir bit eşlemi kaynak kimliği.  
  
 [in] *bAlphaBlend*  
 Alfa kanalını kullanma kullanımı yalnızca 32-bit görüntüleri için true; Yalnızca alfa kanal resimleri kullanmak için FALSE. Varsayılan değer false'tur.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setfacecolor"></a>  CMFCButton::SetFaceColor  
 Düğme metnini arka plan rengini ayarlar.  
  
```  
void SetFaceColor(
    COLORREF crFace,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *crFace*  
 Bir RGB renk değeri.  
  
 [in] *bRedraw*  
 Ekranın hemen yeniden çizmek için TRUE; Aksi takdirde FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni bir dolgu rengi düğmesi arka planının (yüz) tanımlamak için bu yöntemi kullanın. Arka plan olmadığına dikkat edin doldurulmuş [CMFCButton::m_bTransparent](#m_btransparent) üye değişkeni ise TRUE.  
  
##  <a name="setimage"></a>  CMFCButton::SetImage  
 Bir düğme için resim ayarlar.  
  
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
 [in] *hIcon*  
 Bit eşlem ve yeni görüntüyü maskesinin içeren simgesine işleyin.  
  
 [in] *bAutoDestroy*  
 Bit eşlem kaynakları otomatik olarak yok edilecek belirtmek için TRUE; Aksi takdirde FALSE. Varsayılan değer True'dur.  
  
 [in] *hIconHot*  
 Seçilen durum görüntüsünü içeren simgesine işleyin.  
  
 [in] *Hbıtmap*  
 Seçili olmayan durum görüntüsünü içeren bir bit eşlemi işleyin.  
  
 [in] *hBitmapHot*  
 Seçilen durum görüntüsünü içeren bir bit eşlemi işleyin.  
  
 [in] *uiBmpResId*  
 Görüntü seçildi kaynak kimliği.  
  
 [in] *uiBmpHotResId*  
 Seçili görüntü için kaynak kimliği.  
  
 [in] *bMap3dColors*  
 Bir düğme arka saydam rengini belirtir. diğer bir deyişle, yüz tanıma düğmesi. (192, 192, 192); RGB renk değeri TRUE Tarafından tanımlanan renk değeri FALSE `AFX_GLOBAL_DATA::clrBtnFace`.  
  
 [in] *hIconDisabled*  
 Devre dışı görüntü için simgesine işleyin.  
  
 [in] *hBitmapDisabled*  
 Devre dışı görüntüsünü içeren bir bit eşlem için işler.  
  
 [in] *uiBmpDsblResID*  
 Devre dışı bırakılmış bir bit eşlemi kaynak kimliği.  
  
 [in] *bAlphaBlend*  
 Alfa kanalını kullanma kullanımı yalnızca 32-bit görüntüleri için true; Yalnızca alfa kanal resimleri kullanmak için FALSE. Varsayılan değer false'tur.  
  
### <a name="remarks"></a>Açıklamalar  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek, çeşitli sürümlerini kullanma işlemini gösterir `SetImage` yönteminde `CMFCButton` sınıfı. Bir örneğin parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#31](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_2.cpp)]  
  
##  <a name="setmousecursor"></a>  CMFCButton::SetMouseCursor  
 İmleç görüntü ayarlar.  
  
```  
void SetMouseCursor(HCURSOR hcursor);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *hcursor*  
 İmleç tanıtıcı.  
  
### <a name="remarks"></a>Açıklamalar  
 Elle imleci gibi bir imleç görüntü düğme ile ilişkilendirmek için bu yöntemi kullanın. İmleç uygulama kaynaklarından yüklenir.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir `SetMouseCursor` yönteminde `CMFCButton` sınıfı. Örneğin kodda bir parçasıdır [yeni denetimler örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#28](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#30](../../mfc/reference/codesnippet/cpp/cmfcbutton-class_6.cpp)]  
  
##  <a name="setmousecursorhand"></a>  CMFCButton::SetMouseCursorHand  
 İmleç el görüntüyü ayarlar.  
  
```  
void SetMouseCursorHand();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İmleç görüntü el ile düğme ilişkilendirmek için bu yöntemi kullanın. İmleç uygulama kaynaklarından yüklenir.  
  
##  <a name="setstdimage"></a>  CMFCButton::SetStdImage  
 Kullanan bir `CMenuImages` nesne düğmesi ayarlayın.  
  
```  
void SetStdImage(
    CMenuImages::IMAGES_IDS id,  
    CMenuImages::IMAGE_STATE state=CMenuImages::ImageBlack,  
    CMenuImages::IMAGES_IDS idDisabled=(CMenuImages::IMAGES_IDS)0);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *kimliği*  
 Tanımlanan düğmesine görüntü tanımlayıcılarından birini `CMenuImage::IMAGES_IDS` sabit listesi. Resim değerleri görüntüleri oklar, PIN ve radyo düğmeleri gibi belirtin.  
  
 [in] *durumu*  
 Tanımlanan düğmesine görüntü durum tanımlayıcılarından birini `CMenuImages::IMAGE_STATE` sabit listesi. Görüntü durumları gibi siyah, gri, açık gri, beyaz ve koyu gri düğme renkleri belirtin. Varsayılan değer `CMenuImages::ImageBlack` şeklindedir.  
  
 [in] *idDisabled*  
 Tanımlanan düğmesine görüntü tanımlayıcılarından birini `CMenuImage::IMAGES_IDS` sabit listesi. Görüntüyü düğme devre dışı olduğunu gösterir. İlk düğme resminin varsayılan değer: ( `CMenuImages::IdArrowDown`).  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="settextcolor"></a>  CMFCButton::SetTextColor  
 Seçili olmayan bir düğmenin düğme metni rengini ayarlar.  
  
```  
void SetTextColor(COLORREF clrText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *clrText*  
 Bir RGB renk değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="settexthotcolor"></a>  CMFCButton::SetTextHotColor  
 Seçilen bir düğmenin düğme metni rengini ayarlar.  
  
```  
void SetTextHotColor(COLORREF clrTextHot);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *clrTextHot*  
 Bir RGB renk değeri.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="settooltip"></a>  CMFCButton::SetTooltip  
 Bir araç ipucu, bir düğme ile ilişkilendirir.  
  
```  
void SetTooltip(LPCTSTR lpszToolTipText);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *lpszToolTipText*  
 Araç ipucu metnini işaretçisi. Araç İpucu devre dışı bırakmak için NULL belirtin.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="sizetocontent"></a>  CMFCButton::SizeToContent  
 Bir düğme, düğme metni ve görüntüyü içerecek şekilde yeniden boyutlandırır.  
  
```  
virtual CSize SizeToContent(BOOL bCalcOnly=FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bCalcOnly*  
 Hesaplar, ancak, yeni düğmeyi boyutunu değiştirilmemesi için TRUE; Düğmenin boyutunu değiştirmek için FALSE. Varsayılan değer false'tur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CSize` düğme yeni boyutunu içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, bu yöntem bir yatay boşluğu 10 piksel ve 5 piksel dikey bir kenar boşluğu içeren yeni bir boyut hesaplar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCLinkCtrl sınıfı](../../mfc/reference/cmfclinkctrl-class.md)   
 [CMFCColorButton sınıfı](../../mfc/reference/cmfccolorbutton-class.md)   
 [CMFCMenuButton Sınıfı](../../mfc/reference/cmfcmenubutton-class.md)
