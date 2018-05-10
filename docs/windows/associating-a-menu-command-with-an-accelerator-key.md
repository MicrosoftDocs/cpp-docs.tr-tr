---
title: Menü komutunu Hızlandırıcı tuşuyla ilişkilendirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts, menu association
- commands, associating menu commands with accelerator keys
- menu commands, associating with keyboard shortcuts
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c4f1aa4b80aec2e7c16485c08d2505695b21f4d5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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