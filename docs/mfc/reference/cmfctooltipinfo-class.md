---
title: CMFCToolTipInfo Sınıfı
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
ms.openlocfilehash: 000a2fd33928e59685efa6f145406542a4935819
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377332"
---
# <a name="cmfctooltipinfo-class"></a>CMFCToolTipInfo Sınıfı

Araç ipuçlarının görsel görünümü hakkında bilgi depolar.

## <a name="syntax"></a>Sözdizimi

```
class CMFCToolTipInfo
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCToolTipInfo::operator=](#operator_eq)||

### <a name="data-members"></a>Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CMFCToolTipInfo::m_bBalloonTooltip](#m_bballoontooltip)|Araç ucunun balon görünümüne sahip olup olmadığını gösteren bir Boolean değişkeni.|
|[CMFCToolTipInfo::m_bBoldLabel](#m_bboldlabel)|Araç ipucu etiketlerinin kalın bir yazı tipinde görüntülenip görüntülenmediğini gösteren bir Boolean değişkeni.|
|[CMFCToolTipInfo::m_bDrawDescription](#m_bdrawdescription)|Araç ucunun bir açıklama içerip içermediğini gösteren bir Boolean değişkeni.|
|[CMFCToolTipInfo::m_bDrawIcon](#m_bdrawicon)|Araç ucunun bir simge bulunup içermediğini gösteren bir Boolean değişkeni.|
|[CMFCToolTipInfo::m_bDrawSeparator](#m_bdrawseparator)|Araç ucu etiketi ile araç ucu açıklaması arasında ayırıcının görüntülenip görüntülenmediğini gösteren bir Boolean değişkeni.|
|[CMFCToolTipInfo::m_bRoundedCorners](#m_broundedcorners)|Araç ucunun yuvarlak köşeleri olup olmadığını gösteren bir Boolean değişkeni.|
|[CMFCToolTipInfo::m_bVislManagerTheme](#m_bvislmanagertheme)|Araç ucunun görünümünün görsel bir yönetici tarafından kontrol edilip edilmemesi gerektiğini belirten bir Boolean değişkeni (bkz. [CMFCVisualManager Sınıfı).](../../mfc/reference/cmfcvisualmanager-class.md)|
|[CMFCToolTipInfo::m_clrBorder](#m_clrborder)|Araç ucu kenarlığı rengi.|
|[CMFCToolTipInfo::m_clrFill](#m_clrfill)|Araç ucu arka planının rengi.|
|[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient)|Degradenin rengi araç ucunu doldurur.|
|[CMFCToolTipInfo::m_clrText](#m_clrtext)|Araç ucundaki metin rengi.|
|[CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)|Degradenin açısı araç ucunu doldurur.|
|[CMFCToolTipInfo::m_nMaxDescrWidth](#m_nmaxdescrwidth)|Araç ucundaki açıklamanın piksellerde mümkün olan en yüksek genişlik.|

## <a name="remarks"></a>Açıklamalar

Uygulamanızda özelleştirilmiş araç ipuçlarını uygulamak için [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md)ve `CMFCToolTipInfo` [CTooltipManager Class'ı](../../mfc/reference/ctooltipmanager-class.md) birlikte kullanın. Bu araç ipucu sınıflarının nasıl kullanılacağına bir örnek olarak [CMFCToolTipCtrl Sınıfı](../../mfc/reference/cmfctooltipctrl-class.md) konusuna bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCToolTipInfo` sınıftaki çeşitli üye değişkenlerin değerlerinin nasıl ayarlandığını göstermektedir.

[!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cmfctooltipınfo](../../mfc/reference/cmfctooltipinfo-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtooltipctrl.h

## <a name="cmfctooltipinfom_bballoontooltip"></a><a name="m_bballoontooltip"></a>CMFCToolTipInfo::m_bBalloonTooltip

Tüm araç ipuçlarının ekran stilini belirtir.

```
BOOL m_bBalloonTooltip;
```

### <a name="remarks"></a>Açıklamalar

TRUE, araç uçlarının balon stilini kullandığını, FALSE ise araç uçlarının dikdörtgen stili kullandığını gösterir.

## <a name="cmfctooltipinfom_bboldlabel"></a><a name="m_bboldlabel"></a>CMFCToolTipInfo::m_bBoldLabel

Araç ipucu metninin yazı tipinin kalın olup olmadığını belirtir.

```
BOOL m_bBoldLabel;
```

### <a name="remarks"></a>Açıklamalar

Araç ipucu metinlerini kalın yazı tipiyle görüntülemek için bu üyeyi TRUE veya kalın olmayan yazı tipiyle araç ipucu etiketlerini görüntülemek için FALSE olarak ayarlayın.

## <a name="cmfctooltipinfom_bdrawdescription"></a><a name="m_bdrawdescription"></a>CMFCToolTipInfo::m_bDrawDescription

Her araç ucunun açıklama metnini gösterip görüntülemediğini belirtir.

```
BOOL m_bDrawDescription;
```

### <a name="remarks"></a>Açıklamalar

Açıklamayı görüntülemek için bu üyeyi TRUE'ya veya açıklamayı gizlemek için FALSE'a ayarlayın. [CMFCToolTipCtrl'i](../../mfc/reference/cmfctooltipctrl-class.md#setdescription) arayarak açıklamayı bir araç ipucunda belirtebilirsiniz::SetDescription

## <a name="cmfctooltipinfom_bdrawicon"></a><a name="m_bdrawicon"></a>CMFCToolTipInfo::m_bDrawIcon

Tüm araç ipuçlarının simgeleri gösterip göstermediğini belirtir.

```
BOOL m_bDrawIcon;
```

### <a name="remarks"></a>Açıklamalar

Bu üyeyi, her araç ucunda bir simge görüntülemek için TRUE veya simgeleri olmayan araç ipuçlarını görüntülemek için FALSE olarak ayarlayın.

## <a name="cmfctooltipinfom_bdrawseparator"></a><a name="m_bdrawseparator"></a>CMFCToolTipInfo::m_bDrawSeparator

Her araç ucunun etiketi ile açıklaması arasında bir ayırıcı olup olmadığını belirtir.

```
BOOL m_bDrawSeparator;
```

### <a name="remarks"></a>Açıklamalar

Bu üyeyi, araç ucu etiketi ve açıklaması arasında ayırıcı yı görüntülemek için TRUE veya takım uçlarını ayırıcı olmadan görüntülemek için FALSE olarak ayarlayın.

## <a name="cmfctooltipinfom_broundedcorners"></a><a name="m_broundedcorners"></a>CMFCToolTipInfo::m_bRoundedCorners

Tüm araç uçlarının yuvarlak köşelere sahip olup olmadığını belirtir.

```
BOOL m_bRoundedCorners;
```

### <a name="remarks"></a>Açıklamalar

Bu üyeyi, araç uçlarında yuvarlatılmış köşeleri görüntülemek için TRUE'ya veya araç uçlarında dikdörtgen köşeleri görüntülemek için FALSE olarak ayarlayın.

## <a name="cmfctooltipinfom_clrborder"></a><a name="m_clrborder"></a>CMFCToolTipInfo::m_clrBorder

Tüm araç uçlarında kenarlıkların rengini belirtir.

```
COLORREF m_clrBorder;
```

## <a name="cmfctooltipinfom_clrfill"></a><a name="m_clrfill"></a>CMFCToolTipInfo::m_clrFill

Araç ucu arka planlarının rengini belirtir.

```
COLORREF m_clrFill;
```

### <a name="remarks"></a>Açıklamalar

[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) -1 ise, araç ucu `m_clrFill`arka plan rengidir. Aksi `m_clrFill` takdirde, degradenin başlangıcının rengini belirtir `m_clrFillGradient` ve degradenin ucunun rengini belirtir. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) degrade yönünü belirler.

## <a name="cmfctooltipinfom_clrfillgradient"></a><a name="m_clrfillgradient"></a>CMFCToolTipInfo::m_clrFillGradient

Araç uçları için degrade arka plan için son rengi belirtir.

```
COLORREF m_clrFillGradient;
```

### <a name="remarks"></a>Açıklamalar

-1 ise, `m_clrFillGradient` degrade yoktur. Aksi takdirde, degrade ilk renk [CMFCToolTipInfo tarafından belirtilir::m_clrFill](#m_clrfill) ve `m_clrFillGradient`degrade bitiş rengi tarafından belirtilir. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) degrade yönünü belirler.

## <a name="cmfctooltipinfom_clrtext"></a><a name="m_clrtext"></a>CMFCToolTipInfo::m_clrText

Tüm araç ipuçlarının metin rengini belirtir.

```
COLORREF m_clrText;
```

## <a name="cmfctooltipinfom_ngradientangle"></a><a name="m_ngradientangle"></a>CMFCToolTipInfo::m_nGradientAngle

Araç uçlarının arka planında bir degradenin çizildiği açıyı belirtir.

```
int m_nGradientAngle;
```

### <a name="remarks"></a>Açıklamalar

`m_nGradientAngle`derece olarak açıyı, takım uçlarının arka planındaki degradenin yataydan dengelendiğini belirtir. 0 `m_nGradientAngle` ise, degrade soldan sağa doğru çizilir. 1 `m_nGradientAngle` ile 360 arasındaysa, degrade bu derece sayısına göre saat yönünde dönüyor. Varsayılan `m_nGradientAngle` değer olan -1 ise, degrade yukarıdan aşağıya doğru çizilir. Bu, 90'a ayar `m_nGradientAngle` la aynıdır.

[CMFCToolTipInfo::m_clrFill](#m_clrfill) `clrFill` degrade nin başlangıcının rengini belirtir ve [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) `clrFillGradient` degradenin ucunun rengini belirtir. -1 ise, `m_clrFillGradient` degrade yoktur.

## <a name="cmfctooltipinfom_nmaxdescrwidth"></a><a name="m_nmaxdescrwidth"></a>CMFCToolTipInfo::m_nMaxDescrWidth

Her araç ipucunda görüntülendiği açıklamanın maksimum genişliğini belirtir. Açıklama genişliği belirtilen değeri aşarsa, metin sarılır.

```
int m_nMaxDescrWidth;
```

## <a name="cmfctooltipinfom_bvislmanagertheme"></a><a name="m_bvislmanagertheme"></a>CMFCToolTipInfo::m_bVislManagerTheme

Uygulamanın görsel yöneticisinin tüm araç ipuçlarının görünümünü kontrol edip etmediğini belirtir.

```
BOOL m_bVislManagerTheme;
```

### <a name="remarks"></a>Açıklamalar

`m_bVislManagerTheme` Doğruysa, her araç ucu ekranda görünmeden önce uygulamanın görsel yöneticisinden yeni bir [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) ister ve görünümlerini belirlemek için bu nesnedeki değerleri kullanır. [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) diğer üyeleri göz ardı edilir.

## <a name="cmfctooltipinfooperator"></a><a name="operator_eq"></a>CMFCToolTipInfo::operator=

Daha fazla ayrıntı için Visual Studio kurulumunuzun **VC\\atlmfc\\\\src mfc** klasöründe bulunan kaynak koduna bakın.

```
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```

### <a name="parameters"></a>Parametreler

[içinde] *src*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CTooltipManager Sınıfı](../../mfc/reference/ctooltipmanager-class.md)<br/>
[CMFCToolTipCtrl Sınıfı](../../mfc/reference/cmfctooltipctrl-class.md)
