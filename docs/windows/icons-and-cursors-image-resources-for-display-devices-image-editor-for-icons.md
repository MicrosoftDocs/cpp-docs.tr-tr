---
title: 'Simgeler ve İmleçler: görüntüleme cihazları (simgeler için görüntü Düzenleyicisi) için görüntü kaynakları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- cursors [C++], creating
- image resources, display devices
- icons [C++], creating
- cursors [C++], types
- icons [C++]
- Image editor [C++], icons and cursors
- cursors [C++]
- display devices, creating icons for
- cursors [C++], hot spots
- icons [C++], types
ms.assetid: 8f0809a8-0cf0-4da9-b23d-51f28bf15f5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a977629cbae140afa1463a7765f193a7519e1f68
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons"></a>Simgeler ve İmleçler: Görüntüleme Cihazları için Görüntü Kaynakları (Simgeler İçin Görüntü Düzenleyicisi)
Simgeler ve İmleçler farklı boyutlarda birden fazla görüntü içeren ve renk düzenleri farklı türlerdeki görüntüleme cihazları için grafik kaynaklardır. Ayrıca, bir imleç "etkin nokta," Windows konumunu izlemek için kullandığı konumun sahiptir. Simgeler ve İmleçler oluşturulur ve görüntü Düzenleyicisi'ni kullanarak, bit eşlemler ve diğer görüntüleri gibi düzenlenebilir.  
  
 Yeni simgesi veya imleci oluşturduğunuzda, görüntü Düzenleyicisi ilk standart türü görüntüsü oluşturur. Görüntü başlangıçta ekran (saydam) renkle doldurulur. Görüntünün bir imleç etkin nokta başlangıçta sol üst köşesindeki (koordinatları 0,0) ise.  
  
 Varsayılan olarak, görüntü Düzenleyicisi, aşağıdaki tabloda gösterilen cihazlar için ek görüntüleri oluşturulmasını destekler. Genişlik, yükseklik ve renk sayısı parametreleri içine yazarak diğer cihazlar için görüntüleri oluşturabilirsiniz [özel görüntü iletişim kutusu](custom-image-dialog-box-image-editor-for-icons.md).  
  
> [!NOTE]
>  Resim Düzenleyicisi'ni kullanarak 32 bitlik resimleri görüntüleyebilirsiniz, ancak onları düzenleyemezsiniz.  
  
|Renk|Genişliği (piksel cinsinden)|Yükseklik (piksel cinsinden)|  
|-----------|----------------------|-----------------------|  
|Tek renkli|16|16|  
|Tek renkli|32|32|  
|Tek renkli|48|48|  
|Tek renkli|64|64|  
|Tek renkli|96|96|  
|16|16|16|  
|16|32|32|  
|16|64|64|  
|16|48|48|  
|16|96|96|  
|256|16|16|  
|256|32|32|  
|256|48|48|  
|256|64|64|  
|256|96|96|  
  
-   [(Simgesi veya imleci) yeni cihaz görüntüsü oluşturma](../windows/creating-a-device-image-image-editor-for-icons.md)  
  
-   [Farklı görüntüleme cihazı için görüntü ekleme](../windows/adding-an-image-for-a-different-display-device-image-editor-for-icons.md)  
  
-   [Cihaz görüntüsü kopyalama](../windows/copying-a-device-image-image-editor-for-icons.md)  
  
-   [Cihaz görüntüsünü silme](../windows/deleting-a-device-image-image-editor-for-icons.md)  
  
-   [Cihaz görüntülerinde saydam veya ters bölgeler oluşturma](../windows/creating-transparent-or-inverse-regions-in-device-images.md)  
  
-   [256-renk simgesi veya imleci oluşturma](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)  
  
-   [İmlecin etkin noktasını ayarlama](../windows/setting-a-cursor-s-hot-spot-image-editor-for-icons.md)  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Simgeler için görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)   
 [Simgeler](http://msdn.microsoft.com/library/windows/desktop/ms646973)   
 [İmleçler](http://msdn.microsoft.com/library/windows/desktop/ms646970)

