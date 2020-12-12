---
description: 'Daha fazla bilgi edinin: CMFCToolTipInfo sınıfı'
title: CMFCToolTipInfo sınıfı
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
ms.openlocfilehash: 06ceca500ad92d5f3a27e2740a298d9c1bbfe1cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143435"
---
# <a name="cmfctooltipinfo-class"></a>CMFCToolTipInfo sınıfı

Araç ipuçlarının görsel görünümüyle ilgili bilgileri depolar.

## <a name="syntax"></a>Syntax

```
class CMFCToolTipInfo
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolTipInfo:: operator =](#operator_eq)||

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CMFCToolTipInfo:: m_bBalloonTooltip](#m_bballoontooltip)|ToolTip 'in balon görünümüne sahip olup olmadığını gösteren bir Boole değişkeni.|
|[CMFCToolTipInfo:: m_bBoldLabel](#m_bboldlabel)|Araç ipucu etiketlerinin kalın yazı tipinde görüntülenip görüntülenmeyeceğini belirten bir Boole değişkeni.|
|[CMFCToolTipInfo:: m_bDrawDescription](#m_bdrawdescription)|ToolTip 'in bir açıklama içerip içermediğini gösteren bir Boolean değişkeni.|
|[CMFCToolTipInfo:: m_bDrawIcon](#m_bdrawicon)|ToolTip 'in bir simge içerip içermediğini gösteren bir Boolean değişkeni.|
|[CMFCToolTipInfo:: m_bDrawSeparator](#m_bdrawseparator)|Araç ipucu etiketi ve araç ipucu açıklaması arasında bir ayırıcısının görüntülenip görüntülenmeyeceğini gösteren Boolean bir değişken.|
|[CMFCToolTipInfo:: m_bRoundedCorners](#m_broundedcorners)|ToolTip 'in yuvarlatılmış köşeler içerip içermediğini gösteren bir Boolean değişkeni.|
|[CMFCToolTipInfo:: m_bVislManagerTheme](#m_bvislmanagertheme)|Araç ipucunun görünümünün bir görsel yönetici tarafından denetlenmesi gerekip gerekmediğini belirten bir Boolean değişkeni (bkz. [CMFCVisualManager sınıfı](../../mfc/reference/cmfcvisualmanager-class.md)).|
|[CMFCToolTipInfo:: m_clrBorder](#m_clrborder)|Araç ipucu kenarlığının rengi.|
|[CMFCToolTipInfo:: m_clrFill](#m_clrfill)|Araç İpucu arka planının rengi.|
|[CMFCToolTipInfo:: m_clrFillGradient](#m_clrfillgradient)|Araç ipucunda gradyan dolgusunun rengi.|
|[CMFCToolTipInfo:: m_clrText](#m_clrtext)|Araç ipucunda metin rengi.|
|[CMFCToolTipInfo:: m_nGradientAngle](#m_ngradientangle)|Araç ipucunda gradyan dolgusunun açısı.|
|[CMFCToolTipInfo:: m_nMaxDescrWidth](#m_nmaxdescrwidth)|Araç ipucunda açıklamanın en yüksek olası genişliği (piksel cinsinden).|

## <a name="remarks"></a>Açıklamalar

Uygulamanızda özelleştirilmiş araç ipuçları uygulamak için [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo` ve [CTooltipManager sınıfını](../../mfc/reference/ctooltipmanager-class.md) birlikte kullanın. Bu araç ipucu sınıflarının nasıl kullanılacağına ilişkin bir örnek için, bkz. [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md) konusu.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, sınıfındaki çeşitli üye değişkenlerinin değerlerinin nasıl ayarlanacağı gösterilmektedir `CMFCToolTipInfo` .

[!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxToolTipCtrl. h

## <a name="cmfctooltipinfom_bballoontooltip"></a><a name="m_bballoontooltip"></a> CMFCToolTipInfo:: m_bBalloonTooltip

Tüm araç ipuçlarının görüntüleme stilini belirtir.

```
BOOL m_bBalloonTooltip;
```

### <a name="remarks"></a>Açıklamalar

TRUE, araç ipuçlarının balon stilini kullanacağını gösterir, yanlış araç ipuçlarının dikdörtgen stili kullanacağını gösterir.

## <a name="cmfctooltipinfom_bboldlabel"></a><a name="m_bboldlabel"></a> CMFCToolTipInfo:: m_bBoldLabel

Araç ipucu metninin yazı tipinin kalın olup olmadığını belirtir.

```
BOOL m_bBoldLabel;
```

### <a name="remarks"></a>Açıklamalar

Bu üyeyi, kalın yazı tipiyle araç ipucu metnini göstermek için TRUE, kalın olmayan yazı tipiyle araç ipucu etiketlerini göstermek için FALSE olarak ayarlayın.

## <a name="cmfctooltipinfom_bdrawdescription"></a><a name="m_bdrawdescription"></a> CMFCToolTipInfo:: m_bDrawDescription

Her araç ipucunun açıklama metnini görüntüleyip görüntülemediğini belirtir.

```
BOOL m_bDrawDescription;
```

### <a name="remarks"></a>Açıklamalar

Açıklamayı göstermek için bu üyeyi TRUE, açıklamayı gizlemek için FALSE olarak ayarlayın. [CMFCToolTipCtrl:: SetDescription](../../mfc/reference/cmfctooltipctrl-class.md#setdescription) öğesini çağırarak bir araç ipucunda açıklama belirtebilirsiniz

## <a name="cmfctooltipinfom_bdrawicon"></a><a name="m_bdrawicon"></a> CMFCToolTipInfo:: m_bDrawIcon

Tüm ToolTip 'lerin simge görüntüleyip görüntülememediğini belirtir.

```
BOOL m_bDrawIcon;
```

### <a name="remarks"></a>Açıklamalar

Her araç ipucunda bir simge göstermek için bu üyeyi TRUE, simgeler olmadan araç ipuçlarını göstermek için FALSE olarak ayarlayın.

## <a name="cmfctooltipinfom_bdrawseparator"></a><a name="m_bdrawseparator"></a> CMFCToolTipInfo:: m_bDrawSeparator

Her ToolTip 'in etiketi ve açıklaması arasında bir ayırıcı olup olmadığını belirtir.

```
BOOL m_bDrawSeparator;
```

### <a name="remarks"></a>Açıklamalar

Araç ipucu etiketi ve açıklaması arasındaki ayırıcıyı göstermek için bu üyeyi TRUE, ayırıcı olmadan araç ipuçlarını göstermek için FALSE olarak ayarlayın.

## <a name="cmfctooltipinfom_broundedcorners"></a><a name="m_broundedcorners"></a> CMFCToolTipInfo:: m_bRoundedCorners

Tüm ToolTip 'lerin köşeleri yuvarlatılmış olup olmadığını belirtir.

```
BOOL m_bRoundedCorners;
```

### <a name="remarks"></a>Açıklamalar

Araç ipuçlarında Yuvarlatılmış köşeleri göstermek için bu üyeyi TRUE, araç ipuçlarında dikdörtgen köşeleri göstermek için FALSE olarak ayarlayın.

## <a name="cmfctooltipinfom_clrborder"></a><a name="m_clrborder"></a> CMFCToolTipInfo:: m_clrBorder

Tüm araç ipuçlarında kenarlıkların rengini belirtir.

```
COLORREF m_clrBorder;
```

## <a name="cmfctooltipinfom_clrfill"></a><a name="m_clrfill"></a> CMFCToolTipInfo:: m_clrFill

Araç İpucu arka planlarının rengini belirtir.

```
COLORREF m_clrFill;
```

### <a name="remarks"></a>Açıklamalar

[CMFCToolTipInfo:: m_clrFillGradient](#m_clrfillgradient) -1 ise, araç ipucu arka plan rengi olur `m_clrFill` . Aksi takdirde, `m_clrFill` degradenin başlangıcını belirtir ve `m_clrFillGradient` degradenin sonundaki rengi belirtir. [CMFCToolTipInfo:: m_nGradientAngle](#m_ngradientangle) degradenin yönünü belirler.

## <a name="cmfctooltipinfom_clrfillgradient"></a><a name="m_clrfillgradient"></a> CMFCToolTipInfo:: m_clrFillGradient

Araç ipuçları için bir gradyan arka planının bitiş rengini belirtir.

```
COLORREF m_clrFillGradient;
```

### <a name="remarks"></a>Açıklamalar

`m_clrFillGradient`-1 ise gradyan yoktur. Aksi takdirde, gradyan başlangıç rengi [CMFCToolTipInfo:: m_clrFill](#m_clrfill) tarafından belirtilir ve gradyan bitiş rengi tarafından belirtilir `m_clrFillGradient` . [CMFCToolTipInfo:: m_nGradientAngle](#m_ngradientangle) degradenin yönünü belirler.

## <a name="cmfctooltipinfom_clrtext"></a><a name="m_clrtext"></a> CMFCToolTipInfo:: m_clrText

Tüm araç ipuçlarının metin rengini belirtir.

```
COLORREF m_clrText;
```

## <a name="cmfctooltipinfom_ngradientangle"></a><a name="m_ngradientangle"></a> CMFCToolTipInfo:: m_nGradientAngle

Araç ipuçlarının arka planında çizilen bir degradenin açısını belirtir.

```
int m_nGradientAngle;
```

### <a name="remarks"></a>Açıklamalar

`m_nGradientAngle` araç ipuçlarının arka planında bulunan gradyanın yatay olarak kaydırılacağı açıyı derece cinsinden belirtir. `m_nGradientAngle`0 ise, gradyan soldan sağa çizilir. `m_nGradientAngle`1 ile 360 arasında, gradyan saat yönünde bu sayıda derece olarak döner. `m_nGradientAngle`Varsayılan değer olan-1 ise, gradyan üstten alta çizilir. Bu ayar `m_nGradientAngle` 90 ile aynıdır.

[CMFCToolTipInfo:: m_clrFill](#m_clrfill) `clrFill` degradenin başlangıcının rengini belirtir ve [CMFCToolTipInfo:: m_clrFillGradient](#m_clrfillgradient) `clrFillGradient` degradenin sonundaki rengi belirtir. `m_clrFillGradient`-1 ise gradyan yoktur.

## <a name="cmfctooltipinfom_nmaxdescrwidth"></a><a name="m_nmaxdescrwidth"></a> CMFCToolTipInfo:: m_nMaxDescrWidth

Her araç ipucunda görüntülenen açıklamanın en büyük genişliğini belirtir. Açıklama genişliği belirtilen değeri aşarsa metin sarmalanır.

```
int m_nMaxDescrWidth;
```

## <a name="cmfctooltipinfom_bvislmanagertheme"></a><a name="m_bvislmanagertheme"></a> CMFCToolTipInfo:: m_bVislManagerTheme

Uygulamanın görsel yöneticisinin tüm araç ipuçlarının görünüşünü kontrol edilip edilmeyeceğini belirtir.

```
BOOL m_bVislManagerTheme;
```

### <a name="remarks"></a>Açıklamalar

`m_bVislManagerTheme`True ise, her araç ipucu, ekranda görüntülenmeden önce uygulamanın görsel yöneticisinden yeni bir [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) ister ve görünümünü belirlemede bu nesnedeki değerleri kullanır. [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) uygulamanızın diğer üyeleri yok sayılır.

## <a name="cmfctooltipinfooperator"></a><a name="operator_eq"></a> CMFCToolTipInfo:: operator =

Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

```
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```

### <a name="parameters"></a>Parametreler

'ndaki *src*<br/>

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CTooltipManager sınıfı](../../mfc/reference/ctooltipmanager-class.md)<br/>
[CMFCToolTipCtrl sınıfı](../../mfc/reference/cmfctooltipctrl-class.md)
