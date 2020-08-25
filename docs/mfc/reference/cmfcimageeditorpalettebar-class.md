---
title: CMFCImageEditorPaletteBar sınıfı
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
ms.openlocfilehash: 007fa94269a6a42bf076d2d75a18860896503aa1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831170"
---
# <a name="cmfcimageeditorpalettebar-class"></a>CMFCImageEditorPaletteBar sınıfı

Bir görüntü Düzenleyici iletişim kutusuna palet Bar işlevselliği sağlar.

## <a name="syntax"></a>Syntax

```
class CMFCImageEditorPaletteBar : public CMFCToolBar
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|-|-|
|[CMFCImageEditorPaletteBar:: GetRowHeight](#getrowheight)|Araç çubuğu düğmelerinin yüksekliğini döndürür. ( [CMFCToolBar:: GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|
|[CMFCImageEditorPaletteBar:: IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|Araç çubuğunun genişletilmiş kenarlıkları olan düğmeleri görüntüleyip görüntülemeyeceğini belirler. ( [CMFCToolBar:: IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).) öğesini geçersiz kılar|

### <a name="remarks"></a>Açıklamalar

Bu sınıf doğrudan kodunuzdan kullanılmaya yönelik değildir.

Framework, bir resim Düzenleyicisi iletişim kutusunda bir palet çubuğunu göstermek için bu sınıfı kullanır. Görüntü Düzenleyicisi iletişim kutusu hakkında daha fazla bilgi için bkz. [CMFCImageEditorDialog sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBa](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCImageEditorPaletteBar](../../mfc/reference/cmfcimageeditorpalettebar-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afximageeditordialog. h

## <a name="cmfcimageeditorpalettebargetrowheight"></a><a name="getrowheight"></a> CMFCImageEditorPaletteBar:: GetRowHeight

Araç çubuğu düğmelerinin yüksekliğini döndürür.

```
virtual int GetRowHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Araç çubuğundaki her düğmenin yüksekliği.

## <a name="cmfcimageeditorpalettebarisbuttonextrasizeavailable"></a><a name="isbuttonextrasizeavailable"></a> CMFCImageEditorPaletteBar:: IsButtonExtraSizeAvailable

Araç çubuğunun genişletilmiş kenarlıkları olan düğmeleri görüntüleyip görüntülemeyeceğini belirler.

```
virtual BOOL IsButtonExtraSizeAvailable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem FALSE döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImageEditorDialog sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md)
