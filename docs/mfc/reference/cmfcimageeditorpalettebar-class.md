---
title: Cmfcımageeditorpalettebar sınıfı
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
ms.openlocfilehash: 6812f3f425186484ef892d7f5c626c0dfce0f863
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302994"
---
# <a name="cmfcimageeditorpalettebar-class"></a>Cmfcımageeditorpalettebar sınıfı

Bir Resim Düzenleyicisi iletişim kutusu için palet çubuğu işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CMFCImageEditorPaletteBar : public CMFCToolBar
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Ad|Açıklama|
|[CMFCImageEditorPaletteBar::GetRowHeight](#getrowheight)|Araç çubuğu düğmeleri yüksekliğini döndürür. (Geçersiz kılmaları [CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight).)|
|[CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|Araç çubuğu kenarlık genişletilmiş düğmeleri görüntüleyip görüntülemeyeceğini belirler. (Geçersiz kılmaları [CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable).)|

### <a name="remarks"></a>Açıklamalar

Bu sınıf doğrudan sizin kodunuzdan kullanılmak üzere tasarlanmamıştır.

Framework, bir Resim Düzenleyicisi iletişim kutusunda bir palet çubuğunu görüntülemek için bu sınıfı kullanır. Resim Düzenleyicisi iletişim kutusu hakkında daha fazla bilgi için bkz. [CMFCImageEditorDialog sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md).

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

**Başlık:** afximageeditordialog.h

##  <a name="getrowheight"></a>  CMFCImageEditorPaletteBar::GetRowHeight

Araç çubuğu düğmeleri yüksekliğini döndürür.

```
virtual int GetRowHeight() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her araç çubuğunda yüksekliği.

##  <a name="isbuttonextrasizeavailable"></a>  CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable

Araç çubuğu kenarlık genişletilmiş düğmeleri görüntüleyip görüntülemeyeceğini belirler.

```
virtual BOOL IsButtonExtraSizeAvailable() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem FALSE döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImageEditorDialog Sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md)
