---
title: CMFCAutoHideButton sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::BringToTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Create
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAlignment
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAutoHideWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetParentToolBar
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetRect
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetTextSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::HighlightButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsActive
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHighlighted
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHorizontal
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsVisible
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Move
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDraw
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDrawBorder
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnFillBackground
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ReplacePane
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowAttachedWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::UnSetAutoHideMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCAutoHideButton [MFC], BringToTop
- CMFCAutoHideButton [MFC], Create
- CMFCAutoHideButton [MFC], GetAlignment
- CMFCAutoHideButton [MFC], GetAutoHideWindow
- CMFCAutoHideButton [MFC], GetParentToolBar
- CMFCAutoHideButton [MFC], GetRect
- CMFCAutoHideButton [MFC], GetSize
- CMFCAutoHideButton [MFC], GetTextSize
- CMFCAutoHideButton [MFC], HighlightButton
- CMFCAutoHideButton [MFC], IsActive
- CMFCAutoHideButton [MFC], IsHighlighted
- CMFCAutoHideButton [MFC], IsHorizontal
- CMFCAutoHideButton [MFC], IsTop
- CMFCAutoHideButton [MFC], IsVisible
- CMFCAutoHideButton [MFC], Move
- CMFCAutoHideButton [MFC], OnDraw
- CMFCAutoHideButton [MFC], OnDrawBorder
- CMFCAutoHideButton [MFC], OnFillBackground
- CMFCAutoHideButton [MFC], ReplacePane
- CMFCAutoHideButton [MFC], ShowAttachedWindow
- CMFCAutoHideButton [MFC], ShowButton
- CMFCAutoHideButton [MFC], UnSetAutoHideMode
ms.assetid: c80e6b8b-25ca-4d12-9d27-457731028ab0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48dc35a5b3e7f6b12376a47d68a95602bed48c49
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcautohidebutton-class"></a>CMFCAutoHideButton sınıfı
Gösterir veya gizler bir düğmeyi bir [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md) gizlemek için yapılandırılmış.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]    
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCAutoHideButton : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCAutoHideButton::BringToTop](#bringtotop)||  
|[CMFCAutoHideButton::Create](#create)|Oluşturur ve otomatik olarak gizle düğmesi başlatır.|  
|[CMFCAutoHideButton::GetAlignment](#getalignment)|Otomatik Gizle düğmesini hizalamasını alır.|  
|[CMFCAutoHideButton::GetAutoHideWindow](#getautohidewindow)|Döndürür [CDockablePane](../../mfc/reference/cdockablepane-class.md) otomatik olarak gizle düğmesi ile ilişkili nesne.|  
|[CMFCAutoHideButton::GetParentToolBar](#getparenttoolbar)||  
|[CMFCAutoHideButton::GetRect](#getrect)||  
|[CMFCAutoHideButton::GetSize](#getsize)|Otomatik Gizle düğmesini boyutunu belirler.|  
|[CMFCAutoHideButton::GetTextSize](#gettextsize)|Otomatik olarak gizle düğmesi için metin etiketi boyutu döndürür.|  
|[CMFCAutoHideButton::HighlightButton](#highlightbutton)|Vurgular Gizle düğmesini otomatik.|  
|[CMFCAutoHideButton::IsActive](#isactive)|Otomatik olarak gizle düğmesi etkin olup olmadığını gösterir.|  
|[CMFCAutoHideButton::IsHighlighted](#ishighlighted)|Otomatik Gizle düğmesini durumunu döndürür vurgulayın.|  
|[CMFCAutoHideButton::IsHorizontal](#ishorizontal)|Otomatik Gizle düğmesini yatay veya dikey olup olmadığını belirler.|  
|[CMFCAutoHideButton::IsTop](#istop)||  
|[CMFCAutoHideButton::IsVisible](#isvisible)|Düğmenin görünür olup olmadığını gösterir.|  
|[CMFCAutoHideButton::Move](#move)||  
|[CMFCAutoHideButton::OnDraw](#ondraw)|Otomatik Gizle düğmesini çizer zaman çerçevesi bu yöntemi çağırır.|  
|[CMFCAutoHideButton::OnDrawBorder](#ondrawborder)|Bir otomatik olarak gizle düğmesi kenarlık çizer zaman çerçevesi bu yöntemi çağırır.|  
|[CMFCAutoHideButton::OnFillBackground](#onfillbackground)|Bir otomatik olarak gizle düğmenin arka planı doldurduğunda framework bu yöntemi çağırır.|  
|[CMFCAutoHideButton::ReplacePane](#replacepane)||  
|[CMFCAutoHideButton::ShowAttachedWindow](#showattachedwindow)|Gösterir veya gizler ilişkili [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md).|  
|[CMFCAutoHideButton::ShowButton](#showbutton)|Gösterir veya gizler otomatik gizle düğmesi.|  
|[CMFCAutoHideButton::UnSetAutoHideMode](#unsetautohidemode)||  
  
## <a name="remarks"></a>Açıklamalar  
 Oluşturma, `CMFCAutoHideButton` nesne eklendiği bir [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md). `CDockablePane` Nesne gizli veya kullanıcı ile etkileşime giren olarak görüntülenen `CMFCAutoHideButton` nesnesi.  
  
 Varsayılan olarak, framework otomatik olarak oluşturur bir `CMFCAutoHideButton` kullanıcı otomatik olarak gizle üzerinde ne zaman kapatır. Framework öğenin yerine özel bir kullanıcı Arabirimi sınıfın oluşturabilirsiniz `CMFCAutoHideButton` sınıfı. Framework kullanması gereken hangi Özel UI sınıfı belirtmek için statik üye değişkenini `CMFCAutoHideBar::m_pAutoHideButtonRTS` Özel UI sınıfı eşittir. Varsayılan olarak, bu değişken ayarlamak `CMFCAutoHideButton`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulacağını gösteren bir `CMFCAutoHideButton` nesne ve çeşitli yöntemlerle kullanma `CMFCAutoHideButton` sınıfı. Örnek nasıl başlatılacağını gösterir bir `CMFCAutoHideButton` nesnesini kullanarak kendi `Create` yöntemi, ilişkili Göster `CDockablePane` sınıfı ve otomatik olarak Gizle düğmesini göster.  
  
 [!code-cpp[NVC_MFC_RibbonApp#32](../../mfc/reference/codesnippet/cpp/cmfcautohidebutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCAutoHideButton`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxautohidebutton.h  
  
##  <a name="bringtotop"></a>  CMFCAutoHideButton::BringToTop  

  
```  
void BringToTop();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="create"></a>  CMFCAutoHideButton::Create  
 Oluşturur ve bir otomatik olarak gizle düğmesi başlatır.  
  
```  
virtual BOOL Create(
    CMFCAutoHideBar* pParentBar,  
    CDockablePane* pAutoHideWnd,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pParentBar`  
 Üst araç için bir işaretçi.  
  
 [in] `pAutoHideWnd`  
 Bir işaretçi bir [CDockablePane](../../mfc/reference/cdockablepane-class.md) nesnesi. Bu otomatik olarak gizle düğme gizler ve gösterir `CDockablePane`.  
  
 [in] `dwAlignment`  
 Düğme hizalamasını ile ana çerçeve penceresi belirten bir değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluştururken bir `CMFCAutoHideButton` nesnesi ile belirli bir otomatik olarak gizle düğmesi ilişkilendirmeniz gerekir `CDockablePane`. Kullanıcı ilişkili gösterme ve gizleme için otomatik olarak Gizle düğmesini kullanabilirsiniz `CDockablePane`.  
  
 `dwAlignment` Parametre, otomatik olarak gizle düğmesi uygulamada bulunduğu belirtir. Parametresi şu değerlerden biri olabilir:  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CBRS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
##  <a name="getalignment"></a>  CMFCAutoHideButton::GetAlignment  
 Otomatik Gizle düğmesini hizalamasını alır.  
  
```  
DWORD GetAlignment() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `DWORD` değeri otomatik olarak gizle düğmesi geçerli hizalamasını içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Düğme uygulaması üzerinde bulunduğu Otomatik Gizle düğmesini hizalamasını gösterir. Aşağıdaki değerlerden biri olabilir:  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CRBS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
##  <a name="getautohidewindow"></a>  CMFCAutoHideButton::GetAutoHideWindow  
 Döndürür [CDockablePane](../../mfc/reference/cdockablepane-class.md) otomatik olarak gizle düğmesi ile ilişkili nesne.  
  
```  
CDockablePane* GetAutoHideWindow() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlişkili bir işaretçi `CDockablePane` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir otomatik olarak gizle düğmesi ile ilişkilendirilecek bir `CDockablePane`, geçirmek `CDockablePane` bir parametre olarak [CMFCAutoHideButton::Create](#create) yöntemi.  
  
##  <a name="getparenttoolbar"></a>  CMFCAutoHideButton::GetParentToolBar  

  
```  
CMFCAutoHideBar* GetParentToolBar();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getrect"></a>  CMFCAutoHideButton::GetRect  

  
```  
CRect GetRect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getsize"></a>  CMFCAutoHideButton::GetSize  
 Otomatik Gizle düğmesini boyutunu belirler.  
  
```  
CSize GetSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CSize` düğme boyutu içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Hesaplanan boyutu otomatik olarak gizle düğmesi kenarlık boyutunu içerir.  
  
##  <a name="gettextsize"></a>  CMFCAutoHideButton::GetTextSize  
 Otomatik olarak gizle düğmesi için metin etiketi boyutu döndürür.  
  
```  
virtual CSize GetTextSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) otomatik olarak gizle düğmesi için metin boyutu içeren nesne.  
  
##  <a name="isactive"></a>  CMFCAutoHideButton::IsActive  
 Otomatik olarak gizle düğmesi etkin olup olmadığını gösterir.  
  
```  
BOOL IsActive() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` otomatik olarak gizle düğmesi etkin değilse; `FALSE` Aksi takdirde.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir otomatik olarak gizle düğmesi etkindir ilişkili [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md) penceresi gösterilir.  
  
##  <a name="ishorizontal"></a>  CMFCAutoHideButton::IsHorizontal  
 Otomatik Gizle düğmesini yatay veya dikey olup olmadığını belirler.  
  
```  
BOOL IsHorizontal() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düğme yatay ise sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework yönünü ayarlar bir [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) nesne oluşturduğunuzda.  Yönlendirme kullanarak denetleyebilirsiniz `dwAlignment` parametresinde [CMFCAutoHideButton::Create](#create) yöntemi.  
  
##  <a name="istop"></a>  CMFCAutoHideButton::IsTop  

  
```  
BOOL IsTop() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isvisible"></a>  CMFCAutoHideButton::IsVisible  
 Otomatik olarak gizle düğmesi görünür olup olmadığını gösterir.  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` düğmenin görünür durumdaysa; `FALSE` Aksi takdirde.  
  
##  <a name="ondraw"></a>  CMFCAutoHideButton::OnDraw  
 Otomatik Gizle düğmesini çizer zaman çerçevesi bu yöntemi çağırır.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanızı otomatik olarak gizle düğmeleri görünümünü özelleştirmek istiyorsanız, türetilen yeni bir sınıf oluşturun `CMFCAutoHideButton`. Türetilen sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="ondrawborder"></a>  CMFCAutoHideButton::OnDrawBorder  
 Bir otomatik olarak gizle düğmesi kenarlık çizer zaman çerçevesi bu yöntemi çağırır.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect rectBounds,  
    CRect rectBorderSize);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `rectBounds`  
 Otomatik olarak gizle düğmesinin sınırlayıcı dikdörtgenini.  
  
 [in] `rectBorderSize`  
 Otomatik Gizle düğmesini her iki tarafındaki kenarlığın kalınlığı.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanızdaki her Otomatik Gizle düğmesini kenarlık özelleştirmek istiyorsanız, türetilen yeni bir sınıf oluşturun `CMFCAutoHideButton`. Türetilen sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="onfillbackground"></a>  CMFCAutoHideButton::OnFillBackground  
 Bir otomatik olarak gizle düğmenin arka planı doldurduğunda framework bu yöntemi çağırır.  
  
```  
virtual void OnFillBackground(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `rect`  
 Otomatik olarak gizle düğmesinin sınırlayıcı dikdörtgenini.  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulamanızı otomatik olarak gizle düğmeleri için arka plan özelleştirmek istiyorsanız, türetilen yeni bir sınıf oluşturun `CMFCAutoHideButton`. Türetilen sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="showattachedwindow"></a>  CMFCAutoHideButton::ShowAttachedWindow  
 Gösterir veya gizler ilişkili [CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md).  
  
```  
void ShowAttachedWindow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bShow`  
 Bu yöntem ekli gösterip göstermediğini belirten bir Boole değeri `CDockablePane`.  
  
##  <a name="showbutton"></a>  CMFCAutoHideButton::ShowButton  
 Gösterir veya gizler otomatik gizle düğmesi.  
  
```  
virtual void ShowButton(BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bShow`  
 Otomatik olarak gizle düğmesinin gösterilip gösterilmeyeceğini belirten bir Boole değeri.  
  
##  <a name="move"></a>  CMFCAutoHideButton::Move  

  
```  
void Move(int nOffset);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nOffset`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="replacepane"></a>  CMFCAutoHideButton::ReplacePane  

  
```  
void ReplacePane(CDockablePane* pNewBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pNewBar`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="unsetautohidemode"></a>  CMFCAutoHideButton::UnSetAutoHideMode  
 Otomatik olarak gizle modu devre dışı bırakın.  
  
```  
virtual void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pFirstBarInGroup`  
 Grup ilk çubuğunda bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="highlightbutton"></a>  CMFCAutoHideButton::HighlightButton  
 Otomatik Gizle düğmesini vurgular.  
  
```  
virtual void HighlightButton(BOOL bHighlight);
```  
  
### <a name="parameters"></a>Parametreler  
 `bHighlight`  
 Yeni Otomatik Gizle düğme durumu belirtir. `TRUE` Düğme vurgulandığı gösterir `FALSE` düğmesi vurgulanmış değil gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ishighlighted"></a>  CMFCAutoHideButton::IsHighlighted  
 Otomatik Gizle düğmesini Vurgu durumunu döndürür.  
  
```  
virtual BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` otomatik gizle düğmesi vurgulanan; tersi durumda ise `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCAutoHideBar sınıfı](../../mfc/reference/cmfcautohidebar-class.md)   
 [CAutoHideDockSite Sınıfı](../../mfc/reference/cautohidedocksite-class.md)
