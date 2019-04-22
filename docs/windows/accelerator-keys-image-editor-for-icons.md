---
title: Hızlandırma tuşları (simgeler için görüntü Düzenleyicisi C++)
ms.date: 02/15/2019
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
helpviewer_keywords:
- accelerator keys
- Image editor [C++], accelerator keys
ms.assetid: add37861-3e17-4a6f-89e8-46df12e74a90
ms.openlocfilehash: 45afdf4b3b557b560d7597b1bb4330c36a1fc84d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025091"
---
# <a name="accelerator-keys-c-image-editor-for-icons"></a>Hızlandırma tuşları (simgeler için görüntü Düzenleyicisi C++)

Anahtarlar için varsayılan olarak bağlı olan Resim Düzenleyicisi komutları için hızlandırma tuşları aşağıdadır. Hızlandırıcı tuşları değiştirmek için menüsüne gidin **Araçları** > **seçenekleri** ve **klavye** altında **ortam** klasör. Daha fazla bilgi için [tanımlama ve özelleştirme klavye kısayolları](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).

> [!NOTE]
> İletişim kutuları, adları ve konumları gördüğünüz gibi menü komutlarının Seçenekleri Yardımı'nda, etkin ayarlarınıza ve sürüm bağlı olarak açıklanan nedir öğesinden farklı olabilir. Ayarlarınızı değiştirmek için menüsüne gidin **Araçları** > **içeri ve dışarı aktarma ayarları**. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).

|Komut|anahtarları|Açıklama|
|-------------|----------|-----------------|
|Image.AirBrushTool|**CTRL** + **A**|Seçili boyuta ve renge sahip püskürtme kabı kullanarak çizer.|
|Image.BrushTool|**CTRL** + **B**|Seçilen şekle, boyutu ve rengi bir fırça kullanarak çizer.|
|Image.CopyAndOutlineSelection|**CTRL** + **Shift** + **U**|Geçerli seçimin bir kopyasını oluşturur ve bunu açıklar. Arka plan rengi geçerli seçimse, içeriyorsa, varsa hariç tutulacaktır [saydam](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md) seçili.|
|Image.DrawOpaque|**CTRL** + **J**|Geçerli seçimi ya da yapar [opak ya da şeffaf](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).|
|Image.EllipseTool|**CTRL** + **P**|Seçilen çizgi genişliği ve rengine sahip bir elips çizer.|
|Image.EraserTool|**CTRL** + **Shift** + **ediyorum**|Bir kısmını (geçerli arka plan rengiyle) görüntüyü siler.|
|Image.FilledEllipseTool|**CTRL** + **Shift** + **Alt** + **P**|Dolu bir elips çizer.|
|Image.FilledRectangleTool|**CTRL** + **Shift** + **Alt** + **R**|Dolu bir dikdörtgen çizer.|
|Image.FilledRoundRectangleTool|**CTRL** + **Shift** + **Alt** + **W**|Dolu bir Yuvarlatılmış dikdörtgen çizer.|
|Image.FillTool|**CTRL** + **F**|Bir alan doldurur.|
|Image.FlipHorizontal|**CTRL** + **H**|Görüntüyü ya da seçimi yatay çevirir.|
|Image.FlipVertical|**Shift**+ **Alt** + **H**|Görüntüyü ya da seçimi dikey çevirir.|
|Image.LargerBrush|**CTRL** + **=**|Fırça boyutunu her yönde bir piksel artırır. Fırça boyutunu azaltmak için bu tablodaki Image.smallerbrush'a bakın.|
|Image.LineTool|**CTRL** + **m**|Seçilen şekle, boyutu ve rengi düz bir çizgi çizer.|
|Image.MagnificationTool|**CTRL** + **M**|Etkinleştirir **Magnıfy** görüntünüzün belirli bölümlerini büyütmenize izin veren bir araç.|
|Image.Magnify|**CTRL** + **Shift** + **M**|Geçerli büyütme ve 1:1 büyütme arasında geçiş yapar.|
|Image.NewImageType|**Ekle**|Başlatan [yeni \<cihaz > görüntü türü iletişim kutusu](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md) ile farklı bir görüntü türü için bir görüntü oluşturabilirsiniz.|
|Image.NextColor|**CTRL** + **]**<br /><br /> - veya -<br /><br /> **CTRL** + **sağ ok**|Çizim ön plan rengini sonraki palet rengine değiştirir.|
|Image.NextRightColor|**CTRL** + **Shift** + **]**<br /><br /> - veya -<br /><br /> **Shift** + **Ctrl** + **sağ ok**|Çizim arkaplan rengini sonraki palet rengine değiştirir.|
|Image.OutlinedEllipseTool|**Shift** + **Alt** + **P**|Bir dış dolu bir elips çizer.|
|Image.OutlinedRectangleTool|**Shift** + **Alt** + **R**|Bir dış dolu bir dikdörtgen çizer.|
|Image.OutlinedRoundRectangleTool|**Shift** + **Alt** + **W**|Bir dış dolu bir Yuvarlatılmış dikdörtgen çizer.|
|Image.PencilTool|**CTRL** + **ediyorum**|Tek piksellik bir kalem kullanarak çizer.|
|Image.PreviousColor|**Ctrl** + **[**<br /><br /> - veya -<br /><br /> **CTRL** + **sol ok**|Çizim ön plan rengini önceki palet rengine değiştirir.|
|Image.PreviousRightColor|**CTRL** + **Shift** + **[**<br /><br /> - veya -<br /><br /> **Shift** + **Ctrl** + **sol ok**|Çizim arkaplan rengini önceki palet rengine değiştirir.|
|Image.RectangleSelectionTool|**Shift** + **Alt** + **S**|Taşıma, kopyalama veya düzenlemek üzere görüntünün dikdörtgen bir bölümünü seçer.|
|Image.RectangleTool|ATL + R|Seçilen çizgi genişliği ve rengine sahip bir dikdörtgen çizer.|
|Image.Rotate90Degrees|**CTRL** + **Shift** + **H**|Görüntüyü ya da seçimi 90 derece çevirir.|
|Image.RoundedRectangleTool|**Alt** + **W**|Seçilen çizgi genişliği ve rengine sahip bir Yuvarlatılmış dikdörtgen çizer.|
|Image.ShowGrid|**CTRL** + **Alt** + **S**|Piksel kılavuzunu açıp kapatır (seçer veya temizler **piksel kılavuzunu** seçeneğini [kılavuz Ayarları iletişim kutusu](../windows/grid-settings-dialog-box-image-editor-for-icons.md)).|
|Image.ShowTileGrid|**CTRL** + **Shift** + **Alt** + **S**|Döşeme kılavuzunu açıp kapatır (seçer veya temizler **döşeme** seçeneğini [kılavuz Ayarları iletişim kutusu](../windows/grid-settings-dialog-box-image-editor-for-icons.md)).|
|Image.SmallBrush|**Ctrl** + **.** (nokta)|Azaltır **fırça** boyutunu bir piksele. (Ayrıca Image.largerbrush ve Image.smallerbrush bu tabloya bakın.)|
|Image.SmallerBrush|**CTRL**  +  **-** (eksi)|Fırça boyutunu her yönde bir piksel azaltır. Fırça boyutunu tekrar artırmak için bu tablodaki Image.largerbrush'a bakın.|
|Image.TextTool|**CTRL** + **T**|Açılır [metin aracı iletişim kutusu](../windows/text-tool-dialog-box-image-editor-for-icons.md).|
|Image.UseSelectionAsBrush|**CTRL** + **U**|Geçerli seçimi bir fırça gibi kullanarak çizer.|
|Image.ZoomIn|**CTRL** + **Shift** + **.** (nokta)<br /><br /> - veya -<br /><br /> **CTRL** + **yukarı ok**|Geçerli görünümün büyütmesini artırır.|
|Image.ZoomOut|**CTRL** + **,** (virgül)<br /><br /> - veya -<br /><br /> **CTRL** + **aşağı ok**|Geçerli görünümün büyütmesini azaltır.|

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca bkz.

[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)<br/>
[Nasıl yapılır: Simge veya Başka Görüntü Oluşturma](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[Nasıl yapılır: Görüntü Kopyalama](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[Nasıl yapılır: Çizim Aracı Kullanma](../windows/using-a-drawing-tool-image-editor-for-icons.md)<br/>
[Nasıl yapılır: Renklerle Çalışma](../windows/working-with-color-image-editor-for-icons.md)<br/>