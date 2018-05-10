---
title: Menü komutlarına erişim tuşları atama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 44a21e5930d0d8f2fcaad79cc5cef5bc984ad8b5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="assigning-access-keys-to-menu-commands"></a>Menü Komutlarına Erişim Tuşları Atama
Menüleri ve menü komutlarını için erişim anahtarı (kullanıcının klavye menüsüyle seçmesine olanak veren bir anımsatıcı) atayabilirsiniz.  
  
### <a name="to-assign-an-access-shortcut-key-to-a-menu-command"></a>Menü komutu için bir erişim (kısayol) anahtarı atamak için  
  
1.  Ve işareti yazın (**&**) menüsü adı ya da bu harfle karşılık gelen erişim anahtarı olarak belirtmek için komut adı bir harf önünde. Örneğin "& dosya" kümeleri ALT + F Dosya menüsünden Microsoft Windows için yazılmış uygulamalar için kısayol tuşu olarak.  
  
     Menü öğesi harfleri biri kendisine atanmış bir kısayol tuşu sahip görünür bir ipucu sağlar. Ve işareti görünür harf aşağıdaki altı çizili (işletim sisteminde contingent).  
  
    > [!NOTE]
    >  Menünüze sağ tıklayıp seçerek menüsündeki tüm erişim anahtarları benzersiz olduğundan emin olun **anımsatıcıları kontrol** kısayol menüsünden.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Menü Düzenleyicisi](../windows/menu-editor.md)