---
title: "Kılavuzdaki denetimleri hizalama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- DLUs (dialog units)
- controls [C++], aligning
- Dialog editor, snap to guides
- guides, tick mark interval
- dialog box controls, placement
- guides, aligning controls
- dialog units (DLUs)
- snap to guides (Dialog editor)
- controls [C++], sizing
- tick mark interval in Dialog editor
- controls [C++], snap to guides/grid
ms.assetid: 17db84ba-5288-4478-be57-afa748aa6447
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eed9acf533939d305e42478bb87307bc0a055d3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="aligning-controls-on-a-guide"></a>Kılavuzdaki Denetimleri Hizalama
Boyutlandırma denetimleri denetimleri taşınır ve (daha önce Kılavuzu'na unsuruna tutturulmuş hiçbir denetim varsa) denetimlere kılavuza Daya Kılavuzlara Daya. Bir kılavuzu taşındığında, kendisine tutturulur denetimleri de taşıyın. Kılavuzlar birini taşındığında birden fazla Kılavuzu'na unsuruna tutturulmuş denetimleri boyutlandırılır.  
  
 Değer çizgilerinin kılavuzları ve denetimleri aralığını belirlemek Cetveller içinde iletişim kutusu birimleri (Dlu'lar) tarafından tanımlanır. Bir DLU iletişim kutusu yazı tipi, normalde 8 nokta MS Kabuk iletişim kutusu boyutuna bağlıdır. Yatay DLU dört tarafından ayrılmış iletişim kutusu yazı tipi ortalama genişliğini ' dir. Dikey DLU sekiz tarafından bölünmüş yazı tipi ortalama yüksekliği olur.  
  
### <a name="to-size-a-group-of-controls-with-guides"></a>Bir denetim grubu kılavuzlarıyla boyut için  
  
1.  Denetim (veya denetimleri) bir yan bir kılavuza Daya.  
  
2.  Diğer tarafını denetim (veya denetimleri) kılavuzu sürükleyin.  
  
     Gerekirse birden çok denetimleri ile her ikinci kılavuzuna Daya boyutu.  
  
3.  Denetim (veya denetimleri) boyut için iki Kılavuzu taşıyın.  
  
### <a name="to-change-the-intervals-of-the-tick-marks"></a>Değer çizgilerinin aralıklarını değiştirmek için  
  
1.  Gelen **biçimi** menüsünde seçin **Kılavuzu ayarları**.  
  
2.  İçinde [kılavuz Ayarları iletişim kutusu](../windows/guide-settings-dialog-box.md), **kılavuz aralığı** alanında, yeni genişlik ve yükseklik içinde Dlu'lar belirtin.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutusu Düzenleyicisi durumları (Kılavuzlar ve Izgaralar)](../windows/dialog-editor-states-guides-and-grids.md)   
 [İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)

