---
title: 'Simgeler ve İmleçler: görüntüleme cihazları (simgeler için görüntü Düzenleyicisi C++) için görüntü kaynakları'
ms.date: 11/04/2016
f1_keywords:
- vc.editors.icon
helpviewer_keywords:
- cursors [C++], creating
- image resources [C++], display devices
- icons [C++], creating
- cursors [C++], types
- icons [C++]
- Image editor [C++], icons and cursors
- cursors [C++]
- display devices [C++], creating icons for
- cursors [C++], hot spots
- icons [C++], types
ms.assetid: 8f0809a8-0cf0-4da9-b23d-51f28bf15f5b
ms.openlocfilehash: 91de1351b3e41701d302d290533b60d4fe791b80
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693015"
---
# <a name="icons-and-cursors-image-resources-for-display-devices-c-image-editor-for-icons"></a>Simgeler ve İmleçler: görüntüleme cihazları (simgeler için görüntü Düzenleyicisi C++) için görüntü kaynakları

Simgeler ve İmleçler, farklı boyutlarda birden fazla görüntüler içerir ve düzenleri görüntüleme cihazları farklı türleri için renk grafik kaynaklardır. Ayrıca, bir imleç "etkin nokta," Windows konumuna izlemek için kullandığı konumun sahiptir. Simgeler ve İmleçler hem oluşturulur ve düzenlenebilir **görüntü** Düzenleyicisi, bit eşlemler ve diğer görüntüler.

Yeni simgesi veya imleci, oluşturduğunuzda **görüntü** Düzenleyicisi ilk standart türünde bir görüntü oluşturur. Görüntü başlangıçta ekran (saydam) renkle doldurulur. Görüntünün bir imleç etkin nokta başlangıçta sol üst köşesinin (koordinatları 0,0) ise.

Varsayılan olarak, **görüntü** Düzenleyicisi aşağıdaki tabloda gösterilen cihazlar için ek görüntüleri oluşturulmasını destekler. Genişlik, yükseklik ve renk sayısı parametreleri içine yazarak diğer cihazları için görüntü oluşturabilirsiniz [özel görüntü iletişim kutusu](custom-image-dialog-box-image-editor-for-icons.md).

> [!NOTE]
> Kullanarak **Resim Düzenleyicisi**, 32 bitlik resimleri görüntüleyebilirsiniz, ancak onları düzenleyemezsiniz.

|Renk|Genişlik (piksel cinsinden)|Yükseklik (piksel cinsinden)|
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

- [(Simgesi veya imleci) yeni cihaz görüntüsü oluşturma](../windows/creating-a-device-image-image-editor-for-icons.md)

- [Farklı görüntüleme cihazı için görüntü ekleme](../windows/adding-an-image-for-a-different-display-device-image-editor-for-icons.md)

- [Cihaz görüntüsü kopyalama](../windows/copying-a-device-image-image-editor-for-icons.md)

- [Cihaz görüntüsünü silme](../windows/deleting-a-device-image-image-editor-for-icons.md)

- [Cihaz görüntülerinde saydam veya ters bölgeler oluşturma](../windows/creating-transparent-or-inverse-regions-in-device-images.md)

- [256-renk simgesi veya imleci oluşturma](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)

- [İmlecin etkin noktasını ayarlama](../windows/setting-a-cursor-s-hot-spot-image-editor-for-icons.md)

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)<br/>
[Simgeler](/windows/desktop/menurc/icons)<br/>
[İmleçler](/windows/desktop/menurc/cursors)