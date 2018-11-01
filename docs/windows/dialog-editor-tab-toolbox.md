---
title: İletişim kutusu Düzenleyicisi sekmesi, araç kutusu (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- Toolbox [C++], Dialog Editor tab
- controls [C++], types
- syslink controls in dialog boxes
- custom controls [C++], dialog boxes
- controls [C++], standard
- Dialog Editor [C++], creating controls
- controls [C++], adding to dialog boxes
ms.assetid: 253885c2-dcb9-4d8e-ac9b-805ea31cbf5e
ms.openlocfilehash: ee5ee95f22c9cbcbde1d6c8b9ba1646f979697a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515241"
---
# <a name="dialog-editor-tab-toolbox-c"></a>İletişim kutusu Düzenleyicisi sekmesi, araç kutusu (C++)

**İletişim kutusu Düzenleyicisi** sekme görünür [araç penceresi](/visualstudio/ide/reference/toolbox) çalışırken **iletişim** Düzenleyici. Yeni, iletişim kutusuna denetimler ekleme, denetimleri sürükleyin **araç kutusu** da iletişim kutusuna oluşturmakta olduğunuz (daha fazla bilgi için bkz. [iletişim kutusuna denetim ekleme](adding-a-control-to-a-dialog-box.md)). Ardından, denetimleri yerleri veya kendi boyutu ve şekli değiştirin.

Standart denetimler bulunan **araç kutusu** şunlardır:

- [Düğme denetimi](../mfc/reference/cbutton-class.md)

- [Onay kutusu denetimi](../mfc/reference/styles-used-by-mfc.md#button-styles)

- [Birleşik giriş kutusu denetimi](../mfc/reference/ccombobox-class.md)

- [Düzenleme denetimi](../mfc/reference/cedit-class.md)

- Grup kutusu

- [Liste kutusu denetimi](../mfc/reference/clistbox-class.md)

- [Radyo düğmesi denetimini](../mfc/reference/styles-used-by-mfc.md#button-styles)

- [Statik metin denetimi](../mfc/reference/cstatic-class.md)

- [Resim denetimi](../mfc/reference/cpictureholder-class.md)

- [Zengin düzenleme 2.0 denetimi](../mfc/using-cricheditctrl.md)

- [Kaydırma çubuğu denetimi](../mfc/reference/cscrollbar-class.md)

[Windows ortak denetimleri](../mfc/controls-mfc.md) bulunan **araç kutusu** uygulamanızdaki işlevsellik sağlar. Bunlara aşağıdakiler dahildir:

- [Kaydırıcı denetimi](../mfc/slider-control-styles.md)

- [Döndürme denetimi](../mfc/using-cspinbuttonctrl.md)

- [İlerleme denetimi](../mfc/styles-for-the-progress-control.md)

- [Sık kullanılan anahtarı denetimi](../mfc/using-a-hot-key-control.md)

- [Liste denetimi](../mfc/list-control-and-list-view.md)

- [Ağaç denetimi](../mfc/tree-control-styles.md)

- [Sekme denetimi](../mfc/tab-controls-and-property-sheets.md)

- [Animasyon denetimi](../mfc/using-an-animation-control.md)

- [Tarih Saat Seçici denetimi](../mfc/creating-the-date-and-time-picker-control.md)

- [Ay takvim denetimi](../mfc/month-calendar-control-examples.md)

- [IP adresi denetimi](../mfc/reference/cipaddressctrl-class.md)

- [Genişletilmiş Birleşik giriş kutusu denetimi](../mfc/creating-an-extended-combo-box-control.md)

- [Özel Denetim](custom-controls-in-the-dialog-editor.md)

Seçerek iletişim kutusuna özel denetimleri ekleyebilirsiniz **özel denetim** simgesini **araç kutusu** ve, iletişim kutusuna sürükleyerek. Eklemek için bir **Syslink** denetimi, bir özel denetim eklemek ve ardından denetimin değiştirme **sınıfı** özelliğini **Syslink**. Bu özellikleri yenileyin ve göstermek neden **Syslink** denetim özellikleri. MFC sarmalayıcı sınıfı hakkında daha fazla bilgi için bkz. [CLinkCtrl](../mfc/reference/clinkctrl-class.md).

Ayrıca [, iletişim kutusuna ActiveX denetimleri ekleme](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md).

Ayrıca özelleştirebilirsiniz **araç kutusu** penceresi daha kolay kullanım için. Daha fazla bilgi için [araç kutusunu kullanma](/visualstudio/ide/using-the-toolbox).

Kullanma hakkında daha fazla bilgi için **RichEdit 1.0** MFC ile denetlemek için bkz: [MFC ile RichEdit 1.0 denetimini kullanma](../windows/using-the-richedit-1-0-control-with-mfc.md)

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Denetimler](../mfc/controls-mfc.md)<br/>
[Denetim Sınıfları](../mfc/control-classes.md)<br/>
[İletişim Kutusu Sınıfları](../mfc/dialog-box-classes.md)<br/>
[Kaydırma çubuğu stilleri](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles)<br/>
[Zengin Düzenleme Denetimine Örnekler](../mfc/rich-edit-control-examples.md)<br/>
[İletişim Kutusu Denetimleri için Olay İşleyicileri Ekleme](../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[İletişim Kutusu Denetimleri ve Değişken Türleri](../ide/dialog-box-controls-and-variable-types.md)