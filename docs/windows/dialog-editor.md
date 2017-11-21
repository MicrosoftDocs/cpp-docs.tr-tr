---
title: "İletişim kutusu Düzenleyicisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.dialog.dialog
- vc.editors.dialog.F1
dev_langs: C++
helpviewer_keywords:
- resource editors, Dialog editor
- editors, dialog boxes
- Dialog editor
- dialog boxes, editing
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6e520fb524cd25709b9d03ae992305a4fac41763
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dialog-editor"></a>İletişim Kutusu Düzenleyicisi
İletişim kutusu Düzenleyicisi oluşturma veya düzenleme iletişim kutusu kaynakları sağlar. Kaynak Görünümü penceresi bir iletişim kutusu .rc dosyasına çift tıklayarak iletişim kutusu Düzenleyicisi'ni açın (**Görünüm &#124; Kaynak görünümü**). Kaynak Görünümü Express sürümlerinde kullanılabilir olmadığını unutmayın.  
  
 Yeni iletişim kutusu (veya iletişim kutusu şablonu) alımında ilk adımlarından biri denetimleri için iletişim kutusu ekliyor. İletişim kutusu Düzenleyicisi denetimleri belirli bir boyut, Şekil veya hizalama sığacak şekilde düzenleyebilirsiniz veya, bunları iletişim kutusu içinde çalışmak için taşıyabilirsiniz. Denetimi silme kolaydır.  
  
 Yeniden kullanabileceğiniz şekilde bir iletişim kutusu şablon olarak depolayabilirsiniz. Ayrıca kolayca iletişim kutusu tasarlama ve bunu uygulayan kod düzenleme arasında geçiş yapabilirsiniz.  
  
 İletişim kutusu Düzenleyicisi tek veya birden çok denetim özelliklerini düzenlemek mümkündür. Sekme sırası, diğer bir deyişle, SEKME tuşuna basıldığında içinde denetimleri odak elde sipariş değiştirebilir veya klavyeyi kullanarak denetim seçmek kullanıcılara bir erişim anahtarı (anahtar birleşimi) tanımlayabilirsiniz. Önceden ayarlanmış erişim tuşları listesi için bkz: [kısayol tuşları için iletişim kutusu Düzenleyicisi](../windows/accelerator-keys-for-the-dialog-editor.md).  
  
 İletişim kutusu Düzenleyicisi ActiveX denetimlerini dahil olmak üzere özel denetimleri kullanmanızı sağlar. Ayrıca, düzenleyebileceğiniz bir [form görünümü](../mfc/reference/cformview-class.md), [kayıt görünümleri](../data/record-views-mfc-data-access.md), veya [iletişim kutusu çubukları](../mfc/dialog-bars.md).  
  
 Visual Studio 2015 ile başlayarak, nasıl denetimleri taşıyın ve kullanıcı bir iletişim kutusu yeniden boyutlandırır yeniden boyutlandırılmasını belirtin dinamik düzenleri tanımlamak için iletişim kutusu Düzenleyicisi'ni kullanabilirsiniz. Daha fazla bilgi için bkz: [dinamik düzen](../mfc/dynamic-layout.md).  
  
-   [Yeni bir iletişim kutusu oluşturma](../windows/creating-a-new-dialog-box.md)  
  
-   [Çalışma zamanında kullanıcıların çıkamayacağı iletişim kutusu oluşturma](../windows/creating-a-dialog-box-that-users-cannot-exit.md)  
  
-   [Gösteren veya iletişim kutusu Düzenleyicisi araç çubuğunu gizleme](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)  
  
-   [İletişim kutusu Düzenleyicisi ile kod arasında geçiş yapma](../windows/switching-between-dialog-box-controls-and-code.md)  
  
-   [İletişim kutularındaki denetimler](../windows/controls-in-dialog-boxes.md)  
  
-   [İletişim kutusu denetimleri için olay işleyicileri ekleme](../windows/adding-event-handlers-for-dialog-box-controls.md)  
  
-   [Bir iletişim kutusunu test etme](../windows/testing-a-dialog-box.md)  
  
-   [Kısayol tuşları için iletişim kutusu Düzenleyicisi](../windows/accelerator-keys-for-the-dialog-editor.md)  
  
-   [İletişim kutusu Düzenleyicisi sorunlarını giderme](../windows/troubleshooting-the-dialog-editor.md)  
  
    > [!TIP]
    >  Çoğu durumda iletişim kutusu Düzenleyicisi ' ni kullanırken, sık kullanılan komutlar kısayol menüsünü görüntülemek için sağ fare düğmesini tıklatabilirsiniz.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak düzenleyicileri](../windows/resource-editors.md)   
 [Denetimleri](../mfc/controls-mfc.md)   
 [Denetim sınıfları](../mfc/control-classes.md)   
 [İletişim kutusu sınıfları](../mfc/dialog-box-classes.md)   
 [İletişim kutusu denetimleri ve değişken türleri](../ide/dialog-box-controls-and-variable-types.md)

