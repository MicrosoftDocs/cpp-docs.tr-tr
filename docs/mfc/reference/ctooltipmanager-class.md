---
description: 'Daha fazla bilgi edinin: CTooltipManager sınıfı'
title: CTooltipManager sınıfı
ms.date: 11/04/2016
f1_keywords:
- CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager::CreateToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::DeleteToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipParams
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipText
- AFXTOOLTIPMANAGER/CTooltipManager::UpdateTooltips
helpviewer_keywords:
- CTooltipManager [MFC], CreateToolTip
- CTooltipManager [MFC], DeleteToolTip
- CTooltipManager [MFC], SetTooltipParams
- CTooltipManager [MFC], SetTooltipText
- CTooltipManager [MFC], UpdateTooltips
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
ms.openlocfilehash: 0ec6d691abbceb7026fe9656c17ff899f1d07759
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318552"
---
# <a name="ctooltipmanager-class"></a>CTooltipManager sınıfı

Araç ipuçları hakkında çalışma zamanı bilgilerini korur. `CTooltipManager`Sınıf, uygulama başına bir kez oluşturulur.

## <a name="syntax"></a>Syntax

```
class CTooltipManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTooltipManager:: CreateToolTip](#createtooltip)|Belirtilen Windows Denetim türleri için bir araç ipucu denetimi oluşturur.|
|[CTooltipManager::D eleteToolTip](#deletetooltip)|Bir araç ipucu denetimini siler.|
|[CTooltipManager:: SetTooltipParams](#settooltipparams)|Belirtilen Windows Denetim türleri için araç ipucu denetiminin görsel görünümünü özelleştirir.|
|[CTooltipManager:: SetTooltipText](#settooltiptext)|Araç ipucu denetimi için metin ve açıklama ayarlar.|
|[CTooltipManager:: UpdateToolTip 'ler](#updatetooltips)||

## <a name="remarks"></a>Açıklamalar

Uygulamanızdaki özelleştirilmiş araç ipuçlarını uygulamak için [CMFCToolTipCtrl sınıfı](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo` ve `CTooltipManager` birlikte kullanın. Bu araç ipucu sınıflarının nasıl kullanılacağına ilişkin bir örnek için, bkz. [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md) konusu.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtooltipmanager. h

## <a name="ctooltipmanagercreatetooltip"></a><a name="createtooltip"></a> CTooltipManager:: CreateToolTip

Araç ipucu denetimi oluşturur.

```
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,
    CWnd* pWndParent,
    UINT nType);
```

### <a name="parameters"></a>Parametreler

*pToolTip*<br/>
dışı Bir araç ipucu işaretçisine başvuru. İşlevin döndürdüğü yeni oluşturulan araç ipucunu işaret etmek üzere ayarlanır.

*pWndParent*<br/>
'ndaki Araç ipucunun üst öğesi.

*nTür*<br/>
'ndaki Araç ipucunun türü.

### <a name="return-value"></a>Dönüş Değeri

Bir araç ipucu başarıyla oluşturulmuşsa sıfır dışı.

### <a name="remarks"></a>Açıklamalar

*PToolTip*'e geri geçirilen araç ipucu denetimini silmek Için [CTooltipManager::D eletetooltip](#deletetooltip) ' i çağırmanız gerekir.

[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) , *nType* tarafından belirlenen araç ipucu türüne göre oluşturduğu her araç ipucunun görsel görüntüleme parametrelerini ayarlar. Bir veya daha fazla araç ipucu türünün parametrelerini değiştirmek için [CTooltipManager:: SetTooltipParams](#settooltipparams)' ı çağırın.

Geçerli araç ipucu türleri aşağıdaki tabloda listelenmiştir:

|Araç ipucu türü|Denetim kategorisi|Örnek türler|
|------------------|----------------------|-------------------|
|AFX_TOOLTIP_TYPE_BUTTON|Düğme.|CMFCButton|
|AFX_TOOLTIP_TYPE_CAPTIONBAR|Başlık çubuğu.|CMFCCaptionBar|
|AFX_TOOLTIP_TYPE_DEFAULT|Başka bir kategoriye uymayan herhangi bir denetim.|Yok.|
|AFX_TOOLTIP_TYPE_DOCKBAR|Bir yerleştirilebilir bölmesi.|CDockablePane|
|AFX_TOOLTIP_TYPE_EDIT|Metin kutusu.|Yok.|
|AFX_TOOLTIP_TYPE_MINIFRAME|Mini iframe.|Cbölmesi Framewnd|
|AFX_TOOLTIP_TYPE_PLANNER|Bir Planner.|Yok.|
|AFX_TOOLTIP_TYPE_RIBBON|Şerit çubuğu.|CMFCRibbonBar, CMFCRibbonPanelMenuBar|
|AFX_TOOLTIP_TYPE_TAB|Sekme denetimi.|CMFCTabCtrl|
|AFX_TOOLTIP_TYPE_TOOLBAR|Bir araç çubuğu.|CMFCToolBar, CMFCPopupMenuBar|
|AFX_TOOLTIP_TYPE_TOOLBOX|Bir araç kutusu.|Yok.|

## <a name="ctooltipmanagerdeletetooltip"></a><a name="deletetooltip"></a> CTooltipManager::D eleteToolTip

Bir araç ipucu denetimini siler.

```
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```

### <a name="parameters"></a>Parametreler

*pToolTip*<br/>
[in, out] Bir araç ipucunun yok edileceği işaretçiye yönelik bir başvuru.

### <a name="remarks"></a>Açıklamalar

[CTooltipManager:: CreateToolTip](#createtooltip)tarafından oluşturulan her [CToolTipCtrl sınıfı](../../mfc/reference/ctooltipctrl-class.md) için bu yöntemi çağırın. Üst denetim işleyiciden bu yöntemi çağırmalıdır `OnDestroy` . Araç ipucunu çerçeveden doğru bir şekilde kaldırmak için bu gereklidir. Bu yöntem, *pToolTip* 'i döndürülmadan önce null olarak ayarlar.

## <a name="ctooltipmanagersettooltipparams"></a><a name="settooltipparams"></a> CTooltipManager:: SetTooltipParams

Belirtilen Windows Denetim türleri için araç ipucu denetiminin görünümünü özelleştirir.

```cpp
void SetTooltipParams(
    UINT nTypes,
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),
    CMFCToolTipInfo* pParams=NULL);
```

### <a name="parameters"></a>Parametreler

*Ntürler*<br/>
'ndaki Denetim türlerini belirtir.

*pRTC*<br/>
'ndaki Özel araç ipucunun çalışma zamanı sınıfı.

*pParams*<br/>
'ndaki Araç ipucu parametreleri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, çalışma zamanı sınıfını ve [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) 'ın araç ipuçları oluşturduğunda kullandığı başlangıç parametrelerini ayarlar. Bir denetim [CTooltipManager:: CreateToolTip](#createtooltip) çağırdığında ve *nTypes* tarafından belirtilen türlerden biri olan bir araç ipucu türünde geçtiğinde, ToolTip Manager, *pRTC* tarafından belirtilen çalışma zamanı sınıfının bir örneği olan bir araç ipucu denetimi oluşturur ve *pParams* tarafından belirtilen parametreleri yeni araç ipucuna geçirir.

Bu yöntemi çağırdığınızda, mevcut tüm araç ipucu sahipleri AFX_WM_UPDATETOOLTIPS iletisini alır ve [CTooltipManager:: CreateToolTip](#createtooltip)kullanarak araç ipuçlarını yeniden oluşturmaları gerekir.

*nTypes* , [CTooltipManager:: CreateToolTip](#createtooltip) 'in kullandığı geçerli araç ipucu türlerinin herhangi bir birleşimi olabilir veya AFX_TOOLTIP_TYPE_ALL olabilir. AFX_TOOLTIP_TYPE_ALL geçirirseniz, tüm araç ipucu türleri etkilenir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının yönteminin nasıl kullanılacağını gösterir `SetTooltipParams` `CTooltipManager` . Bu kod parçacığı, [Çizim istemci örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_DrawClient#11](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]

## <a name="ctooltipmanagersettooltiptext"></a><a name="settooltiptext"></a> CTooltipManager:: SetTooltipText

Araç ipucu için metin ve açıklama ayarlar.

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
'ndaki TOOLıNFO nesnesine yönelik bir işaretçi.

*pToolTip*<br/>
[in, out] Metin ve açıklama ayarlanacak araç ipucu denetimine yönelik bir işaretçi.

*nTür*<br/>
'ndaki Bu ToolTip 'in ilişkilendirildiği denetimin türünü belirtir.

*strText*<br/>
'ndaki Araç ipucu metni olarak ayarlanacak metin.

*lpszDescr*<br/>
'ndaki Araç ipucu açıklamasına yönelik bir işaretçi. NULL olabilir.

### <a name="remarks"></a>Açıklamalar

Araç ipucunu oluştururken *nType* değeri [CTooltipManager:: CreateToolTip](#createtooltip) parametresinin *nType* parametresiyle aynı değer olmalıdır.

## <a name="ctooltipmanagerupdatetooltips"></a><a name="updatetooltips"></a> CTooltipManager:: UpdateToolTip 'ler

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```cpp
void UpdateTooltips();
```

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolTipCtrl sınıfı](../../mfc/reference/cmfctooltipctrl-class.md)<br/>
[CMFCToolTipInfo sınıfı](../../mfc/reference/cmfctooltipinfo-class.md)
