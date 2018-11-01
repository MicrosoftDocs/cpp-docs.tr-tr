---
title: Cmfctooltipınfo sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBalloonTooltip
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bBoldLabel
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bRoundedCorners
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_bVislManagerTheme
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrBorder
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFill
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrFillGradient
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_clrText
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nGradientAngle
- AFXTOOLTIPCTRL/CMFCToolTipInfo::m_nMaxDescrWidth
helpviewer_keywords:
- CMFCToolTipInfo [MFC], m_bBalloonTooltip
- CMFCToolTipInfo [MFC], m_bBoldLabel
- CMFCToolTipInfo [MFC], m_bDrawDescription
- CMFCToolTipInfo [MFC], m_bDrawIcon
- CMFCToolTipInfo [MFC], m_bDrawSeparator
- CMFCToolTipInfo [MFC], m_bRoundedCorners
- CMFCToolTipInfo [MFC], m_bVislManagerTheme
- CMFCToolTipInfo [MFC], m_clrBorder
- CMFCToolTipInfo [MFC], m_clrFill
- CMFCToolTipInfo [MFC], m_clrFillGradient
- CMFCToolTipInfo [MFC], m_clrText
- CMFCToolTipInfo [MFC], m_nGradientAngle
- CMFCToolTipInfo [MFC], m_nMaxDescrWidth
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
ms.openlocfilehash: 07f2882570e77d554230853dff87bc81df80e4cd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668630"
---
# <a name="cmfctooltipinfo-class"></a>Cmfctooltipınfo sınıfı

Araç ipuçlarının görsel görünümünü hakkındaki bilgileri depolar.

## <a name="syntax"></a>Sözdizimi

```
class CMFCToolTipInfo
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolTipInfo::operator =](#operator_eq)||

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolTipInfo::m_bBalloonTooltip](#m_bballoontooltip)|Araç İpucu bir balon görünüm olup olmadığını belirten bir Boolean değişkeni.|
|[CMFCToolTipInfo::m_bBoldLabel](#m_bboldlabel)|Araç İpucu etiketleri bir kalın yazı tipiyle görüntülenip görüntülenmeyeceğini belirten bir Boolean değişkeni.|
|[CMFCToolTipInfo::m_bDrawDescription](#m_bdrawdescription)|Tooltip açıklamasını içerip içermediğini gösteren bir Boolean değişkeni.|
|[CMFCToolTipInfo::m_bDrawIcon](#m_bdrawicon)|Araç İpucu simge içerip içermediğini gösteren bir Boolean değişkeni.|
|[CMFCToolTipInfo::m_bDrawSeparator](#m_bdrawseparator)|Araç İpucu etiket ve araç ipucu açıklaması arasında bir ayırıcı görüntülenip görüntülenmeyeceğini belirten bir Boolean değişkeni.|
|[CMFCToolTipInfo::m_bRoundedCorners](#m_broundedcorners)|Araç İpucu yuvarlatılmış köşelere olup olmadığını belirten bir Boolean değişkeni.|
|[CMFCToolTipInfo::m_bVislManagerTheme](#m_bvislmanagertheme)|Araç İpucu görünümünü bir görsel yöneticiyi tarafından denetlenen olup olmadığını belirten bir Boolean değişkeni (bkz [CMFCVisualManager sınıfı](../../mfc/reference/cmfcvisualmanager-class.md)).|
|[CMFCToolTipInfo::m_clrBorder](#m_clrborder)|Araç İpucu kenarlığı rengi.|
|[CMFCToolTipInfo::m_clrFill](#m_clrfill)|Araç İpucu arka plan rengi.|
|[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient)|Araç ipucunda Gradyan Dolgu rengi.|
|[CMFCToolTipInfo::m_clrText](#m_clrtext)|Araç İpucu metin rengi.|
|[CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)|Araç ipucunda Gradyan Dolgu açısı.|
|[CMFCToolTipInfo::m_nMaxDescrWidth](#m_nmaxdescrwidth)|En fazla olası piksel genişliği, araç ipucunda açıklaması.|

## <a name="remarks"></a>Açıklamalar

Kullanım [CMFCToolTipCtrl sınıfı](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, ve [CTooltipManager sınıfı](../../mfc/reference/ctooltipmanager-class.md) birlikte, uygulamanızda özel araç ipuçları uygulamak için. Bu araç ipucu sınıflarını kullanma örneği için bkz: [CMFCToolTipCtrl sınıfı](../../mfc/reference/cmfctooltipctrl-class.md) konu.

## <a name="example"></a>Örnek

Aşağıdaki örnek çeşitli üye değişkenlerinde değerlerini ayarlamak gösterilmiştir `CMFCToolTipInfo` sınıfı.

[!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cmfctooltipınfo](../../mfc/reference/cmfctooltipinfo-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtooltipctrl.h

##  <a name="m_bballoontooltip"></a>  CMFCToolTipInfo::m_bBalloonTooltip

Tüm araç ipuçlarını görüntüleme stilini belirtir.

```
BOOL m_bBalloonTooltip;
```

### <a name="remarks"></a>Açıklamalar

Araç ipuçları balon stili kullanan doğru gösterir, yanlış araç ipuçları dikdörtgen stili kullanan gösterir.

##  <a name="m_bboldlabel"></a>  CMFCToolTipInfo::m_bBoldLabel

Araç ipucu metninin yazı tipini kalın olup olmadığını belirtir.

```
BOOL m_bBoldLabel;
```

### <a name="remarks"></a>Açıklamalar

Birlikte yazı tipinin kalın araç ipucu etiketleri görüntülemek için bu üye için görünen araç ipucu metni kalın yazı tipiyle ya da yanlış true olarak ayarlayın.

##  <a name="m_bdrawdescription"></a>  CMFCToolTipInfo::m_bDrawDescription

Her araç ipucu açıklaması metni görüntülenip görüntülenmeyeceğini belirtir.

```
BOOL m_bDrawDescription;
```

### <a name="remarks"></a>Açıklamalar

Bu üye için görüntü açıklaması veya açıklama gizlemek için FALSE true olarak ayarlayın. Çağırarak bir araç ipucu açıklaması belirtebilirsiniz [CMFCToolTipCtrl::SetDescription](../../mfc/reference/cmfctooltipctrl-class.md#setdescription)

##  <a name="m_bdrawicon"></a>  CMFCToolTipInfo::m_bDrawIcon

Tüm araç ipuçları simgeleri görüntüler olup olmadığını belirtir.

```
BOOL m_bDrawIcon;
```

### <a name="remarks"></a>Açıklamalar

Her araç ipucu bir simge görüntülemek için TRUE veya FALSE araç ipuçları simgeler olmadan görüntülemek için bu üye ayarlayın.

##  <a name="m_bdrawseparator"></a>  CMFCToolTipInfo::m_bDrawSeparator

Her araç ipucu etiketini açıklamasını arasındaki ayırıcı olup olmadığını belirtir.

```
BOOL m_bDrawSeparator;
```

### <a name="remarks"></a>Açıklamalar

Araç İpucu etiket ve açıklama arasındaki ayırıcı görüntülemek için TRUE veya FALSE araç ipuçları ayırıcı olmadan görüntülemek için bu üye ayarlayın.

##  <a name="m_broundedcorners"></a>  CMFCToolTipInfo::m_bRoundedCorners

Tüm araç ipuçları yuvarlatılmış köşelere sahip olup olmadığını belirtir.

```
BOOL m_bRoundedCorners;
```

### <a name="remarks"></a>Açıklamalar

Araç ipuçları dikdörtgen köşelerinde görüntülemek için bu üye için araç ipuçları, veya yanlış ekran yuvarlak köşeler için true olarak ayarlayın.

##  <a name="m_clrborder"></a>  CMFCToolTipInfo::m_clrBorder

Tüm araç ipuçları kenarlık rengini belirtir.

```
COLORREF m_clrBorder;
```

##  <a name="m_clrfill"></a>  CMFCToolTipInfo::m_clrFill

Araç İpucu arka plan rengini belirtir.

```
COLORREF m_clrFill;
```

### <a name="remarks"></a>Açıklamalar

Varsa [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) -1, araç ipucu arka plan rengi `m_clrFill`. Aksi takdirde, `m_clrFill` gradyanın başlangıç rengini belirtir ve `m_clrFillGradient` gradyanının Bitiş rengini belirtir. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) geçişin yönü belirler.

##  <a name="m_clrfillgradient"></a>  CMFCToolTipInfo::m_clrFillGradient

Araç ipuçları için gradyan arka plan için Bitiş rengini belirtir.

```
COLORREF m_clrFillGradient;
```

### <a name="remarks"></a>Açıklamalar

Varsa `m_clrFillGradient` -1, hiçbir gradyan yoktur. Gradyan başlangıç rengi tarafından aksi takdirde, belirtilen [CMFCToolTipInfo::m_clrFill](#m_clrfill) ve gradyan bitiş rengi tarafından belirtilen `m_clrFillGradient`. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) geçişin yönü belirler.

##  <a name="m_clrtext"></a>  CMFCToolTipInfo::m_clrText

Tüm araç ipuçlarının metin rengini belirtir.

```
COLORREF m_clrText;
```

##  <a name="m_ngradientangle"></a>  CMFCToolTipInfo::m_nGradientAngle

Gradyan arka planda araç ipuçlarının çizilmiş açıyı belirtir.

```
int m_nGradientAngle;
```

### <a name="remarks"></a>Açıklamalar

`m_nGradientAngle` açısını derece araç ipuçlarının arka planı gradyan yatay uzaklığını belirtir. Varsa `m_nGradientAngle` 0 ise, geçişin soldan sağa çizilir. Varsa `m_nGradientAngle` olan 1 ile 360 arasında geçişin o derece sayısına göre saat yönünde döndürme. Varsa `m_nGradientAngle` varsayılan değerdir, -1'dir gradyan üstten alta çizilir. Bu ayar ile aynı olur `m_nGradientAngle` 90.

[CMFCToolTipInfo::m_clrFill](#m_clrfill) `clrFill` gradyanın başlangıç rengini belirtir ve [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) `clrFillGradient` gradyanının Bitiş rengini belirtir. Varsa `m_clrFillGradient` -1, hiçbir gradyan yoktur.

##  <a name="m_nmaxdescrwidth"></a>  CMFCToolTipInfo::m_nMaxDescrWidth

Her araç ipucunda görüntülenen açıklama en fazla genişliğini belirtir. Metin açıklama genişliğini belirtilen değeri aşıyorsa, paketlenir.

```
int m_nMaxDescrWidth;
```

##  <a name="m_bvislmanagertheme"></a>  CMFCToolTipInfo::m_bVislManagerTheme

Görsel yöneticiyi uygulamanın tüm araç ipuçlarının görünüm denetimleri olup olmadığını belirtir.

```
BOOL m_bVislManagerTheme;
```

### <a name="remarks"></a>Açıklamalar

Varsa `m_bVislManagerTheme` doğru ise, her araç ipucu yeni bir istek [Cmfctooltipınfo](../../mfc/reference/cmfctooltipinfo-class.md) ekrana gelen ve değerleri o nesnenin görünümlerini belirlemek için kullanır. önce uygulamanın visual Yöneticisi'nden. Diğer üyeleri, [Cmfctooltipınfo](../../mfc/reference/cmfctooltipinfo-class.md) göz ardı edilir.

##  <a name="operator_eq"></a>  CMFCToolTipInfo::operator =

Daha fazla ayrıntı için bulunan kaynak koduna bakın **VC\\atlmfc\\src\\mfc** Visual Studio yüklemenizin klasör.

```
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```

### <a name="parameters"></a>Parametreler

[in] *src*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CTooltipManager Sınıfı](../../mfc/reference/ctooltipmanager-class.md)<br/>
[CMFCToolTipCtrl Sınıfı](../../mfc/reference/cmfctooltipctrl-class.md)
