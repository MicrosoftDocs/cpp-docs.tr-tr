---
title: 'MFC ActiveX Denetimleri: Stok Özellikler Ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- BackColor property [MFC]
- properties [MFC], adding stock
- ForeColor property [MFC]
- MFC ActiveX controls [MFC], properties
- foreground colors, ActiveX controls
- foreground colors [MFC]
ms.assetid: 8b98c8c5-5b69-4366-87bf-0e61e6668ecb
ms.openlocfilehash: 27fed55ac8a5fc8b95f81c1bfd2c6edb3da6227d
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502242"
---
# <a name="mfc-activex-controls-adding-stock-properties"></a>MFC ActiveX Denetimleri: Stok Özellikler Ekleme

Hisse senedi özellikleri, sınıfı tarafından zaten uygulanmış oldukları özel özelliklerden farklıdır `COleControl` . `COleControl` Denetim için ortak özellikleri destekleyen önceden tanımlanmış üye işlevlerini içerir. Bazı ortak özellikler, denetimin başlığını ve ön plan ve arka plan renklerini içerir. Diğer stok özellikleri hakkında daha fazla bilgi için bu makalenin ilerleyen kısımlarında [Özellik Ekleme Sihirbazı tarafından desteklenen stok özellikleri](#_core_stock_properties_supported_by_classwizard) bölümüne bakın. Hisse senedi özelliklerine ait dağıtım eşleme girişlerine DISP_STOCKPROP her zaman ön eki uygulanır.

Bu makalede Özellik Ekleme Sihirbazı kullanılarak bir ActiveX denetimine stok özelliğinin (Bu örnekte, açıklamalı alt yazı) nasıl ekleneceği ve sonuçta elde edilen kod değişikliklerinin nasıl yapılacağı açıklanır. Konu başlıkları şunlardır:

- [Stok özelliği eklemek için Özellik Ekleme Sihirbazı 'Nı kullanma](#_core_using_classwizard_to_add_a_stock_property)

- [Stok özellikleri için Özellik Ekleme Sihirbazı değişiklikleri](#_core_classwizard_changes_for_stock_properties)

- [Özellik Ekleme Sihirbazı tarafından desteklenen stok özellikleri](#_core_stock_properties_supported_by_classwizard)

- [Hisse senedi özellikleri ve bildirimi](#_core_stock_properties_and_notification)

- [Renk özellikleri](#_core_color_properties)

    > [!NOTE]
    >  Visual Basic özel denetimler genellikle top, Left, Width, Height, ALIGN, Tag, Name, TabIndex, TabStop ve Parent gibi özelliklere sahiptir. Ancak, ActiveX denetim kapsayıcıları bu denetim özelliklerini uygulamaktan sorumludur ve bu nedenle ActiveX denetimleri bu özellikleri desteklememelidir.

## <a name="using-the-add-property-wizard-to-add-a-stock-property"></a><a name="_core_using_classwizard_to_add_a_stock_property"></a> Stok özelliği eklemek için Özellik Ekleme Sihirbazı 'Nı kullanma

Özellik için destek, tarafından otomatik olarak işlendiğinden, stok özelliklerinin eklenmesi özel özellikler eklemekten daha az kod gerektirir `COleControl` . Aşağıdaki yordamda, bir ActiveX denetim çerçevesine hisse senedi başlık özelliğinin eklenmesi gösterilmektedir ve diğer stok özelliklerini eklemek için de kullanılabilir. Başlık için seçili stok özelliği adını değiştirin.

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı 'nı kullanarak hisse senedi başlık özelliğini eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü, denetiminizin kitaplık düğümünü genişletin.

1. Kısayol menüsünü açmak için denetiminizin arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **Özellik Ekle**' ye tıklayın.

   Bu, [Özellik Ekleme Sihirbazı](../ide/adding-a-property-visual-cpp.md#names-add-property-wizard)' nı açar.

1. **Özellik adı** kutusunda, **başlık**' a tıklayın.

1. **Son**'a tıklayın.

## <a name="add-property-wizard-changes-for-stock-properties"></a><a name="_core_classwizard_changes_for_stock_properties"></a> Stok özellikleri için Özellik Ekleme Sihirbazı değişiklikleri

`COleControl`Stok özelliklerini desteklediğinden Özellik Ekleme Sihirbazı sınıf bildirimini herhangi bir şekilde değiştirmez; özelliği dağıtım haritasına ekler. Özellik Ekleme Sihirbazı, uygulamada bulunan denetimin dağıtım eşlemesine aşağıdaki satırı ekler (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxUI#22](codesnippet/cpp/mfc-activex-controls-adding-stock-properties_1.cpp)]

Denetiminizin arabirim açıklamasına () aşağıdaki satır eklenir. IDL) dosyası:

[!code-cpp[NVC_MFC_AxUI#23](codesnippet/cpp/mfc-activex-controls-adding-stock-properties_2.idl)]

Bu satır, Caption özelliğini belirli bir KIMLIK olarak atar. Özelliğin bağlanabilir olduğunu ve değeri değiştirmeden önce veritabanından izin isteyeceğini unutmayın.

Bu, Caption özelliğini denetiminizin kullanıcıları için kullanılabilir hale getirir. Bir stok özelliğinin değerini kullanmak için, taban sınıfının üye değişkenine veya üye işlevine erişin `COleControl` . Bu üye değişkenleri ve üye işlevleri hakkında daha fazla bilgi için, Özellik Ekleme Sihirbazı tarafından desteklenen stok özellikleri başlıklı sonraki bölüme bakın.

## <a name="stock-properties-supported-by-the-add-property-wizard"></a><a name="_core_stock_properties_supported_by_classwizard"></a> Özellik Ekleme Sihirbazı tarafından desteklenen stok özellikleri

`COleControl`Sınıfı dokuz hisse senedi özellikleri sağlar. Özellik Ekleme Sihirbazı 'nı kullanarak istediğiniz özellikleri ekleyebilirsiniz.

|Özellik|Dağıtım eşleme girişi|Değere erişme|
|--------------|------------------------|-------------------------|
|`Appearance`|DISP_STOCKPROP_APPEARANCE ()|Değer olarak erişilebilir `m_sAppearance` .|
|`BackColor`|DISP_STOCKPROP_BACKCOLOR ()|Çağırarak değere erişilebilir `GetBackColor` .|
|`BorderStyle`|DISP_STOCKPROP_BORDERSTYLE ()|Değer olarak erişilebilir `m_sBorderStyle` .|
|`Caption`|DISP_STOCKPROP_CAPTION ()|Çağırarak değere erişilebilir `InternalGetText` .|
|`Enabled`|DISP_STOCKPROP_ENABLED ()|Değer olarak erişilebilir `m_bEnabled` .|
|`Font`|DISP_STOCKPROP_FONT ()|[MFC ActiveX denetimleri: Kullanım Için yazı tiplerini kullanma](mfc-activex-controls-using-fonts.md) makalesine bakın.|
|`ForeColor`|DISP_STOCKPROP_FORECOLOR ()|Çağırarak değere erişilebilir `GetForeColor` .|
|`hWnd`|DISP_STOCKPROP_HWND ()|Değer olarak erişilebilir `m_hWnd` .|
|`Text`|DISP_STOCKPROP_TEXT ()|Çağırarak değere erişilebilir `InternalGetText` . Bu özellik `Caption` , özellik adı hariç, ile aynıdır.|
|`ReadyState`|DISP_STOCKPROP_READYSTATE ()|Değer veya olarak erişilebilir `m_lReadyState``GetReadyState`|

## <a name="stock-properties-and-notification"></a><a name="_core_stock_properties_and_notification"></a> Hisse senedi özellikleri ve bildirimi

Çoğu stok özelliği geçersiz kılınabilen bildirim işlevlerine sahiptir. Örneğin, `BackColor` özellik her değiştirildiğinde, `OnBackColorChanged` işlev (denetim sınıfının üye işlevi) çağrılır. Varsayılan uygulama (ın `COleControl` ) çağrılarında `InvalidateControl` . Bu duruma yanıt olarak ek eylemler gerçekleştirmek istiyorsanız bu işlevi geçersiz kılın.

## <a name="color-properties"></a><a name="_core_color_properties"></a> Renk özellikleri

`ForeColor` `BackColor` Denetimi boyadığınızda stok ve özellikleri ya da kendi özel renk özelliklerinizi kullanabilirsiniz. Color özelliği kullanmak için [Coelcontrol:: TranslateColor](reference/colecontrol-class.md#translatecolor) üye işlevini çağırın. Bu işlevin parametreleri, Color özelliğinin ve isteğe bağlı bir palet tanıtıcısının değeridir. Dönüş değeri, ve gibi GDI işlevlerine geçirilebilecek bir **colorref** değeridir `SetTextColor` `CreateSolidBrush` .

Stok ve özelliklerin renk değerlerine, `ForeColor` `BackColor` `GetForeColor` sırasıyla veya işlevi çağırarak erişilir `GetBackColor` .

Aşağıdaki örnek, bir denetim boyadığınızda bu iki renk özelliklerinin kullanımını gösterir. Geçici bir **colorref** değişkeni ve çağrısı olan bir nesnesi, özelliğini kullanarak `CBrush` `TranslateColor` `ForeColor` özelliği ve diğerini kullanarak başlatır `BackColor` . `CBrush`Daha sonra denetimin dikdörtgenini boyamak için geçici bir nesne kullanılır ve metin rengi özelliği kullanılarak ayarlanır `ForeColor` .

[!code-cpp[NVC_MFC_AxUI#24](codesnippet/cpp/mfc-activex-controls-adding-stock-properties_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)<br/>
[MFC ActiveX denetimleri: Özellikler](mfc-activex-controls-properties.md)<br/>
[MFC ActiveX denetimleri: Yöntemler](mfc-activex-controls-methods.md)<br/>
[Coelcontrol sınıfı](reference/colecontrol-class.md)
