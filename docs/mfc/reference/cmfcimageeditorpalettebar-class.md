---
title: CMFCImageEditorPaletteBar Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::GetRowHeight
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable
helpviewer_keywords:
- CMFCImageEditorPaletteBar [MFC], GetRowHeight
- CMFCImageEditorPaletteBar [MFC], IsButtonExtraSizeAvailable
ms.assetid: 3fb7ba8e-f254-4d56-b913-9941b4ed8138
ms.openlocfilehash: 33d4bc0c72718d028031ac11bc67da6aec5e4907
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374421"
---
# <a name="cmfcimageeditorpalettebar-class"></a>CMFCImageEditorPaletteBar Sınıfı

Görüntü düzenleyicisi iletişim kutusuna palet çubuğu işlevselliği sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CMFCImageEditorPaletteBar : public CMFCToolBar
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Adı|Açıklama|
|[CMFCImageEditorPaletteBar::GetRowHeight](#getrowheight)|Araç çubuğu düğmelerinin yüksekliğini verir. [(CMFCToolBar geçersiz kılar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|
|[CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|Araç çubuğunun kenarlıkları uzatan düğmeleri görüntüleyip görüntüleyemeyeceğini belirler. [(Overrides CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|

### <a name="remarks"></a>Açıklamalar

Bu sınıf doğrudan kodunuzdan kullanılmak üzere tasarlanmamıştır.

Çerçeve, görüntü düzenleyicisi iletişim kutusunda bir palet çubuğu görüntülemek için bu sınıfı kullanır. Görüntü düzenleyicisi iletişim kutusu hakkında daha fazla bilgi için [CMFCImageEditorDialog Class'a](../../mfc/reference/cmfcimageeditordialog-class.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[Cpane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBa](../../mfc/reference/cmfcbasetoolbar-class.md)

[Cmfctoolbar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCImageEditorPaletteBar](../../mfc/reference/cmfcimageeditorpalettebar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afximageeditordialog.h

## <a name="cmfcimageeditorpalettebargetrowheight"></a><a name="getrowheight"></a>CMFCImageEditorPaletteBar::GetRowHeight

Araç çubuğu düğmelerinin yüksekliğini verir.

```
virtual int GetRowHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Araç çubuğundaki her düğmenin yüksekliği.

## <a name="cmfcimageeditorpalettebarisbuttonextrasizeavailable"></a><a name="isbuttonextrasizeavailable"></a>CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable

Araç çubuğunun kenarlıkları uzatan düğmeleri görüntüleyip görüntüleyemeyeceğini belirler.

```
virtual BOOL IsButtonExtraSizeAvailable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem FALSE döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImageEditorDialog Sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md)
