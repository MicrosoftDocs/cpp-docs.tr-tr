---
title: Denetim ekleme iletişim kutusu (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.dialog
helpviewer_keywords:
- dialog boxes [C++], adding controls to
- Toolbox [C++], Dialog Editor tab
- controls [C++], types
- syslink controls in dialog boxes
- custom controls [C++], dialog boxes
- controls [C++], standard
- Dialog Editor [C++], creating controls
- controls [C++], adding to dialog boxes
- controls [C++], adding multiple
- dialog box controls [C++], size
- controls [C++], sizing
ms.assetid: b2a26d19-093f-49ca-93da-fef00dfbb381
ms.openlocfilehash: 92b644769bcbe2649d00ba68437bd474ee06dfcc
ms.sourcegitcommit: b488462a6e035131121e6f32d8f3b108cc798b5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55293630"
---
# <a name="adding-a-control-to-a-dialog-box-c"></a>Denetim ekleme iletişim kutusu (C++)

**İletişim kutusu Düzenleyicisi** sekme görünür [araç penceresi](/visualstudio/ide/reference/toolbox) çalışırken **iletişim** Düzenleyici. Yeni, iletişim kutusuna denetimler ekleme, denetimleri sürükleyin **araç kutusu** oluşturduğunuz iletişim kutusu. Ardından, denetimleri yerleri veya kendi boyutu ve şekli değiştirin.

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

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="to-add-a-control-to-a-dialog-box"></a>İletişim kutusuna denetim ekleme

1. Sekmeli pencere iletişim kutusu Düzenleyicisi çerçeveyi geçerli belgede olduğundan emin olun. Bir iletişim kutusu geçerli belge değilse göremezsiniz **iletişim kutusu Düzenleyicisi sekmesi** içinde **araç kutusu**.

1. Üzerinde **iletişim kutusu Düzenleyicisi** sekmesinde [araç penceresi](/visualstudio/ide/reference/toolbox), ardından istediğiniz denetimi seçin:

   - İletişim kutusunu denetimi yerleştirmek istediğiniz yeri seçin. Burada seçtiğiniz denetimi görünür.

       \- veya -

   - Sürükle ve bırak denetiminden **araç kutusu** pencere, iletişim kutusu konumuna.

       \- veya -

   - Denetimde çift **araç kutusu** penceresi (iletişim kutusunda görünür) sonra denetim tercih ettiğiniz bir konuma yeniden konumlandırma.

## <a name="to-add-multiple-controls"></a>Birden çok denetim eklemek için

1. Tutarken **Ctrl** anahtar, bir denetimi seçin [araç penceresi](/visualstudio/ide/reference/toolbox).

1. Yayın **Ctrl** anahtar ve birçok kez olarak özel denetim eklemek istediğiniz gibi iletişim kutusunu seçin.

1. Tuşuna **Esc** denetimleri yerleştirme durdurmak için.

## <a name="to-size-a-control-while-you-add-it"></a>Eklerken denetimi bir boyutu

1. Bir denetimi seçin [araç penceresi](/visualstudio/ide/reference/toolbox).

1. (Bu çizgileri gibi çapraz görünür) imlecinizi yeni denetim, iletişim kutusunda sol üst köşesindeki istediğiniz konuma yerleştirin.

1. Seçin ve iletişim kutusunda, denetimin sol üst köşesinin bağlantı için fare düğmesini basılı tutun ve imleci denetimin istediğiniz boyuta kadar sağa ve aşağı sürükleyin.

   > [!NOTE]
   > Aslında, çizim denetimi dört köşelerini hiçbirini kenarına bağlanabilir. Bu yordam üst sol löşede örnek olarak kullanılır.

1. Fare düğmesini bırakın. İletişim kutusunda, belirtilen boyut üzerine denetimini kapatır.

   > [!TIP]
   > İletişim kutusuna boyutlandırma kenarlığı denetimin taşıyarak bırakmadan sonra denetimi yeniden boyutlandırabilirsiniz. Daha fazla bilgi için [tek denetimleri boyutlandırma](../windows/sizing-individual-controls.md).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)<br/>
[İletişim Kutusu Denetimleri için Olay İşleyicileri Ekleme](../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[İletişim Kutusu Denetimleri ve Değişken Türleri](../ide/dialog-box-controls-and-variable-types.md)<br/>
[Denetimler](../mfc/controls-mfc.md)<br/>
[Denetim Sınıfları](../mfc/control-classes.md)<br/>
[İletişim Kutusu Sınıfları](../mfc/dialog-box-classes.md)<br/>
[Kaydırma çubuğu stilleri](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles)<br/>
[Zengin Düzenleme Denetimine Örnekler](../mfc/rich-edit-control-examples.md)<br/>
