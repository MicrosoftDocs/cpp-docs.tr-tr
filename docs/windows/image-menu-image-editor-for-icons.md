---
title: Görüntü menüsü (simgeler için görüntü Düzenleyicisi C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.bitmap
- vc.editors.dialog.GridSettings
- vc.editors.gridsettings
helpviewer_keywords:
- Image menu
- Grid Settings dialog box [C++]
ms.assetid: ac2b4d53-1919-4fd1-a0af-d3c085c45af2
ms.openlocfilehash: e7d7d92401d5910cbb8aba8ab4c6000eca45cb01
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849736"
---
# <a name="image-menu-c-image-editor-for-icons"></a>Görüntü menüsü (simgeler için görüntü Düzenleyicisi C++)

**Görüntü** yalnızca görüntülenen menü **görüntü** Düzenleyici etkin, görüntüleri düzenleme, renk paletlerini yönetmek ve ayarlamak için komutlarını **Resim Düzenleyicisi** penceresi Seçenekler. Ayrıca, simgeler ve İmleçler ile çalışırken komutları kullanarak cihaz görüntüleri için kullanılabilir.

|Komut|Açıklama|
|---|---|
|**Renkleri ters çevir**|Renkleri tersine çevirir. Daha fazla bilgi için [seçimdeki renkleri ters çevirme](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md).|
|**Yatay Çevir**|Görüntüyü ya da seçimi yatay çevirir. Daha fazla bilgi için [görüntüyü çevirme](../windows/flipping-an-image-image-editor-for-icons.md).|
|**Dikey Çevir**|Görüntüyü ya da seçimi dikey çevirir. Daha fazla bilgi için [görüntüyü çevirme](../windows/flipping-an-image-image-editor-for-icons.md).|
|**90 derece döndür**|Görüntüyü ya da seçimi 90 derece çevirir. Daha fazla bilgi için [görüntüyü çevirme](../windows/flipping-an-image-image-editor-for-icons.md).|
|**Renkler penceresini göster**|Açılır [renkler penceresini](../windows/colors-window-image-editor-for-icons.md), içinde görüntünüzü kullanmak için renkleri seçebilirsiniz. Daha fazla bilgi için [renklerle çalışma](../windows/working-with-color-image-editor-for-icons.md).|
|**Seçimi fırça olarak kullanma**|Özel fırça görüntü bölümünden oluşturmanızı sağlar. Seçimdeki renkleri arasında görüntüyü dağıtır özel bir fırça seçiminizi olur. Seçimin bir kopyasını sürükleyerek yol boyunca bırakılır. Daha yavaş sürükleyin, kopya yapılmaz. Daha fazla bilgi için [özel Fırça oluşturma](../windows/creating-a-custom-brush-image-editor-for-icons.md).|
|**Kopyalama ve ana hat seçimi**|Geçerli seçimin bir kopyasını oluşturur ve bunu açıklar. Arka plan rengi geçerli seçimse, içeriyorsa, belirttiyseniz hariç tutulacaktır [saydam](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md) seçili.
|**Renkleri Ayarla**|Açılır [özel renk seçici](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md), görüntünüzü kullanmak renkleri özelleştirme sağlar. Daha fazla bilgi için [özelleştirme veya değiştirme renklerini](../windows/customizing-or-changing-colors-image-editor-for-icons.md).|
|**Palet yükle**|Açılır [renk paletini Yükle iletişim kutusu](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md), daha önce .pal dosyasına kaydedildi palet renkleri yükle sağlar.|
|**Palet Kaydet**|Palet renkleri .pal dosyaya kaydeder.|
|**Donuk Çiz**|Bu onay kutusu seçildiğinde, geçerli seçimi opak yapar. Bu onay kutusu temizlenirse, geçerli seçimi saydam hale getirir. Daha fazla bilgi için [opak ya da saydam arka plan seçme](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).|
|**Araç Çubuğu Düzenleyicisi**|Açılır [yeni araç çubuğu kaynağı iletişim kutusu](../windows/new-toolbar-resource-dialog-box.md).|
|**Kılavuz ayarları**|Açılır **Kılavuz ayarları** içinde belirtebilirsiniz Kılavuzlar görüntünüzü iletişim kutusu.|
|**Yeni görüntü tipi**|Açılır [yeni \<cihaz > görüntü türü iletişim kutusu](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md). Tek bir simge kaynak birkaç görüntüyü farklı boyutlardaki içerebilir ve windows görüntülenecek nasıl kolaylaştıracağını bağlı olarak uygun bir simge boyutu kullanabilirsiniz. Yeni bir cihaz türü simge boyutunu değiştirmez, ancak bunun yerine simgesi içinde yeni bir görüntü oluşturur. Yalnızca, simgeler ve İmleçler için geçerlidir.|
|**Geçerli simge/imleç görüntü tipi**|İlk kullanılabilir işaretçi veya simge görüntüleri (ilk dokuz) listeleyen bir alt menü açılır. Son komut, alt **daha...** , açılır [açık \<cihaz > Görüntü iletişim kutusu](../windows/open-device-image-dialog-box-image-editor-for-icons.md).|
|**Görüntü türünü Sil**|Seçili cihaz görüntüsünü siler.|
|**Araçlar**|Kullanılabilir olan tüm araçları içeren bir alt başlatır [Resim Düzenleyicisi araç çubuğu](../windows/toolbar-image-editor-for-icons.md).|

**Kılavuz ayarları** iletişim kutusunda, görüntünüzü için kılavuz ayarları belirtmenize olanak tanır ve düzenlenen görüntüsünden kılavuz çizgilerini görüntüler. Satırları düzenleme görüntüsü için yararlıdır, ancak görüntünün kendisi bir parçası olarak kaydedilmez.

|Özellik|Açıklama|
|---|---|
|**Piksel Kılavuzu**|Bu onay kutusu işaretlendiğinde, her pikselin çevresindeki bir kılavuz Resim Düzenleyicisi'nde görüntüler. Kılavuz, yalnızca 4 × ve daha yüksek çözünürlüklerde görünür.|
|**Döşeme**|Seçili olduğunda, görüntü düzenleyicisinde kılavuz aralık değerleri tarafından belirtilen blokları piksel etrafında bir kılavuz görüntüler.|
|**Genişlik**|Her kutucuk bloğunun genişliğini belirtir. Bu özellik, düzenli aralıklarla düzenlenmiş birden fazla görüntü içeren bir bit eşlem yeniden çizilirken yararlıdır.|
|**Yükseklik**|Her kutucuk blok yüksekliğini belirtir. Bu özellik, düzenli aralıklarla düzenlenmiş birden fazla görüntü içeren bir bit eşlem yeniden çizilirken yararlıdır.|

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca bkz.

[Hızlandırıcı Tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Görüntüyü yeniden boyutlandırma](../windows/resizing-an-image-image-editor-for-icons.md)<br/>
[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)