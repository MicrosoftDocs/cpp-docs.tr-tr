---
title: Cmfcımagepaintarea::ımage_edıt_mode numaralandırması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- IMAGE_EDIT_MODE Enumeration
dev_langs:
- C++
helpviewer_keywords:
- IMAGE_EDIT_MODE Enumeration method [MFC]
ms.assetid: e51db66a-fa1c-4766-9dac-a25b595f871a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 913a87383e617f331043751c4e3089acac744c7f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374650"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCImagePaintArea Sınıfı](../../mfc/reference/cmfcimagepaintarea-class.md)<br/>
[CMFCImageEditorDialog Sınıfı](../../mfc/reference/cmfcimageeditordialog-class.md)
