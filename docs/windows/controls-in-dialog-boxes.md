---
title: (C++) iletişim kutularındaki denetimler | Microsoft Docs
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], dialog boxes
- dialog box controls [C++], about dialog box controls
- dialog box controls
ms.assetid: e216c4f9-2fd4-429d-889a-8ebce7bad177
ms.openlocfilehash: 3f559a82d7c73dd8050f23e0b3af34f0bcb410c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644892"
---
# <a name="controls-in-dialog-box-ces"></a>Es denetimleri iletişim kutusu (C++)

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

- [İletişim Kutusu Düzenleyicisindeki Özel Denetimler](custom-controls-in-the-dialog-editor.md)

- [Anımsatıcıları Tanımlama (Erişim Tuşları)](../windows/defining-mnemonics-access-keys.md)

- [İletişim Kutusunun Boyutunu ve Konumunu Belirtme](../windows/specifying-the-location-and-size-of-a-dialog-box.md)

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutusu Denetimleri için Olay İşleyicileri Ekleme](../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[İletişim Kutusu Denetimleri ve Değişken Türleri](../ide/dialog-box-controls-and-variable-types.md)<br/>
[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)