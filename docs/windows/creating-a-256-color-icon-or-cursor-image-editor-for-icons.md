---
title: "256-renk simgesi veya imleci (simgeler için görüntü Düzenleyicisi) oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- 256-color palette
- cursors, color
- colors, icons
- colors, cursors
- icons, color
ms.assetid: 2738089b-4fd3-4c45-96ae-6a15e4c6b780
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 11c25c808ad9d1917413a66044e052e4c49ea584
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-256-color-icon-or-cursor-image-editor-for-icons"></a>256-Renk Simgesi veya İmleci Oluşturma (Simgeler İçin Görüntü Düzenleyicisi)
Görüntü Düzenleyicisi'ni kullanarak, simgeler ve İmleçler boyutlu büyük (64 × 64) aralarından seçim yapabileceğiniz 256-renk paletini sahip olabilir. Kaynak oluşturduktan sonra bir cihaz görüntü stili seçilir.  
  
### <a name="to-create-a-256-color-icon-or-cursor"></a>256-renk simgesi veya imleci oluşturma  
  
1.  İçinde [kaynak görünümü](../windows/resource-view-window.md).rc dosyanızı sağ tıklayın ve ardından seçin **Ekle kaynak** kısayol menüsünden. (.Rc dosyanızda, bir imleç gibi varolan bir görüntü kaynağı zaten varsa yalnızca sağ tıklayarak **imleç** klasörü ve select **Ekle imleci** kısayol menüsünden.)  
  
     **Not** projeniz zaten bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  İçinde [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md)seçin **simgesi** veya **imleç** tıklatıp **yeni**.  
  
3.  Üzerinde **görüntü** menüsünde tıklatın **yeni cihaz görüntüsü**.  
  
4.  256-renk görüntü stili seçin.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
 **Gereksinimler**  
  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [256-renk paletini kullanma](../windows/using-the-256-color-palette-image-editor-for-icons.md)   
 [Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Simgeler ve İmleçler: görüntüleme cihazları için görüntü kaynakları](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)

