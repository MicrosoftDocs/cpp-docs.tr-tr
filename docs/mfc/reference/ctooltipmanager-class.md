---
title: "CTooltipManager sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager::CreateToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::DeleteToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipParams
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipText
- AFXTOOLTIPMANAGER/CTooltipManager::UpdateTooltips
dev_langs:
- C++
helpviewer_keywords:
- CTooltipManager [MFC], CreateToolTip
- CTooltipManager [MFC], DeleteToolTip
- CTooltipManager [MFC], SetTooltipParams
- CTooltipManager [MFC], SetTooltipText
- CTooltipManager [MFC], UpdateTooltips
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2adb62f107cb50ade529d552ce1735c57f74b171
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ctooltipmanager-class"></a>CTooltipManager sınıfı
Araç ipuçları hakkında çalışma zamanı bilgileri korur. `CTooltipManager` Uygulama başına başlatılan bir kez bir sınıftır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CTooltipManager : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTooltipManager::CreateToolTip](#createtooltip)|Belirtilen Windows Denetim türü için bir araç ipucu denetimi oluşturur.|  
|[CTooltipManager::DeleteToolTip](#deletetooltip)|Bir araç ipucu denetimi siler.|  
|[CTooltipManager::SetTooltipParams](#settooltipparams)|Belirtilen Windows Denetim türü için araç ipucu denetimi görsel görünümünü özelleştirir.|  
|[CTooltipManager::SetTooltipText](#settooltiptext)|Metin ve açıklama araç ipucu denetimi için ayarlar.|  
|[CTooltipManager::UpdateTooltips](#updatetooltips)||  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım [CMFCToolTipCtrl sınıfı](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, ve `CTooltipManager` birlikte, uygulamanızda özelleştirilmiş araç ipuçları uygulamak için. Bu araç ipucu sınıflarını kullanma örneği için bkz: [CMFCToolTipCtrl sınıfı](../../mfc/reference/cmfctooltipctrl-class.md) konu.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtooltipmanager.h  
  
##  <a name="createtooltip"></a>CTooltipManager::CreateToolTip  
 Bir araç ipucu denetimi oluşturur.  
  
```  
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,  
    CWnd* pWndParent,  
    UINT nType);
```  
  
### <a name="parameters"></a>Parametreler  
 [out]`pToolTip`  
 Bir araç ipucu işaretçi başvuru. İşlevi döndüğünde yeni oluşturulan araç ipucunu işaret edecek şekilde ayarlanır.  
  
 [in]`pWndParent`  
 Üst araç ipucu.  
  
 [in]`nType`  
 Araç İpucu türü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Araç İpucu bir sıfır olmayan varsa başarıyla oluşturuldu.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız [CTooltipManager::DeleteToolTip](#deletetooltip) geri geçirilen araç ipucunu denetimini silmek için `pToolTip`.  
  
 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) oluşturduğu her araç ipucu görsel görüntü parametrelerinin üzerinde araç ipucu kümeleri yazın `nType` belirtir. Bir veya daha fazla araç ipucu türleri için parametreleri değiştirmek için çağrı [CTooltipManager::SetTooltipParams](#settooltipparams).  
  
 Geçerli araç ipucu türleri aşağıdaki tabloda listelenmiştir:  
  
|Araç İpucu türü|Denetim kategorisi|Örnek türleri|  
|------------------|----------------------|-------------------|  
|AFX_TOOLTIP_TYPE_BUTTON|Bir düğme.|CMFCButton|  
|AFX_TOOLTIP_TYPE_CAPTIONBAR|Başlık çubuğu.|CMFCCaptionBar|  
|AFX_TOOLTIP_TYPE_DEFAULT|Başka bir kategori sığmayan herhangi bir denetimi.|Yok.|  
|AFX_TOOLTIP_TYPE_DOCKBAR|Dockable bölmesi.|CDockablePane|  
|AFX_TOOLTIP_TYPE_EDIT|Bir metin kutusu.|Yok.|  
|AFX_TOOLTIP_TYPE_MINIFRAME|Bir miniframe.|CPaneFrameWnd|  
|AFX_TOOLTIP_TYPE_PLANNER|Bir Planlayıcısı.|Yok.|  
|AFX_TOOLTIP_TYPE_RIBBON|Şerit çubuk.|CMFCRibbonBar, CMFCRibbonPanelMenuBar|  
|AFX_TOOLTIP_TYPE_TAB|Sekme denetimi.|CMFCTabCtrl|  
|AFX_TOOLTIP_TYPE_TOOLBAR|Araç çubuğu.|CMFCToolBar, CMFCPopupMenuBar|  
|AFX_TOOLTIP_TYPE_TOOLBOX|Bir araç.|Yok.|  
  
##  <a name="deletetooltip"></a>CTooltipManager::DeleteToolTip  
 Bir araç ipucu denetimi siler.  
  
```  
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```  
  
### <a name="parameters"></a>Parametreler  
 [içinde out]`pToolTip`  
 Bir araç ipucu yok edilmesi için bir işaretçi başvuru.  
  
### <a name="remarks"></a>Açıklamalar  
 Her biri için bu yöntemi çağırabilmeniz [CToolTipCtrl sınıfı](../../mfc/reference/ctooltipctrl-class.md) tarafından oluşturulan [CTooltipManager::CreateToolTip](#createtooltip). Üst denetim bu yöntemi çağırmanız gerekir, `OnDestroy` işleyicisi. Bu araç ipucunu çerçevesinden doğru bir şekilde kaldırmak için gereklidir. Bu yöntem ayarlar `pToolTip` için `NULL` önce onu döndürür.  
  
##  <a name="settooltipparams"></a>CTooltipManager::SetTooltipParams  
 Belirtilen Windows Denetim türü için araç ipucu denetiminin görünümünü özelleştirir.  
  
```  
void SetTooltipParams(
    UINT nTypes,  
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),  
    CMFCToolTipInfo* pParams=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`nTypes`  
 Denetim türleri belirtir.  
  
 [in]`pRTC`  
 Çalışma zamanı sınıf özel araç ipucu.  
  
 [in]`pParams`  
 Araç İpucu parametreleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ilk parametrelerini ve çalışma zamanı sınıf ayarlayan [CToolTipManager](../../mfc/reference/ctooltipmanager-class.md) araç ipuçları oluştururken kullanır. Bir denetim çağırdığında [CTooltipManager::CreateToolTip](#createtooltip) ve araç ipucu geçişlerinde türüdür belirttiği türlerinden birini `nTypes`, araç ipucu Yöneticisi belirtilen çalışma zamanı sınıfının bir örneği olan bir araç ipucu denetimi oluşturur tarafından `pRTC` tarafından belirtilen parametreleri ve geçirir `pParams` için yeni araç ipucu.  
  
 Bu yöntemi çağırın, tüm mevcut araç ipucu sahipleri AFX_WM_UPDATETOOLTIPS iletisi ve bunlar kendi araç ipuçlarını kullanarak yeniden oluşturmanız gerekir [CTooltipManager::CreateToolTip](#createtooltip).  
  
 `nTypes`Geçerli araç ipucu herhangi bir bileşimini türleri olabilir [CTooltipManager::CreateToolTip](#createtooltip) kullanır veya AFX_TOOLTIP_TYPE_ALL olabilir. AFX_TOOLTIP_TYPE_ALL geçirirseniz, tüm araç ipucu türleri etkilenir.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağı ortaya `SetTooltipParams` yöntemi `CTooltipManager` sınıfı. Bu kod parçacığını parçası olan [çizin istemci örnek](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#11](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]  
  
##  <a name="settooltiptext"></a>CTooltipManager::SetTooltipText  
 Metin ve araç ipucu açıklamasını ayarlar.  
  
```  
static void SetTooltipText(
    TOOLINFO* pTI,  
    CToolTipCtrl* pToolTip,  
    UINT nType,  
    const CString strText,  
    LPCTSTR lpszDescr=NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in]`pTI`  
 TOOLINFO nesnesine bir işaretçi.  
  
 [içinde out]`pToolTip`  
 Metin ve açıklama ayarlanacağı için araç ipucu denetimi için bir işaretçi.  
  
 [in]`nType`  
 Bu araç ipucu ilişkilendirildiği denetim türünü belirtir.  
  
 [in]`strText`  
 Araç İpucu metni olarak ayarlamak için metin.  
  
 [in]`lpszDescr`  
 Araç İpucu açıklaması için bir işaretçi. Olabilir `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Değeri `nType` aynı değere olmalıdır `nType` parametresinin [CTooltipManager::CreateToolTip](#createtooltip) araç ipucunu oluşturduğunuzda.  
  
##  <a name="updatetooltips"></a>CTooltipManager::UpdateTooltips  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void UpdateTooltips();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CMFCToolTipCtrl sınıfı](../../mfc/reference/cmfctooltipctrl-class.md)   
 [CMFCToolTipInfo Sınıfı](../../mfc/reference/cmfctooltipinfo-class.md)
