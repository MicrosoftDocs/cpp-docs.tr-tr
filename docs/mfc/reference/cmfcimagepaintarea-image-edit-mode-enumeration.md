---
title: CMFCImagePaintArea::IMAGE_EDIT_MODE Numaralandırması
ms.date: 11/04/2016
f1_keywords:
- IMAGE_EDIT_MODE Enumeration
helpviewer_keywords:
- IMAGE_EDIT_MODE Enumeration method [MFC]
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
ms.openlocfilehash: 37c877cc8562a9479535d9c6132e49e7c9b7e82f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831144"
---
# <a name="cmfcimagepaintareaimage_edit_mode-enumeration"></a>CMFCImagePaintArea::IMAGE_EDIT_MODE Numaralandırması

Görüntü Düzenleyici iletişim kutusunda bir görüntüyü değiştirmek için kullandığınız çizim modunu belirtir.

## <a name="syntax"></a>Syntax

```
enum IMAGE_EDIT_MODE
{
    IMAGE_EDIT_MODE_PEN = 0,
    IMAGE_EDIT_MODE_FILL,
    IMAGE_EDIT_MODE_LINE,
    IMAGE_EDIT_MODE_RECT,
    IMAGE_EDIT_MODE_ELLIPSE,
    IMAGE_EDIT_MODE_COLOR
};
```

## <a name="members"></a>Üyeler

|Ad|Açıklama|
|-|-|
|IMAGE_EDIT_MODE_PEN|Tek pikselleri çizmek için kullanılır.|
|IMAGE_EDIT_MODE_FILL|Geçerli imleç konumundaki rengi içeren tüm bitişik alanları dolduracak şekilde kullanılır.|
|IMAGE_EDIT_MODE_LINE|Bir çizgi çizmek için kullanılır.|
|IMAGE_EDIT_MODE_RECT|Dikdörtgen çizmek için kullanılır.|
|IMAGE_EDIT_MODE_ELLIPSE|Elips çizmek için kullanılır.|
|IMAGE_EDIT_MODE_COLOR|Geçerli rengi geçerli imleç konumundaki renge ayarlamak için kullanılır.|

### <a name="remarks"></a>Açıklamalar

`CMFCImagePaintArea`Ve `CMFCImageEditorDialog` sınıfları, bu sabit listesini geçerli çizim modunu ayarlamak için kullanır. Çizim modu ve geçerli renk, görüntü Düzenleyici iletişim kutusunda resim alanını değiştirmek için kullanılır. Ve hakkında daha fazla bilgi için `CMFCImagePaintArea` `CMFCImageEditorDialog` bkz. [CMFCImagePaintArea Class](../../mfc/reference/cmfcimagepaintarea-class.md) and [CMFCImageEditorDialog sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md).

IMAGE_EDIT_MODE_COLOR çizim modunu kullanarak bir görüntüden renk seçtiğinizde, çerçeve geçerli çizim modunu IMAGE_EDIT_MODE_PEN olarak ayarlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afximagepaintarea. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImagePaintArea sınıfı](../../mfc/reference/cmfcimagepaintarea-class.md)<br/>
[CMFCImageEditorDialog sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md)
