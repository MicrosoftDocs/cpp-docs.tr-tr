---
title: "Menü oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.menu
dev_langs:
- C++
helpviewer_keywords:
- mnemonics, associating menu items
- menus, associating commands with mnemonic keys
- menus, creating
ms.assetid: 66f94448-9b97-4b73-bf97-10d4bf87cc65
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7d5d600a168c93b663ebe446ddd912d98fee1b19
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-menu"></a>Menü Oluşturma
> [!NOTE]
>  Kaynak penceresi Express sürümlerinde kullanılabilir değil.  
  
### <a name="to-create-a-standard-menu"></a>Standart menü oluşturmak için  
  
1.  Gelen **Görünüm** menüsünde tıklatın **kaynak görünümü** ve ardından sağ tıklayın **menü** başlık ve seçin **kaynak ekleme**. Seçin **menü**.  
  
2.  Seçin **yeni öğe** menü çubuğunda kutusuna ("Buraya türü" içeren dikdörtgen).  
  
     ![Menü düzenleyicisi yeni öğe kutusunda](../windows/media/vcmenueditornewitembox.gif "vcMenuEditorNewItemBox")  
Yeni öğe kutusu  
  
3.  Yeni menünüze, örneğin, "Dosyası" için bir ad yazın.  
  
     Yazdığınız metin görünür **menü** Düzenleyicisi ve **resim yazısı** kutusunda [Özellikler penceresini](/visualstudio/ide/reference/properties-window). Her iki konumda yeni menünüze için özelliklerini düzenleyin.  
  
     Menü çubuğunda, yeni menü bir adı verilen sonra yeni öğe kutusunda (başka bir menü eklemenize izin vermek için) sağa kaydırır ve menü komutlarını ekleyebilmek için ilk menüsünün altında başka bir yeni öğe kutusu açılır.  
  
     ![Genişletilmiş yeni öğe kutusunda](../windows/media/vcmenueditornewitemboxexpanded.gif "vcMenuEditorNewItemBoxExpanded")  
Menü adını yazdıktan sonra gölgeye odaklanılan yeni öğe kutusu  
  
    > [!NOTE]
    >  Menü çubuğunda tek öğesi menüsü oluşturmak için açılan özelliğini False olarak ayarlayın.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
 **Gereksinimler**  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Menü Düzenleyicisi](../windows/menu-editor.md)