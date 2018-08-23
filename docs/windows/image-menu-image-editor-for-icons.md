---
title: Görüntü menüsü (simgeler için görüntü Düzenleyicisi) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
dev_langs:
- C++
helpviewer_keywords:
- Image menu
ms.assetid: ac2b4d53-1919-4fd1-a0af-d3c085c45af2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1729f98222d0f5c2d15ae907ac464367bc39a559
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593954"
---
# <a name="image-menu-image-editor-for-icons"></a>Görüntü Menüsü (Simgeler İçin Görüntü Düzenleyicisi)

**Görüntü** yalnızca görüntülenen menü **görüntü** Düzenleyici etkin, görüntüleri düzenleme, renk paletlerini yönetmek ve ayarlamak için komutlarını **Resim Düzenleyicisi** penceresi Seçenekler. Ayrıca, simgeler ve İmleçler ile çalışırken komutları kullanarak cihaz görüntüleri için kullanılabilir.

**Renkleri ters çevir**  
Renkleri tersine çevirir. Daha fazla bilgi için [seçimdeki renkleri ters çevirme](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md).

**Yatay Çevir**  
Görüntüyü ya da seçimi yatay çevirir. Daha fazla bilgi için [görüntüyü çevirme](../windows/flipping-an-image-image-editor-for-icons.md).

**Dikey Çevir**  
Görüntüyü ya da seçimi dikey çevirir. Daha fazla bilgi için [görüntüyü çevirme](../windows/flipping-an-image-image-editor-for-icons.md).

**90 derece döndür**  
Görüntüyü ya da seçimi 90 derece çevirir. Daha fazla bilgi için [görüntüyü çevirme](../windows/flipping-an-image-image-editor-for-icons.md).

**Renkler penceresini göster**  
Açılır [renkler penceresini](../windows/colors-window-image-editor-for-icons.md), içinde görüntünüzü kullanmak için renkleri seçebilirsiniz. Daha fazla bilgi için [renklerle çalışma](../windows/working-with-color-image-editor-for-icons.md).

**Seçimi fırça olarak kullanma**  
Özel fırça görüntü bölümünden oluşturmanızı sağlar. Seçimdeki renkleri arasında görüntüyü dağıtır özel bir fırça seçiminizi olur. Seçimin bir kopyasını sürükleyerek yol boyunca bırakılır. Daha yavaş sürükleyin, kopya yapılmaz. Daha fazla bilgi için [özel Fırça oluşturma](../windows/creating-a-custom-brush-image-editor-for-icons.md).

**Kopyalama ve ana hat seçimi**  
Geçerli seçimin bir kopyasını oluşturur ve bunu açıklar. Arka plan rengi geçerli seçimse, içeriyorsa, varsa hariç tutulacaktır [saydam](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md) seçili.

**Renkleri Ayarla**  
Açılır [özel renk seçici](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md), görüntünüzü kullanmak renkleri özelleştirme sağlar. Daha fazla bilgi için [özelleştirme veya değiştirme renklerini](../windows/customizing-or-changing-colors-image-editor-for-icons.md).

**Palet yükle**  
Açılır [renk paletini Yükle iletişim kutusu](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md), daha önce .pal dosyasına kaydedildi palet renkleri yükle sağlar.

**Palet Kaydet**  
Palet renkleri .pal dosyaya kaydeder.

**Donuk Çiz**  
Bu onay kutusu seçildiğinde, geçerli seçimi opak yapar. Bu onay kutusu temizlenirse, geçerli seçimi saydam hale getirir. Daha fazla bilgi için [opak ya da saydam arka plan seçme](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).

**Araç Çubuğu Düzenleyicisi**  
Açılır [yeni araç çubuğu kaynağı iletişim kutusu](../windows/new-toolbar-resource-dialog-box.md).

**Kılavuz ayarları**  
Açılır [kılavuz Ayarları iletişim kutusu](../windows/grid-settings-dialog-box-image-editor-for-icons.md) içinde belirtebilirsiniz Kılavuzlar görüntünüzü.

**Yeni görüntü tipi**  
Açılır [yeni \<cihaz > görüntü türü iletişim kutusu](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md). Tek bir simge kaynak farklı boyutlardaki birden fazla görüntüleri içerebilir. Windows, görüntülenecek nasıl kolaylaştıracağını bağlı olarak uygun bir simge boyutu kullanabilirsiniz. Yeni bir cihaz türü simge boyutunu değiştirmez, ancak bunun yerine simgesi içinde yeni bir görüntü oluşturur. Yalnızca, simgeler ve İmleçler için geçerlidir.

**Geçerli simge/imleç görüntü tipi**  
İlk kullanılabilir işaretçi veya simge görüntüleri (ilk dokuz) listeleyen bir alt menü açılır. Son komut, alt **daha...** , açılır [açık \<cihaz > Görüntü iletişim kutusu](../windows/open-device-image-dialog-box-image-editor-for-icons.md).

**Görüntü türünü Sil**  
Seçili cihaz görüntüsünü siler.

**Araçlar**  
Kullanılabilir olan tüm araçları içeren bir alt başlatır [Resim Düzenleyicisi araç çubuğu](../windows/toolbar-image-editor-for-icons.md).

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)  
[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)