---
title: "Nasıl yapılır: kaynak oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- toolbars [C++], resources
- resource toolbars
- resources [Visual Studio], creating
ms.assetid: aad44914-9145-45a3-a7d8-9de89b366716
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 46e03602e53c79ff6c384ad9cc613849cb329423
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-create-a-resource"></a>Nasıl Yapılır: Kaynak Oluşturma
> [!NOTE]
>  Kaynak Görünümü Express sürümlerinde desteklenmez.  
  
### <a name="to-create-a-new-resource-in-resource-view"></a>Kaynak Görünümü'nde yeni bir kaynak oluşturmak için  
  
1.  .Rc dosyanızda odaklanmak ile [kaynak görünümü](../windows/resource-view-window.md), tıklatın **Düzenle** menü ve seçin **kaynak ekleme** (veya kaynak görünümünde .rc dosyasını sağ tıklatın ve seçin  **Kaynak ekleme** kısayol menüsünde).  
  
     **Not** projeniz zaten bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  İçinde [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md), projenize eklemek istediğiniz kaynak türünü seçin.  
  
### <a name="to-create-a-new-resource-in-solution-explorer"></a>Çözüm Gezgini'nde yeni bir kaynak oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, proje klasörünü sağ tıklatın ve seçin **Ekle**, ardından **kaynak ekleme** kısayol menüsünde.  
  
     Projenizde .rc dosya yoksa, bu adımı tane oluşturun. Ardından, belirli kaynak türlerine yeni .rc dosyasına eklemek için bu adımı yineleyebilirsiniz.  
  
2.  İçinde [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md), projenize eklemek istediğiniz kaynak türünü seçin.  
  
### <a name="to-create-a-new-resource-in-class-view"></a>Sınıf Görünümü'nde yeni bir kaynak oluşturmak için  
  
1.  İçinde [sınıf görünümü](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)sınıfınız sağ tıklatın ve seçin **Ekle**, ardından **kaynak ekleme** kısayol menüsünden.  
  
2.  İçinde [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md), projenize eklemek istediğiniz kaynak türünü seçin.  
  
### <a name="to-create-a-new-resource-from-the-project-menu"></a>Proje menüsünden Yeni bir kaynak oluşturmak için  
  
1.  Gelen **proje** menüsünde seçin **kaynak ekleme**.  
  
 Yeni bir kaynak oluşturduğunuzda, Visual C++ benzersiz bir ad, örneğin, IDD_DIALOG1 atar. İlişkili kaynak Düzenleyicisi'ni veya kaynak özelliklerini düzenleyerek bu kaynak kimliği özelleştirebilirsiniz [Özellikler penceresini](/visualstudio/ide/reference/properties-window).  
  
 Yeni bir varsayılan kaynak (bir şablona dayalı olmayan bir kaynak) veya sonra desenleri bir kaynak olarak kaynak oluşturabileceğiniz bir [şablon](../windows/how-to-use-resource-templates.md).  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.*  
  
 **Gereksinimler**  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [Kaynak düzenleyicileri](../windows/resource-editors.md)   
 [Kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md)