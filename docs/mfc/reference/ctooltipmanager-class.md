---
title: CTooltipManager Sınıfı
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
ms.openlocfilehash: 37fcf47b7537e89974a61e6c50c41e164d555678
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365082"
---
# <a name="ctooltipmanager-class"></a>CTooltipManager Sınıfı

Araç ipuçları hakkında çalışma zamanı bilgilerini saklar. Sınıf `CTooltipManager` uygulama başına bir kez anında verilir.

## <a name="syntax"></a>Sözdizimi

```
class CTooltipManager : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CTooltipManager::CreateToolTip](#createtooltip)|Belirtilen Windows denetim türü(ler) için bir araç ipucu denetimi oluşturur.|
|[CTooltipManager::DeleteToolTip](#deletetooltip)|Araç ipucu denetimini siler.|
|[CTooltipManager::SetTooltipParams](#settooltipparams)|Belirtilen Windows denetim türü(ler) için araç ipucu denetiminin görsel görünümünü özelleştirir.|
|[CTooltipManager::SetTooltipText](#settooltiptext)|Araç ipucu denetimi için metni ve açıklamayı ayarlar.|
|[CTooltipManager::UpdateTooltips](#updatetooltips)||

## <a name="remarks"></a>Açıklamalar

[CMFCToolTipCtrl Class'ı](../../mfc/reference/cmfctooltipctrl-class.md) `CMFCToolTipInfo` `CTooltipManager` ve uygulamanızda özelleştirilmiş araç ipuçlarını birlikte kullanın. Bu araç ipucu sınıflarının nasıl kullanılacağına bir örnek olarak [CMFCToolTipCtrl Sınıfı](../../mfc/reference/cmfctooltipctrl-class.md) konusuna bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ctooltipmanager](../../mfc/reference/ctooltipmanager-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtooltipmanager.h

## <a name="ctooltipmanagercreatetooltip"></a><a name="createtooltip"></a>CTooltipManager::CreateToolTip

Bir araç ucu denetimi oluşturur.

```
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,
    CWnd* pWndParent,
    UINT nType);
```

### <a name="parameters"></a>Parametreler

*pToolTip*<br/>
[çıkış] Araç ipucu işaretçisine başvuru. İşlev döndüğünde yeni oluşturulan araç ucunu işaret etmek üzere ayarlanır.

*pWndParent*<br/>
[içinde] Araç ucunun üst öğesi.

*nTipi*<br/>
[içinde] Araç ucunun türü.

### <a name="return-value"></a>Dönüş Değeri

Bir araç ipucu başarıyla oluşturulduysa sıfırsız.

### <a name="remarks"></a>Açıklamalar

PToolTip'te geri geçirilen araç ipucu denetimini silmek için [CTooltipManager::DeleteToolTip'i](#deletetooltip) aramalısınız. *pToolTip*

[CTooltipManager,](../../mfc/reference/ctooltipmanager-class.md) oluşturduğu her araç ucunun görsel ekran parametrelerini *nType'ın* belirttiği araç ucu türüne göre ayarlar. Bir veya daha fazla araç ipucu türü için parametreleri değiştirmek için [CTooltipManager'ı arayın::SetTooltipParams.](#settooltipparams)

Geçerli araç ipucu türleri aşağıdaki tabloda listelenir:

|Araç ucu türü|Kontrol kategorisi|Örnek türleri|
|------------------|----------------------|-------------------|
|AFX_TOOLTIP_TYPE_BUTTON|Bir düğme.|CMFCDüğmesi|
|AFX_TOOLTIP_TYPE_CAPTIONBAR|Resim yazısı çubuğu.|CMFCCaptionBar|
|AFX_TOOLTIP_TYPE_DEFAULT|Başka bir kategoriye uymayan herhangi bir denetim.|Yok.|
|AFX_TOOLTIP_TYPE_DOCKBAR|Sabitlenebilir bir bölme.|Cdockablepane|
|AFX_TOOLTIP_TYPE_EDIT|Bir metin kutusu.|Yok.|
|AFX_TOOLTIP_TYPE_MINIFRAME|Bir mini çerçeve.|Cpaneframewnd|
|AFX_TOOLTIP_TYPE_PLANNER|Bir planlayıcı.|Yok.|
|AFX_TOOLTIP_TYPE_RIBBON|Kurdele çubuğu.|CMFCRibbonBar, CMFCRibbonPanelMenuBar|
|AFX_TOOLTIP_TYPE_TAB|Bir sekme denetimi.|CMFCTabCtrl|
|AFX_TOOLTIP_TYPE_TOOLBAR|Araç çubuğu.|CMFCToolBar, CMFCPopupMenuBar|
|AFX_TOOLTIP_TYPE_TOOLBOX|Bir alet çantası.|Yok.|

## <a name="ctooltipmanagerdeletetooltip"></a><a name="deletetooltip"></a>CTooltipManager::DeleteToolTip

Araç ipucu denetimini siler.

```
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```

### <a name="parameters"></a>Parametreler

*pToolTip*<br/>
[içinde, dışarı] Yok edilecek bir araç ucu için işaretçiye başvuru.

### <a name="remarks"></a>Açıklamalar

CToolTipManager tarafından oluşturulan her [CToolTipCtrl Sınıfı](../../mfc/reference/ctooltipctrl-class.md) için bu yöntemi [arayın::CreateToolTip](#createtooltip). Üst denetim `OnDestroy` işleyicisi bu yöntemi aramalıdır. Bu, araç ucunu çerçeveden doğru bir şekilde kaldırmak için gereklidir. Bu yöntem, *pToolTip'i* dönmeden önce NULL olarak ayarlar.

## <a name="ctooltipmanagersettooltipparams"></a><a name="settooltipparams"></a>CTooltipManager::SetTooltipParams

Belirtilen Windows denetim türleri için araç ipucu denetiminin görünümünü özelleştirir.

```
void SetTooltipParams(
    UINT nTypes,
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),
    CMFCToolTipInfo* pParams=NULL);
```

### <a name="parameters"></a>Parametreler

*nTypes*<br/>
[içinde] Denetim türlerini belirtir.

*pRTC*<br/>
[içinde] Özel araç ucunun çalışma zamanı sınıfı.

*pParams*<br/>
[içinde] Araç ipucu parametreleri.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [CToolTipManager'ın](../../mfc/reference/ctooltipmanager-class.md) araç ipuçları oluştururken kullandığı çalışma zamanı sınıfını ve ilk parametreleri ayarlar. Bir denetim [CTooltipManager::CreateToolTip'i](#createtooltip) aradığında ve *nTypes*tarafından belirtilen türlerden biri olan bir araç ucu türünden geçtiğinde, araç ucu yöneticisi *pRTC* tarafından belirtilen çalışma zamanı sınıfının bir örneği olan bir araç ipucu denetimi oluşturur ve *pParam'lar* tarafından belirtilen parametreleri yeni araç ucuna geçirir.

Bu yöntemi aradiğinizde, varolan tüm araç ucu sahipleri AFX_WM_UPDATETOOLTIPS iletisini alır ve [CTooltipManager::CreateToolTip](#createtooltip)kullanarak araç uçlarını yeniden oluşturmaları gerekir.

*nTypes,* [CTooltipManager::CreateToolTip'in](#createtooltip) kullandığı geçerli araç ipucu türlerinin herhangi bir birleşimi olabilir veya AFX_TOOLTIP_TYPE_ALL edilebilir. AFX_TOOLTIP_TYPE_ALL geçerseniz, tüm araç ucu türleri etkilenir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın yönteminin `SetTooltipParams` nasıl `CTooltipManager` kullanılacağını göstermektedir. Bu kod snippet [Çekme İstemci örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_DrawClient#11](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]

## <a name="ctooltipmanagersettooltiptext"></a><a name="settooltiptext"></a>CTooltipManager::SetTooltipText

Bir araç ipucu için metni ve açıklamayı ayarlar.

```
static void SetTooltipText(
    TOOLINFO* pTI,
    CToolTipCtrl* pToolTip,
    UINT nType,
    const CString strText,
    LPCTSTR lpszDescr=NULL);
```

### <a name="parameters"></a>Parametreler

*Ptı*<br/>
[içinde] TOOLINFO nesnesine işaretçi.

*pToolTip*<br/>
[içinde, dışarı] Metni ve açıklamayı ayarlamak için araç ipucu denetimine işaretçi.

*nTipi*<br/>
[içinde] Bu araç ucunun ilişkili olduğu denetim türünü belirtir.

*strText*<br/>
[içinde] Araç ipucu metni olarak ayarlanan metin.

*lpszDescr*<br/>
[içinde] Araç ipucu açıklamasıiçin bir işaretçi. NULL olabilir.

### <a name="remarks"></a>Açıklamalar

*nType* değeri, araç ipucunu oluştururken [CTooltipManager::CreateToolTip'in](#createtooltip) *nType* parametresi ile aynı değerde olmalıdır.

## <a name="ctooltipmanagerupdatetooltips"></a><a name="updatetooltips"></a>CTooltipManager::UpdateTooltips

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
void UpdateTooltips();
```

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolTipCtrl Sınıfı](../../mfc/reference/cmfctooltipctrl-class.md)<br/>
[CMFCToolTipInfo Sınıfı](../../mfc/reference/cmfctooltipinfo-class.md)
