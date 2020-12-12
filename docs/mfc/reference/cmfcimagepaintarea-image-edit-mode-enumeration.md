---
description: 'Hakkında daha fazla bilgi edinin: CMFCImagePaintArea:: IMAGE_EDIT_MODE numaralandırması'
title: CMFCImagePaintArea::IMAGE_EDIT_MODE Numaralandırması
ms.date: 11/04/2016
f1_keywords:
- IMAGE_EDIT_MODE Enumeration
helpviewer_keywords:
- IMAGE_EDIT_MODE Enumeration method [MFC]
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
ms.openlocfilehash: f28880d108be8fb4f2b14ede1a3cbd3c7dac9f2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265330"
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
