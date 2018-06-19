---
title: CMFCReBar sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCReBar
- AFXREBAR/CMFCReBar
- AFXREBAR/CMFCReBar::AddBar
- AFXREBAR/CMFCReBar::CalcFixedLayout
- AFXREBAR/CMFCReBar::CanFloat
- AFXREBAR/CMFCReBar::Create
- AFXREBAR/CMFCReBar::EnableDocking
- AFXREBAR/CMFCReBar::GetReBarBandInfoSize
- AFXREBAR/CMFCReBar::GetReBarCtrl
- AFXREBAR/CMFCReBar::OnShowControlBarMenu
- AFXREBAR/CMFCReBar::OnToolHitTest
- AFXREBAR/CMFCReBar::OnUpdateCmdUI
- AFXREBAR/CMFCReBar::SetPaneAlignment
dev_langs:
- C++
helpviewer_keywords:
- CMFCReBar [MFC], AddBar
- CMFCReBar [MFC], CalcFixedLayout
- CMFCReBar [MFC], CanFloat
- CMFCReBar [MFC], Create
- CMFCReBar [MFC], EnableDocking
- CMFCReBar [MFC], GetReBarBandInfoSize
- CMFCReBar [MFC], GetReBarCtrl
- CMFCReBar [MFC], OnShowControlBarMenu
- CMFCReBar [MFC], OnToolHitTest
- CMFCReBar [MFC], OnUpdateCmdUI
- CMFCReBar [MFC], SetPaneAlignment
ms.assetid: 02a60e29-6224-49c1-9e74-e0a7d9f8d023
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: abb880c1add83ec03d787c28b816f2e82caeddd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368806"
---
# <a name="cmfcrebar-class"></a>CMFCReBar sınıfı
A `CMFCReBar` düzeni, sürdürme ve rebar denetimleri için durum bilgilerini sağlayan bir denetim çubuğu nesnesidir.  
   [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCReBar : public CPane  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCReBar::AddBar](#addbar)|Bir bandı bir rebar ekler.|  
|[CMFCReBar::CalcFixedLayout](#calcfixedlayout)|(Geçersiz kılmaları [CBasePane::CalcFixedLayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CMFCReBar::CanFloat](#canfloat)|(Geçersiz kılmaları [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|  
|[CMFCReBar::Create](#create)|Rebar denetimi oluşturur ve ona ekler `CMFCReBar` nesnesi.|  
|[CMFCReBar::EnableDocking](#enabledocking)|(Geçersiz kılmaları [CBasePane::EnableDocking](../../mfc/reference/cbasepane-class.md#enabledocking).)|  
|[CMFCReBar::GetReBarBandInfoSize](#getrebarbandinfosize)||  
|[CMFCReBar::GetReBarCtrl](#getrebarctrl)|Arka plandaki doğrudan erişim sağlayan [CReBarCtrl](../../mfc/reference/crebarctrl-class.md) ortak denetimi.|  
|[CMFCReBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|(Geçersiz kılmaları [CPane::OnShowControlBarMenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu).)|  
|[CMFCReBar::OnToolHitTest](#ontoolhittest)|(Geçersiz kılmaları [CWnd::OnToolHitTest](../../mfc/reference/cwnd-class.md#ontoolhittest).)|  
|[CMFCReBar::OnUpdateCmdUI](#onupdatecmdui)|(Geçersiz kılmaları [CBasePane::OnUpdateCmdUI](http://msdn.microsoft.com/en-us/e139f06a-9793-4ee2-bc3d-517389368c77).)|  
|[CMFCReBar::SetPaneAlignment](#setpanealignment)|(Geçersiz kılmaları [CBasePane::SetPaneAlignment](../../mfc/reference/cbasepane-class.md#setpanealignment).)|  
  
## <a name="remarks"></a>Açıklamalar  
 A `CMFCReBar` nesne alt öğe pencerelerini çeşitli içerebilir. Bu düzen kutuları, araç çubukları ve liste kutularını içerir. Rebar program aracılığıyla boyutlandırabilirsiniz veya kullanıcı el ile rebar Mandal çubuğunu sürükleyerek genişletebilir. Bir rebar nesnesi arka planı tercih ettiğiniz bir bit eşlem için de ayarlayabilirsiniz.  
  
 Bir rebar nesnesi bir araç nesnesine benzer şekilde davranır. Rebar denetimi bir veya daha fazla bantları içerebilir ve her bant bir Mandal çubuğu, bir bit eşlem, bir metin etiketi ve alt pencere içerebilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çeşitli yöntemlerle kullanımı gösterilmiştir `CMFCReBar` sınıfı. Örneğin, bir rebar denetimi oluşturma ve bir bant ekleyin gösterilmektedir. Bir iç araç bant görür. Bu kod parçacığını parçası olan [Rebar Test örneği](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RebarTest#1](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_1.h)]  
[!code-cpp[NVC_MFC_RebarTest#2](../../mfc/reference/codesnippet/cpp/cmfcrebar-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CMFCReBar](../../mfc/reference/cmfcrebar-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxRebar.h  
  
##  <a name="addbar"></a>  CMFCReBar::AddBar  
 Bir bandı bir rebar ekler.  
  
```  
BOOL AddBar(
    CWnd* pBar,  
    LPCTSTR pszText = NULL,  
    CBitmap* pbmp = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,  
    COLORREF clrFore,  
    COLORREF clrBack,  
    LPCTSTR pszText = NULL,  
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out] `pBar`  
 Rebar eklenecek alt pencere için bir işaretçi. Başvurulan nesne olmalıdır **WS_CHILD** pencere stili.  
  
 [in] `pszText`  
 Rebar üzerinde görüntülenecek metni belirtir. Metnin alt pencere parçası değil. Bunun yerine, rebar üzerinde görüntülenir.  
  
 [in] [out] `pbmp`  
 Rebar arka planda görüntülenecek bit eşlem belirtir.  
  
 [in] `dwStyle`  
 Bant için uygulanacak stilini içerir. Açıklamasını bant stilleri tam bir listesi için bkz `fStyle` içinde [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) yapısı içinde Windows SDK Belgeleri.  
  
 [in] `clrFore`  
 Rebar ön plan rengini temsil eder.  
  
 [in] `clrBack`  
 Rebar arka plan rengi temsil eder.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` bant rebar başarıyla eklendi Aksi takdirde `FALSE`.  
  
##  <a name="create"></a>  CMFCReBar::Create  
 Rebar denetimi oluşturur ve ona ekler [CMFCReBar](../../mfc/reference/cmfcrebar-class.md) nesnesi.  
  
```  
BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = RBS_BANDBORDERS,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,  
    UINT nID = AFX_IDW_REBAR);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] [out] `pParentWnd`  
 Üst pencere bu rebar denetimi için bir işaretçi.  
  
 [in] `dwCtrlStyle`  
 Rebar denetimiyle stilini belirtir. Varsayılan Stil değer **RBS_BANDBORDERS**, hangi görüntüler rebar denetiminde bitişik bantları ayırmak için satırları daraltın. Geçerli stilleri listesi için bkz: [Rebar denetimi stilleri](http://msdn.microsoft.com/library/windows/desktop/bb774377) Windows SDK belgelerinde.  
  
 [in] `dwStyle`  
 Rebar denetimiyle pencere stili. Geçerli stilleri listesi için bkz: [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles).  
  
 [in] `nID`  
 Rebar ait alt pencere kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` rebar başarıyla oluşturulduysa; Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getrebarctrl"></a>  CMFCReBar::GetReBarCtrl  
 Doğrudan erişim sağlayan `CReBarCtrl` için yaygın bir temel alınan denetim `CMFCReBar` nesneleri.  
  
```  
CReBarCtrl& GetReBarCtrl() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arka plandaki başvuru `CReBarCtrl` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Windows rebar ortak denetim işlevselliği, rebar özelleştirirken yararlanmak için bu yöntemi çağırın.  
  
##  <a name="calcfixedlayout"></a>  CMFCReBar::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `bStretch`  
 [in] `bHorz`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="canfloat"></a>  CMFCReBar::CanFloat  

  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="enabledocking"></a>  CMFCReBar::EnableDocking  

  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `dwDockStyle`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="getrebarbandinfosize"></a>  CMFCReBar::GetReBarBandInfoSize  

  
```  
UINT GetReBarBandInfoSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onshowcontrolbarmenu"></a>  CMFCReBar::OnShowControlBarMenu  

  
```  
virtual BOOL OnShowControlBarMenu(CPoint);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `CPoint`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ontoolhittest"></a>  CMFCReBar::OnToolHitTest  

  
```  
virtual INT_PTR OnToolHitTest(
    CPoint point,  
    TOOLINFO* pTI) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `point`  
 [in] `pTI`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="onupdatecmdui"></a>  CMFCReBar::OnUpdateCmdUI  

  
```  
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,  
    BOOL bDisableIfNoHndler);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pTarget`  
 [in] `bDisableIfNoHndler`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setpanealignment"></a>  CMFCReBar::SetPaneAlignment  

  
```  
virtual void SetPaneAlignment(DWORD dwAlignment);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `dwAlignment`  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CReBarCtrl sınıfı](../../mfc/reference/crebarctrl-class.md)   
 [CPane Sınıfı](../../mfc/reference/cpane-class.md)
