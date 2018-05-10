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
ms.openlocfilehash: 8bfeeda8d358bf3144cd5c3168686561b3586581
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="image-menu-image-editor-for-icons"></a>Görüntü Menüsü (Simgeler İçin Görüntü Düzenleyicisi)
Görüntü Düzenleyicisi etkin olduğunda görüntülenir, Görüntü menüsü görüntüleri düzenleme, renk paletlerini yönetme ve görüntü Düzenleyicisi penceresini seçeneklerini ayarlama komutlar vardır. Ayrıca, simgeler ve İmleçler ile çalışırken, cihaz görüntüleri kullanma komutlar kullanılabilir.  
  
 **Renkleri ters çevir**  
 Renkleri ters çevirir. Daha fazla bilgi için bkz: [seçimdeki renkleri ters çevirme](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md).  
  
 **Yatay Ters Çevir**  
 Görüntüyü veya seçimi yatay olarak döndürür. Daha fazla bilgi için bkz: [görüntüyü çevirme](../windows/flipping-an-image-image-editor-for-icons.md).  
  
 **Dikey Ters Çevir**  
 Görüntüyü veya seçimi düşey olarak döndürür. Daha fazla bilgi için bkz: [görüntüyü çevirme](../windows/flipping-an-image-image-editor-for-icons.md).  
  
 **90 derece döndürün**  
 Görüntüyü veya seçimi 90 derece döndürür. Daha fazla bilgi için bkz: [görüntüyü çevirme](../windows/flipping-an-image-image-editor-for-icons.md).  
  
 **Renkler penceresini göster**  
 Açılır [renkler penceresi](../windows/colors-window-image-editor-for-icons.md), görüntünüzü için kullanılacak renk seçebileceği içinde. Daha fazla bilgi için bkz: [renklerle çalışma](../windows/working-with-color-image-editor-for-icons.md).  
  
 **Seçim fırça olarak kullan**  
 Özel fırça görüntünün bir kısmına oluşturmanıza olanak sağlar. Seçimdeki renkleri görüntü boyunca dağıtan özel fırça seçiminizi olur. Seçimi kopyalarını sürükleme yol boyunca bırakılır. Daha yavaş sürüklediğiniz, o kadar fazla kopya yapılır. Daha fazla bilgi için bkz: [özel Fırça oluşturma](../windows/creating-a-custom-brush-image-editor-for-icons.md).  
  
 **Kopyalama ve anahat seçimi**  
 Geçerli seçim bir kopyasını oluşturur ve bunu özetler. Arka plan rengi geçerli seçim içeriyorsa, varsa onu dışlanıp [saydam](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md) seçili.  
  
 **Renkleri Ayarla**  
 Açılır [özel renk seçici](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md), görüntünüzü için kullandığınız renkleri özelleştirmenizi sağlar. Daha fazla bilgi için bkz: [özelleştirme veya değiştirme renkleri](../windows/customizing-or-changing-colors-image-editor-for-icons.md).  
  
 **Palet yükle**  
 Açılır [renk paletini Yükle iletişim kutusu](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md), daha önce .pal dosyasına kaydedilen palet renkleri yükle sağlar.  
  
 **Palet Kaydet**  
 Palet renkleri .pal dosyasına kaydeder.  
  
 **Donuk Çiz**  
 Seçili olduğunda, geçerli seçim opak yapar. Bu onay kutusu temizlendiğinde, geçerli seçim saydam yapar. Daha fazla bilgi için bkz: [donuk veya saydam arka plan seçme](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).  
  
 **Araç Çubuğu Düzenleyicisi**  
 Açılır [yeni araç çubuğu kaynağı iletişim kutusu](../windows/new-toolbar-resource-dialog-box.md).  
  
 **Kılavuz ayarları**  
 Açılır [kılavuz Ayarları iletişim kutusu](../windows/grid-settings-dialog-box-image-editor-for-icons.md) içinde belirtebilirsiniz kılavuzları görüntünüzü için.  
  
 **Yeni görüntü türü**  
 Açılır [yeni \<aygıt > görüntü türü iletişim kutusu](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md). Tek bir simge kaynak birkaç farklı boyutlarda görüntülerini içerebilir; Windows, görüntülenecek nasıl gittiğini bağlı olarak uygun simge boyutu kullanabilirsiniz. Yeni bir aygıt türü simgenin boyutunu değiştirmez, ancak bunun yerine simgesi içinde yeni bir görüntü oluşturur. Yalnızca, simgeler ve İmleçler için geçerlidir.  
  
 **Geçerli simgesini/imleç görüntü türü**  
 İlk kullanılabilir işaretçi veya simge görüntüleri (ilk dokuz) listeler bir alt açar. Alt son komutu **daha...** , açılır [açık \<aygıt > Görüntü iletişim kutusu](../windows/open-device-image-dialog-box-image-editor-for-icons.md).  
  
 **Resim türünü Sil**  
 Seçilen aygıt görüntüsünü siler.  
  
 **Araçlar**  
 Kullanılabilir tüm araçlar içeren bir alt başlatır [görüntü Düzenleyicisi araç](../windows/toolbar-image-editor-for-icons.md).  
  
## <a name="requirements"></a>Gereksinimler  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)

