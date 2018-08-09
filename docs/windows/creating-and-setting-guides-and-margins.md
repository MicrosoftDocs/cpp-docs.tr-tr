---
title: Oluşturma ve ayarlama kılavuzlarını ve kenar boşlukları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 11631a2ac6a2c83cd667d14a490c57b1a191c1a7
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642564"
---
# <a name="creating-and-setting-guides-and-margins"></a>Kılavuzlar ve Kenar Boşlukları Oluşturma ve Ayarlama
Denetimleri ekleme denetimleri taşıyor ister geçerli düzenini yeniden düzenleme, kılavuzları yardımcı olabilir denetimleri bir iletişim kutusu içinde doğru bir şekilde hizalayın. Kılavuzlar arasında Düzenleyicisi'ni ve karşılık gelen okları Cetveller görüntülenen iletişim kutusu olarak mavi noktalı çizgilerin görüntülenir (üst ve sol tarafında **iletişim** Düzenleyici).  
  
 Bir iletişim kutusu oluşturduğunuzda, dört kenar boşlukları sağlanır. Kenar boşlukları, mavi noktalı çizgiler olarak görünen, değiştirilen kılavuzlardır.  
  
### <a name="to-create-a-guide"></a>Bir kılavuz oluşturmak için  
  
1.  Cetvel içinde bir kılavuz oluşturmak için bir kez tıklayın. (Tek bir tıklamayla oluşturur, yeni bir kılavuzu; başlatır çift [kılavuz Ayarları iletişim kutusu](../windows/guide-settings-dialog-box.md) Kılavuz ayarları belirttiğiniz.)  
  
### <a name="to-set-a-guide"></a>Bir kılavuz ayarlamak için  
  
1.  İletişim kutusunda, Kılavuzu'nu tıklatın ve yeni bir konuma sürükleyin. (Ayrıca ilişkili Kılavuzu sürüklemek için cetvelin oka tıklayabilirsiniz.)  
  
     Kılavuzu koordinatlarını cetvel ve pencerenin altındaki durum çubuğunda görüntülenir. Tam Kılavuzu konumunu görüntülemek için cetvelin oka üzerine getirin.  
  
### <a name="to-delete-a-guide"></a>Bir kılavuz silmek için  
  
1.  İletişim kutusunu kılavuzu sürükleyin.  
  
 \- veya -  
  
-   Cetvelin karşılık gelen oku sürükleyin.  
  
### <a name="to-move-margins"></a>Kenar boşlukları taşımak için  
  
1.  Kenar boşluğu yeni konumuna sürükleyin.  
  
     Bir kenar boşluğu kaybolmasını sağlamak için kenar sıfır bir konuma taşıyın. Kenar boşluğu geri getirmek için işaretçiyi kenar ait sıfır konumuna getirin ve kenar boşluğu konumuna taşıyın.  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutusu Düzenleyicisi durumları (Kılavuzlar ve Izgaralar)](../windows/dialog-editor-states-guides-and-grids.md)   
 [İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)