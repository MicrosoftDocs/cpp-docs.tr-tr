---
title: "Yeni araç çubuğu düğmesi oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.toolbar
dev_langs: C++
helpviewer_keywords:
- Toolbar editor, creating buttons
- toolbar buttons (in Toolbar editor), button image
- toolbar buttons (in Toolbar editor), creating
- toolbar buttons (in Toolbar editor)
ms.assetid: 46c120fe-4f2a-4887-a08f-bd1fea04b3f4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 340756fcb85af8402f3c01d9efb8f1c62c6b0b41
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-a-new-toolbar-button"></a>Yeni Araç Çubuğu Düğmesi Oluşturma
### <a name="to-create-a-new-toolbar-button"></a>Yeni araç çubuğu düğmesi oluşturmak için  
  
1.  İçinde [kaynak görünümü](../windows/resource-view-window.md) (örneğin, Project1.rc) kaynak klasörünü genişletin.  
  
    > [!NOTE]
    >  Projenizi bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Genişletme **araç** klasörü ve düzenlemek için bir araç seçin.  
  
3.  Boş düğme araç çubuğunun sağ ucunda bir kimliği atayın. Düzenleyerek yapabilirsiniz **kimliği** özelliğinde [Özellikler penceresini](/visualstudio/ide/reference/properties-window). Örneğin, bir araç çubuğu düğmesi menü seçeneği aynı Kimliğe vermek isteyebilirsiniz. Bu durumda, seçmek için aşağı açılan liste kutusunu kullanın **kimliği** menü seçeneğinin.  
  
     veya  
  
     (Araç çubuğu görünümü bölmesinde) araç çubuğunun sağ ucunda boş düğmesini seçin ve çizim başlayın. Bir varsayılan düğme komut kimliği atanır (ID_BUTTON\<n >).  
  
 Ayrıca, kopyalayın ve görüntüyü yeni düğmesi olarak bir araç çubuğu üzerine yapıştırın.  
  
#### <a name="to-add-an-image-to-a-toolbar-as-a-button"></a>Görüntüyü bir araç çubuğu düğmesi olarak eklemek için  
  
1.  İçinde [kaynak görünümü](../windows/resource-view-window.md), araç çift tıklatarak açın.  
  
2.  Ardından, araç çubuğuna eklemek istediğiniz görüntüyü açın.  
  
    > [!NOTE]
    >  Visual Studio'da görüntü açarsanız, görüntü Düzenleyicisi'nde açılır. Görüntü diğer grafik programında da açabilirsiniz.  
  
3.  Gelen **Düzenle** menüsünde seçin **kopya**.  
  
4.  Araç çubuğuna kaynak pencerenin üstündeki kendi sekmesine tıklayarak geçin.  
  
5.  Gelen **Düzenle** menüsünde seçin **Yapıştır**.  
  
     Görüntü, araç çubuğunda yeni düğmesi olarak görünür.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
### <a name="requirements"></a>Gereksinimler  
 MFC ya da ATL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Araç çubuğu düğmesi özellikleri](../windows/toolbar-button-properties.md)   
 [Oluşturma, taşıma ve düzenleme araç çubuğu düğmeleri](../windows/creating-moving-and-editing-toolbar-buttons.md)   
 [Araç çubuğu Düzenleyicisi](../windows/toolbar-editor.md)

