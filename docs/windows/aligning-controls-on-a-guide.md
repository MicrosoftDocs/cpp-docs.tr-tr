---
title: Kılavuzdaki denetimleri hizalama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLUs (dialog units)
- controls [C++], aligning
- Dialog Editor [C++], snap to guides
- guides, tick mark interval
- dialog box controls [C++], placement
- guides, aligning controls
- dialog units (DLUs)
- snap to guides (Dialog editor)
- controls [C++], sizing
- tick mark interval in Dialog editor
- controls [C++], snap to guides/grid
ms.assetid: 17db84ba-5288-4478-be57-afa748aa6447
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2790d9fc3bd4e0af6c86bdbd71be236d8980ab4a
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44314995"
---
# <a name="aligning-controls-on-a-guide"></a>Kılavuzdaki Denetimleri Hizalama

Boyutlandırma denetimleri denetimleri taşınır ve kılavuzları (daha önce Kılavuzu yaslanmış denetim varsa) denetimleri için ek bileşen Kılavuzlara Daya. Bir kılavuz taşındığında, kendisine tutturulduğunu denetimleri de taşıyın. Bir kılavuz taşındığında birden fazla Kılavuzu yaslanmış denetimleri yeniden boyutlandırılır.

Değer çizgilerinin kılavuzları ve denetimlerin aralığı belirlemek Cetveller içinde iletişim kutusu birimleri (Dlu'lar) tarafından tanımlanır. Bir DLU iletişim kutusu yazı tipi, normalde 8 noktası MS Shell Dlg boyutuna bağlıdır. Yatay DLU dört tarafından ayrılmış iletişim kutusu yazı tipinin ortalama genişliğidir. Dikey DLU sekiz tarafından ayrılmış yazı tipi ortalama yüksekliği olur.

### <a name="to-size-a-group-of-controls-with-guides"></a>Denetim grubunun kılavuzlarıyla boyutlandırmak için

1. Denetimin (veya denetimleri) bir tarafı bir kılavuza yapışır.

2. Diğer tarafında denetimin (veya denetimleri) için bir kılavuz sürükleyin.

   Gerekirse birden çok denetimlerle her ikinci kılavuza uydurmayı boyutu.

3. Denetimin (veya denetimleri) boyutlandırmak için iki Kılavuzu taşıyın.

### <a name="to-change-the-intervals-of-the-tick-marks"></a>Değer çizgilerinin aralıklarına değiştirmek için

1. Gelen **biçimi** menüsünde seçin **Kılavuz ayarları**.

2. İçinde [kılavuz Ayarları iletişim kutusu](../windows/guide-settings-dialog-box.md), **ızgara Aralama** alanında, yeni genişliği ve yüksekliği içinde Dlu'lar belirtin.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutusu Düzenleyicisi Durumları (Kılavuzlar ve Izgaralar)](../windows/dialog-editor-states-guides-and-grids.md)  
[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)