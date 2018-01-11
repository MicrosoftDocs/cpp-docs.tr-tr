---
title: "Size rehberlik eder ve kenar boşlukları oluşturma ve ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- guides, clearing
- guides
- Dialog editor, guides and margins
- dialog box controls, placement
- controls [C++], guides and margins
- guides, creating
- guides, moving
- margins, moving
ms.assetid: fafa4545-8f00-436f-b590-300e76601156
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e767eaa8fbb91f0cf49c63d5d7aca3a05c5dd518
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-and-setting-guides-and-margins"></a>Kılavuzlar ve Kenar Boşlukları Oluşturma ve Ayarlama
Denetimler ekleme denetimlerini taşıyor ya da geçerli bir düzen yeniden düzenleme, kılavuzları yardımcı olabilecek denetimleri doğru bir şekilde bir iletişim kutusu içinde hizalayın. Kılavuzlar, düzenleyici ve bunlara Cetveller (üst ve sol tarafında iletişim kutusu Düzenleyicisi) karşılık gelen okları görüntülenen bir iletişim kutusu üzerinden mavi noktalı çizgiler olarak görünür.  
  
 Bir iletişim kutusu oluşturduğunuzda, dört kenar boşluklarını sağlanır. Kenar boşlukları değiştirilmiş kılavuzları, mavi noktalı çizgiler olarak görünen olur.  
  
### <a name="to-create-a-guide"></a>Bir kılavuz oluşturmak için  
  
1.  Cetvel içinde bir kez bir kılavuz oluşturmak için tıklatın. (Tek bir tıklatmayla oluşturur Yeni bir kılavuzu; başlatır çift [kılavuz Ayarları iletişim kutusu](../windows/guide-settings-dialog-box.md) içinde belirtebilirsiniz Kılavuzu ayarlarını.)  
  
### <a name="to-set-a-guide"></a>Bir kılavuz ayarlamak için  
  
1.  İletişim kutusundaki Kılavuzu'nu tıklatın ve yeni bir konuma sürükleyin. (Ayrıca ilişkili kılavuzu sürükleyin cetveldeki oku de tıklatabilirsiniz.)  
  
     Kılavuzun koordinatları pencerenin altındaki durum çubuğu ve cetvel görüntülenir. Kılavuzun tam konumu görüntülenecek cetveldeki oku üzerine getirin.  
  
### <a name="to-delete-a-guide"></a>Bir kılavuzu silmek için  
  
1.  Kılavuzu iletişim kutusunu sürükleyin.  
  
 \-veya -  
  
-   Cetvel kapalı karşılık gelen oku sürükleyin.  
  
#### <a name="to-move-margins"></a>Kenar boşlukları taşımak için  
  
1.  Kenar yeni bir konuma sürükleyin.  
  
     Kayboluyor kenar boşluğu yapmak için kenar sıfır bir konuma taşıyın. Kenar boşluğu geri getirmek için işaretçiyi kenar 's sıfır konuma yerleştirin ve kenar konumda taşıyın.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
### <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutusu Düzenleyicisi durumları (Kılavuzlar ve Izgaralar)](../windows/dialog-editor-states-guides-and-grids.md)   
 [İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)

