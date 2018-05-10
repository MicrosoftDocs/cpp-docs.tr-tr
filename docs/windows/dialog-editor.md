---
title: İletişim kutusu Düzenleyicisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.dialog
- vc.editors.dialog.F1
dev_langs:
- C++
helpviewer_keywords:
- resource editors, Dialog editor
- editors, dialog boxes
- Dialog editor
- dialog boxes, editing
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7b8cb99b2002dab3fb04ffa8c5b117a49d23adc1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="dialog-editor"></a>İletişim Kutusu Düzenleyicisi
İletişim kutusu Düzenleyicisi oluşturma veya düzenleme iletişim kutusu kaynakları sağlar. Kaynak Görünümü penceresi bir iletişim kutusu .rc dosyasına çift tıklayarak iletişim kutusu Düzenleyicisi'ni açın (**Görünüm &#124; kaynak görünümü**). Kaynak Görünümü Express sürümlerinde kullanılabilir olmadığını unutmayın.  
  
 Yeni iletişim kutusu (veya iletişim kutusu şablonu) alımında ilk adımlarından biri denetimleri için iletişim kutusu ekliyor. İletişim kutusu Düzenleyicisi denetimleri belirli bir boyut, Şekil veya hizalama sığacak şekilde düzenleyebilirsiniz veya, bunları iletişim kutusu içinde çalışmak için taşıyabilirsiniz. Denetimi silme kolaydır.  
  
 Yeniden kullanabileceğiniz şekilde bir iletişim kutusu şablon olarak depolayabilirsiniz. Ayrıca kolayca iletişim kutusu tasarlama ve bunu uygulayan kod düzenleme arasında geçiş yapabilirsiniz.  
  
 İletişim kutusu Düzenleyicisi tek veya birden çok denetim özelliklerini düzenlemek mümkündür. Sekme sırası, diğer bir deyişle, SEKME tuşuna basıldığında içinde denetimleri odak elde sipariş değiştirebilir veya klavyeyi kullanarak denetim seçmek kullanıcılara bir erişim anahtarı (anahtar birleşimi) tanımlayabilirsiniz. Önceden ayarlanmış erişim tuşları listesi için bkz: [kısayol tuşları için iletişim kutusu Düzenleyicisi](../windows/accelerator-keys-for-the-dialog-editor.md).  
  
 İletişim kutusu Düzenleyicisi ActiveX denetimlerini dahil olmak üzere özel denetimleri kullanmanızı sağlar. Ayrıca, düzenleyebileceğiniz bir [form görünümü](../mfc/reference/cformview-class.md), [kayıt görünümleri](../data/record-views-mfc-data-access.md), veya [iletişim kutusu çubukları](../mfc/dialog-bars.md).  
  
 Visual Studio 2015 ile başlayarak, nasıl denetimleri taşıyın ve kullanıcı bir iletişim kutusu yeniden boyutlandırır yeniden boyutlandırılmasını belirtin dinamik düzenleri tanımlamak için iletişim kutusu Düzenleyicisi'ni kullanabilirsiniz. Daha fazla bilgi için bkz: [dinamik düzen](../mfc/dynamic-layout.md).  
  
-   [Yeni İletişim Kutusu Oluşturma](../windows/creating-a-new-dialog-box.md)  
  
-   [Çalışma zamanında kullanıcıların çıkamayacağı iletişim kutusu oluşturma](../windows/creating-a-dialog-box-that-users-cannot-exit.md)  
  
-   [İletişim Kutusu Araç Çubuğunu Gösterme veya Gizleme](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)  
  
-   [İletişim kutusu Düzenleyicisi ile kod arasında geçiş yapma](../windows/switching-between-dialog-box-controls-and-code.md)  
  
-   [İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)  
  
-   [İletişim Kutusu Denetimleri için Olay İşleyicileri Ekleme](../windows/adding-event-handlers-for-dialog-box-controls.md)  
  
-   [İletişim Kutusunu Test Etme](../windows/testing-a-dialog-box.md)  
  
-   [İletişim Kutusu Düzenleyicisi için Hızlandırma Tuşları](../windows/accelerator-keys-for-the-dialog-editor.md)  
  
-   [İletişim Kutusu Düzenleyicisinde Sorun Giderme](../windows/troubleshooting-the-dialog-editor.md)  
  
    > [!TIP]
    >  Çoğu durumda iletişim kutusu Düzenleyicisi ' ni kullanırken, sık kullanılan komutlar kısayol menüsünü görüntülemek için sağ fare düğmesini tıklatabilirsiniz.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak düzenleyicileri](../windows/resource-editors.md)   
 [denetimleri](../mfc/controls-mfc.md)   
 [Denetim sınıfları](../mfc/control-classes.md)   
 [İletişim kutusu sınıfları](../mfc/dialog-box-classes.md)   
 [İletişim Kutusu Denetimleri ve Değişken Türleri](../ide/dialog-box-controls-and-variable-types.md)

