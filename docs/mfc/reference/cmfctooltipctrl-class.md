---
title: CMFCToolTipCtrl Sınıfı
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
ms.openlocfilehash: 6c8bb41b82d1dca9235e1184c2152a61c07c8071
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377348"
---
# <a name="cmfctooltipctrl-class"></a>CMFCToolTipCtrl Sınıfı

[CToolTipCtrl Sınıfı'na](../../mfc/reference/ctooltipctrl-class.md)dayalı genişletilmiş bir araç ucu uygulaması. Sınıfa `CMFCToolTipCtrl` dayalı bir araç ucu bir simge, etiket ve açıklama görüntüleyebilir. Degrade dolgu, özel metin ve kenarlık renkleri, kalın metin, yuvarlak köşeler veya balon stili kullanarak görsel görünümünü özelleştirebilirsiniz.

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Sözdizimi

```cpp
class CMFCToolTipCtrl : public CToolTipCtrl
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|`CMFCToolTipCtrl::CMFCToolTipCtrl`|Varsayılan oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCToolTipCtrl::GetIconSize](#geticonsize)|Araç ucundaki simgenin boyutunu döndürür.|
|[CMFCToolTipCtrl::GetParams](#getparams)|Araç ucunun ekran ayarlarını döndürür.|
|[CMFCToolTipCtrl::OnDrawBorder](#ondrawborder)|Bir araç ucunun kenarlığı çizer.|
|[CMFCToolTipCtrl::OnDrawDescription](#ondrawdescription)||
|[CMFCToolTipCtrl::OnDrawIcon](#ondrawicon)|Araç ucunda bir simge görüntüler.|
|[CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel)|Araç ucunun etiketini çizer veya etiketin boyutunu hesaplar.|
|[CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator)|Ayırıcıyı etiket ve açıklama arasında bir araç ucuçizer.|
|[CMFCToolTipCtrl::OnFillBackground](#onfillbackground)|Araç ucu arka planını doldurur.|
|[CMFCToolTipCtrl::SetDescription](#setdescription)|Araç ucu tarafından görüntülenecek açıklamayı ayarlar.|
|[CMFCToolTipCtrl::SetFixedWidth](#setfixedwidth)||
|[CMFCToolTipCtrl::SetHotRibbonButton](#sethotribbonbutton)||
|[CMFCToolTipCtrl::SetLocation](#setlocation)||
|[CMFCToolTipCtrl::SetParams](#setparams)|Bir `CMFCToolTipInfo` nesne kullanarak bir araç ucunun görsel görünümünü belirtir.|

## <a name="remarks"></a>Açıklamalar

Uygulamanızda özelleştirilmiş araç ipuçlarını uygulamak için [ctooltipManager Sınıf](../../mfc/reference/ctooltipmanager-class.md) nesnelerini birlikte kullanın. `CMFCToolTipCtrl` `CMFCToolTipInfo`

Örneğin, balon stili araç ipuçlarını kullanmak için aşağıdaki adımları izleyin:

1. Uygulamanızdaki araç ipucu yöneticisini ortaya çıkarmak için [CWinAppEx Class](../../mfc/reference/cwinappex-class.md) yöntemini kullanın.

2. İstediğiniz görsel stili belirtmek için bir `CMFCToolTipInfo` yapı oluşturun:

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

3. `CMFCToolTipInfo` [CTooltipManager kullanın::SetTooltipParams](../../mfc/reference/ctooltipmanager-class.md#settooltipparams) yöntemi nesnede tanımlanan stilleri kullanarak uygulamadaki tüm araç ipuçları için görsel stili ayarlamak için:

    ```cpp
    theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
        RUNTIME_CLASS (CMFCToolTipCtrl), &params);
    ```

Ayrıca, araç ipucu davranışını `CMFCToolTipCtrl` ve işlemeyi denetlemek için yeni bir sınıf elde edebilirsiniz. Yeni bir araç ipucu denetim sınıfı `CTooltipManager::SetTooltipParams` belirtmek için yöntemi kullanın:

```cpp
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    RUNTIME_CLASS (CMyToolTipCtrl))
```

Varsayılan araç ipucu denetim sınıfını geri yüklemek ve araç ipucu görünümünü varsayılan durumuna sıfırlamak için, `SetTooltipParams`çalışma zamanı sınıfında NULL ve araç ipucu bilgi parametrelerinde NULL belirtin:

```cpp
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,
    NULL,
    NULL);
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCToolTipCtrl` nesnenin nasıl oluşturulabildiğini, araç ucunun görüntülenebildiğini nasıl ayarladığını ve araç ipucu denetiminin genişliğini nasıl ayarladığını gösterir.

[!code-cpp[NVC_MFC_RibbonApp#41](../../mfc/reference/codesnippet/cpp/cmfctooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Ctooltipctrl](../../mfc/reference/ctooltipctrl-class.md)

[CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtooltipctrl.h

## <a name="cmfctooltipctrlcmfctooltipctrl"></a><a name="cmfctooltipctrl"></a>CMFCToolTipCtrl::CMFCToolTipCtrl

```cpp
CMFCToolTipCtrl(CMFCToolTipInfo* pParams = NULL);
```

### <a name="parameters"></a>Parametreler

[içinde] *pParams*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctooltipctrlgeticonsize"></a><a name="geticonsize"></a>CMFCToolTipCtrl::GetIconSize

Araç ucundaki simgenin boyutunu döndürür.

```cpp
virtual CSize GetIconSize();
```

### <a name="return-value"></a>Dönüş Değeri

Simgenin boyutu, piksel olarak.

## <a name="cmfctooltipctrlgetparams"></a><a name="getparams"></a>CMFCToolTipCtrl::GetParams

Araç ucunun ekran ayarlarını döndürür.

```cpp
const CMFCToolTipInfo& GetParams() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli araç ipucu ekran ayarları , bir [CMFCToolTipInfo Sınıf](../../mfc/reference/cmfctooltipinfo-class.md) nesnesinde depolanır.

## <a name="cmfctooltipctrlondrawborder"></a><a name="ondrawborder"></a>CMFCToolTipCtrl::OnDrawBorder

Bir araç ucunun kenarlığı çizer.

```cpp
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect,
    COLORREF clrLine);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*Rect*<br/>
[içinde] Araç ucunun sınırlayıcı dikdörtgeni.

*clrLine*<br/>
[içinde] Kenarlık rengi.

### <a name="remarks"></a>Açıklamalar

Araç ucu kenarlığı görünümünü özelleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfctooltipctrlondrawdescription"></a><a name="ondrawdescription"></a>CMFCToolTipCtrl::OnDrawDescription

```cpp
virtual CSize OnDrawDescription(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>Parametreler

[içinde] *pDC*<br/>
[içinde] *rekt*<br/>
[içinde] *bCalcSadece*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctooltipctrlondrawicon"></a><a name="ondrawicon"></a>CMFCToolTipCtrl::OnDrawIcon

Araç ucunda bir simge görüntüler.

```cpp
virtual BOOL OnDrawIcon(
    CDC* pDC,
    CRect rectImage);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*rectImage*<br/>
[içinde] Simgenin koordinatları.

### <a name="return-value"></a>Dönüş Değeri

Simge çizilmişse DOĞRU. Aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Özel bir simge görüntülemek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın. Ayrıca [CMFCToolTipCtrl geçersiz kılmanız gerekir::GetIconSize](#geticonsize) doğru metin ve açıklama düzenini hesaplamak için araç ucunu etkinleştirmek için.

## <a name="cmfctooltipctrlondrawlabel"></a><a name="ondrawlabel"></a>CMFCToolTipCtrl::OnDrawLabel

Araç ucunun etiketini çizer veya etiketin boyutunu hesaplar.

```cpp
virtual CSize OnDrawLabel(
    CDC* pDC,
    CRect rect,
    BOOL bCalcOnly);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*Rect*<br/>
[içinde] Etiket alanının sınırlayıcı dikdörtgeni.

*bCalcSadece*<br/>
[içinde] TRUE ise, etiket çizilmez.

### <a name="return-value"></a>Dönüş Değeri

Piksel olarak etiketboyutu.

### <a name="remarks"></a>Açıklamalar

Araç ipucu etiketinin görünümünü özelleştirmek istiyorsanız, türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfctooltipctrlondrawseparator"></a><a name="ondrawseparator"></a>CMFCToolTipCtrl::OnDrawSeparator

Ayırıcıyı etiket ve açıklama arasında bir araç ucuçizer.

```cpp
virtual void OnDrawSeparator(
    CDC* pDC,
    int x1,
    int x2,
    int y);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*x1*<br/>
[içinde] Ayırıcının sol ucunun yatay koordinatı.

*x2*<br/>
[içinde] Ayırıcının sağ ucunun yatay koordinatı.

*Y*<br/>
[içinde] Ayırıcının dikey koordinatı.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama, noktadan (x1, y) noktaya (x2, y) bir çizgi çizer.

Ayırıcının görünümünü özelleştirmek için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfctooltipctrlonfillbackground"></a><a name="onfillbackground"></a>CMFCToolTipCtrl::OnFillBackground

Araç ucu arka planını doldurur.

```cpp
virtual void OnFillBackground(
    CDC* pDC,
    CRect rect,
    COLORREF& clrText,
    COLORREF& clrLine);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*Rect*<br/>
[içinde] Doldurulacak alanın sınırlayıcı dikdörtgenini belirtir.

*clrMetin*<br/>
[içinde] Tooltip ön plan rengi.

*clrLine*<br/>
[içinde] Kenarlıkların rengi ve etiket ve açıklama arasındaki sınır tanımayan çizgi.

### <a name="remarks"></a>Açıklamalar

Varsayılan uygulama CMFCToolTipCtrl için en son çağrı tarafından belirtilen renk veya desen ile *rect* tarafından belirtilen dikdörtgen [doldurur::SetParams](#setparams).

Araç ucunun görünümünü özelleştirmek istiyorsanız, türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

## <a name="cmfctooltipctrlsetdescription"></a><a name="setdescription"></a>CMFCToolTipCtrl::SetDescription

Araç ucu tarafından görüntülenecek açıklamayı ayarlar.

```cpp
virtual void SetDescription(const CString strDesrciption);
```

### <a name="parameters"></a>Parametreler

*strDesrciption*<br/>
[içinde] Açıklama metni.

### <a name="remarks"></a>Açıklamalar

Açıklama metni ayırıcının altındaki araç ucunda görüntülenir.

## <a name="cmfctooltipctrlsetfixedwidth"></a><a name="setfixedwidth"></a>CMFCToolTipCtrl::SetFixedWidth

```cpp
void SetFixedWidth(
    int nWidthRegular,
    int nWidthLargeImage);
```

### <a name="parameters"></a>Parametreler

[içinde] *nWidthRegular*<br/>
[içinde] *nWidthLargeImage*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctooltipctrlsethotribbonbutton"></a><a name="sethotribbonbutton"></a>CMFCToolTipCtrl::SetHotRibbonButton

```cpp
void SetHotRibbonButton(CMFCRibbonButton* pRibbonButton);
```

### <a name="parameters"></a>Parametreler

[içinde] *pRibbonButton*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctooltipctrlsetlocation"></a><a name="setlocation"></a>CMFCToolTipCtrl::SetLocation

```cpp
void SetLocation(CPoint pt);
```

### <a name="parameters"></a>Parametreler

[içinde] *pt*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfctooltipctrlsetparams"></a><a name="setparams"></a>CMFCToolTipCtrl::SetParams

[CMFCToolTipInfo Class](../../mfc/reference/cmfctooltipinfo-class.md) nesnesi kullanarak bir araç ucunun görsel görünümünü belirtir.

```cpp
void SetParams(CMFCToolTipInfo* pParams);
```

### <a name="parameters"></a>Parametreler

*pParams*<br/>
[içinde] Görüntü parametrelerini içeren [cmfctooltipinfo sınıf](../../mfc/reference/cmfctooltipinfo-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Araç ucu görüntülendiğinde, *pParams'ın* belirttiği renkler ve görsel stiller kullanılarak çizilir. *PParam'ların* değeri, [CMFCToolTipCtrl::OnDrawBorder](#ondrawborder), [CMFCToolTipCtrl::OnDrawIcon , CMFCToolTipCtrl::OnDrawIcon](#ondrawicon), [CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel), [CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator)veya [CMFCToolTipCtrl::OnFillBackground'u](#onfillbackground) geçersiz kılan türemiş bir sınıf tarafından erişilebilen korumalı üyede `m_Params`depolanır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CToolTipCtrl Sınıfı](../../mfc/reference/ctooltipctrl-class.md)<br/>
[CTooltipManager Sınıfı](../../mfc/reference/ctooltipmanager-class.md)<br/>
[CMFCToolTipInfo Sınıfı](../../mfc/reference/cmfctooltipinfo-class.md)<br/>
[CWinAppEx Sınıfı](../../mfc/reference/cwinappex-class.md)
