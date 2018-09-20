---
title: İletişim kutusu Düzenleyicisi (C++) | Microsoft Docs
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
- resource editors [C++], Dialog editor
- editors, dialog boxes
- Dialog editor
- dialog boxes [C++], editing
ms.assetid: d94884ef-2cca-49d8-9b58-775f34848134
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c1fc2d9f816e5487f5d89f9c429db85f2592731f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439542"
---
# <a name="dialog-editor-c"></a>İletişim kutusu Düzenleyicisi (C++)

**İletişim** Düzenleyicisi oluşturma veya düzenleme iletişim kutusu kaynakları sağlar. İletişim kutusu Düzenleyicisi iletişim kutusu .rc dosyasına çift tıklayarak açın **kaynak görünümü** penceresi (**görünümü** > **kaynak görünümü**). Unutmayın **kaynak görünümü** Express sürümlerinde kullanılamaz.

Yeni iletişim kutusu (veya iletişim kutusu şablonu) yapma, ilk adımlarından biri, denetimleri iletişim kutusuna eklemektir. İçinde **iletişim** Düzenleyicisi, belirli bir boyut, Şekil veya hizalama sığması için denetimleri düzenlemek ya da bunları yaklaşık iletişim kutusu içinde çalışacak şekilde taşıyabilirsiniz. Bir denetimi silmek kolaydır.

Onu tekrar kullanabilirsiniz, böylece şablon olarak bir iletişim kutusu depolayabilirsiniz. Ayrıca bir kolayca iletişim kutusu tasarlama ve onu uygulayan kod düzenleme arasında geçiş yapabilirsiniz.

İletişim kutusu düzenleyicisinde tek veya birden çok denetim özelliklerini düzenlemek mümkündür. Sekme sırasını değiştirebilirsiniz, diğer bir deyişle, hangi denetimlerin elde sırasını Odaklan ne zaman **sekmesini** tuşuna basıldığında veya klavyeyi kullanarak denetim seçmelerini sağlar bir erişim anahtarı (bir tuş bileşimi) tanımlayabilirsiniz. Önceden oluşturulmuş erişim anahtarları listesi için bkz. [iletişim kutusu Düzenleyicisi için hızlandırma tuşları](../windows/accelerator-keys-for-the-dialog-editor.md).

**İletişim** Düzenleyicisi de ActiveX denetimleri de dahil olmak üzere özel denetimler kullanmanızı sağlar. Ayrıca, düzenleyebileceğiniz bir [form görünümü](../mfc/reference/cformview-class.md), [kayıt görünümleri](../data/record-views-mfc-data-access.md), veya [iletişim kutusu çubukları](../mfc/dialog-bars.md).

Visual Studio 2015 ile başlayarak, iletişim kutusu Düzenleyicisi nasıl denetimleri taşımak kullanıcının bir iletişim kutusu boyutlandırdığında yeniden boyutlandırma belirtin ve dinamik düzenleri tanımlamak için kullanabilirsiniz. Daha fazla bilgi için [dinamik düzen](../mfc/dynamic-layout.md).

- [Yeni İletişim Kutusu Oluşturma](../windows/creating-a-new-dialog-box.md)

- [Çalışma zamanında kullanıcıların çıkamayacağı iletişim kutusu oluşturma](../windows/creating-a-dialog-box-that-users-cannot-exit.md)

- [İletişim Kutusu Araç Çubuğunu Gösterme veya Gizleme](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)

- [İletişim kutusu Düzenleyicisi ile kod arasında geçiş yapma](../windows/switching-between-dialog-box-controls-and-code.md)

- [İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)

- [İletişim Kutusu Denetimleri için Olay İşleyicileri Ekleme](../windows/adding-event-handlers-for-dialog-box-controls.md)

- [İletişim Kutusunu Test Etme](../windows/testing-a-dialog-box.md)

- [İletişim Kutusu Düzenleyicisi için Hızlandırma Tuşları](../windows/accelerator-keys-for-the-dialog-editor.md)

- [İletişim Kutusu Düzenleyicisinde Sorun Giderme](../windows/troubleshooting-the-dialog-editor.md)

   > [!TIP]
   > Kullanırken **iletişim** düzenleyicisinde birçok örneği, sık kullanılan komutlar kısayol menüsünü görüntülemek için sağ fare düğmesine tıklayabilirsiniz.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Denetimler](../mfc/controls-mfc.md)<br/>
[Denetim Sınıfları](../mfc/control-classes.md)<br/>
[İletişim Kutusu Sınıfları](../mfc/dialog-box-classes.md)<br/>
[İletişim Kutusu Denetimleri ve Değişken Türleri](../ide/dialog-box-controls-and-variable-types.md)