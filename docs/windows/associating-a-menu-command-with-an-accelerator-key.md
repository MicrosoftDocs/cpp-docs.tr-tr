---
title: "Menü komutunu Hızlandırıcı tuşuyla ilişkilendirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts, menu association
- commands, associating menu commands with accelerator keys
- menu commands, associating with keyboard shortcuts
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 79a16cf8d67fb7a6a45043c28455a7ed22f90ffa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="associating-a-menu-command-with-an-accelerator-key"></a>Menü Komutunu Hızlandırıcı Tuşuyla İlişkilendirme
Çoğunlukla menü komutu ve tuş bileşimini aynı program komutu vermek istediğiniz saatleri vardır. Bunun için aynı kaynak tanımlayıcısı menü komutu ve uygulamanızın Hızlandırıcı tablosunda bir giriş atamak için menü Düzenleyicisi'ni kullanarak. Daha sonra Düzenle [resim yazısı](../windows/menu-command-properties.md) Hızlandırıcı anahtarın adını göstermek için menü komutu.  
  
### <a name="to-associate-a-menu-command-with-an-accelerator-key"></a>Menü komutunu Hızlandırıcı tuşuyla ilişkilendirme  
  
1.  İçinde **menü** Düzenleyicisi, seçmek istediğiniz menü komutu.  
  
2.  İçinde [Özellikler penceresini](/visualstudio/ide/reference/properties-window), Hızlandırıcı anahtarın adını eklemek **resim yazısı** özelliği:  
  
    -   Böylece tüm menünün Hızlandırıcı tuşları sola hizalı menü başlığı kaçış sırası bir sekme (\t) yazın.  
  
    -   Değiştirici tuşa adını yazın (**CTRL**, **ALT**, veya **SHIFT**) ve ardından bir artı işareti (**+**) ve ad, harf, veya İlave bir anahtar simgesi.  
  
         Örneğin, atamak için **CTRL + O** için **açık** komutunu **dosya** menüsünde menü komutuna değiştirme **resim yazısı** böylece gibi görünüyor Bu:  
  
        ```  
        &Open...\tCtrl+O   
        ```  
  
         Menü Düzenleyicisi'nde menü komutu, siz yazarken yeni resim yazısını yansıtacak şekilde güncelleştirilir.  
  
3.  [Hızlandırıcı tablosu girişi oluşturmak](../windows/adding-an-entry-to-an-accelerator-table.md) içinde **hızlandırıcı** Düzenleyicisi ve menü komutu aynı kimliğe atayın. Anımsaması kolay olacağını düşündüğünüz bir tuş bileşimini kullanın.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
 **Gereksinimler**  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Menüye komut ekleme](../windows/adding-commands-to-a-menu.md)   
 [Menü Düzenleyicisi](../windows/menu-editor.md)