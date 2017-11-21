---
title: "Cihaz görüntüsü (simgeler için görüntü Düzenleyicisi) oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.icon
dev_langs: C++
helpviewer_keywords:
- cursors [C++], creating
- icons [C++], creating
- display devices
- display devices, creating image
- images [C++], creating for display devices
- icons [C++], inserting
ms.assetid: 5a536928-32df-4ace-beb1-1521ce3b871f
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8a4f71b2877eaaa7af125918c7fe2b71bb031d39
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-a-device-image-image-editor-for-icons"></a>Cihaz Görüntüsü Oluşturma (Simgeler İçin Görüntü Düzenleyicisi)
Düzenleyici yeni simgesi veya imleci kaynak, görüntü oluştururken ilk görüntü (32 × 32, simgeler için 16 renk ve 32 x 32, imleçler için tek renkli) belirli bir stil oluşturur. Ardından ilk simgesi veya imleci görüntüleri farklı boyut ve stil ekleyin ve her ek görüntü, farklı görüntüleme cihazları için gerektiği gibi düzenleyin. Varolan bir görüntü türü ya da bir grafik programında oluşturulan bir bit eşlem kesme ve yapıştırma işlemi gerçekleştirerek görüntüyü da düzenleyebilirsiniz.  
  
 Simgesi veya imleci kaynak açtığınızda [görüntü Düzenleyicisi](../windows/image-editor-for-icons.md), resmin en yakın geçerli görüntü aygıtı eşleşen varsayılan olarak açılır.  
  
### <a name="to-create-a-new-icon-or-cursor"></a>Yeni simgesi veya imleci oluşturmak için  
  
1.  İçinde [kaynak görünümü](../windows/resource-view-window.md).rc dosyanızı sağ tıklayın ve ardından seçin **Ekle kaynak** kısayol menüsünden. (.Rc dosyanızda, bir imleç gibi varolan bir görüntü kaynağı zaten varsa yalnızca sağ tıklayarak **imleç** klasörü ve select **Ekle imleci** kısayol menüsünden.)  
  
    > [!NOTE]
    >  Projenizi bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  İçinde [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md)seçin **simgesi** veya **imleç** tıklatıp **yeni**. Simgeler için bu simge kaynak, bir 32 x 32 ile 16-renk simgesi oluşturur. İmleçler, bir 32 x 32, tek renkli (2-color) görüntüsü oluşturulur.  
  
     Bir artı işareti (**+**) yanındaki görüntü kaynak türü görünen **Ekle kaynak** iletişim kutusu, geldiğini araç şablonları kullanılabilir. Şablonları'nı genişletin, bir şablon seçin ve'artı işaretini tıklatın **yeni**.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 **Gereksinimler**  
  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Simgeler ve İmleçler: görüntüleme cihazları için görüntü kaynakları](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)   
 [Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Simgeler ve İmleçler: görüntüleme cihazları için görüntü kaynakları](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)
