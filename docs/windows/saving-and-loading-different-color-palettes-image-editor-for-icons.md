---
title: Farklı Renk Paletlerini Kaydetme ve Yükleme (Simgeler İçin Görüntü Düzenleyicisi)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.image.color
- vc.editors.loadcolorpalette
helpviewer_keywords:
- color palettes [C++]
- palettes
- palettes, Image editor
- colors [C++], Image editor
- Image editor [C++], palettes
- color palettes
- Load Palette Colors dialog box [C++]
ms.assetid: 694b6346-e606-4f19-aa01-9b4ceb47f423
ms.openlocfilehash: fd2664407d33d8e3ed594921501b7f80e6c8850b
ms.sourcegitcommit: efcc8c97570ddf7631570226c700e8f6ebb6c7be
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2019
ms.locfileid: "55560276"
---
# <a name="saving-and-loading-different-color-palettes-image-editor-for-icons"></a>Farklı Renk Paletlerini Kaydetme ve Yükleme (Simgeler İçin Görüntü Düzenleyicisi)

Kaydet ve yük bir **renkleri** içeren palet [renkleri özelleştirilmiş](../windows/customizing-or-changing-colors-image-editor-for-icons.md). (Varsayılan olarak, **renkleri** en son kullanılan palet Visual Studio'yu başlattığınızda otomatik olarak yüklenir.)

> [!TIP]
> Bu yana **görüntü** Düzenleyicisi olan varsayılan geri yüklemek için anlamına gelir **renkleri** paleti varsayılan kaydetmelisiniz **renkleri** palet gibi bir ad altında  *Standard.PAL* veya *default.pal* böylece bir kolayca varsayılan ayarları geri yükleyebilirsiniz.

Kullanma **palet renkleri Yükle** C++ projenizde kullanılacak özel renk paletlerini yüklemek için iletişim kutusu. Dahil edilen aşağıdaki özellikler şunlardır:

|Özellik|Açıklama|
|---|---|
|**İçine bak**|Bir dosya veya klasörü bulmak için istediğiniz konumu belirtir. Başka bir konum seçmek için oku seçin veya düzeyleri yukarı taşımak için araç çubuğundaki klasör simgesini seçin.|
|**Dosya adı**|Açmak istediğiniz dosyanın adını yazmanız için bir alan sağlar. Hızlıca önceden açmış olduğunuz dosyayı bulmak için varsa aşağı açılan listede, dosya adı seçin.<br/><br/>Bir dosya için arıyorsanız, joker karakter olarak yıldız işareti (*) kullanabilirsiniz. Örneğin, yazabilirsiniz \*.\* tüm dosyaların listesini görmek için. Ayrıca, örneğin, C:\My Documents\MyColorPalette.pal dosyasının tam yolunu yazın veya \\\NetworkServer\MyFolder\MyColorPalette.pal.|
|**Dosya türü**|Görüntülenecek dosya türlerini listeler. Palet (* .pal) renk paletlerini için varsayılan dosya türüdür.|

## <a name="to-save-a-custom-colors-palette"></a>Özel renkler paleti kaydetmek için

1. Gelen **görüntü** menüsünde seçin **Kaydet palet**.

1. Palet kaydetmek istediğiniz dizine gidin ve palet için bir ad yazın.

1. **Kaydet**’i seçin.

## <a name="to-load-a-custom-colors-palette"></a>Özel renkler paleti yüklemek için

1. Gelen **görüntü** menüsünde seçin **palet Yükle**.

1. İçinde **renk paletini yük** iletişim kutusunda doğru dizine gidin ve yüklemek istediğiniz paletini seçin. **Renk** paletleri .pal dosya uzantısıyla kaydedilir.

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı Tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Renklerle çalışma](../windows/working-with-color-image-editor-for-icons.md)<br/>
[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)