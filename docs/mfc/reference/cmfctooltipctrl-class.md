---
description: 'Daha fazla bilgi edinin: CMFCToolTipCtrl sınıfı'
title: CMFCToolTipCtrl sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 918a702a94f2847298d86868d35b2bad65b65b33
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331696"
---
# <a name="cmfctooltipctrl-class"></a>CMFCToolTipCtrl sınıfı

[CToolTipCtrl sınıfına](../../mfc/reference/ctooltipctrl-class.md)dayalı genişletilmiş bir araç ipucu uygulama. Sınıfına dayalı bir araç ipucu `CMFCToolTipCtrl` , bir simge, etiket ve açıklama gösterebilir. Görsel görünümünü, bir gradyan dolgusu, özel metin ve kenarlık renkleri, kalın metin, yuvarlatılmış köşeler veya balon stili kullanarak özelleştirebilirsiniz.

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Syntax

```cpp
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
|[CMFCToolTipCtrl:: GetIconSize](#geticonsize)|Araç ipucunda bir simgenin boyutunu döndürür.|
|[CMFCToolTipCtrl:: GetParams](#getparams)|Bir araç ipucunun görüntüleme ayarlarını döndürür.|
|[CMFCToolTipCtrl:: OnDrawBorder](#ondrawborder)|Bir araç ipucunun kenarlığını çizer.|
|[CMFCToolTipCtrl:: OnDrawDescription](#ondrawdescription)||
|[CMFCToolTipCtrl:: OnDrawIcon](#ondrawicon)|Araç ipucunda bir simge görüntüler.|
|[CMFCToolTipCtrl:: OnDrawLabel](#ondrawlabel)|Bir araç ipucunun etiketini çizer veya etiketin boyutunu hesaplar.|
|[CMFCToolTipCtrl:: OnDrawSeparator](#ondrawseparator)|Bir araç ipucunda etiket ve açıklama arasındaki ayırıcıyı çizer.|
|[CMFCToolTipCtrl:: OnFillBackground](#onfillbackground)|Araç İpucu arka planını doldurur.|
|[CMFCToolTipCtrl:: SetDescription](#setdescription)|Araç İpucu tarafından görüntülenecek açıklamayı ayarlar.|
|[CMFCToolTipCtrl:: SetFixedWidth](#setfixedwidth)||
|[CMFCToolTipCtrl:: Sethotribbondüğmesi](#sethotribbonbutton)||
|[CMFCToolTipCtrl:: SetLocation](#setlocation)||
|[CMFCToolTipCtrl:: SetParams](#setparams)|Bir araç ipucunun görsel görünümünü bir nesne kullanarak belirtir `CMFCToolTipInfo` .|

## <a name="remarks"></a>Açıklamalar

`CMFCToolTipCtrl` `CMFCToolTipInfo` Uygulamanızda özelleştirilmiş araç ipuçları uygulamak için, ve [CTooltipManager sınıf](../../mfc/reference/ctooltipmanager-class.md) nesnelerini birlikte kullanın.

Örneğin, balon stili araç ipuçlarını kullanmak için şu adımları izleyin:

1. Uygulamanızdaki araç ipucu Yöneticisini başlatmak için [CWinAppEx Class](../../mfc/reference/cwinappex-class.md) metodunu kullanın.

2. İstediğiniz `CMFCToolTipInfo` görsel stili belirtmek için bir yapı oluşturun:

    ```cpp
    CMFCToolTipInfo params;
    params.m_bBoldLabel = FALSE;
    params.m_bDrawDescription = FALSE;
    params.m_bDrawIcon = FALSE;
    params.m_bRoundedCorners = TRUE;
    params.m_bDrawSeparator = FALSE;
    if (m_bCustomColors)
    {
        params.m_clrFill = RGB (255, 255, 255);
        params.m_clrFillGradient = RGB (228, 228, 240);
        params.m_clrText = RGB (61, 83, 80);
        params.m_clrBorder = RGB (144, 149, 168);

    }
    ```

3. Nesnede tanımlanan stilleri kullanarak uygulamadaki tüm araç ipuçlarının görsel stilini ayarlamak için [CTooltipManager:: SetTooltipParams](../../mfc/reference/ctooltipmanager-class.md#settooltipparams) metodunu kullanın `CMFCToolTipInfo` :

    ```cpp
    theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
        RUNTIME_CLASS (CMFCToolTipCtrl), &params);
    ```

`CMFCToolTipCtrl`Araç ipucu davranışını ve işlemeyi denetlemek için ' den yeni bir sınıf de türetebilirsiniz. Yeni bir araç ipucu denetim sınıfı belirtmek için yöntemini kullanın `CTooltipManager::SetTooltipParams` :

```cpp
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    RUNTIME_CLASS (CMyToolTipCtrl))
```

Varsayılan araç ipucu denetim sınıfını geri yüklemek ve araç ipucu görünümünü varsayılan durumuna sıfırlamak için, çalışma zamanı sınıfında NULL değerini ve araç ipucu bilgi parametrelerini seçin `SetTooltipParams` :

```cpp
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    NULL,
    NULL);
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnesinin nasıl oluşturulduğunu `CMFCToolTipCtrl` , araç ipucunun görüntüleyeceği açıklamayı ayarlamayı ve araç ipucu denetiminin genişliğini ayarlamayı gösterir.

[!code-cpp[NVC_MFC_RibbonApp#41](../../mfc/reference/codesnippet/cpp/cmfctooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)

[CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxToolTipCtrl. h

## <a name="cmfctooltipctrlcmfctooltipctrl"></a><a name="cmfctooltipctrl"></a> CMFCToolTipCtrl:: CMFCToolTipCtrl

```cpp
CMFCToolTipCtrl(CMFCToolTipInfo* pParams = NULL);
```

### <a name="parameters"></a>Parametreler

'ndaki *pParams*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctooltipctrlgeticonsize"></a><a name="geticonsize"></a> CMFCToolTipCtrl:: GetIconSize

Araç ipucunda bir simgenin boyutunu döndürür.

```cpp
virtual CSize GetIconSize();
```

### <a name="return-value"></a>Dönüş Değeri

Simgenin piksel cinsinden boyutu.

## <a name="cmfctooltipctrlgetparams"></a><a name="getparams"></a> CMFCToolTipCtrl:: GetParams

Bir araç ipucunun görüntüleme ayarlarını döndürür.

```cpp
const CMFCToolTipInfo& GetParams() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir [CMFCToolTipInfo sınıfı](../../mfc/reference/cmfctooltipinfo-class.md) nesnesinde depolanan geçerli araç ipucu görüntüleme ayarları.

## <a name="cmfctooltipctrlondrawborder"></a><a name="ondrawborder"></a> CMFCToolTipCtrl:: OnDrawBorder

Bir araç ipucunun kenarlığını çizer.

```cpp
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect,
    COLORREF clrLine);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamı işaretçisi.

*Rect*<br/>
'ndaki Araç ipucunun sınırlayıcı dikdörtgeni.

*clrLine*<br/>
'ndaki Kenarlık rengi.

### <a name="remarks"></a>Açıklamalar

Araç ipucu kenarlığının görünümünü özelleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfctooltipctrlondrawdescription"></a><a name="ondrawdescription"></a> CMFCToolTipCtrl:: OnDrawDescription

```cpp
virtual CSize OnDrawDescription(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>Parametreler

'ndaki *PDC*<br/>
'ndaki *Rect*<br/>
'ndaki *bCalcOnly*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctooltipctrlondrawicon"></a><a name="ondrawicon"></a> CMFCToolTipCtrl:: OnDrawIcon

Araç ipucunda bir simge görüntüler.

```cpp
virtual BOOL OnDrawIcon(
    CDC* pDC,
    CRect rectImage);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*rectImage*<br/>
'ndaki Simgenin koordinatları.

### <a name="return-value"></a>Dönüş Değeri

Simge çizildiyse doğru. Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Özel bir simge göstermek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın. Ayrıca, araç ipucunun metin ve açıklamanın yerleşimini doğru bir şekilde hesaplamasını sağlamak için [CMFCToolTipCtrl:: GetIconSize](#geticonsize) ' i geçersiz kılmanız gerekir.

## <a name="cmfctooltipctrlondrawlabel"></a><a name="ondrawlabel"></a> CMFCToolTipCtrl:: OnDrawLabel

Bir araç ipucunun etiketini çizer veya etiketin boyutunu hesaplar.

```cpp
virtual CSize OnDrawLabel(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*Rect*<br/>
'ndaki Etiket alanının sınırlayıcı dikdörtgeni.

*bCalcOnly*<br/>
'ndaki TRUE ise etiket çizilmez.

### <a name="return-value"></a>Dönüş Değeri

Etiketin piksel cinsinden boyutu.

### <a name="remarks"></a>Açıklamalar

Araç ipucu etiketinin görünümünü özelleştirmek istiyorsanız türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfctooltipctrlondrawseparator"></a><a name="ondrawseparator"></a> CMFCToolTipCtrl:: OnDrawSeparator

Bir araç ipucunda etiket ve açıklama arasındaki ayırıcıyı çizer.

```cpp
virtual void OnDrawSeparator(
    CDC* pDC,
    int x1,
    int x2,
    int y);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*x1*<br/>
'ndaki Ayırıcının sol ucunun yatay koordinatı.

*x2*<br/>
'ndaki Ayracın sağ ucunun yatay koordinatı.

*E*<br/>
'ndaki Ayırıcının Dikey koordinatı.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, noktadan (x1, y) noktaya (x2, y) kadar bir çizgi çizer.

Ayırıcının görünümünü özelleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfctooltipctrlonfillbackground"></a><a name="onfillbackground"></a> CMFCToolTipCtrl:: OnFillBackground

Araç İpucu arka planını doldurur.

```cpp
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect,
    COLORREF& clrText,
    COLORREF& clrLine);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*Rect*<br/>
'ndaki Doldurulacak alanın sınırlayıcı dikdörtgenini belirtir.

*clrText*<br/>
'ndaki Araç ipucu ön plan rengi.

*clrLine*<br/>
'ndaki Kenarlıkların rengi ve etiket ile açıklama arasındaki sınırlayıcı çizgi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, *Rect* tarafından belirtilen dikdörtgeni, [CMFCToolTipCtrl:: setparams](#setparams)en son çağrısıyla belirtilen renkle veya düzeniyle doldurur.

Araç ipucunun görünümünü özelleştirmek istiyorsanız türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfctooltipctrlsetdescription"></a><a name="setdescription"></a> CMFCToolTipCtrl:: SetDescription

Araç İpucu tarafından görüntülenecek açıklamayı ayarlar.

```cpp
virtual void SetDescription(const CString strDesrciption);
```

### <a name="parameters"></a>Parametreler

*Strdesrşifre*<br/>
'ndaki Açıklama metni.

### <a name="remarks"></a>Açıklamalar

Açıklama metni, ayırıcıdaki araç ipucunda görüntülenir.

## <a name="cmfctooltipctrlsetfixedwidth"></a><a name="setfixedwidth"></a> CMFCToolTipCtrl:: SetFixedWidth

```cpp
void SetFixedWidth(
    int nWidthRegular,
    int nWidthLargeImage);
```

### <a name="parameters"></a>Parametreler

'ndaki *nWidthRegular*<br/>
'ndaki *nWidthLargeImage*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctooltipctrlsethotribbonbutton"></a><a name="sethotribbonbutton"></a> CMFCToolTipCtrl:: Sethotribbondüğmesi

```cpp
void SetHotRibbonButton(CMFCRibbonButton* pRibbonButton);
```

### <a name="parameters"></a>Parametreler

'ndaki *Pribbondüğmesi*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctooltipctrlsetlocation"></a><a name="setlocation"></a> CMFCToolTipCtrl:: SetLocation

```cpp
void SetLocation(CPoint pt);
```

### <a name="parameters"></a>Parametreler

'ndaki *PT*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctooltipctrlsetparams"></a><a name="setparams"></a> CMFCToolTipCtrl:: SetParams

Bir [CMFCToolTipInfo sınıfı](../../mfc/reference/cmfctooltipinfo-class.md) nesnesi kullanarak bir araç ipucunun görsel görünümünü belirtir.

```cpp
void SetParams(CMFCToolTipInfo* pParams);
```

### <a name="parameters"></a>Parametreler

*pParams*<br/>
'ndaki Görüntüleme parametrelerini içeren bir [CMFCToolTipInfo sınıfı](../../mfc/reference/cmfctooltipinfo-class.md) nesnesine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Araç ipucu her görüntülendiğinde, *pParams* 'in belirttiği renkler ve görsel stiller kullanılarak çizilir. *PParams* değeri korunan üyede depolanır, bu, `m_Params` bir türetilmiş sınıf tarafından erişilebilen [CMFCToolTipCtrl:: OnDrawBorder](#ondrawborder), CMFCToolTipCtrl:: OnDrawIcon, CMFCToolTipCtrl [](#ondrawicon):: [OnDrawLabel](#ondrawlabel), CMFCToolTipCtrl:: [OnDrawSeparator](#ondrawseparator)veya CMFCToolTipCtrl:: [OnFillBackground](#onfillbackground) , belirtilen görünümü sürdürmek için.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CToolTipCtrl sınıfı](../../mfc/reference/ctooltipctrl-class.md)<br/>
[CTooltipManager sınıfı](../../mfc/reference/ctooltipmanager-class.md)<br/>
[CMFCToolTipInfo sınıfı](../../mfc/reference/cmfctooltipinfo-class.md)<br/>
[CWinAppEx sınıfı](../../mfc/reference/cwinappex-class.md)
