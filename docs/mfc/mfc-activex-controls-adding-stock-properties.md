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
ms.openlocfilehash: 16bdfddf0c028bc6a312767844b38c58c942d56e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364655"
---
# <a name="mfc-activex-controls-adding-stock-properties"></a>MFC ActiveX Denetimleri: Stok Özellikler Ekleme

Stok özellikleri, sınıf `COleControl`tarafından zaten uygulanmış olması açısından özel özelliklerden farklıdır. `COleControl`denetim için ortak özellikleri destekleyen önceden tanımlanmış üye işlevleri içerir. Bazı yaygın özellikler denetimin başlığı ve ön plan ve arka plan renkleri içerir. Diğer stok özellikleri hakkında bilgi için, bu makalenin ilerleyen günlerinde [Özellik Ekle Sihirbazı tarafından desteklenen Stok Özellikleri'ne](#_core_stock_properties_supported_by_classwizard) bakın. Stok özellikleri için sevkiyat haritası girişleri her zaman DISP_STOCKPROP tarafından önceden belirlenmiştir.

Bu makalede, Özellik Ekle Sihirbazı'nı kullanarak ActiveX denetimine bir stok özelliğinin (bu durumda, Resim Yazısı) nasıl ekleyeceğiniz açıklanır ve ortaya çıkan kod değişikliklerini açıklar. Konu başlıkları şunlardır:

- [Stok özelliği eklemek için Özellik Ekle Sihirbazı'nı kullanma](#_core_using_classwizard_to_add_a_stock_property)

- [Stok özellikleri için Özellik Sihirbazı değişiklikleri ekleme](#_core_classwizard_changes_for_stock_properties)

- [Özellik Ekle Sihirbazı tarafından desteklenen stok özellikleri](#_core_stock_properties_supported_by_classwizard)

- [Stok özellikleri ve bildirim](#_core_stock_properties_and_notification)

- [Renk özellikleri](#_core_color_properties)

    > [!NOTE]
    >  Visual Basic özel denetimleri genellikle Üst, Sol, Genişlik, Yükseklik, Hizala, Etiket, Ad, Sekme Dizini, TabStop ve Üst öğe gibi özelliklere sahiptir. ActiveX denetim kapları, ancak, bu denetim özelliklerinin uygulanmasından sorumludur ve bu nedenle ActiveX denetimleri bu özellikleri desteklememelidir.

## <a name="using-the-add-property-wizard-to-add-a-stock-property"></a><a name="_core_using_classwizard_to_add_a_stock_property"></a>Stok Özelliği Eklemek Için Özellik Ekle Sihirbazı'nı Kullanma

Stok özellikleri eklemek, özel özellikler eklemekten daha az kod `COleControl`gerektirir, çünkü özellik için destek otomatik olarak . Aşağıdaki yordam, stok Başlığı özelliğinin ActiveX denetim çerçevesine eklenmesini gösterir ve diğer stok özelliklerini eklemek için de kullanılabilir. Seçili stok mülk adını Resim Yazısı ile değiştirin.

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>Özellik Ekle Sihirbazı'nı kullanarak stok Resim Yazısı özelliğini eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü'nde, denetiminizin kitaplık düğümunu genişletin.

1. Kısayol menüsünü açmak için denetiminiz için arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünden **Ekle'yi** tıklatın ve ardından **Özellik Ekle'yi**tıklatın.

   Bu Özellik [Ekle Sihirbazı'nı](../ide/names-add-property-wizard.md)açar.

1. Özellik **Adı** kutusunda **Resim Yazısı'nı**tıklatın.

1. **Son**'a tıklayın.

## <a name="add-property-wizard-changes-for-stock-properties"></a><a name="_core_classwizard_changes_for_stock_properties"></a>Stok Özellikleri için Özellik Sihirbazı Değişiklikleri Ekleme

Stok `COleControl` özelliklerini desteklediğinden, Özellik Ekle Sihirbazı sınıf bildirimini hiçbir şekilde değiştirmez; özelliği sevk haritasına ekler. Özellik Ekle Sihirbazı, uygulamada bulunan denetimin sevk haritasına aşağıdaki satırı ekler (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxUI#22](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_1.cpp)]

Aşağıdaki satır denetiminizin arabirim açıklamasına eklenir (. IDL) dosyası:

[!code-cpp[NVC_MFC_AxUI#23](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_2.idl)]

Bu satır, Resim Yazısı özelliğine belirli bir kimlik atar. Özelliğin bağlanabilir olduğuna ve değeri değiştirmeden önce veritabanından izin isteyeceğine dikkat edin.

Bu, Resim Yazısı özelliğini denetiminizdeki kullanıcılar tarafından kullanılabilir hale getirir. Bir stok özelliğinin değerini kullanmak için, taban sınıfın `COleControl` bir üye değişkenine veya üye işlevine erişin. Bu üye değişkenler ve üye işlevler hakkında daha fazla bilgi için, Özellik Ekle Sihirbazı tarafından desteklenen stok özellikleri sonraki bölüme bakın.

## <a name="stock-properties-supported-by-the-add-property-wizard"></a><a name="_core_stock_properties_supported_by_classwizard"></a>Özellik Ekle Sihirbazı tarafından desteklenen Stok Özellikleri

Sınıf `COleControl` dokuz stok özelliği sağlar. Özellik Ekle Sihirbazı'nı kullanarak istediğiniz özellikleri ekleyebilirsiniz.

|Özellik|Sevkiyat haritası girişi|Değere nasıl erişilir?|
|--------------|------------------------|-------------------------|
|`Appearance`|DISP_STOCKPROP_APPEARANCE ( )|Değer olarak `m_sAppearance`erişilebilir.|
|`BackColor`|DISP_STOCKPROP_BACKCOLOR ( )|Arayarak erişilebilen `GetBackColor`değer.|
|`BorderStyle`|DISP_STOCKPROP_BORDERSTYLE( )|Değer olarak `m_sBorderStyle`erişilebilir.|
|`Caption`|DISP_STOCKPROP_CAPTION ( )|Arayarak erişilebilen `InternalGetText`değer.|
|`Enabled`|DISP_STOCKPROP_ENABLED ( )|Değer olarak `m_bEnabled`erişilebilir.|
|`Font`|DISP_STOCKPROP_FONT ( )|[MFC ActiveX Denetimleri makalesine bakın:](../mfc/mfc-activex-controls-using-fonts.md) Kullanım için Yazı Tiplerini Kullanma.|
|`ForeColor`|DISP_STOCKPROP_FORECOLOR ( )|Arayarak erişilebilen `GetForeColor`değer.|
|`hWnd`|DISP_STOCKPROP_HWND ( )|Değer olarak `m_hWnd`erişilebilir.|
|`Text`|DISP_STOCKPROP_TEXT ( )|Arayarak erişilebilen `InternalGetText`değer. Bu `Caption`özellik, özellik adı dışında aynıdır.|
|`ReadyState`|DISP_STOCKPROP_READYSTATE()|Veya olarak `m_lReadyState` erişilebilir değer`GetReadyState`|

## <a name="stock-properties-and-notification"></a><a name="_core_stock_properties_and_notification"></a>Stok Özellikleri ve Bildirim

Çoğu stok özelliğigeçersiz kılınabilecek bildirim işlevlerine sahiptir. Örneğin, `BackColor` özellik değiştirildiğinde, `OnBackColorChanged` işlev (denetim sınıfının bir üye işlevi) çağrılır. Varsayılan uygulama `COleControl`(in) `InvalidateControl`çağırır. Bu duruma yanıt olarak ek eylemler de yapmak istiyorsanız bu işlevi geçersiz kılın.

## <a name="color-properties"></a><a name="_core_color_properties"></a>Renk Özellikleri

Denetimi boyarken `ForeColor` stok `BackColor` ve özellikleri veya kendi özel renk özelliklerinizi kullanabilirsiniz. Renk özelliği ni kullanmak için [COleControl::TranslateColor](../mfc/reference/colecontrol-class.md#translatecolor) üye işlevini arayın. Bu işlevin parametreleri renk özelliğinin değeri ve isteğe bağlı palet tutamacıdır. İade değeri, GDI işlevlerine aktarılabilen `SetTextColor` bir **COLORREF** değeridir. `CreateSolidBrush`

Stok `ForeColor` ve `BackColor` özelliklerin renk değerlerine sırasıyla `GetForeColor` işlevi `GetBackColor` veya işlevi arayarak erişilir.

Aşağıdaki örnek, denetimi boyarken bu iki renk özelliğinin kullanılmasını gösterir. Geçici bir **COLORREF** değişkenini `CBrush` ve çağrıiçeren `TranslateColor`bir nesneyi: biri `ForeColor` özelliği, diğerini `BackColor` özelliği kullanarak baş harfe çağırır. Daha `CBrush` sonra denetimin dikdörtgenini boyamak için geçici bir nesne kullanılır `ForeColor` ve metin rengi özellik kullanılarak ayarlanır.

[!code-cpp[NVC_MFC_AxUI#24](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: Özellikler](../mfc/mfc-activex-controls-properties.md)<br/>
[MFC ActiveX Denetimleri: Yöntemler](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl Sınıfı](../mfc/reference/colecontrol-class.md)
