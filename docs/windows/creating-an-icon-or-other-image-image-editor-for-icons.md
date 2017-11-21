---
title: "Simge veya başka görüntü (simgeler için görüntü Düzenleyicisi) oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.bitmap
dev_langs: C++
helpviewer_keywords:
- bitmaps [C++]
- images [C++], creating
- resource toolbars
- resources [Visual Studio], creating images
- bitmaps [C++], creating
- graphics [C++], creating
- Image editor [C++], creating images
ms.assetid: 66db3fb2-cfc1-48a2-9bdd-53f61eb7ee30
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ed026ffda8066f027da6f41e2e4accc7766a9a2b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-an-icon-or-other-image-image-editor-for-icons"></a>Simge veya Başka Görüntü Oluşturma (Simgeler İçin Görüntü Düzenleyicisi)
Yeni bir görüntü (bit eşlem, simge, imleç veya araç) oluşturmak, sonra görünümünü özelleştirmek için görüntü Düzenleyicisi'ni kullanın. Sonra desenleri yeni bir bit eşlem oluşturabilirsiniz bir [şablon](../windows/how-to-use-resource-templates.md).  
  
### <a name="to-add-a-new-image-resource-to-an-unmanaged-c-project"></a>Yeni bir görüntü kaynağı yönetilmeyen bir C++ projeye eklemek için  
  
1.  İçinde [kaynak görünümü](../windows/resource-view-window.md).rc dosyanızı sağ tıklayın ve ardından seçin **Ekle kaynak** kısayol menüsünden. (.Rc dosyanızda, bir imleç gibi varolan bir görüntü kaynağı zaten varsa yalnızca sağ tıklayarak **imleç** klasörü ve select **Ekle imleci** kısayol menüsünden.)  
  
    > [!NOTE]
    >  **Not** projeniz zaten bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  İçinde [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md), oluşturmak istediğiniz görüntü kaynak türünü seçin (**bit eşlem**, örneğin) ardından **yeni**.  
  
     Bir artı işareti (**+**) yanındaki görüntü kaynak türü görünen **Ekle kaynak** iletişim kutusu, geldiğini araç şablonları kullanılabilir. Şablonları'nı genişletin, bir şablon seçin ve'artı işaretini tıklatın **yeni**.  
  
### <a name="to-add-a-new-image-resource-to-a-project-in-a-net-programming-language"></a>Bir .NET programlama dili projede yeni bir görüntü kaynağı eklemek için  
  
1.  İçinde **Çözüm Gezgini**, proje klasörüne sağ tıklayın (örneğin, **WindowsApplication1**).  
  
2.  Kısayol menüsünden tıklatın **Ekle**, ardından **Yeni Öğe Ekle**.  
  
3.  İçinde **kategorileri** bölmesinde genişletin **yerel proje öğeleri** klasörünü seçin **kaynakları**.  
  
4.  İçinde **şablonları** bölmesinde projenize eklemek istediğiniz kaynak türünü seçin.  
  
     Çözüm Gezgini'nde projenize kaynak eklenir ve kaynak açılır [görüntü Düzenleyicisi](../windows/image-editor-for-icons.md). Şimdi, görüntünüzü değiştirmek için görüntü Düzenleyicisi'nde kullanılabilir tüm araçları da kullanabilirsiniz. Bir yönetilen projenin görüntüler ekleme ile ilgili daha fazla bilgi için bkz: [tasarım zamanında resim yükleme](/dotnet/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms).  
  
    > [!NOTE]
    >  Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez. Daha fazla bilgi için bkz: [oluşturma kaynak dosyaları](/dotnet/framework/resources/creating-resource-files-for-desktop-apps) içinde *.NET Framework Geliştirici Kılavuzu*.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 Gereksinimler  
  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Simgeler ve İmleçler: görüntüleme cihazları için görüntü kaynakları](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [Bit eşlemleri araç çubuklarına dönüştürme](../windows/converting-bitmaps-to-toolbars.md)   
 [Yeni araç çubukları oluşturma](../windows/creating-new-toolbars.md)   
 [Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Simgeler için görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)

