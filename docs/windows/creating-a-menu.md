---
title: "Menü oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.menu
dev_langs: C++
helpviewer_keywords:
- mnemonics, associating menu items
- menus, associating commands with mnemonic keys
- menus, creating
ms.assetid: 66f94448-9b97-4b73-bf97-10d4bf87cc65
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 953de61b199acda1b6cf4f9e0d06b1bd1875ab1c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 **Gereksinimler**  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Menü düzenleyicisi](../windows/menu-editor.md)