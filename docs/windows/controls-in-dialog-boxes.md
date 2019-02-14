---
title: (C++) iletişim kutularındaki denetimler | Microsoft Docs
ms.date: 11/04/2016
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
ms.openlocfilehash: 1f231a376b335d7fb711ef2039c13f49624e6bfb
ms.sourcegitcommit: eb2b34a24e6edafb727e87b138499fa8945f981e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2019
ms.locfileid: "56264848"
---
# <a name="controls-in-dialog-boxes-c"></a>(C++) iletişim kutularındaki denetimler

Kullanarak bir iletişim kutusu denetimleri ekleyebilirsiniz [iletişim kutusu Düzenleyicisi sekmesi](../windows/dialog-editor-tab-toolbox.md) içinde [araç penceresi](/visualstudio/ide/reference/toolbox), iletişim kutusuna sürükleyin ve istediğiniz denetim seçmenize olanak sağlar. Varsayılan olarak, araç penceresi otomatik gizleme için ayarlanır. İletişim kutusu düzenleyicisini açtığınızda çözümünüzün sol kenar çubuğunda sekme olarak görünür. Ancak, sabitleyebilirsiniz **araç kutusu** tıklayarak konumu penceresine **Otomatik Gizle** pencerenin sağ üst köşesindeki düğme. Bu pencere davranışını denetleme hakkında daha fazla bilgi için bkz. [pencere yönetimi](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

En hızlı yolu, iletişim kutusuna denetimler ekleme, mevcut denetimleri yeniden konumlandırma veya denetimleri bir iletişim kutusundan bir diğerine taşımak için sürükle ve bırak yöntemini kullanmaktır. Bu iletişim kutusuna bırakılana kadar denetimin konumu noktalı çizgi gösterebilir. Sürükle ve bırak yöntemiyle bir iletişim kutusu için bir denetim eklediğinizde, denetimin denetim türü için uygun bir standart yüksekliğini verilir.

İletişim kutusuna denetim ekleme ya da yeniden konumlandırdığınız son yerleşimi kılavuzları veya kenar boşlukları tarafından belirlenebilir veya açık Düzen kılavuzunu gerekip gerekmediğini belirtir.

İletişim kutusuna bir denetimi ekledikten sonra özellikleri gibi başlığı değiştirebilirsiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Birden çok denetim seçin ve özelliklerini tamamını aynı anda değiştirebilirsiniz.

- [Denetimleri Ekleme, Düzenleme veya Silme](adding-editing-or-deleting-controls.md)

- [Denetim Seçme](../windows/selecting-controls.md)

- [Tek Denetimleri Boyutlandırma](../windows/sizing-individual-controls.md)

- [Denetimleri Aynı Genişliğe, Yüksekliğe veya Boyuta Getirme](../windows/making-controls-the-same-width-height-or-size.md)

- [Birleşik Giriş Kutusu ve Aşağı Açılan Listesinin Boyutunu Ayarlama](setting-the-size-of-the-combo-box-and-its-drop-down-list.md)

- [Birleşik Giriş Kutusu Denetimine Değer Ekleme](../windows/adding-values-to-a-combo-box-control.md)

- [Yatay Kaydırma Çubuğunun Genişliğini Ayarlama](../windows/setting-the-width-of-a-horizontal-scroll-bar.md)

- [İletişim kutularındaki denetimlerin düzenlenmesi](../windows/arrangement-of-controls-on-dialog-boxes.md)

- [Anımsatıcıları Tanımlama (Erişim Tuşları)](../windows/defining-mnemonics-access-keys.md)

- [İletişim Kutusunun Boyutunu ve Konumunu Belirtme](../windows/specifying-the-location-and-size-of-a-dialog-box.md)

Kullanılabilir standart denetimler **araç kutusu** varsayılan olaylar şunlardır:

|Denetim adı|Varsayılan olay|
|---|---|
|[Düğme denetimi](../mfc/reference/cbutton-class.md)|BN_CLICKED|
|[Onay kutusu denetimi](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[Birleşik giriş kutusu denetimi](../mfc/reference/ccombobox-class.md)|CBN_SELCHANGE|
|[Düzenleme denetimi](../mfc/reference/cedit-class.md)|EN_CHANGE|
|Grup kutusu|(Uygulanamaz)|
|[Liste kutusu denetimi](../mfc/reference/clistbox-class.md)|LBN_SELCHANGE|
|[Radyo düğmesi denetimini](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[Statik metin denetimi](../mfc/reference/cstatic-class.md)|(Uygulanamaz)|
|[Resim denetimi](../mfc/reference/cpictureholder-class.md)|(Uygulanamaz)|
|[Zengin düzenleme 2.0 denetimi](../mfc/using-cricheditctrl.md)|EN_CHANGE|
|[Kaydırma çubuğu denetimi](../mfc/reference/cscrollbar-class.md)|NM_THEMECHANGED|

Kullanma hakkında daha fazla bilgi için **RichEdit 1.0** MFC ile denetlemek için bkz: [MFC ile RichEdit 1.0 denetimini kullanma](../windows/using-the-richedit-1-0-control-with-mfc.md) ve [zengin düzenleme denetimine örnekler](../mfc/rich-edit-control-examples.md).

[Windows ortak denetimleri](../mfc/controls-mfc.md) bulunan **araç kutusu** uygulamanızdaki işlevsellik sağlar. Bunlara aşağıdakiler dahildir:

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

Daha fazla bilgi için [denetim sınıfları](../mfc/control-classes.md), [iletişim kutusu sınıfları](../mfc/dialog-box-classes.md), ve [kaydırma çubuğu stilleri](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles).

## <a name="custom-controls"></a>Özel denetimler

İletişim kutusu Düzenleyicisi var olanı kullan "özel" veya "kullanıcı" iletişim kutusunda şablon denetimlerinde sağlar.

> [!NOTE]
> Bu bağlamdaki özel denetimler ActiveX denetimleri ile karıştırılmamalıdır üzeresiniz. ActiveX denetimleri, bazen OLE özel denetimler adı veriliyordu. Ayrıca, bu denetimlerin Windows kullanıcı çizimli denetimler ile karıştırmayın.

Bu işlevsellik, Windows tarafından sağlanan dışındaki denetimleri kullanmanıza olanak yöneliktir. Çalışma zamanında denetim bir pencere sınıfı (değil bir C++ sınıfı aynı) ile ilişkilidir. Aynı görevi başarmak için daha yaygın bir yolu, sizin iletişim kutunuzda statik bir denetimi gibi herhangi bir denetimi yüklemektir. Ardından çalışma zamanında, buna [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) işlev, bu denetim kaldırın ve kendi özel bir denetim ile değiştirin.

Bu eski bir tekniktir. Bugün bir ActiveX denetimi veya bir Windows ortak denetimi alt yazmak için çoğu durumda önerilir.

Bu özel denetimler için sınırlı olursunuz:

- Konum iletişim kutusunda ayar.

- Bir başlık yazın.

- (Uygulama kodunuzun bu ada göre denetim kaydetmelisiniz) denetimin Windows sınıfının adını belirleme.

- Denetimin stilini ayarlar bir 32 bit onaltılık değer yazarak.

- Genişletilmiş stili ayarlanıyor.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[İletişim Kutusu Denetimleri için Olay İşleyicileri Ekleme](../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[İletişim Kutusu Denetimleri ve Değişken Türleri](../ide/dialog-box-controls-and-variable-types.md)<br/>
[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)<br/>
[Denetimler](../mfc/controls-mfc.md)<br/>