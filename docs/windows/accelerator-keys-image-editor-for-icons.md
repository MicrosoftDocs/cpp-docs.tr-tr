---
title: Hızlandırıcı tuşları (simgeler için C++ görüntü Düzenleyicisi)
ms.date: 02/15/2019
helpviewer_keywords:
- accelerator keys
- Image editor [C++], accelerator keys
ms.assetid: add37861-3e17-4a6f-89e8-46df12e74a90
ms.openlocfilehash: 0f54b244526bbda878dd75b0e1ca97a89d680ea6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622001"
---
# <a name="accelerator-keys-c-image-editor-for-icons"></a>Hızlandırıcı tuşları (simgeler için C++ görüntü Düzenleyicisi)

Aşağıda varsayılan olarak anahtarlara bağlanan resim Düzenleyicisi komutlarının kısayol tuşları bulunur. Hızlandırıcı tuşlarını değiştirmek için menü **araçları**  >  **Seçenekler** ' e gidin ve ortam klasörü altında **klavye** ' **yi** seçin. Daha fazla bilgi için bkz. [klavye kısayollarını tanımlama ve özelleştirme](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio).

> [!NOTE]
> İletişim kutularında kullanılabilen seçenekler ve gördüğünüz menü komutlarının adları ve konumları, etkin ayarlarınıza veya sürümüne bağlı olarak yardım altında açıklananlar arasından farklılık gösterebilir. Ayarlarınızı değiştirmek için menü **araçları**  >  **içeri ve dışarı aktarma ayarları**' na gidin. Daha fazla bilgi için bkz. [Visual STUDIO IDE 'Yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).

|Komut|Anahtarlar|Açıklama|
|-------------|----------|-----------------|
|Image. Airbrühtool|**CTRL**  +  **Bir**|Seçili boyut ve renge sahip bir püskürtme kabı kullanarak çizer.|
|Image.BrushTool|**CTRL**  +  **B**|Seçili şekil, boyut ve renge sahip bir fırça kullanarak çizer.|
|Image. CopyAndOutlineSelection|**CTRL**  +  **SHIFT**  +  **U**|Geçerli seçimin bir kopyasını oluşturur ve bu seçimi özetler. Arka plan rengi geçerli seçimde yer alıyorsa, [saydam](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md) seçiliyse, bu, dışarıda bırakılır.|
|Image.DrawOpaque|**CTRL**  +  **J**|Geçerli seçimi [donuk ya da saydam](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)yapar.|
|Image.EllipseTool|**CTRL**  +  **P**|Seçilen çizgi genişliği ve rengine sahip bir elips çizer.|
|Image. silinebilir Sertool|**CTRL**  +  **SHIFT**  +  **Ben**|Görüntünün bir bölümünü siler (geçerli arka plan rengiyle).|
|Image.FilledEllipseTool|**CTRL**  +  **SHIFT**  +  **Alt**  +  **P**|Dolgulu bir elips çizer.|
|Image.FilledRectangleTool|**CTRL**  +  **SHIFT**  +  **Alt**  +  **R**|Dolgulu bir dikdörtgen çizer.|
|Image. FilledRoundRectangleTool|**CTRL**  +  **SHIFT**  +  **Alt**  +  **W**|Dolgulu yuvarlak bir dikdörtgen çizer.|
|Image.FillTool|**CTRL**  +  **F**|Bir alanı doldurur.|
|Image.FlipHorizontal|**CTRL**  +  **H**|Görüntüyü veya seçimi yatay olarak çevirir.|
|Image.FlipVertical|**SHIFT** +  **Alt**  +  **H**|Görüntüyü veya seçimi dikey olarak çevirir.|
|Image.LargerBrush|**T** + **=**|Fırça boyutunu her yönde bir piksel artırır. Fırça boyutunu azaltmak için bu tablodaki Image. SmallerBrush başlığına bakın.|
|Image.LineTool|**CTRL**  +  **L**|Seçili şekil, boyut ve renge sahip düz bir çizgi çizer.|
|Image.MagnificationTool|**CTRL**  +  **A**|Görüntünüzün belirli bölümlerini büyütme yapmanıza olanak sağlayan **büyütme** aracını etkinleştirir.|
|Image.Magnify|**CTRL**  +  **SHIFT**  +  **A**|Geçerli büyütme ve 1:1 büyütme arasında geçiş yapar.|
|Image.NewImageType|**Ekle**|Farklı bir görüntü türü için görüntü oluşturabileceğiniz [Yeni \<Device> görüntü türü iletişim kutusunu](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md) başlatır.|
|Image.NextColor|**CTRL**  +  **]**<br /><br /> - veya -<br /><br /> **CTRL**  +  **Sağ ok**|Çizim ön plan rengini sonraki palet rengine değiştirir.|
|Image.NextRightColor|**CTRL**  +  **SHIFT**  +  **]**<br /><br /> - veya -<br /><br /> **SHIFT**  +  **CTRL**  +  **Sağ ok**|Çizim arka plan rengini sonraki palet rengine değiştirir.|
|Image.OutlinedEllipseTool|**SHIFT**  +  **Alt**  +  **P**|Ana hatlarıyla doldurulmuş bir elips çizer.|
|Image.OutlinedRectangleTool|**SHIFT**  +  **Alt**  +  **R**|Anahatsız doldurulmuş bir dikdörtgen çizer|
|Image. OutlinedRoundRectangleTool|**SHIFT**  +  **Alt**  +  **W**|Anahatlarla doldurulmuş yuvarlak bir dikdörtgen çizer.|
|Image.PencilTool|**CTRL**  +  **Ben**|Tek piksellik Kurşun kalem kullanarak çizer.|
|Image.PreviousColor|**CTRL**  +  **[**<br /><br /> - veya -<br /><br /> **CTRL**  +  **Sol ok**|Çizim ön plan rengini önceki palet rengine değiştirir.|
|Image.PreviousRightColor|**CTRL**  +  **SHIFT**  +  **[**<br /><br /> - veya -<br /><br /> **SHIFT**  +  **CTRL**  +  **Sol ok**|Çizim arka plan rengini önceki palet rengine değiştirir.|
|Image.RectangleSelectionTool|**SHIFT**  +  **Alt**  +  **S**|Taşımak, kopyalamak veya düzenlemek için görüntünün dikdörtgen bir kısmını seçer.|
|Image.RectangleTool|ATL + R|Seçilen çizgi genişliği ve rengine sahip bir dikdörtgen çizer.|
|Image.Rotate90Degrees|**CTRL**  +  **SHIFT**  +  **H**|Görüntüyü veya seçimi 90 derece döndürür.|
|Image.RoundedRectangleTool|**Alt**  +  **W**|Seçilen çizgi genişliği ve rengine sahip yuvarlak bir dikdörtgen çizer.|
|Image.ShowGrid|**CTRL**  +  **Alt**  +  **S**|Piksel kılavuzuna geçiş yapar ( [Kılavuz ayarları iletişim kutusundaki](../windows/grid-settings-dialog-box-image-editor-for-icons.md) **piksel kılavuz** seçeneğini seçer veya temizler).|
|Image.ShowTileGrid|**CTRL**  +  **SHIFT**  +  **Alt**  +  **S**|Döşeme kılavuzuna geçiş yapar ( [Kılavuz ayarları iletişim kutusunda](../windows/grid-settings-dialog-box-image-editor-for-icons.md) **döşeme kılavuz** seçeneğini seçer veya temizler).|
|Image.SmallBrush|**CTRL**  +  **.** (nokta)|**Fırça** boyutunu bir piksel azaltır. (Ayrıca bkz. bu tablodaki Image. LargerBrush ve Image. SmallerBrush.)|
|Image.SmallerBrush|**Ctrl**  +  CTRL **-** dakini|Fırça boyutunu her yönde bir piksel azaltır. Fırça boyutunu yeniden genişletmek için bu tablodaki Image. LargerBrush bölümüne bakın.|
|Image.TextTool|**CTRL**  +  **T**|[Metin aracı iletişim kutusunu](../windows/text-tool-dialog-box-image-editor-for-icons.md)açar.|
|Image. UseSelectionAsBrush|**CTRL**  +  **U**|Geçerli seçimi fırça olarak kullanarak çizer.|
|Image.ZoomIn|**CTRL**  +  **SHIFT**  +  **.** (nokta)<br /><br /> - veya -<br /><br /> **CTRL**  +  **Yukarı ok**|Geçerli görünüm için büyütmeyi artırır.|
|Image.ZoomOut|**CTRL**  +  **,** (virgül)<br /><br /> - veya -<br /><br /> **CTRL**  +  **Aşağı ok**|Geçerli görünümün büyütme oranını azaltır.|

## <a name="requirements"></a>Gereksinimler

Yok

## <a name="see-also"></a>Ayrıca bkz.

[Simgeler için görüntü Düzenleyicisi](image-editor-for-icons.md)<br/>
[Nasıl yapılır: simge veya başka görüntü oluşturma](creating-an-icon-or-other-image-image-editor-for-icons.md)<br/>
[Nasıl yapılır: görüntü düzenleme](selecting-an-area-of-an-image-image-editor-for-icons.md)<br/>
[Nasıl yapılır: çizim aracını kullanma](using-a-drawing-tool-image-editor-for-icons.md)<br/>
[Nasıl yapılır: renklerle çalışma](working-with-color-image-editor-for-icons.md)<br/>
