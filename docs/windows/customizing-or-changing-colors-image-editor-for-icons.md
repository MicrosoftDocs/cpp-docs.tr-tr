---
title: Renkleri Özelleştirme veya Değiştirme (Simgeler İçin Görüntü Düzenleyicisi)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.customcolorselector
helpviewer_keywords:
- dithered color, Image editor
- Custom Color Selector dialog box [C++]
- Image editor [C++], Colors Palette
- colors [C++], image
- bitmaps [C++], colors
- images [C++], colors
- HSL values
- Colors Palette, Image editor
- RGB color values
- Adjust Colors command [C++]
- Image editor [C++], dithered color
ms.assetid: e58f6b32-f435-4d9a-a570-7569433661ae
ms.openlocfilehash: 7ab353ad0aa22c74eeba58e9310d9bc0f8d5a832
ms.sourcegitcommit: efcc8c97570ddf7631570226c700e8f6ebb6c7be
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2019
ms.locfileid: "55560289"
---
# <a name="customizing-or-changing-colors-image-editor-for-icons"></a>Renkleri Özelleştirme veya Değiştirme (Simgeler İçin Görüntü Düzenleyicisi)

**Görüntü** düzenleyicinin [renkler paleti](../windows/colors-window-image-editor-for-icons.md) başlangıçta 16 standart renkler görüntüler. Görüntülenen renklerle kendi özel renkler de oluşturabilirsiniz. Daha sonra [kaydetme ve özelleştirilmiş renk paleti yükleme](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md).

**Özel renk seçici** iletişim kutusu, görüntünüzü kullanmak renkleri özelleştirmek tanır. Dahil edilen aşağıdaki özellikler şunlardır:

|Özellik|Açıklama|
|---|---|
|**Gradyan renk görüntüleme**|Seçili renk değerlerini değiştirir. Değiştirmek istediğiniz konumu artı işaretinin rengi. Ardından kaydırıcıyı parlaklık veya rengin RGB değerleri yukarı veya aşağı değişiklik taşıyın.|
|**Parlaklık Çubuğu**|Seçtiğiniz renk parlaklığını ayarlar **gradyan renkli görüntüyü** kutusu. Büyük parlaklık için çıtayı yukarı beyaz oku sürükleyin ya da daha az aşağı. **Renk** kutusu seçtiğiniz rengi ve ayarladığınız parlaklık etkisini gösterir.|
|**Renk**|Tanımlama renk tonunu (renk tekerleği değer) listeler. Burada 0 kırmızı, 60 sarı, 120 yeşil, mavi 180 olduğundan, 200 Eflatun ve 240 mavi 240 değerler aralığı 0.|
|**Hue**|Tanımlama renk tonunu (renk tekerleği değer) listeler. Burada 0 kırmızı, 60 sarı, 120 yeşil, mavi 180 olduğundan, 200 Eflatun ve 240 mavi 240 değerler aralığı 0.|
|**CTS**|Tanımlama renk doygunluğu değerini belirtir. Doygunluk belirtilen bir renk tonu rengi miktarıdır. Değerler aralığı 0-240.|
|**Par**|Tanımlama renk parlaklığını (Parlaklık) listeler. Değerler aralığı 0-240.|
|**Kırmızı**|Kırmızı, tanımlayacağınız renk değerini belirtir. Değerler aralığı 0-255.|
|**Yeşil**|Yeşil, tanımlayacağınız renk değerini belirtir. Değerler aralığı 0-255.|
|**Mavi**|Tanımlama rengini Mavi değerini belirtir. Değerler aralığı 0-255.|

## <a name="to-change-colors-on-the-colors-palette"></a>Renkler paleti renkleri değiştirmek için

1. Gelen **görüntü** menüsünde seçin **renkleri Ayarla**.

1. İçinde **özel renk seçici** iletişim kutusunda rengin RGB veya HSL değerleri ilgili metin kutularına yazarak tanımlayın veya bir renk seçin **gradyan renkli görüntüyü** kutusu.

1. Kaydırıcıyı hareket ettirerek parlaklık ayarlamak **parlaklık** çubuğu.

1. Birçok özel renkler Titrek. Düz renk Titremeli renk en yakın istiyorsanız çift **renk** kutusu.

   Titremeli renk istediğiniz daha sonra karar verirseniz, kaydırıcıyı taşıyın **parlaklık** çubuk veya işaretçileri taşıma **gradyan renkli görüntüyü** renk paleti öykünmesi yeniden yüklemeyi kutusu.

1. Seçin **Tamam** rengi ekleyin.

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı Tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Renklerle çalışma](../windows/working-with-color-image-editor-for-icons.md)<br/>
[Görüntü menüsü](../windows/image-menu-image-editor-for-icons.md)<br/>
[Renkler penceresi](../windows/colors-window-image-editor-for-icons.md)