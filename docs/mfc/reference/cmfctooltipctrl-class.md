---
title: CMFCToolTipCtrl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetIconSize
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetParams
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawBorder
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawLabel
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnFillBackground
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetFixedWidth
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetHotRibbonButton
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetLocation
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetParams
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolTipCtrl [MFC], GetIconSize
- CMFCToolTipCtrl [MFC], GetParams
- CMFCToolTipCtrl [MFC], OnDrawBorder
- CMFCToolTipCtrl [MFC], OnDrawDescription
- CMFCToolTipCtrl [MFC], OnDrawIcon
- CMFCToolTipCtrl [MFC], OnDrawLabel
- CMFCToolTipCtrl [MFC], OnDrawSeparator
- CMFCToolTipCtrl [MFC], OnFillBackground
- CMFCToolTipCtrl [MFC], SetDescription
- CMFCToolTipCtrl [MFC], SetFixedWidth
- CMFCToolTipCtrl [MFC], SetHotRibbonButton
- CMFCToolTipCtrl [MFC], SetLocation
- CMFCToolTipCtrl [MFC], SetParams
ms.assetid: 9fbfcfb1-a8ab-417f-ae29-9a9ca85ee58f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 09a701498b47957f64558fe42408ff64351c238b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cmfctooltipctrl-class"></a>CMFCToolTipCtrl sınıfı
Genişletilmiş araç ipucu uygulaması temel alarak [CToolTipCtrl sınıfı](../../mfc/reference/ctooltipctrl-class.md). Bir araç ipucu temel alarak `CMFCToolTipCtrl` sınıfı bir simge, bir etiket ve açıklama görüntüleyebilirsiniz. Gradyan Dolgu, özel metin ve renkler, kalın metin, yuvarlatılmış köşeleri veya balon stil kullanarak görünümünü özelleştirebilirsiniz.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCToolTipCtrl : public CToolTipCtrl  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`CMFCToolTipCtrl::CMFCToolTipCtrl`|Varsayılan Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMFCToolTipCtrl::GetIconSize](#geticonsize)|Bir simge boyutu bir araç ipucunda döndürür.|  
|[CMFCToolTipCtrl::GetParams](#getparams)|Araç İpucu görüntü ayarlarını döndürür.|  
|[CMFCToolTipCtrl::OnDrawBorder](#ondrawborder)|Bir araç ipucu kenarlık çizer.|  
|[CMFCToolTipCtrl::OnDrawDescription](#ondrawdescription)||  
|[CMFCToolTipCtrl::OnDrawIcon](#ondrawicon)|Simge bir araç ipucunda görüntüler.|  
|[CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel)|Bir araç ipucu etiketini çizer veya etiketin boyutunu hesaplar.|  
|[CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator)|Etiket ve araç ipucu açıklamasında arasında ayırıcı çizer.|  
|[CMFCToolTipCtrl::OnFillBackground](#onfillbackground)|Araç İpucu arka plan doldurur.|  
|[CMFCToolTipCtrl::SetDescription](#setdescription)|Araç İpucu gösterilecek açıklama ayarlar.|  
|[CMFCToolTipCtrl::SetFixedWidth](#setfixedwidth)||  
|[CMFCToolTipCtrl::SetHotRibbonButton](#sethotribbonbutton)||  
|[CMFCToolTipCtrl::SetLocation](#setlocation)||  
|[CMFCToolTipCtrl::SetParams](#setparams)|Bir araç ipucu görsel görünümünü kullanarak belirtir bir `CMFCToolTipInfo` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `CMFCToolTipCtrl`, `CMFCToolTipInfo`, ve [CTooltipManager sınıfı](../../mfc/reference/ctooltipmanager-class.md) birlikte, uygulamanızda özelleştirilmiş araç ipuçları uygulamak için nesneleri.  
  
 Örneğin, balon stili araç ipuçları kullanmak için şu adımları izleyin:  
  
 1. Kullanım [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md) uygulamanızda araç ipucu Yöneticisi'ni başlatmak için yöntem.  
  
 2. Oluşturma bir `CMFCToolTipInfo` istediğiniz görsel stilini belirlemek için yapısı:  
  
```  
CMFCToolTipInfo params;  
    params.m_bBoldLabel = FALSE;  
    params.m_bDrawDescription = FALSE;  
    params.m_bDrawIcon = FALSE;  
    params.m_bRoundedCorners = TRUE;  
    params.m_bDrawSeparator = FALSE;  
    if (m_bCustomColors)  
 {  
    params.m_clrFill = RGB (255,
    255,
    255);

    params.m_clrFillGradient = RGB (228,
    228,
    240);

    params.m_clrText = RGB (61,
    83,
    80);

    params.m_clrBorder = RGB (144,
    149,
    168);

 }  
```  
3. Kullanım [CTooltipManager::SetTooltipParams](../../mfc/reference/ctooltipmanager-class.md#settooltipparams) tanımlanan stiller kullanarak tüm araç ipuçları için görsel stil uygulamada ayarlamak için yöntemin `CMFCToolTipInfo` nesnesi:  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMFCToolTipCtrl), &params);
```  
Ayrıca yeni bir sınıftan türetilemeyeceğini `CMFCToolTipCtrl` araç ipucu davranışını denetlemeye ve işleme. Yeni bir araç ipucu denetimi sınıf belirtmek için kullanın `CTooltipManager::SetTooltipParams` yöntemi:  
  
```  
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMyToolTipCtrl))  
```  
Varsayılan geri yüklemek için araç ipucu kontrol sınıfı ve araç ipucu görünümünü varsayılan durumuna getirmek sıfırlama çalışma zamanı sınıf ve araç ipucu bilgisi parametrelerinde NULL belirtin `SetTooltipParams`:  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    NULL,
    NULL);
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulacağını gösteren bir `CMFCToolTipCtrl` nesnesi, araç ipucu görüntüler açıklama ve araç ipucu denetimi genişliğini ayarlayın.  
  
 [!code-cpp[NVC_MFC_RibbonApp#41](../../mfc/reference/codesnippet/cpp/cmfctooltipctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)  
  
 [CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtooltipctrl.h  
  
##  <a name="cmfctooltipctrl"></a>  CMFCToolTipCtrl::CMFCToolTipCtrl  

  
```  
CMFCToolTipCtrl(CMFCToolTipInfo* pParams = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pParams`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="geticonsize"></a>  CMFCToolTipCtrl::GetIconSize  
 Bir simge boyutu bir araç ipucunda döndürür.  
  
```  
virtual CSize GetIconSize();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Simge piksel cinsinden büyüklüğü.  
  
##  <a name="getparams"></a>  CMFCToolTipCtrl::GetParams  
 Araç İpucu görüntü ayarlarını döndürür.  
  
```  
const CMFCToolTipInfo& GetParams() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İçinde depolanan geçerli araç ipucu görüntü ayarlarını bir [CMFCToolTipInfo sınıfı](../../mfc/reference/cmfctooltipinfo-class.md) nesnesi.  
  
##  <a name="ondrawborder"></a>  CMFCToolTipCtrl::OnDrawBorder  
 Bir araç ipucu kenarlık çizer.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect rect,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>Parametreler  
 `[in] pDC`  
 Bir cihaz bağlamı işaretçi.  
  
 `[in] rect`  
 Sınırlayıcı dikdörtgenini araç ipucu.  
  
 `[in] clrLine`  
 Kenarlık rengi.  
  
### <a name="remarks"></a>Açıklamalar  
 Araç İpucu kenarlık görünümünü özelleştirmek için bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="ondrawdescription"></a>  CMFCToolTipCtrl::OnDrawDescription  

  
```  
virtual CSize OnDrawDescription(
    CDC* pDC,  
    CRect rect,  
    BOOL bCalcOnly);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 [in] `rect`  
 [in] `bCalcOnly`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondrawicon"></a>  CMFCToolTipCtrl::OnDrawIcon  
 Simge bir araç ipucunda görüntüler.  
  
```  
virtual BOOL OnDrawIcon(
    CDC* pDC,  
    CRect rectImage);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `rectImage`  
 Simge koordinatları.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `TRUE` simge çizilmiş durumunda. Aksi takdirde `FALSE`.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel bir simge görüntülemek için bir türetilmiş sınıfta bu yöntemi geçersiz kılın. Ayrıca geçersiz kılmanız gerekir [CMFCToolTipCtrl::GetIconSize](#geticonsize) metin ve açıklama düzenini doğru hesaplamak araç ipucu etkinleştirmek için.  
  
##  <a name="ondrawlabel"></a>  CMFCToolTipCtrl::OnDrawLabel  
 Bir araç ipucu etiketini çizer veya etiketin boyutunu hesaplar.  
  
```  
virtual CSize OnDrawLabel(
    CDC* pDC,  
    CRect rect,  
    BOOL bCalcOnly);
```  
  
### <a name="parameters"></a>Parametreler  
 `[in] pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 `[in] rect`  
 Etiket alanı sınırlayıcı dikdörtgenini.  
  
 `[in] bCalcOnly`  
 Varsa `TRUE`, etiket değil çizileceğini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Etiketin piksel cinsinden boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Araç İpucu etiket görünümünü özelleştirmek istiyorsanız bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="ondrawseparator"></a>  CMFCToolTipCtrl::OnDrawSeparator  
 Etiket ve araç ipucu açıklamasında arasında ayırıcı çizer.  
  
```  
virtual void OnDrawSeparator(
    CDC* pDC,  
    int x1,  
    int x2,  
    int y);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 [in] `x1`  
 Ayırıcının solundaki yatay koordinatı.  
  
 [in] `x2`  
 Ayırıcı sağ ucunu yatay koordinatı.  
  
 [in] `Y`  
 Ayırıcı dikey koordinatı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama noktasından bir çizgi çizer (x1, y) noktasına (x2, y).  
  
 Ayırıcı görünümünü özelleştirmek için bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="onfillbackground"></a>  CMFCToolTipCtrl::OnFillBackground  
 Araç İpucu arka plan doldurur.  
  
```  
virtual void OnFillBackground(
    CDC* pDC,  
    CRect rect,  
    COLORREF& clrText,  
    COLORREF& clrLine);
```  
  
### <a name="parameters"></a>Parametreler  
 `[in] pDC`  
 Bir cihaz bağlamı için bir işaretçi.  
  
 `[in] rect`  
 Doldurmak için alan sınırlayıcı dikdörtgenini belirtir.  
  
 `[in] clrText`  
 Araç İpucu ön plan rengi.  
  
 `[in] clrLine`  
 Kenarlıklar ve etiket ve açıklama arasında sınırlayıcı çizgi rengi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama tarafından belirtilen dikdörtgen doldurur `rect` renk veya en son çağrı tarafından belirtilen desenle [CMFCToolTipCtrl::SetParams](#setparams).  
  
 Araç İpucu görünümünü özelleştirmek istiyorsanız bir türetilmiş sınıfta bu yöntemi geçersiz kılın.  
  
##  <a name="setdescription"></a>  CMFCToolTipCtrl::SetDescription  
 Araç İpucu gösterilecek açıklama ayarlar.  
  
```  
virtual void SetDescription(const CString strDesrciption);
```  
  
### <a name="parameters"></a>Parametreler  
 `[in] strDesrciption`  
 Açıklama metni.  
  
### <a name="remarks"></a>Açıklamalar  
 Açıklama metnini araç ipucu ayırıcı altında görüntülenir.  
  
##  <a name="setfixedwidth"></a>  CMFCToolTipCtrl::SetFixedWidth  

  
```  
void SetFixedWidth(
    int nWidthRegular,  
    int nWidthLargeImage);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `nWidthRegular`  
 [in] `nWidthLargeImage`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="sethotribbonbutton"></a>  CMFCToolTipCtrl::SetHotRibbonButton  

  
```  
void SetHotRibbonButton(CMFCRibbonButton* pRibbonButton);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pRibbonButton`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setlocation"></a>  CMFCToolTipCtrl::SetLocation  

  
```  
void SetLocation(CPoint pt);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `pt`  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setparams"></a>  CMFCToolTipCtrl::SetParams  
 Bir araç ipucu görsel görünümünü kullanarak belirtir bir [CMFCToolTipInfo sınıfı](../../mfc/reference/cmfctooltipinfo-class.md) nesnesi.  
  
```  
void SetParams(CMFCToolTipInfo* pParams);
```  
  
### <a name="parameters"></a>Parametreler  
 `[in] pParams`  
 İşaretçi bir [CMFCToolTipInfo sınıfı](../../mfc/reference/cmfctooltipinfo-class.md) görüntüleme parametreleri içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Ne zaman araç ipucu, renkler kullanarak çizilir ve görsel stilleri `pParams` belirtir. Değeri `pParams` korumalı üye depolanan `m_Params`, hangi erişilebilir kılan türetilmiş bir sınıf tarafından [CMFCToolTipCtrl::OnDrawBorder](#ondrawborder), [CMFCToolTipCtrl::OnDrawIcon](#ondrawicon), [CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel), [CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator), veya [CMFCToolTipCtrl::OnFillBackground](#onfillbackground) korumak için Belirtilen görünüm.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CToolTipCtrl sınıfı](../../mfc/reference/ctooltipctrl-class.md)   
 [CTooltipManager sınıfı](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipInfo sınıfı](../../mfc/reference/cmfctooltipinfo-class.md)   
 [CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)
