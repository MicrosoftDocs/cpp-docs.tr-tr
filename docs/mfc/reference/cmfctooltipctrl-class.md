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
ms.openlocfilehash: 9f395ae726725507bf27f5033b20a4ece2a226a6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715669"
---
# <a name="cmfctooltipctrl-class"></a>CMFCToolTipCtrl sınıfı
Genişletilmiş araç ipucu uygulaması temel alarak [CToolTipCtrl sınıfı](../../mfc/reference/ctooltipctrl-class.md). Bir araç ipucu temel alarak `CMFCToolTipCtrl` sınıfı bir simge bir etiket ve bir açıklama görüntüleyebilirsiniz. Degrade dolgusu, özel metin ve kenarlık renkleri, kalın metin, yuvarlak köşeler veya balon stili kullanarak görünümünü özelleştirebilirsiniz.  

 Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.  
  
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
|[CMFCToolTipCtrl::GetIconSize](#geticonsize)|Bir araç ipucunda bir simge boyutu döndürür.|  
|[CMFCToolTipCtrl::GetParams](#getparams)|Bir araç ipucu görüntü ayarlarını döndürür.|  
|[CMFCToolTipCtrl::OnDrawBorder](#ondrawborder)|Bir araç ipucu kenarlığı çizer.|  
|[CMFCToolTipCtrl::OnDrawDescription](#ondrawdescription)||  
|[CMFCToolTipCtrl::OnDrawIcon](#ondrawicon)|Bir araç ipucunda bir simge görüntüler.|  
|[CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel)|Etiket araç ipucu çizer ve etiket boyutunu hesaplar.|  
|[CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator)|Etiket araç ipucu açıklamasında arasındaki ayırıcı çizer.|  
|[CMFCToolTipCtrl::OnFillBackground](#onfillbackground)|Araç İpucu arka plan doldurur.|  
|[CMFCToolTipCtrl::SetDescription](#setdescription)|Araç İpucu gösterilecek açıklama ayarlar.|  
|[CMFCToolTipCtrl::SetFixedWidth](#setfixedwidth)||  
|[CMFCToolTipCtrl::SetHotRibbonButton](#sethotribbonbutton)||  
|[CMFCToolTipCtrl::SetLocation](#setlocation)||  
|[CMFCToolTipCtrl::SetParams](#setparams)|Bir araç ipucu görsel görünümünü kullanarak belirtir bir `CMFCToolTipInfo` nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `CMFCToolTipCtrl`, `CMFCToolTipInfo`, ve [CTooltipManager sınıfı](../../mfc/reference/ctooltipmanager-class.md) birlikte özelleştirilmiş araç ipuçları uygulamanıza nesneleri.  
  
 Örneğin, balon stili araç ipuçları kullanmak için aşağıdaki adımları izleyin:  
  
 1. Kullanım [CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md) uygulamanızdaki araç ipucu Yöneticisi'ni başlatmak için yöntemi.  
  
 2. Oluşturma bir `CMFCToolTipInfo` yapısını istediğiniz görsel stilini belirlemek için:  
  
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
3. Kullanım [CTooltipManager::SetTooltipParams](../../mfc/reference/ctooltipmanager-class.md#settooltipparams) tüm araç ipuçları için görsel stil içinde tanımlanan stilleri kullanarak uygulamada ayarlamak için yöntemin `CMFCToolTipInfo` nesnesi:  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMFCToolTipCtrl), &params);
```  
Ayrıca yeni bir sınıf türetebilirsiniz `CMFCToolTipCtrl` denetimi araç ipucu davranışına ve işleme. Yeni bir araç ipucu denetimi sınıf belirtmek için kullanın `CTooltipManager::SetTooltipParams` yöntemi:  
  
```  
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMyToolTipCtrl))  
```  
Varsayılanı geri yüklemek için araç ipucu denetimi sınıf ve araç ipucu görünümünü varsayılan durumuna sıfırlamak çalışma zamanı sınıf ve araç ipucu bilgisi parametrelerinin içinde NULL belirtin `SetTooltipParams`:  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    NULL,
    NULL);
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `CMFCToolTipCtrl` nesne, araç ipucu görüntüleyen bir açıklama ve araç ipucu denetiminin genişliğini ayarlayın.  
  
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
 [in] *pParams*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="geticonsize"></a>  CMFCToolTipCtrl::GetIconSize  
 Bir araç ipucunda bir simge boyutu döndürür.  
  
```  
virtual CSize GetIconSize();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Simgesi, piksel cinsinden boyutu.  
  
##  <a name="getparams"></a>  CMFCToolTipCtrl::GetParams  
 Bir araç ipucu görüntü ayarlarını döndürür.  
  
```  
const CMFCToolTipInfo& GetParams() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İçinde depolanan geçerli araç ipucu görüntü ayarlarını bir [Cmfctooltipınfo sınıfı](../../mfc/reference/cmfctooltipinfo-class.md) nesne.  
  
##  <a name="ondrawborder"></a>  CMFCToolTipCtrl::OnDrawBorder  
 Bir araç ipucu kenarlığı çizer.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect rect,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>Parametreler  
*pDC*<br/>
[in] Bir cihaz bağlamı işaretçisi.  
  
*Rect*<br/>
[in] Araç İpucu sınırlayıcı dikdörtgenini.  
  
*clrLine*<br/>
[in] Kenarlık rengi.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta araç ipucu kenarlığı görünümünü özelleştirmek için bu yöntemi yok sayın.  
  
##  <a name="ondrawdescription"></a>  CMFCToolTipCtrl::OnDrawDescription  

  
```  
virtual CSize OnDrawDescription(
    CDC* pDC,  
    CRect rect,  
    BOOL bCalcOnly);
```  
  
### <a name="parameters"></a>Parametreler  
*pDC*<br/>
[in] [in] *dikdörtgen*  
 [in] *bCalcOnly*  
  
### <a name="return-value"></a>Dönüş Değeri  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="ondrawicon"></a>  CMFCToolTipCtrl::OnDrawIcon  
 Bir araç ipucunda bir simge görüntüler.  
  
```  
virtual BOOL OnDrawIcon(
    CDC* pDC,  
    CRect rectImage);
```  
  
### <a name="parameters"></a>Parametreler  
*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.  
  
*rectImage*<br/>
[in] Simge koordinatları.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Simge çizilmiş TRUE. Aksi durumda FALSE.  
  
### <a name="remarks"></a>Açıklamalar  
 Türetilen bir sınıfta özel bir simge görüntülemek için bu yöntemi yok sayın. Geçersiz kılmalısınız [CMFCToolTipCtrl::GetIconSize](#geticonsize) düzenini metin ve açıklaması doğru hesaplamak araç ipucu sağlamak.  
  
##  <a name="ondrawlabel"></a>  CMFCToolTipCtrl::OnDrawLabel  
 Etiket araç ipucu çizer ve etiket boyutunu hesaplar.  
  
```  
virtual CSize OnDrawLabel(
    CDC* pDC,  
    CRect rect,  
    BOOL bCalcOnly);
```  
  
### <a name="parameters"></a>Parametreler  
*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.  
  
*Rect*<br/>
[in] Sınırlayıcı dikdörtgeni etiket alanının.  
  
*bCalcOnly*<br/>
[in] TRUE ise, etiket çizilmez.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Etiketin piksel cinsinden boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Araç İpucu etiket görünümünü özelleştirmek istiyorsanız türetilen bir sınıfta bu yöntemi yok sayın.  
  
##  <a name="ondrawseparator"></a>  CMFCToolTipCtrl::OnDrawSeparator  
 Etiket araç ipucu açıklamasında arasındaki ayırıcı çizer.  
  
```  
virtual void OnDrawSeparator(
    CDC* pDC,  
    int x1,  
    int x2,  
    int y);
```  
  
### <a name="parameters"></a>Parametreler  
*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.  
  
*x1*<br/>
[in] Ayırıcının sol ucuna yatay koordinatı.  
  
*x2*<br/>
[in] Yatay koordinatı sağ ucunun ayırıcı.  
  
*Y*<br/>
[in] Ayırıcı dikey koordinatı.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama noktasından bir çizgi çizer (x1, y) noktasına (x2, y).  
  
 Türetilen bir sınıfta ayırıcı görünümünü özelleştirmek için bu yöntemi yok sayın.  
  
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
*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.  
  
*Rect*<br/>
[in] Sınırlayıcı dikdörtgenini doldurmak için alanı belirtir.  
  
*clrText*<br/>
[in] Araç İpucu ön plan rengi.  
  
*clrLine*<br/>
[in] Kenarlıklar ve etiket ve açıklama arasında sınırlayıcı çizgi rengi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan uygulama tarafından belirtilen dikdörtgen doldurur *rect* renk veya en son çağrısı tarafından belirtilen desenle [CMFCToolTipCtrl::SetParams](#setparams).  
  
 Araç İpucu görünümünü özelleştirmek istiyorsanız türetilen bir sınıfta bu yöntemi yok sayın.  
  
##  <a name="setdescription"></a>  CMFCToolTipCtrl::SetDescription  
 Araç İpucu gösterilecek açıklama ayarlar.  
  
```  
virtual void SetDescription(const CString strDesrciption);
```  
  
### <a name="parameters"></a>Parametreler  
*strDesrciption*<br/>
[in] Açıklama metni.  
  
### <a name="remarks"></a>Açıklamalar  
 Açıklama metnini ayırıcı altında araç ipucu görüntülenir.  
  
##  <a name="setfixedwidth"></a>  CMFCToolTipCtrl::SetFixedWidth  

  
```  
void SetFixedWidth(
    int nWidthRegular,  
    int nWidthLargeImage);
```  
  
### <a name="parameters"></a>Parametreler  
*nWidthRegular*<br/>
[in] [in] *nWidthLargeImage*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="sethotribbonbutton"></a>  CMFCToolTipCtrl::SetHotRibbonButton  

  
```  
void SetHotRibbonButton(CMFCRibbonButton* pRibbonButton);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pRibbonButton*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setlocation"></a>  CMFCToolTipCtrl::SetLocation  

  
```  
void SetLocation(CPoint pt);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *pt*  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="setparams"></a>  CMFCToolTipCtrl::SetParams  
 Bir araç ipucu görsel görünümünü kullanarak belirtir bir [Cmfctooltipınfo sınıfı](../../mfc/reference/cmfctooltipinfo-class.md) nesne.  
  
```  
void SetParams(CMFCToolTipInfo* pParams);
```  
  
### <a name="parameters"></a>Parametreler  
*pParams*<br/>
[in] İşaretçi bir [Cmfctooltipınfo sınıfı](../../mfc/reference/cmfctooltipinfo-class.md) görüntüleme parametreleri içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Her araç ipucu görüntülenir, renkler kullanarak çizildiğinde ve görsel stilleri *pParams* belirtir. Değerini *pParams* korumalı üye depolanan `m_Params`, hangi erişilebilir kılan türetilmiş bir sınıf tarafından [CMFCToolTipCtrl::OnDrawBorder](#ondrawborder), [CMFCToolTipCtrl: : OnDrawIcon](#ondrawicon), [CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel), [CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator), veya [CMFCToolTipCtrl::OnFillBackground](#onfillbackground)belirtilen görünümünü korumak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [CToolTipCtrl sınıfı](../../mfc/reference/ctooltipctrl-class.md)   
 [CTooltipManager sınıfı](../../mfc/reference/ctooltipmanager-class.md)   
 [Cmfctooltipınfo sınıfı](../../mfc/reference/cmfctooltipinfo-class.md)   
 [CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)
