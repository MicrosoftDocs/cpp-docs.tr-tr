---
title: CMFCImagePaintArea::IMAGE_EDIT_MODE Numaralandırması
ms.date: 11/04/2016
f1_keywords:
- IMAGE_EDIT_MODE Enumeration
helpviewer_keywords:
- IMAGE_EDIT_MODE Enumeration method [MFC]
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
ms.openlocfilehash: 372a1df6500f4d7219c89d8f82425246c2236514
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410180"
---
# <a name="cmfcimagepaintareaimageeditmode-enumeration"></a>CMFCImagePaintArea::IMAGE_EDIT_MODE Numaralandırması

Bir Resim Düzenleyicisi iletişim kutusunu görüntüdeki değiştirmek için kullandığınız bir çizim modunu belirtir.

## <a name="syntax"></a>Sözdizimi

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

|||
|-|-|
|Ad|Açıklama|
|IMAGE_EDIT_MODE_PEN|Tek tek her piksel çizmek için kullanılır.|
|IMAGE_EDIT_MODE_FILL|Geçerli imleç konumu rengi içeren tüm bitişik alanları doldurmak için kullanılır.|
|IMAGE_EDIT_MODE_LINE|Bir çizgi çizmek için kullanılır.|
|IMAGE_EDIT_MODE_RECT|Bir dikdörtgen çizmek için kullanılır.|
|IMAGE_EDIT_MODE_ELLIPSE|Elips çizin için kullanılır.|
|IMAGE_EDIT_MODE_COLOR|Geçerli renk geçerli İmleç konumuna rengini ayarlamak için kullanılır.|

### <a name="remarks"></a>Açıklamalar

`CMFCImagePaintArea` Ve `CMFCImageEditorDialog` sınıfları bu sabit listesi geçerli çizim modu ayarlamak için kullanın. Geçerli renk ve çizim modu, bir Resim Düzenleyicisi iletişim kutusu resim alanı değiştirmek için kullanılır. Hakkında daha fazla bilgi için `CMFCImagePaintArea` ve `CMFCImageEditorDialog`, bkz: [Cmfcımagepaintarea sınıfı](../../mfc/reference/cmfcimagepaintarea-class.md) ve [CMFCImageEditorDialog sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md).

IMAGE_EDIT_MODE_COLOR çizim modu kullanarak görüntüden bir renk seçtiğinizde, framework IMAGE_EDIT_MODE_PEN için geçerli çizim modu ayarlar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afximagepaintarea.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImagePaintArea Sınıfı](../../mfc/reference/cmfcimagepaintarea-class.md)<br/>
[CMFCImageEditorDialog Sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md)
