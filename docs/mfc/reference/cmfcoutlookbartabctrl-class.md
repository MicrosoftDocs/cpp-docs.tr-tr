---
title: CMFCOutlookBarTabCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::AddControl
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::CanShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::Create
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableInPlaceEdit
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::EnableScrollButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::GetVisiblePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsAnimation
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::IsMode2003
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowFewerPageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowMorePageButtons
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::OnShowOptions
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetActiveTab
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetBorderSize
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetPageButtonTextAlign
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetToolbarImageList
- AFXOUTLOOKBARTABCTRL/CMFCOutlookBarTabCtrl::SetVisiblePageButtons
dev_langs:
- C++
helpviewer_keywords:
- CMFCOutlookBarTabCtrl [MFC], AddControl
- CMFCOutlookBarTabCtrl [MFC], CanShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], CanShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], Create
- CMFCOutlookBarTabCtrl [MFC], EnableAnimation
- CMFCOutlookBarTabCtrl [MFC], EnableInPlaceEdit
- CMFCOutlookBarTabCtrl [MFC], EnableScrollButtons
- CMFCOutlookBarTabCtrl [MFC], GetBorderSize
- CMFCOutlookBarTabCtrl [MFC], GetVisiblePageButtons
- CMFCOutlookBarTabCtrl [MFC], IsAnimation
- CMFCOutlookBarTabCtrl [MFC], IsMode2003
- CMFCOutlookBarTabCtrl [MFC], OnShowFewerPageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowMorePageButtons
- CMFCOutlookBarTabCtrl [MFC], OnShowOptions
- CMFCOutlookBarTabCtrl [MFC], SetActiveTab
- CMFCOutlookBarTabCtrl [MFC], SetBorderSize
- CMFCOutlookBarTabCtrl [MFC], SetPageButtonTextAlign
- CMFCOutlookBarTabCtrl [MFC], SetToolbarImageList
- CMFCOutlookBarTabCtrl [MFC], SetVisiblePageButtons
ms.assetid: b1f2b3f7-cc59-49a3-99d8-7ff9b37c044b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e677879079eaab3dd36481fec76ca53da92ef87d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcoutlookbartabctrl-class"></a>CMFCOutlookBarTabCtrl sınıfı
Görsel görünümünü sahip bir sekme denetimi **Gezinti Bölmesi** Microsoft Outlook.  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]    
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCOutlookBarTabCtrl : public CMFCBaseTabCtrl  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCOutlookBarTabCtrl::CMFCOutlookBarTabCtrl`|Varsayılan Oluşturucu.|  
|`CMFCOutlookBarTabCtrl::~CMFCOutlookBarTabCtrl`|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCOutlookBarTabCtrl::AddControl](#addcontrol)|Outlook çubuğu yeni bir sekmede olarak bir Windows denetimini ekler.|  
|`CMFCOutlookBarTabCtrl::CalcRectEdit`|Çerçevesi tarafından çağrılır bir kullanıcı görünür düzenleme kutusuna boyutlarını belirlemek için bir sekme yeniden adlandırır. (Geçersiz kılmaları `CMFCBaseTabCtrl::CalcRectEdit`.)|  
|[CMFCOutlookBarTabCtrl::CanShowFewerPageButtons](#canshowfewerpagebuttons)|Görüntülenmekte olan daha az Outlook çubuğu sekmesini sayfa düğmelerini görüntülenebilir belirlemek için yeniden boyutlandırma işlemleri sırasında çerçevesi tarafından çağrılır.|  
|[CMFCOutlookBarTabCtrl::CanShowMorePageButtons](#canshowmorepagebuttons)|Daha fazla Outlook Çubuğu sekmesinde sayfa düğmelerini görüntülenmekte olan daha görüntülenen belirlemek için yeniden boyutlandırma işlemleri sırasında çerçevesi tarafından çağrılır.|  
|[CMFCOutlookBarTabCtrl::Create](#create)|Outlook Çubuğu sekme denetimi oluşturur.|  
|`CMFCOutlookBarTabCtrl::CreateObject`|Bu sınıf türü dinamik bir örneğini oluşturmak için framework tarafından kullanıldı.|  
|[CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation)|Etkin sekmeler arasında geçiş sırasında ortaya çıkan animasyonun etkinleştirilip etkinleştirilmeyeceğini belirtir.|  
|[CMFCOutlookBarTabCtrl::EnableInPlaceEdit](#enableinplaceedit)|Bir kullanıcı Outlook çubuğu sekmesini düğmelerini üzerindeki metin etiketleri değiştirebilir olup olmadığını belirtir. (Geçersiz kılmaları [CMFCBaseTabCtrl::EnableInPlaceEdit](../../mfc/reference/cmfcbasetabctrl-class.md#enableinplaceedit).)|  
|[CMFCOutlookBarTabCtrl::EnableScrollButtons](#enablescrollbuttons)|Outlook Çubuğu bölmesi düğmeleri kaydırmak kullanıcı izin düğmelerini etkinleştirmek için çerçevesi tarafından çağrılır.|  
|`CMFCOutlookBarTabCtrl::FindTargetWnd`|Belirtilen bir nokta içeren bölme tanımlar. (Geçersiz kılmaları [CMFCBaseTabCtrl::FindTargetWnd](../../mfc/reference/cmfcbasetabctrl-class.md#findtargetwnd).)|  
|[CMFCOutlookBarTabCtrl::GetBorderSize](#getbordersize)|Outlook sekme denetimi kenarlık boyutu döndürür.|  
|`CMFCOutlookBarTabCtrl::GetTabArea`|Boyut ve sekme denetimi sekme alanı konumunu alır. (Geçersiz kılmaları [CMFCBaseTabCtrl::GetTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#gettabarea).)|  
|`CMFCOutlookBarTabCtrl::GetThisClass`|Bir işaretçi elde etmek için çerçevesi tarafından kullanılan [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) Bu sınıf türü ile ilişkili nesne.|  
|[CMFCOutlookBarTabCtrl::GetVisiblePageButtons](#getvisiblepagebuttons)||  
|[CMFCOutlookBarTabCtrl::IsAnimation](#isanimation)|Etkin sekmeler arasında geçiş sırasında ortaya çıkan animasyon etkin olup olmadığını belirler.|  
|[CMFCOutlookBarTabCtrl::IsMode2003](#ismode2003)|Outlook Çubuğu sekme denetimi Microsoft Outlook 2003 öykünen bir modunda olup olmadığını belirler.|  
|`CMFCOutlookBarTabCtrl::IsPtInTabArea`|Bir noktayı sekme alanı içinde olup olmadığını belirler. (Geçersiz kılmaları [CMFCBaseTabCtrl::IsPtInTabArea](../../mfc/reference/cmfcbasetabctrl-class.md#isptintabarea).)|  
|`CMFCOutlookBarTabCtrl::IsTabDetachable`|Sekme çıkarılabilir olup olmadığını belirler. (Geçersiz kılmaları [CMFCBaseTabCtrl::IsTabDetachable](../../mfc/reference/cmfcbasetabctrl-class.md#istabdetachable).)|  
|`CMFCOutlookBarTabCtrl::OnChangeTabs`|Sekme eklenen veya kaldırılan çerçevesi tarafından çağrılır. (Geçersiz kılmaları `CMFCBaseTabCtrl::OnChangeTabs`.)|  
|[CMFCOutlookBarTabCtrl::OnShowFewerPageButtons](#onshowfewerpagebuttons)|Görünür sekmesinde sayfa düğmelerini sayısını azaltmak için çerçevesi tarafından çağrılır.|  
|[CMFCOutlookBarTabCtrl::OnShowMorePageButtons](#onshowmorepagebuttons)|Görünür sekmesinde sayfa düğmelerini sayısını artırmak için çerçevesi tarafından çağrılır.|  
|[CMFCOutlookBarTabCtrl::OnShowOptions](#onshowoptions)|Görüntüler **Gezinti Bölmesi Seçenekleri** iletişim.|  
|`CMFCOutlookBarTabCtrl::RecalcLayout`|Sekme denetimi iç düzenini yeniden hesaplar. (Geçersiz kılmaları [CMFCBaseTabCtrl::RecalcLayout](../../mfc/reference/cmfcbasetabctrl-class.md#recalclayout).)|  
|[CMFCOutlookBarTabCtrl::SetActiveTab](#setactivetab)|Etkin sekme ayarlar. (Geçersiz kılmaları [CMFCBaseTabCtrl::SetActiveTab](../../mfc/reference/cmfcbasetabctrl-class.md#setactivetab).)|  
|[CMFCOutlookBarTabCtrl::SetBorderSize](#setbordersize)|Outlook sekme denetimi kenarlık boyutunu ayarlar.|  
|[CMFCOutlookBarTabCtrl::SetPageButtonTextAlign](#setpagebuttontextalign)|Metin etiketlerini hizalamasını Outlook çubuğu sekmesini düğmeleri ayarlar.|  
|[CMFCOutlookBarTabCtrl::SetToolbarImageList](#settoolbarimagelist)|Outlook 2003 modunda Outlook çubuğunun altındaki görüntülenen simgeler içeren bit eşlem ayarlar (bkz [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)).|  
|[CMFCOutlookBarTabCtrl::SetVisiblePageButtons](#setvisiblepagebuttons)||  
  
## <a name="remarks"></a>Açıklamalar  
 Yerleşik desteği olan bir Outlook çubuğu oluşturmak için bir `CMFCOutlookBar` Outlook sekme denetimi çubuğu barındırmak için nesne. Daha fazla bilgi için bkz: [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl başlatılacağını gösteren bir `CMFCOutlookBarTabCtrl` nesne ve çeşitli yöntemlerle kullanma `CMFCOutlookBarTabCtrl` sınıfı. Örnek yerinde Outlook Çubuğu sekme sayfası düğmelerinin metin etiketi düzenlemeyi etkinleştirmek, animasyonun etkinleştirmek Outlook Çubuğu bölmesi düğmeleri kaydırın, Outlook sekmesini devamı kenarlık boyutunu ayarlamak kullanıcının kaydırma tanıtıcıları, nasıl gösterir Rol ve Outlook çubuğu sekmesini düğmelerinin üzerindeki metin etiketlerini hizalamasını ayarlama. Bu kod parçacığını parçası olan [Outlook gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookDemo#1](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_1.cpp)]  
[!code-cpp[NVC_MFC_OutlookDemo#2](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCBaseTabCtrl](../../mfc/reference/cmfcbasetabctrl-class.md)  
  
 [CMFCOutlookBarTabCtrl](../../mfc/reference/cmfcoutlookbartabctrl-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxoutlookbartabctrl.h  
  
##  <a name="addcontrol"></a>  CMFCOutlookBarTabCtrl::AddControl  
 Outlook çubuğu yeni bir sekmede olarak bir Windows denetimini ekler.  
  
```  
void AddControl(
    CWnd* pWndCtrl,  
    LPCTSTR lpszName,  
    int nImageID=-1,  
    BOOL bDetachable=TRUE,  
    DWORD dwControlBarStyle=AFX_CBRS_FLOAT |  AFX_CBRS_CLOSE | AFX_CBRS_RESIZE |  CBRS_AFX_AUTOHIDE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pWndCtrl`  
 Eklemek için bir denetim için bir işaretçi.  
  
 [in] `lpszName`  
 Sekmenin adını belirtir.  
  
 [in] `bDetachable`  
 Varsa `TRUE`, sayfa gibi çıkarılabilir oluşturulur.  
  
 [in] `nImageID`  
 Görüntü dizini yeni sekmede gösterilecek görüntü için iç görüntü listesinde.  
  
 [in] `dwControlBarStyle`  
 AFX_ belirtir `CBRS_`* Sarmalanan takma bölmeleri stili.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni bir outlook çubuğu sayfa denetim eklemek için bu işlevi kullanın.  
  
 Bu işlev dahili olarak çağırır [CMFCBaseTabCtrl::AddTab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab).  
  
 Ayarlarsanız `bDetachable` için `TRUE`, `AddControl` dahili oluşturur bir `CDockablePaneAdapter` nesne ve eklenen denetim sarmalar. Otomatik olarak çalışma zamanı sınıf çalışma zamanı sınıf sekmeli penceresinin ayarlar `CMFCOutlookBar` ve kayan çerçevesi çalışma zamanı sınıfı `CMultiPaneFrameWnd`.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `AddControl` yönteminde `CMFCOutlookBarTabCtrl` sınıfı. Bu kod parçacığını parçası olan [Outlook gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_OutlookDemo#3](../../mfc/reference/codesnippet/cpp/cmfcoutlookbartabctrl-class_3.cpp)]  
  
##  <a name="canshowfewerpagebuttons"></a>  CMFCOutlookBarTabCtrl::CanShowFewerPageButtons  
 Yeniden boyutlandırma görüntülenmekte olan çok daha az Outlook Çubuğu sekmesinde sayfa düğmelerini görüntülenebilir olup olmadığını belirlemek için işlemleri sırasında çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL CanShowFewerPageButtons() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` birden fazla düğmesini ise; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Outlook Çubuğu sekme denetimi dinamik olarak ekler veya ne kadar kullanılabilir yer bağlı olarak görünen sekmeler kaldırır. Bu yöntem, bu işlemde yardımcı olması için çerçevesi tarafından kullanılır.  
  
##  <a name="canshowmorepagebuttons"></a>  CMFCOutlookBarTabCtrl::CanShowMorePageButtons  
 Yeniden boyutlandırma görüntülenmekte olan çok daha fazla Outlook Çubuğu sekmesinde sayfa düğmelerini görüntülenebilir olup olmadığını belirlemek için işlemleri sırasında çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL CanShowMorePageButtons() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` şu anda görünmez düğmeleri varsa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Outlook Çubuğu sekme denetimi dinamik olarak ekler veya sekmeler ne kadar kullanılabilir yer bağlı olarak bu görünümden kaldırır. Bu yöntem, bu işlemde yardımcı olması için çerçevesi tarafından kullanılır.  
  
##  <a name="create"></a>  CMFCOutlookBarTabCtrl::Create  
 Outlook Çubuğu sekme denetimi oluşturur.  
  
```  
virtual BOOL Create(
    const CRect& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `rect`  
 İlk boyutunu ve konumunu piksel cinsinden belirtir.  
  
 [in] `pParentWnd`  
 Üst pencere noktalarına. Olmamalıdır `NULL`.  
  
 [in] `nID`  
 Denetim kimliği.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Denetimi başarıyla oluşturulduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle, ne zaman oluşturulan outlook çubuğu sekme denetimleri [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md) denetimleri `WM_CREATE` işleminin ileti.  
  
##  <a name="enableanimation"></a>  CMFCOutlookBarTabCtrl::EnableAnimation  
 Etkin sekmeler arasında geçiş sırasında ortaya çıkan animasyonun etkinleştirilip etkinleştirilmeyeceğini belirtir.  
  
```  
static void EnableAnimation(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bEnable`  
 Animasyonun etkin veya devre dışı belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevi etkinleştirmek ve animasyon devre dışı bırakmak için çağırın. Sekme sayfası kullanıcı oturum açtığında, animasyon etkinse, sayfanın başlığı yukarı veya aşağı slayt. Animasyon devre dışıysa, sayfa hemen etkin olur.  
  
 Varsayılan olarak, animasyon etkindir.  
  
##  <a name="enableinplaceedit"></a>  CMFCOutlookBarTabCtrl::EnableInPlaceEdit  
 Bir kullanıcı, Outlook Çubuğu sekmesinde sayfa düğmelerini üzerindeki metin etiketlerini değiştirebilir olup olmadığını belirtir.  
  
```  
virtual void EnableInPlaceEdit(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parametreler  
 `bEnable`  
 Varsa `TRUE`, yerinde metin etiketini düzenleme etkinleştirin. Varsa `FALSE`, yerinde düzenlemeyi devre dışı bırakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlevi etkinleştirmek veya sekmesinde sayfa düğmelerini üzerindeki metin etiketlerini yerinde düzenlemeyi devre dışı bırakmak için çağırın. Varsayılan olarak, yerinde düzenleme devre dışıdır.  
  
##  <a name="enablescrollbuttons"></a>  CMFCOutlookBarTabCtrl::EnableScrollButtons  
 Outlook Çubuğu bölmesi düğmeleri kaydırmak kullanıcı izin kaydırma tanıtıcıları etkinleştirmek için çerçevesi tarafından çağrılır.  
  
```  
void EnableScrollButtons(
    BOOL bEnable = TRUE,  
    BOOL bIsUp = TRUE,  
    BOOL bIsDown = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bEnable`  
 Kaydırma düğmelerini görüntülenip görüntülenmeyeceğini belirler.  
  
 [in] `bIsUp`  
 Üst scrollbar görüntülenip görüntülenmeyeceğini belirler.  
  
 [in] `bIsDown`  
 Alt scrollbar görüntülenip görüntülenmeyeceğini belirler.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaydırma düğmelerini görüntülemeyi etkinleştirir. Etkin sekme kaydırma düğmelerini geri yüklemek için değiştiğinde bu yöntem çerçevesi tarafından çağrılır.  
  
##  <a name="getbordersize"></a>  CMFCOutlookBarTabCtrl::GetBorderSize  
 Outlook sekme denetimi kenarlık boyutu döndürür.  
  
```  
int GetBorderSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kenarlığın piksel cinsinden boyutu.  
  
##  <a name="getvisiblepagebuttons"></a>  CMFCOutlookBarTabCtrl::GetVisiblePageButtons  

  
```  
int GetVisiblePageButtons() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isanimation"></a>  CMFCOutlookBarTabCtrl::IsAnimation  
 Etkin sekmeler arasında geçiş sırasında ortaya çıkan animasyonun etkinleştirilip etkinleştirilmeyeceğini belirtir.  
  
```  
static BOOL IsAnimation();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Animasyonun etkinse, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation) etkinleştirme veya devre dışı animasyon işlevi.  
  
##  <a name="ismode2003"></a>  CMFCOutlookBarTabCtrl::IsMode2003  
 Outlook Çubuğu sekme denetimi Microsoft Outlook 2003 öykünen bir modunda olup olmadığını belirler.  
  
```  
BOOL IsMode2003() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` Outlook sekme denetimi çubuğu Outlook 2003 modundaysa; Aksi takdirde `FALSE`;  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer belirlediği [CMFCOutlookBar::SetMode2003](../../mfc/reference/cmfcoutlookbar-class.md#setmode2003).  
  
##  <a name="onshowfewerpagebuttons"></a>  CMFCOutlookBarTabCtrl::OnShowFewerPageButtons  
 Görünür sekmesinde sayfa düğmelerini sayısını azaltmak için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnShowFewerPageButtons();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim yeniden boyutlandırıldığında bu yöntem görünür sayfası sekmesi düğme sayısını ayarlar.  
  
##  <a name="onshowmorepagebuttons"></a>  CMFCOutlookBarTabCtrl::OnShowMorePageButtons  
 Görünür sekmesinde sayfa düğmelerini sayısını artırmak için çerçevesi tarafından çağrılır.  
  
```  
virtual void OnShowMorePageButtons();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem denetimi yeniden boyutlandırıldığında görünür olan sekme sayfası düğme sayısını ayarlayın.  
  
##  <a name="onshowoptions"></a>  CMFCOutlookBarTabCtrl::OnShowOptions  
 Görüntüler **Gezinti Bölmesi Seçenekleri** iletişim kutusu.  
  
```  
virtual void OnShowOptions();
```  
  
### <a name="remarks"></a>Açıklamalar  
 **Gezinti Bölmesi Seçenekleri** iletişim kutusu sekmesinde sayfa düğmelerini görüntüleneceğini seçin ve bunlar görüntülenme sırasıyla kullanıcıya sağlar.  
  
 Bu yöntem kullanıcı seçtiğinde çerçevesi tarafından çağrılır **Gezinti Bölmesi Seçenekleri** denetimin özelleştirme menüsünde menü öğesi.  
  
##  <a name="setactivetab"></a>  CMFCOutlookBarTabCtrl::SetActiveTab  
 Etkin sekme ayarlar. Etkin sekme görünür içeriğinin ile açık olan adrestir.  
  
```  
virtual BOOL SetActiveTab(int iTab);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `iTab`  
 Açılacak şekilde bir sekme sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen sekme başarıyla açılıp açılmadığını sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Animasyon olup etkinleştirdiyseniz üzerinde etkin sekme ayarı visual etkisini bağlıdır. Daha fazla bilgi için bkz: [CMFCOutlookBarTabCtrl::EnableAnimation](#enableanimation).  
  
##  <a name="setbordersize"></a>  CMFCOutlookBarTabCtrl::SetBorderSize  
 Outlook sekme denetimi kenarlık boyutunu ayarlar.  
  
```  
void SetBorderSize(int nBorderSize);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nBorderSize`  
 Yeni sınır boyutunu piksel cinsinden belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni sınır boyutu ayarlar ve outlook pencere düzenini yeniden hesaplar.  
  
##  <a name="setpagebuttontextalign"></a>  CMFCOutlookBarTabCtrl::SetPageButtonTextAlign  
 Metin etiketlerini hizalamasını Outlook çubuğu sekmesini düğmeleri ayarlar.  
  
```  
void SetPageButtonTextAlign(
    UINT uiAlign,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiAlign`  
 Metin hizalamasını belirtir.  
  
 [in] `bRedraw`  
 Varsa `TRUE`, outlook penceresi çizilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Metin hizalama sayfa düğmelerinin değiştirmek için bu işlevi kullanın.  
  
 `uiAlign` Aşağıdaki değerlerden biri olabilir:  
  
|Sabit|Açıklama|  
|--------------|-------------|  
|TA_LEFT|Sol hizalama|  
|TA_CENTER|Ortala|  
|TA_RIGHT|Sağa hizalama|  
  
 TA_CENTER varsayılan değerdir.  
  
##  <a name="settoolbarimagelist"></a>  CMFCOutlookBarTabCtrl::SetToolbarImageList  
 Outlook 2003 modunda Outlook çubuğunun altındaki görüntülenen simgeler içeren bit eşlem ayarlar.  
  
```  
BOOL SetToolbarImageList(
    UINT uiID,  
    int cx,  
    COLORREF clrTransp=RGB(255, 0, 255));
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `uiID`  
 Yüklemek için görüntü kaynak Kimliğini belirtir.  
  
 [in] `cx`  
 Görüntü listesinde, piksel cinsinden görüntü genişliğini belirtir.  
  
 [in] `clrTransp`  
 Saydam Rengi belirten bir RGB değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `TRUE` başarılıysa; Aksi takdirde döndürür `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Microsoft Office 2003 modu araç çubuğu düğmeleri görüntüleri görüntülenecek bir görüntü listesi eklemek için bu işlevi kullanın. Görüntü dizinleri sayfa dizine karşılık gelmelidir.  
  
 Bu yöntem, Microsoft Office 2003 modundaysa içinde değil çağrılmamalıdır. Daha fazla bilgi için bkz: [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md).  
  
##  <a name="setvisiblepagebuttons"></a>  CMFCOutlookBarTabCtrl::SetVisiblePageButtons  

  
```  
void SetVisiblePageButtons(int nVisiblePageButtons);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nVisiblePageButtons`  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCBaseTabCtrl sınıfı](../../mfc/reference/cmfcbasetabctrl-class.md)   
 [CMFCOutlookBar sınıfı](../../mfc/reference/cmfcoutlookbar-class.md)   
 [CMFCOutlookBarPane Sınıfı](../../mfc/reference/cmfcoutlookbarpane-class.md)
