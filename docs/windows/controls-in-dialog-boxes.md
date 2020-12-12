---
description: 'Hakkında daha fazla bilgi edinin: Iletişim kutusu denetimleri (C++)'
title: İletişim kutusu denetimleri (C++) | Microsoft Docs
ms.date: 02/15/2019
f1_keywords:
- Custom Control
helpviewer_keywords:
- controls [C++], dialog boxes
- dialog box controls [C++], about dialog box controls
- dialog box controls
- controls [C++], templates
- custom controls [C++], dialog boxes
- custom controls [C++]
- dialog box controls [C++], custom (user) controls
- Dialog Editor [C++], custom controls
ms.assetid: e216c4f9-2fd4-429d-889a-8ebce7bad177
ms.openlocfilehash: e68547ebd550797d4ad195c6bef4c3f2a71e769e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327154"
---
# <a name="dialog-box-controls-c"></a>İletişim kutusu denetimleri (C++)

İletişim kutusuna, istediğiniz denetimi seçmenizi ve iletişim kutusu üzerine [sürüklemeyi sağlayan](/visualstudio/ide/reference/toolbox) **iletişim kutusu Düzenleyicisi** sekmesini kullanarak denetim ekleyebilirsiniz. Varsayılan olarak, **araç kutusu** penceresi otomatik olarak gizleyecek şekilde ayarlanır. **Iletişim kutusu Düzenleyicisi** açıkken çözümünüzün sol kenar boşluğunda bir sekme olarak görünür. Ancak, pencerenin sağ üst köşesindeki **Otomatik Gizle** düğmesini seçerek **araç kutusu** penceresini konuma sabitleyebilirsiniz. Bu pencerenin davranışını denetleme hakkında daha fazla bilgi için bkz. [pencere yönetimi](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

Bir iletişim kutusuna Denetim eklemenin, varolan denetimlerin yeniden konumlandırmanın veya denetimleri bir iletişim kutusundan diğerine taşımanın en hızlı yolu, sürükle ve bırak yöntemini kullanmaktır. Denetimin konumu, iletişim kutusuna bırakılana kadar noktalı bir satırda ana hatlarıyla açıklanmıştır. Sürükle ve bırak yöntemiyle bir iletişim kutusuna bir denetim eklediğinizde, denetime bu denetim türüne uygun standart bir yükseklik verilir.

Bir iletişim kutusuna bir denetim eklediğinizde veya onu yeniden konumlandırdığınızda, son yerleşimi kılavuzlar veya kenar boşlukları tarafından belirlenebilir ya da Düzen kılavuzunun açık olup olmadığını gösterebilir.

İletişim kutusuna bir denetim ekledikten sonra, [Özellikler penceresinde](/visualstudio/ide/reference/properties-window)başlık gibi özellikleri değiştirebilirsiniz. Ayrıca, birden çok denetim seçebilir ve özelliklerini tek seferde değiştirebilirsiniz.

**Iletişim kutusu Düzenleyicisi** hakkında daha fazla bilgi için bkz. [denetimleri ekleme, düzenleme veya silme](adding-editing-or-deleting-controls.md), [düzen denetimleri](../windows/arrangement-of-controls-on-dialog-boxes.md)ve [Denetim erişimini ve değerlerini tanımlama](../windows/defining-mnemonics-access-keys.md).

Denetimler ve iletişim kutuları hakkında daha fazla bilgi için bkz. [denetim sınıfları](../mfc/control-classes.md), [iletişim kutusu sınıfları](../mfc/dialog-box-classes.md)ve [kaydırma çubuğu stilleri](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles).

**Araç kutusunda** varsayılan olaylarla kullanılabilen standart denetimler şunlardır:

|Denetim adı|Varsayılan olay|
|---|---|
|[Düğme denetimi](../mfc/reference/cbutton-class.md)|BN_CLICKED|
|[Onay kutusu denetimi](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[Birleşik giriş kutusu denetimi](../mfc/reference/ccombobox-class.md)|CBN_SELCHANGE|
|[Denetimi Düzenle](../mfc/reference/cedit-class.md)|EN_CHANGE|
|Grup kutusu|(uygulanamaz)|
|[Liste kutusu denetimi](../mfc/reference/clistbox-class.md)|LBN_SELCHANGE|
|[Radyo düğmesi denetimi](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[Statik metin denetimi](../mfc/reference/cstatic-class.md)|(uygulanamaz)|
|[Resim denetimi](../mfc/reference/cpictureholder-class.md)|(uygulanamaz)|
|[Zengin düzenleme 2,0 denetimi](../mfc/using-cricheditctrl.md)|EN_CHANGE|
|[Kaydırma çubuğu denetimi](../mfc/reference/cscrollbar-class.md)|NM_THEMECHANGED|

> [!NOTE]
> MFC ile **richedit 1,0** denetimini kullanma hakkında daha fazla bilgi için bkz. MFC ve [zengin düzenleme denetimi örnekleri](../mfc/rich-edit-control-examples.md) [ile RichEdit 1,0 denetimini kullanma](./adding-editing-or-deleting-controls.md) .

Daha fazla işlevsellik sağlamak için **araç kutusu** 'Nda bulunan [Windows ortak denetimleri](../mfc/controls-mfc.md) şunlardır:

|Denetim adı|Varsayılan olay|
|---|---|
|[Kaydırıcı denetimi](../mfc/slider-control-styles.md)|NM_CUSTOMDRAW|
|[Döndürme denetimi](../mfc/using-cspinbuttonctrl.md)|UDN_DELTAPOS|
|[İlerleme denetimi](../mfc/styles-for-the-progress-control.md)|NM_CUSTOMDRAW|
|[Sık kullanılan tuş denetimi](../mfc/using-a-hot-key-control.md)|NM_OUTOFMEMORY|
|[Liste denetimi](../mfc/list-control-and-list-view.md)|LVN_ITEMCHANGE|
|[Ağaç denetimi](../mfc/tree-control-styles.md)|TVN_SELCHANGE|
|[Sekme denetimi](../mfc/tab-controls-and-property-sheets.md)|TCN_SELCHANGE|
|[Animasyon denetimi](../mfc/using-an-animation-control.md)|ACN_START|
|[Tarih saat seçici denetimi](../mfc/creating-the-date-and-time-picker-control.md)|DTN_DATETIMECHANGE|
|[Aylık Takvim denetimi](../mfc/month-calendar-control-examples.md)|MCN_SELCHANGE|
|[IP adresi denetimi](../mfc/reference/cipaddressctrl-class.md)|IPN_FIELDCHANGED|
|[Genişletilmiş Birleşik giriş kutusu denetimi](../mfc/creating-an-extended-combo-box-control.md)||
|Özel denetim|TTN_GETDISPINFO|

## <a name="custom-controls"></a>Özel denetimler

**İletişim kutusu Düzenleyicisi** , mevcut özel veya kullanıcı denetimlerini bir iletişim kutusu şablonunda kullanmanıza olanak sağlar.

> [!NOTE]
> Bu anlamda özel denetimlerin, ActiveX denetimleriyle karıştırılmamalıdır. ActiveX denetimleri bazen OLE özel denetimleri olarak adlandırılır. Ayrıca, bu denetimleri Windows 'daki sahip tarafından çizilen denetimlerle karıştırmayın.

Bu işlevsellik, Windows tarafından sağlananlardan farklı denetimleri kullanmanıza olanak sağlamak için tasarlanmıştır. Çalışma zamanında, denetim bir pencere sınıfıyla ilişkilendirilir (C++ sınıfıyla aynı değildir). Aynı görevi gerçekleştirmenin daha yaygın bir yolu, iletişim kutusunda statik denetim gibi herhangi bir denetimi yüklemektir. Sonra, [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) işlevinde, çalışma zamanında bu denetimi kaldırın ve kendi özel denetiinkini değiştirin.

> [!NOTE]
> Bu, eski bir tekniktir. Bugün, çoğu durumda bir ActiveX denetimi yazmak veya Windows ortak denetimi alt sınıfı yapmanız önerilir.

Bu özel denetimler için şu adımları sınırlayabilirsiniz:

- İletişim kutusunda konum ayarlanıyor.

- Bir resim yazısı yazma.

- Uygulama kodunuzun denetimi bu ada göre kaydetmesi gerektiğinden, denetimin Windows sınıfının adını tanımlama.

- Denetimin stilini ayarlayan 32 bitlik bir onaltılı değer yazın.

- Genişletilmiş Stil ayarlanıyor.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[İletişim kutusu Düzenleyicisi](../windows/dialog-editor.md)

<!--
[Adding Event Handlers for Dialog Box Controls](./adding-editing-or-deleting-controls.md)<br/>
[Dialog Box Controls and Variable Types](../ide/adding-a-member-variable-visual-cpp.md#dialog-box-controls-and-variable-types)<br/>
[Controls](../mfc/controls-mfc.md)<br/>-->
