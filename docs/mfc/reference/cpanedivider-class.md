---
title: CPaneDivider sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPaneDivider
- AFXPANEDIVIDER/CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::CPaneDivider
- AFXPANEDIVIDER/CPaneDivider::AddPaneContainer
- AFXPANEDIVIDER/CPaneDivider::AddPane
- AFXPANEDIVIDER/CPaneDivider::AddRecentPane
- AFXPANEDIVIDER/CPaneDivider::CalcExpectedDockedRect
- AFXPANEDIVIDER/CPaneDivider::CalcFixedLayout
- AFXPANEDIVIDER/CPaneDivider::CheckVisibility
- AFXPANEDIVIDER/CPaneDivider::CreateEx
- AFXPANEDIVIDER/CPaneDivider::DoesAllowDynInsertBefore
- AFXPANEDIVIDER/CPaneDivider::DoesContainFloatingPane
- AFXPANEDIVIDER/CPaneDivider::FindPaneContainer
- AFXPANEDIVIDER/CPaneDivider::FindTabbedPane
- AFXPANEDIVIDER/CPaneDivider::GetDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::GetFirstPane
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividerStyle
- AFXPANEDIVIDER/CPaneDivider::GetRootContainerRect
- AFXPANEDIVIDER/CPaneDivider::GetWidth
- AFXPANEDIVIDER/CPaneDivider::Init
- AFXPANEDIVIDER/CPaneDivider::InsertPane
- AFXPANEDIVIDER/CPaneDivider::IsAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::IsDefault
- AFXPANEDIVIDER/CPaneDivider::IsHorizontal
- AFXPANEDIVIDER/CPaneDivider::Move
- AFXPANEDIVIDER/CPaneDivider::NotifyAboutRelease
- AFXPANEDIVIDER/CPaneDivider::OnShowPane
- AFXPANEDIVIDER/CPaneDivider::ReleaseEmptyPaneContainers
- AFXPANEDIVIDER/CPaneDivider::RemovePane
- AFXPANEDIVIDER/CPaneDivider::ReplacePane
- AFXPANEDIVIDER/CPaneDivider::RepositionPanes
- AFXPANEDIVIDER/CPaneDivider::Serialize
- AFXPANEDIVIDER/CPaneDivider::SetAutoHideMode
- AFXPANEDIVIDER/CPaneDivider::SetPaneContainerManager
- AFXPANEDIVIDER/CPaneDivider::ShowWindow
- AFXPANEDIVIDER/CPaneDivider::StoreRecentDockSiteInfo
- AFXPANEDIVIDER/CPaneDivider::StoreRecentTabRelatedInfo
- AFXPANEDIVIDER/CPaneDivider::GetPanes
- AFXPANEDIVIDER/CPaneDivider::GetPaneDividers
- AFXPANEDIVIDER/CPaneDivider::m_nDefaultWidth
- AFXPANEDIVIDER/CPaneDivider::m_pSliderRTC
dev_langs:
- C++
helpviewer_keywords:
- CPaneDivider [MFC], CPaneDivider
- CPaneDivider [MFC], AddPaneContainer
- CPaneDivider [MFC], AddPane
- CPaneDivider [MFC], AddRecentPane
- CPaneDivider [MFC], CalcExpectedDockedRect
- CPaneDivider [MFC], CalcFixedLayout
- CPaneDivider [MFC], CheckVisibility
- CPaneDivider [MFC], CreateEx
- CPaneDivider [MFC], DoesAllowDynInsertBefore
- CPaneDivider [MFC], DoesContainFloatingPane
- CPaneDivider [MFC], FindPaneContainer
- CPaneDivider [MFC], FindTabbedPane
- CPaneDivider [MFC], GetDefaultWidth
- CPaneDivider [MFC], GetFirstPane
- CPaneDivider [MFC], GetPaneDividerStyle
- CPaneDivider [MFC], GetRootContainerRect
- CPaneDivider [MFC], GetWidth
- CPaneDivider [MFC], Init
- CPaneDivider [MFC], InsertPane
- CPaneDivider [MFC], IsAutoHideMode
- CPaneDivider [MFC], IsDefault
- CPaneDivider [MFC], IsHorizontal
- CPaneDivider [MFC], Move
- CPaneDivider [MFC], NotifyAboutRelease
- CPaneDivider [MFC], OnShowPane
- CPaneDivider [MFC], ReleaseEmptyPaneContainers
- CPaneDivider [MFC], RemovePane
- CPaneDivider [MFC], ReplacePane
- CPaneDivider [MFC], RepositionPanes
- CPaneDivider [MFC], Serialize
- CPaneDivider [MFC], SetAutoHideMode
- CPaneDivider [MFC], SetPaneContainerManager
- CPaneDivider [MFC], ShowWindow
- CPaneDivider [MFC], StoreRecentDockSiteInfo
- CPaneDivider [MFC], StoreRecentTabRelatedInfo
- CPaneDivider [MFC], GetPanes
- CPaneDivider [MFC], GetPaneDividers
- CPaneDivider [MFC], m_nDefaultWidth
- CPaneDivider [MFC], m_pSliderRTC
ms.assetid: 8e828a5d-232f-4127-b8e3-7fa45a7a476e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7315adc855b0bfbe1cc4ffae87c416fbaa584d57
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079370"
---
# <a name="cpanedivider-class"></a>CPaneDivider sınıfı
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 `CPaneDivider` Sınıfı iki bölme böler, bölmeleri iki grupları böler veya bir grup ana çerçeve penceresi istemci alanından bölmeleri ayırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPaneDivider : public CBasePane  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPaneDivider::CPaneDivider](#cpanedivider)||  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPaneDivider::AddPaneContainer](#addpanecontainer)||  
|[CPaneDivider::AddPane](#addpane)||  
|[CPaneDivider::AddRecentPane](#addrecentpane)||  
|[CPaneDivider::CalcExpectedDockedRect](#calcexpecteddockedrect)||  
|[CPaneDivider::CalcFixedLayout](#calcfixedlayout)|(Geçersiz kılmaları [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CPaneDivider::CheckVisibility](#checkvisibility)||  
|[CPaneDivider::CreateEx](#createex)|(Geçersiz kılmaları [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex).)|  
|[CPaneDivider::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|(Geçersiz kılmaları [CBasePane::DoesAllowDynInsertBefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CPaneDivider::DoesContainFloatingPane](#doescontainfloatingpane)||  
|[CPaneDivider::FindPaneContainer](#findpanecontainer)||  
|[CPaneDivider::FindTabbedPane](#findtabbedpane)||  
|[CPaneDivider::GetDefaultWidth](#getdefaultwidth)||  
|[CPaneDivider::GetFirstPane](#getfirstpane)||  
|[CPaneDivider::GetPaneDividerStyle](#getpanedividerstyle)||  
|[CPaneDivider::GetRootContainerRect](#getrootcontainerrect)||  
|[CPaneDivider::GetWidth](#getwidth)||  
|[CPaneDivider::Init](#init)||  
|[CPaneDivider::InsertPane](#insertpane)||  
|[CPaneDivider::IsAutoHideMode](#isautohidemode)|(Geçersiz kılmaları [CBasePane::IsAutoHideMode](../../mfc/reference/cbasepane-class.md#isautohidemode).)|  
|[CPaneDivider::IsDefault](#isdefault)||  
|[CPaneDivider::IsHorizontal](#ishorizontal)|(Geçersiz kılmaları [CBasePane::IsHorizontal](../../mfc/reference/cbasepane-class.md#ishorizontal).)|  
|[CPaneDivider::Move](#move)||  
|[CPaneDivider::NotifyAboutRelease](#notifyaboutrelease)||  
|[CPaneDivider::OnShowPane](#onshowpane)||  
|[CPaneDivider::ReleaseEmptyPaneContainers](#releaseemptypanecontainers)||  
|[CPaneDivider::RemovePane](#removepane)||  
|[CPaneDivider::ReplacePane](#replacepane)||  
|[CPaneDivider::RepositionPanes](#repositionpanes)||  
|[CPaneDivider::Serialize](#serialize)|(Geçersiz kılmaları `CBasePane::Serialize`.)|  
|[CPaneDivider::SetAutoHideMode](#setautohidemode)||  
|[CPaneDivider::SetPaneContainerManager](#setpanecontainermanager)||  
|[CPaneDivider::ShowWindow](#showwindow)||  
|[CPaneDivider::StoreRecentDockSiteInfo](#storerecentdocksiteinfo)||  
|[CPaneDivider::StoreRecentTabRelatedInfo](#storerecenttabrelatedinfo)||  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPaneDivider::GetPanes](#getpanes)|Bulunan bölmeleri listesini döndürür [CPaneContainer sınıfı](../../mfc/reference/cpanecontainer-class.md). Bu yöntem yalnızca varsayılan bölmesinde Bölücü çağrılmalıdır.|  
|[CPaneDivider::GetPaneDividers](#getpanedividers)|Bulunan bölmesinde Bölücü listesini döndürür [CPaneContainer sınıfı](../../mfc/reference/cpanecontainer-class.md). Bu yöntem yalnızca varsayılan bölmesinde Bölücü çağrılmalıdır.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPaneDivider::m_nDefaultWidth](#m_ndefaultwidth)|Uygulamadaki tüm bölmesinde Bölücü piksel varsayılan genişliğini belirtir.|  
|[CPaneDivider::m_pSliderRTC](#m_psliderrtc)|Bir işaretçi hakkında çalışma zamanı sınıf bilgileri tutan bir `CPaneDivider`-türetilmiş bir nesne içermelidir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Framework oluşturur `CPaneDivider` bölme yerleştirildiğinde otomatik olarak nesneleri.  
  
 Bölmesinde Bölücü iki tür vardır:  
  
-   bir grup bölmeleri ana çerçeve penceresi tarafına yerleştirildiğinde varsayılan bölmesinde ayırıcı oluşturulur. Bir işaretçi varsayılan bölmesinde ayırıcı tutan [CPaneContainerManager sınıfı](../../mfc/reference/cpanecontainermanager-class.md) ve bölmeleri grubunda işlemlerinin çoğu yönlendirir (bir bölmesini yeniden boyutlandırmak veya başka bir yerleştirme gibi bölmesi veya kapsayıcı) kapsayıcı Manager. Her takma bölmesinde kendi varsayılan bölmesinde ayırıcı gösteren bir işaretçi tutar.  
  
-   Normal bölmesinde ayırıcı yalnızca bir kapsayıcıda iki bölme böler. Daha fazla bilgi için bkz: [CPaneContainer sınıfı](../../mfc/reference/cpanecontainer-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl alındığını anlatan bir `CPaneDivider` nesnesinin bir `CWorkspaceBar` nesnesi. Bu kod parçacığını parçası olan [MDI sekmeleri gösterim örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#5](../../mfc/reference/codesnippet/cpp/cpanedivider-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPaneDivider](../../mfc/reference/cpanedivider-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxPaneDivider.h  
  
##  <a name="setautohidemode"></a>  CPaneDivider::SetAutoHideMode  

  
```  
void SetAutoHideMode(BOOL bMode);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bMode*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpanecontainermanager"></a>  CPaneDivider::SetPaneContainerManager  

  
```  
void SetPaneContainerManager(CPaneContainerManager* p);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *p*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addpane"></a>  CPaneDivider::AddPane  

  
```  
virtual void AddPane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addpanecontainer"></a>  CPaneDivider::AddPaneContainer  

  
```  
virtual BOOL AddPaneContainer(
    CPaneContainerManager& barContainerManager,  
    BOOL bOuterEdge);

 
virtual BOOL AddPaneContainer(
    CDockablePane* pTargetBar,  
    CPaneContainerManager& barContainerManager,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *barContainerManager*  
 [in] *bOuterEdge*  
 [in] *pTargetBar*  
 [in] *dwAlignment*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="addrecentpane"></a>  CPaneDivider::AddRecentPane  

  
```  
virtual CDockablePane* AddRecentPane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="calcexpecteddockedrect"></a>  CPaneDivider::CalcExpectedDockedRect  

  
```  
virtual void CalcExpectedDockedRect(
    CWnd* pWndToDock,  
    CPoint ptMouse,  
    CRect& rectResult,  
    BOOL& bDrawTab,  
    CDockablePane** ppTargetBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pWndToDock*  
 [in] *ptMouse*  
 [in] *rectResult*  
 [in] *bDrawTab*  
 [in] *ppTargetBar*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="calcfixedlayout"></a>  CPaneDivider::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bStretch*  
 [in] *bHorz*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="checkvisibility"></a>  CPaneDivider::CheckVisibility  

  
```  
virtual BOOL CheckVisibility();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="cpanedivider"></a>  CPaneDivider::CPaneDivider  

  
```  
CPaneDivider();

 
CPaneDivider(
    BOOL bDefaultSlider,  
    CWnd* pParent = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bDefaultSlider*  
 [in] *pParent*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="createex"></a>  CPaneDivider::CreateEx  

  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *dwStyleEx*  
 [in] *dwStyle*  
 [in] *rect*  
 [in] *pParentWnd*  
 [in] *nID*  
 [in] *pContext*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="doesallowdyninsertbefore"></a>  CPaneDivider::DoesAllowDynInsertBefore  

  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="doescontainfloatingpane"></a>  CPaneDivider::DoesContainFloatingPane  

  
```  
virtual BOOL DoesContainFloatingPane();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="findpanecontainer"></a>  CPaneDivider::FindPaneContainer  

  
```  
CPaneContainer* FindPaneContainer(
    CDockablePane* pBar,  
    BOOL& bLeftBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
 [in] *bLeftBar*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="findtabbedpane"></a>  CPaneDivider::FindTabbedPane  

  
```  
CDockablePane* FindTabbedPane(UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nID*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getdefaultwidth"></a>  CPaneDivider::GetDefaultWidth  

  
```  
static int __stdcall GetDefaultWidth();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getfirstpane"></a>  CPaneDivider::GetFirstPane  

  
```  
const CBasePane* GetFirstPane() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpanedividers"></a>  CPaneDivider::GetPaneDividers  
 Bulunan bölmesinde Bölücü listesini döndürür [CPaneContainer sınıfı](../../mfc/reference/cpanecontainer-class.md). Bu yöntem yalnızca varsayılan bölmesinde Bölücü çağrılmalıdır.  
  
```  
void GetPaneDividers(CObList& lstSliders);
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *lstSliders*  
 Bölmesinde kapsayıcıda yer bölmesinde Bölücü listesini içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem yalnızca varsayılan bölmesinde Bölücü çağrılmalıdır. Varsayılan bölmesinde ayırıcı tüm bölmesinde kapsayıcı yeniden boyutlandırır bir ayırıcı ' dir.  
  
##  <a name="getpanedividerstyle"></a>  CPaneDivider::GetPaneDividerStyle  

  
```  
DWORD GetPaneDividerStyle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getpanes"></a>  CPaneDivider::GetPanes  
 Bulunan bölmeleri listesini döndürür [CPaneContainer sınıfı](../../mfc/reference/cpanecontainer-class.md). Bu yöntem, yalnızca varsayılan bölmesinde Bölücü almak için çağrılmalıdır.  
  
```  
void GetPanes(CObList& lstBars);
```  
  
### <a name="parameters"></a>Parametreler  
 [out] *lstBars*  
 Bölmesinde kapsayıcıda yer bölmeleri listesini içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem yalnızca varsayılan bölmesinde Bölücü çağrılmalıdır. Varsayılan bölmesinde ayırıcı tüm bölmesinde kapsayıcı yeniden boyutlandırır bir ayırıcı ' dir.  
  
##  <a name="getrootcontainerrect"></a>  CPaneDivider::GetRootContainerRect  

  
```  
CRect GetRootContainerRect();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getwidth"></a>  CPaneDivider::GetWidth  

  
```  
int GetWidth() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="init"></a>  CPaneDivider::Init  

  
```  
void Init(
    BOOL bDefaultSlider = FALSE,  
    CWnd* pParent = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *bDefaultSlider*  
 [in] *pParent*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="insertpane"></a>  CPaneDivider::InsertPane  

  
```  
virtual BOOL InsertPane(
    CDockablePane* pBarToInsert,  
    CDockablePane* pTargetBar,  
    DWORD dwAlignment,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBarToInsert*  
 [in] *pTargetBar*  
 [in] *dwAlignment*  
 [in] *lpRect*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isautohidemode"></a>  CPaneDivider::IsAutoHideMode  

  
```  
BOOL IsAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="isdefault"></a>  CPaneDivider::IsDefault  

  
```  
BOOL IsDefault() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ishorizontal"></a>  CPaneDivider::IsHorizontal  

  
```  
BOOL IsHorizontal() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_ndefaultwidth"></a>  CPaneDivider::m_nDefaultWidth  
 Piksel cinsinden uygulamadaki tüm bölmesinde Bölücü varsayılan genişliğini belirtir.  
  
```  
AFX_IMPORT_DATA static int m_nDefaultWidth;  
```  
  
##  <a name="move"></a>  CPaneDivider::Move  

  
```  
virtual void Move(
    CPoint& ptOffset,  
    BOOL bAdjustLayout = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *ptOffset*  
 [in] *bAdjustLayout*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_psliderrtc"></a>  CPaneDivider::m_pSliderRTC  
 Bir işaretçi hakkında çalışma zamanı sınıf bilgileri tutan bir `CPaneDivider`-türetilmiş bir nesne içermelidir.  
  
```  
AFX_IMPORT_DATA static CRuntimeClass* m_pSliderRTC;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Özel bölmesi ayırıcı oluşturursanız, bu üye değişkeni ayarlayın. Bu bölmesinde çizildiğinde bölmesinde bölme oluşturmak çerçeve sağlar.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl ayarlanacağını gösterir `m_pSliderRTC` üye değişkeni:  
  
```  
class CMySplitter : public CPaneDivider  
{  
...  
};  
 
CPaneDivider::m_pSliderRTC = RUNTIME_CLASS(CMySpliter);
```  
  
##  <a name="notifyaboutrelease"></a>  CPaneDivider::NotifyAboutRelease  

  
```  
virtual void NotifyAboutRelease();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onshowpane"></a>  CPaneDivider::OnShowPane  

  
```  
virtual void OnShowPane(
    CDockablePane* pBar,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
 [in] *bBilgi Göster*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="releaseemptypanecontainers"></a>  CPaneDivider::ReleaseEmptyPaneContainers  

  
```  
void ReleaseEmptyPaneContainers();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="removepane"></a>  CPaneDivider::RemovePane  

  
```  
virtual void RemovePane(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="replacepane"></a>  CPaneDivider::ReplacePane  

  
```  
virtual BOOL ReplacePane(
    CDockablePane* pBarToReplace,  
    CDockablePane* pBarToReplaceWith);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBarToReplace*  
 [in] *pBarToReplaceWith*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="repositionpanes"></a>  CPaneDivider::RepositionPanes  

  
```  
virtual void RepositionPanes(
    CRect& rectNew,  
    HDWP& hdwp);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *rectNew*  
 [in] *hdwp*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="serialize"></a>  CPaneDivider::Serialize  

  
```  
void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *ar*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="showwindow"></a>  CPaneDivider::ShowWindow  

  
```  
void ShowWindow(int nCmdShow);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *nCmdShow*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="storerecentdocksiteinfo"></a>  CPaneDivider::StoreRecentDockSiteInfo  

  
```  
void StoreRecentDockSiteInfo(CDockablePane* pBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pBar*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="storerecenttabrelatedinfo"></a>  CPaneDivider::StoreRecentTabRelatedInfo  

  
```  
void StoreRecentTabRelatedInfo(
    CDockablePane* pDockingBar,  
    CDockablePane* pTabbedBar);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pDockingBar*  
 [in] *pTabbedBar*  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CPaneContainerManager sınıfı](../../mfc/reference/cpanecontainermanager-class.md)   
 [CPaneContainer sınıfı](../../mfc/reference/cpanecontainer-class.md)   
 [CDockingManager sınıfı](../../mfc/reference/cdockingmanager-class.md)   
 [CBasePane Sınıfı](../../mfc/reference/cbasepane-class.md)
