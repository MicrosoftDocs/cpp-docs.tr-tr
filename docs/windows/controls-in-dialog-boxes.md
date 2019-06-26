---
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
ms.openlocfilehash: 568754bc514ae017293805fab1b25849d5ffe5f8
ms.sourcegitcommit: 8bb2bea1384b290b7570b01608a86c7488ae7a02
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67400879"
---
# <a name="dialog-box-controls-c"></a>İletişim kutusu denetimleri (C++)

Kullanarak bir iletişim kutusu denetimleri ekleyebilirsiniz **iletişim kutusu Düzenleyicisi** sekmesinde [araç penceresi](/visualstudio/ide/reference/toolbox) iletişim kutusuna sürükleyin ve istediğiniz denetimini seçmenize olanak sağlar. Varsayılan olarak, **araç kutusu** pencere otomatik gizleme için ayarlanır. Çözümünüzün sol kenar çubuğunda sekme olarak göründüğü zaman **iletişim kutusu Düzenleyicisi** açıktır. Ancak, sabitleyebilirsiniz **araç kutusu** seçerek konumu penceresine **Otomatik Gizle** pencerenin sağ üst köşesindeki düğme. Bu pencere davranışını denetleme hakkında daha fazla bilgi için bkz. [pencere yönetimi](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

En hızlı yolu, iletişim kutusuna denetimler ekleme, mevcut denetimleri yeniden konumlandırma veya denetimleri bir iletişim kutusundan bir diğerine taşımak için sürükle ve bırak yöntemini kullanmaktır. Bu iletişim kutusuna bırakılana kadar denetimin konumu noktalı çizgi gösterebilir. Sürükle ve bırak yöntemiyle bir iletişim kutusu için bir denetim eklediğinizde, denetimin denetim türü için uygun bir standart yüksekliğini verilir.

İletişim kutusuna denetim ekleme ya da yeniden konumlandırdığınız son yerleşimi kılavuzları veya kenar boşlukları tarafından belirlenebilir veya açık Düzen kılavuzunu gerekip gerekmediğini belirtir.

İletişim kutusuna bir denetimi ekledikten sonra özellikleri gibi başlığı değiştirebilirsiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Ayrıca, birden çok denetim seçin ve özelliklerini tamamını aynı anda değiştirebilirsiniz.

Hakkında daha fazla bilgi için **iletişim kutusu Düzenleyicisi**, bkz. nasıl [ekleme, düzenleme veya silme denetimleri](adding-editing-or-deleting-controls.md), [düzen denetimleri](../windows/arrangement-of-controls-on-dialog-boxes.md), ve [denetim erişimi tanımlar ve değerleri](../windows/defining-mnemonics-access-keys.md).

Denetimler ve iletişim kutuları hakkında daha fazla bilgi için bkz. [denetim sınıfları](../mfc/control-classes.md), [iletişim kutusu sınıfları](../mfc/dialog-box-classes.md), ve [kaydırma çubuğu stilleri](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles).

Kullanılabilir standart denetimler **araç kutusu** varsayılan olaylar şunlardır:

|Denetim adı|Varsayılan olay|
|---|---|
|[Düğme denetimi](../mfc/reference/cbutton-class.md)|BN_CLICKED|
|[Onay kutusu denetimi](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[Birleşik giriş kutusu denetimi](../mfc/reference/ccombobox-class.md)|CBN_SELCHANGE|
|[Düzenleme denetimi](../mfc/reference/cedit-class.md)|EN_CHANGE|
|Grup kutusu|(uygulanamaz)|
|[Liste kutusu denetimi](../mfc/reference/clistbox-class.md)|LBN_SELCHANGE|
|[Radyo düğmesi denetimini](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[Statik metin denetimi](../mfc/reference/cstatic-class.md)|(uygulanamaz)|
|[Resim denetimi](../mfc/reference/cpictureholder-class.md)|(uygulanamaz)|
|[Zengin düzenleme 2.0 denetimi](../mfc/using-cricheditctrl.md)|EN_CHANGE|
|[Kaydırma çubuğu denetimi](../mfc/reference/cscrollbar-class.md)|NM_THEMECHANGED|

> [!NOTE]
> Kullanma hakkında daha fazla bilgi için **RichEdit 1.0** MFC ile denetlemek için bkz: [MFC ile RichEdit 1.0 denetimini kullanma](../windows/using-the-richedit-1-0-control-with-mfc.md) ve [zengin düzenleme denetimine örnekler](../mfc/rich-edit-control-examples.md).

[Windows ortak denetimleri](../mfc/controls-mfc.md) bulunan **araç kutusu** olan işlevsellik sağlamak için:

|Denetim adı|Varsayılan olay|
|---|---|
|[Kaydırıcı denetimi](../mfc/slider-control-styles.md)|NM_CUSTOMDRAW|
|[Döndürme denetimi](../mfc/using-cspinbuttonctrl.md)|UDN_DELTAPOS|
|[İlerleme denetimi](../mfc/styles-for-the-progress-control.md)|NM_CUSTOMDRAW|
|[Sık kullanılan anahtarı denetimi](../mfc/using-a-hot-key-control.md)|NM_OUTOFMEMORY|
|[Liste denetimi](../mfc/list-control-and-list-view.md)|LVN_ITEMCHANGE|
|[Ağaç denetimi](../mfc/tree-control-styles.md)|TVN_SELCHANGE|
|[Sekme denetimi](../mfc/tab-controls-and-property-sheets.md)|TCN_SELCHANGE|
|[Animasyon denetimi](../mfc/using-an-animation-control.md)|ACN_START|
|[Tarih Saat Seçici denetimi](../mfc/creating-the-date-and-time-picker-control.md)|DTN_DATETIMECHANGE|
|[Ay takvim denetimi](../mfc/month-calendar-control-examples.md)|MCN_SELCHANGE|
|[IP adresi denetimi](../mfc/reference/cipaddressctrl-class.md)|IPN_FIELDCHANGED|
|[Genişletilmiş Birleşik giriş kutusu denetimi](../mfc/creating-an-extended-combo-box-control.md)||
|Özel Denetim|TTN_GETDISPINFO|

## <a name="custom-controls"></a>Özel denetimler

**İletişim kutusu Düzenleyicisi** var olanı Kullan özel veya kullanıcı denetimleri içinde bir iletişim kutusu şablonu sağlar.

> [!NOTE]
> Bu bağlamdaki özel denetimler ActiveX denetimleri ile karıştırılmamalıdır üzeresiniz. ActiveX denetimleri, bazen OLE özel denetimler adı veriliyordu. Ayrıca, bu denetimlerin Windows kullanıcı çizimli denetimler ile karıştırmayın.

Bu işlevsellik, Windows tarafından sağlanan dışındaki denetimleri kullanmanıza olanak yöneliktir. Çalışma zamanında denetim bir pencere sınıfı (değil bir C++ sınıfı aynı) ile ilişkilidir. Aynı görevi başarmak için daha yaygın bir yolu, sizin iletişim kutunuzda statik bir denetimi gibi herhangi bir denetimi yüklemektir. Ardından çalışma zamanında, buna [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) işlev, bu denetim kaldırın ve kendi özel bir denetim ile değiştirin.

> [!NOTE]
> Bu eski bir tekniktir. Bugün bir ActiveX denetimi veya bir Windows ortak denetimi alt yazmak için çoğu durumda önerilir.

Bu özel denetimler için sınırlı olursunuz:

- Konum iletişim kutusunda ayar.

- Bir başlık yazın.

- Uygulama kodunuz bu ada göre denetim kaydetmelisiniz beri denetimin Windows sınıfının adını tanımlama.

- Denetimin stilini ayarlar bir 32 bit onaltılık değer yazarak.

- Genişletilmiş stili ayarlanıyor.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)

<!--
[Adding Event Handlers for Dialog Box Controls](../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[Dialog Box Controls and Variable Types](../ide/dialog-box-controls-and-variable-types.md)<br/>
[Controls](../mfc/controls-mfc.md)<br/>-->