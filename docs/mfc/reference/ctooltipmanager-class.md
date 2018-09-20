---
title: CTooltipManager sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae35c6b38bbc5370d0b09341403f38c048bc3ae4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424748"
---
# <a name="ctooltipmanager-class"></a>CTooltipManager sınıfı

İpuçları hakkındaki çalışma zamanı bilgilerini tutar. `CTooltipManager` Sınıfı, uygulama başına örneklenmiş bir kez.

## <a name="syntax"></a>Sözdizimi

```
class CTooltipManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTooltipManager::CreateToolTip](#createtooltip)|Bir araç ipucu denetimi için belirtilen Windows Denetim türlerini oluşturur.|
|[CTooltipManager::DeleteToolTip](#deletetooltip)|Araç İpucu denetimi siler.|
|[CTooltipManager::SetTooltipParams](#settooltipparams)|Araç İpucu denetimi için belirtilen Windows Denetim türlerini öğesinin görsel görünümüne özelleştirir.|
|[CTooltipManager::SetTooltipText](#settooltiptext)|Metin ve açıklama araç ipucu denetimi için ayarlar.|
|[CTooltipManager::UpdateTooltips](#updatetooltips)||

## <a name="remarks"></a>Açıklamalar

Kullanım [CMFCToolTipCtrl sınıfı](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, ve `CTooltipManager` birlikte, uygulamanızda özel araç ipuçları uygulamak için. Bu araç ipucu sınıflarını kullanma örneği için bkz: [CMFCToolTipCtrl sınıfı](../../mfc/reference/cmfctooltipctrl-class.md) konu.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtooltipmanager.h

##  <a name="createtooltip"></a>  CTooltipManager::CreateToolTip

Bir araç ipucu denetimi oluşturur.

```
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,
    CWnd* pWndParent,
    UINT nType);
```

### <a name="parameters"></a>Parametreler

*pToolTip*<br/>
[out] Bir araç ipucu işaretçisi başvurusu. İşlevi döndüğünde, yeni oluşturulan araç ipucu işaret edecek şekilde ayarlanır.

*pWndParent*<br/>
[in] Üst araç ipucu.

*nTür*<br/>
[in] Araç İpucu türü.

### <a name="return-value"></a>Dönüş Değeri

Araç İpucu bir gösterimiyse başarıyla oluşturuldu.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız [CTooltipManager::DeleteToolTip](#deletetooltip) geri geçirilen araç ipucu denetimi silmek *pToolTip*.

[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) kümeleri oluşturduğu her araç ipucu görselle parametrelerini araç ipucu türü *nTür* belirtir. Bir veya daha fazla araç ipucu türleri için parametreleri değiştirmek için çağrı [CTooltipManager::SetTooltipParams](#settooltipparams).

Geçerli bir araç ipucu türleri aşağıdaki tabloda listelenmiştir:

|Araç İpucu türü|Denetim kategorisi|Örnek türleri|
|------------------|----------------------|-------------------|
|AFX_TOOLTIP_TYPE_BUTTON|Bir düğme.|CMFCButton|
|AFX_TOOLTIP_TYPE_CAPTIONBAR|Bir başlık çubuğudur.|CMFCCaptionBar|
|AFX_TOOLTIP_TYPE_DEFAULT|Başka bir kategoriye uymayan herhangi bir denetimi.|Yok.|
|AFX_TOOLTIP_TYPE_DOCKBAR|Yerleştirilebilir bir bölme.|CDockablePane|
|AFX_TOOLTIP_TYPE_EDIT|Metin kutusu.|Yok.|
|AFX_TOOLTIP_TYPE_MINIFRAME|Bir miniframe.|CPaneFrameWnd|
|AFX_TOOLTIP_TYPE_PLANNER|Bir planner.|Yok.|
|AFX_TOOLTIP_TYPE_RIBBON|Bir Şerit çubuğu.|CMFCRibbonBar, CMFCRibbonPanelMenuBar|
|AFX_TOOLTIP_TYPE_TAB|Sekme denetimi.|CMFCTabCtrl|
|AFX_TOOLTIP_TYPE_TOOLBAR|Araç çubuğu.|CMFCToolBar, CMFCPopupMenuBar|
|AFX_TOOLTIP_TYPE_TOOLBOX|Bir araç.|Yok.|

##  <a name="deletetooltip"></a>  CTooltipManager::DeleteToolTip

Araç İpucu denetimi siler.

```
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```

### <a name="parameters"></a>Parametreler

*pToolTip*<br/>
[out içinde] Yok edilecek bir araç ipucu için bir işaretçi başvuru.

### <a name="remarks"></a>Açıklamalar

Her biri için bu yöntemi çağıran [CToolTipCtrl sınıfı](../../mfc/reference/ctooltipctrl-class.md) tarafından oluşturulan [CTooltipManager::CreateToolTip](#createtooltip). Üst denetimin bu yöntemi çağırmanız gerekir, `OnDestroy` işleyici. Bu, doğru framework araç ipucu kaldırmak için gereklidir. Bu yöntem ayarlar *pToolTip* döndürülmeden önce null.

##  <a name="settooltipparams"></a>  CTooltipManager::SetTooltipParams

Belirtilen Windows Denetim tipleri için araç ipucu denetiminin görünümünü özelleştirir.

```
void SetTooltipParams(
    UINT nTypes,
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),
    CMFCToolTipInfo* pParams=NULL);
```

### <a name="parameters"></a>Parametreler

*nTypes*<br/>
[in] Denetim türlerini belirtir.

*pRTC*<br/>
[in] Çalışma zamanı sınıfının özel araç ipucu.

*pParams*<br/>
[in] Araç İpucu parametreleri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem ilk parametrelerini ve çalışma zamanı sınıfı, ayarlar [CToolTipManager](../../mfc/reference/ctooltipmanager-class.md) araç ipuçları oluşturduğunda kullanır. Bir denetim çağırdığında [CTooltipManager::CreateToolTip](#createtooltip) ve bir araç ipucu geçişlerinde tür tarafından belirtilen türlerden birinde *nTypes*, araç ipucu manager örneği olan bir araç ipucu denetimi oluşturur tarafından belirtilen çalışma zamanı sınıf *pRTC* tarafından belirtilen parametreleri ve geçirir *pParams* için yeni bir araç ipucu.

Bu yöntemi çağıran, tüm mevcut araç ipucu sahipleri AFX_WM_UPDATETOOLTIPS iletisi ve bunlar kendi araç ipuçlarını kullanarak yeniden oluşturmanız gerekir [CTooltipManager::CreateToolTip](#createtooltip).

*nTypes* geçerli araç ipucu herhangi bir birleşimini türleri olabilir [CTooltipManager::CreateToolTip](#createtooltip) kullanır veya AFX_TOOLTIP_TYPE_ALL olabilir. AFX_TOOLTIP_TYPE_ALL geçirirseniz, araç ipucu türlü etkilenir.

### <a name="example"></a>Örnek

Aşağıdaki örnek nasıl kullanılacağını gösterir `SetTooltipParams` yöntemi `CTooltipManager` sınıfı. Bu kod parçacığı parçasıdır [çizmek istemci örneği](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_DrawClient#11](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]

##  <a name="settooltiptext"></a>  CTooltipManager::SetTooltipText

Metin ve bir araç ipucu için bir açıklama belirler.

```
static void SetTooltipText(
    TOOLINFO* pTI,
    CToolTipCtrl* pToolTip,
    UINT nType,
    const CString strText,
    LPCTSTR lpszDescr=NULL);
```

### <a name="parameters"></a>Parametreler

*PTI*<br/>
[in] TOOLINFO nesnesine bir işaretçi.

*pToolTip*<br/>
[out içinde] Metin ve açıklama ayarlamak istediğiniz araç ipucu denetimi için bir işaretçi.

*nTür*<br/>
[in] Bu araç ipucu ilişkilendirildiği denetim türünü belirtir.

*strText*<br/>
[in] Araç İpucu metin olarak ayarlamak için metin.

*lpszDescr*<br/>
[in] Araç İpucu açıklaması için bir işaretçi. NULL olabilir.

### <a name="remarks"></a>Açıklamalar

Değerini *nTür* aynı değere sahip olmalıdır *nTür* parametresinin [CTooltipManager::CreateToolTip](#createtooltip) oluşturduğunuzda araç ipucu.

##  <a name="updatetooltips"></a>  CTooltipManager::UpdateTooltips

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.

```
void UpdateTooltips();
```

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolTipCtrl Sınıfı](../../mfc/reference/cmfctooltipctrl-class.md)<br/>
[CMFCToolTipInfo Sınıfı](../../mfc/reference/cmfctooltipinfo-class.md)
