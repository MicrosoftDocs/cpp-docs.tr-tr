---
title: "İletişim kutusu Düzenleyicisi sekmesi, araç kutusu | Microsoft Docs"
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
- Toolbox [C++], Dialog Editor tab
- controls [C++], types
- syslink controls ino dialog boxes
- custom controls [Visual Studio], dialog boxes
- controls [C++], standard
- Dialog editor, creating controls
- controls [C++], adding to dialog boxes
ms.assetid: 253885c2-dcb9-4d8e-ac9b-805ea31cbf5e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9db31d6e152be10f2c4934b7b1f239d1e08387f5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="dialog-editor-tab-toolbox"></a>İletişim Kutusu Düzenleyicisi Sekmesi, Araç Kutusu
İletişim kutusu Düzenleyicisi sekmesi görünür [araç penceresi](/visualstudio/ide/reference/toolbox) iletişim kutusu Düzenleyicisi'nde çalışırken. Denetimleri, yeni bir iletişim kutusu denetimleri eklemek için iletişim kutusuna oluşturmakta Araç Kutusu'ndan sürükleyin (daha fazla bilgi için bkz: [iletişim kutusuna denetim ekleme](adding-a-control-to-a-dialog-box.md)). Ardından, denetimleri hareket ettirin veya kendi boyutu ve şekli değiştirin.  
  
 Araç kutusunda kullanılabilir standart denetimleri şunlardır:  
  
-   [Düğme denetimi](../mfc/reference/cbutton-class.md)  
  
-   [Onay kutusu denetimi](../mfc/reference/styles-used-by-mfc.md#button-styles)  
  
-   [Birleşik giriş kutusu denetimi](../mfc/reference/ccombobox-class.md)  
  
-   [Düzenleme denetimi](../mfc/reference/cedit-class.md)  
  
-   Grup kutusu  
  
-   [Liste kutusu denetimi](../mfc/reference/clistbox-class.md)  
  
-   [Radyo düğmesi denetimi](../mfc/reference/styles-used-by-mfc.md#button-styles)  
  
-   [Statik metin denetimi](../mfc/reference/cstatic-class.md)  
  
-   [Resim denetimi](../mfc/reference/cpictureholder-class.md)  
  
-   [Zengin düzenleme 2.0 denetimi](../mfc/using-cricheditctrl.md)  
  
-   [Kaydırma çubuğu denetimi](../mfc/reference/cscrollbar-class.md)  
  
 [Windows ortak denetimleri](../mfc/controls-mfc.md) araç bulunan uygulamanızda artırılmış işlevsellik sağlar. Bunlara aşağıdakiler dahildir:  
  
-   [Kaydırıcı denetimi](../mfc/slider-control-styles.md)  
  
-   [Döndürme denetimi](../mfc/using-cspinbuttonctrl.md)  
  
-   [İlerleme denetimi](../mfc/styles-for-the-progress-control.md)  
  
-   [Sık kullanılan anahtarı denetimi](../mfc/using-a-hot-key-control.md)  
  
-   [Liste denetimi](../mfc/list-control-and-list-view.md)  
  
-   [Ağaç denetimi](../mfc/tree-control-styles.md)  
  
-   [Sekme denetimi](../mfc/tab-controls-and-property-sheets.md)  
  
-   [Animasyon denetimi](../mfc/using-an-animation-control.md)  
  
-   [Tarih Saat Seçici denetimi](../mfc/creating-the-date-and-time-picker-control.md)  
  
-   [Ay takvim denetleme](../mfc/month-calendar-control-examples.md)  
  
-   [IP adresi denetimi](../mfc/reference/cipaddressctrl-class.md)  
  
-   [Genişletilmiş Birleşik giriş kutusu denetimi](../mfc/creating-an-extended-combo-box-control.md)  
  
-   [Özel Denetim](custom-controls-in-the-dialog-editor.md)  
  
 Seçerek iletişim kutusuna özel denetimler ekleyebilirsiniz **özel denetim** araç ve iletişim kutusuna sürükleyerek simgesi. Syslink denetim eklemek için özel bir denetim ekleyin, sonra denetimin değiştirme **sınıfı** özelliğine **Syslink**. Bu yenileme ve Syslink denetim özelliklerini göstermek özellikler neden olur. MFC sarmalayıcı sınıfı hakkında daha fazla bilgi için bkz: [CLinkCtrl](../mfc/reference/clinkctrl-class.md).  
  
 Ayrıca olabilir [, iletişim kutusuna ActiveX denetimleri ekleme](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
 Araç penceresi daha kolay kullanım için de özelleştirebilirsiniz. Daha fazla bilgi için bkz: [araç kutusunu kullanarak](/visualstudio/ide/using-the-toolbox).  

 MFC ile RichEdit 1.0 denetimini kullanma hakkında daha fazla bilgi için bkz: [MFC ile RichEdit 1.0 denetimini kullanma](../windows/using-the-richedit-1-0-control-with-mfc.md)  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetimleri](../mfc/controls-mfc.md)   
 [Denetim sınıfları](../mfc/control-classes.md)   
 [İletişim kutusu sınıfları](../mfc/dialog-box-classes.md)   
 [Kaydırma çubuğu stilleri](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles)   
 [Zengin düzenleme denetimine örnekler](../mfc/rich-edit-control-examples.md)   
 [İletişim kutusu denetimleri için olay işleyicileri ekleme](../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [İletişim Kutusu Denetimleri ve Değişken Türleri](../ide/dialog-box-controls-and-variable-types.md)

