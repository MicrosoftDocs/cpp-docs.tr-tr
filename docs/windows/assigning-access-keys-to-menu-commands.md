---
title: "Menü komutlarına erişim tuşları atama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- access keys [C++], checking
- menus, shortcut keys
- keyboard shortcuts [C++], command assignments
- access keys [C++], assigning
- mnemonics, adding to menus
- keyboard shortcuts [C++], uniqueness checking
- mnemonics, uniqueness checking
- Check Mnemonics command
ms.assetid: fbcf1a00-af6a-4171-805a-0ac01d4e8b0d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 27291689e3fbfb9418d783917f59ffeee7a54235
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="assigning-access-keys-to-menu-commands"></a>Menü Komutlarına Erişim Tuşları Atama
Menüleri ve menü komutlarını için erişim anahtarı (kullanıcının klavye menüsüyle seçmesine olanak veren bir anımsatıcı) atayabilirsiniz.  
  
### <a name="to-assign-an-access-shortcut-key-to-a-menu-command"></a>Menü komutu için bir erişim (kısayol) anahtarı atamak için  
  
1.  Ve işareti yazın (**&**) menüsü adı ya da bu harfle karşılık gelen erişim anahtarı olarak belirtmek için komut adı bir harf önünde. Örneğin "& dosya" kümeleri ALT + F Dosya menüsünden Microsoft Windows için yazılmış uygulamalar için kısayol tuşu olarak.  
  
     Menü öğesi harfleri biri kendisine atanmış bir kısayol tuşu sahip görünür bir ipucu sağlar. Ve işareti görünür harf aşağıdaki altı çizili (işletim sisteminde contingent).  
  
    > [!NOTE]
    >  Menünüze sağ tıklayıp seçerek menüsündeki tüm erişim anahtarları benzersiz olduğundan emin olun **anımsatıcıları kontrol** kısayol menüsünden.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Menü düzenleyicisi](../windows/menu-editor.md)