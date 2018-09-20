---
title: 'MFC ActiveX denetimleri: Stok Özellikler ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- BackColor property [MFC]
- properties [MFC], adding stock
- ForeColor property [MFC]
- MFC ActiveX controls [MFC], properties
- foreground colors, ActiveX controls
- foreground colors [MFC]
ms.assetid: 8b98c8c5-5b69-4366-87bf-0e61e6668ecb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4100dc14a25a744e5c28ffd1b16119408d800656
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404520"
---
# <a name="mfc-activex-controls-adding-stock-properties"></a>MFC ActiveX Denetimleri: Stok Özellikler Ekleme

Stok özellikleri içeren sınıfı tarafından zaten uygulanmış özel özelliklerinden farklı `COleControl`. `COleControl` Denetim için yaygın olarak kullanılan özellikleri desteklemek önceden tanımlanmış üye işlevleri içerir. Bazı ortak özellikler, denetimin açıklamalı alt yazı ve ön ve arka plan renkleri içerir. Diğer stok özellikleri hakkında daha fazla bilgi için bkz: [stok özellikleri Özellik Ekleme Sihirbazı'nı tarafından desteklenen](#_core_stock_properties_supported_by_classwizard) bu makalenin ilerleyen bölümlerinde. Gönderme eşleme girişleri için stok özellikleri her zaman DISP_STOCKPROP tarafından öneki.

Bu makalede, Özellik Ekleme Sihirbazı'nı kullanarak bir ActiveX denetimine stok bir özellik (Bu durumda, resim yazısı) eklemeyi açıklar ve sonuçta elde edilen kod değişikliklerini açıklar. Konular şunlardır:

- [Stok özelliği eklemek için Özellik Ekleme Sihirbazı'nı kullanma](#_core_using_classwizard_to_add_a_stock_property)

- [Stok özellikleri için özellik Sihirbazı değişiklikleri ekleyin](#_core_classwizard_changes_for_stock_properties)

- [Özellik Ekleme Sihirbazı tarafından desteklenen stok özellikleri](#_core_stock_properties_supported_by_classwizard)

- [Stok özellikleri ve bildirim](#_core_stock_properties_and_notification)

- [Renk özellikleri](#_core_color_properties)

    > [!NOTE]
    >  Visual Basic özel denetimleri, genellikle üst, sol, genişlik, yükseklik, hizalama, etiketi, adı, tabIndex, sekme durağı ve üst gibi özellikleri de vardır. ActiveX denetim kapsayıcıları, ancak bu denetim özellikleri uygulamak için sorumlu değildir ve bu nedenle ActiveX denetimlerini bu özellikleri desteklemesi değil.

##  <a name="_core_using_classwizard_to_add_a_stock_property"></a> Kullanarak stok özelliği eklemek için Özellik Ekleme Sihirbazı

Stok Özellikler ekleme gerektirir çünkü özel özellikler ekleme değerinden daha az kod desteği özelliği tarafından otomatik olarak işlenir `COleControl`. Aşağıdaki yordam bir ActiveX denetim çerçevesi için resim yazısı özelliğini stok ekleme gösterir ve diğer stok özellikleri eklemek için de kullanılabilir. Seçili stok özellik başlığı ile değiştirin.

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak stok resim yazısı özelliğini eklemek için

1. Denetiminizin proje yükleyin.

1. Sınıf Görünümü'nde denetim kitaplığı düğümünü genişletin.

1. Arabirim (ikinci düğüm kitaplığı düğümünün) denetlemek için kısayol menüsünü açmak için düğümü.

1. Kısayol menüsünden tıklayın **Ekle** ve ardından **Özellik Ekle**.

     Bu açılır [Özellik Ekleme Sihirbazı'nı](../ide/names-add-property-wizard.md).

1. İçinde **özellik adı** kutusunun **açıklamalı alt yazı**.

1. **Son**'a tıklayın.

##  <a name="_core_classwizard_changes_for_stock_properties"></a> Stok özellikleri için özellik Sihirbazı değişiklikleri ekleyin

Çünkü `COleControl` destekler stok özellikleri, Özellik Ekleme Sihirbazı'nı sınıf bildirimi içinde hiçbir şekilde değiştirmez; gönderme haritaya özelliği ekler. Özellik Ekleme Sihirbazı'nı uygulamasında bulunan denetim dağıtım eşlemesi aşağıdaki satırı ekler (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxUI#22](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_1.cpp)]

Denetiminizin arabirim açıklaması için aşağıdaki satırı eklenir (. IDL) dosyası:

[!code-cpp[NVC_MFC_AxUI#23](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_2.idl)]

Bu satırı resim yazısı özelliğini bir belirli kimlik atar. Özellik bağlanabilir ve veritabanından değerini değiştirmeden önce izin ister dikkat edin.

Bu resim yazısı özelliğini denetiminiz kullanıcıları için kullanılabilmesini sağlar. Stok özellik değerini kullanmak için bir üye değişkeni veya üye işlevinin erişmek `COleControl` temel sınıfı. Bu üye değişkenleri ve üye işlevleri hakkında daha fazla bilgi için sonraki bölüme stok özellikleri Özellik Ekleme Sihirbazı'nı tarafından desteklenen bakın.

##  <a name="_core_stock_properties_supported_by_classwizard"></a> Stok özellikleri tarafından desteklenen özellik Ekleme Sihirbazı

`COleControl` Sınıfı dokuz stok özellikleri sağlar. Özellik Ekleme Sihirbazı'nı kullanarak istediğiniz özellikleri ekleyebilirsiniz.

|Özellik|Gönderme eşleme girişi|Değere erişmek nasıl|
|--------------|------------------------|-------------------------|
|`Appearance`|DISP_STOCKPROP_APPEARANCE)|Değer olarak erişilebilir `m_sAppearance`.|
|`BackColor`|DISP_STOCKPROP_BACKCOLOR)|Değer çağırarak erişilebilir `GetBackColor`.|
|`BorderStyle`|DISP_STOCKPROP_BORDERSTYLE)|Değer olarak erişilebilir `m_sBorderStyle`.|
|`Caption`|DISP_STOCKPROP_CAPTION)|Değer çağırarak erişilebilir `InternalGetText`.|
|`Enabled`|DISP_STOCKPROP_ENABLED)|Değer olarak erişilebilir `m_bEnabled`.|
|`Font`|DISP_STOCKPROP_FONT)|Makaleye göz atın [MFC ActiveX denetimleri: yazı tiplerini kullanarak](../mfc/mfc-activex-controls-using-fonts.md) kullanım için.|
|`ForeColor`|DISP_STOCKPROP_FORECOLOR)|Değer çağırarak erişilebilir `GetForeColor`.|
|`hWnd`|DISP_STOCKPROP_HWND)|Değer olarak erişilebilir `m_hWnd`.|
|`Text`|DISP_STOCKPROP_TEXT)|Değer çağırarak erişilebilir `InternalGetText`. Bu özellik aynı olan `Caption`, özellik adı dışında.|
|`ReadyState`|DISP_STOCKPROP_READYSTATE()|Değer olarak erişilebilir `m_lReadyState` veya `GetReadyState`|

##  <a name="_core_stock_properties_and_notification"></a> Stok özellikleri ve bildirim

Çoğu stok özellikleri geçersiz kılınabilir bildirim işlevleri vardır. Örneğin, her `BackColor` özelliği değiştirildiğinde `OnBackColorChanged` işlevi (Denetim sınıfının bir üye işlevinde) çağrılır. Varsayılan uygulama (içinde `COleControl`) çağrılarını `InvalidateControl`. Bu işlev, yanıt olarak bu durum ek eylemleri istiyorsanız geçersiz kılar.

##  <a name="_core_color_properties"></a> Renk özellikleri

Hisse senedi kullanabileceğiniz `ForeColor` ve `BackColor` özellikleri veya denetim boyama, kendi özel renk özellikleri. Color özelliği kullanmak için çağrı [COleControl::TranslateColor](../mfc/reference/colecontrol-class.md#translatecolor) üye işlevi. Bu işlev renk özelliğini ve isteğe bağlı palet tanıtıcı değeri parametrelerdir. Dönüş değeri bir **COLORREF** gibi GDI için geçirilen değer işlevlerini `SetTextColor` ve `CreateSolidBrush`.

Hisse senedi için renk değerleri `ForeColor` ve `BackColor` özellikleri ya da çağrılarak erişilen `GetForeColor` veya `GetBackColor` işlevi, sırasıyla.

Aşağıdaki örnek, bir denetim boyama, bu iki color özelliklerini kullanmayı gösterir. Geçici bir başlatır **COLORREF** değişkeni ve `CBrush` çağrılar için nesneyle `TranslateColor`: kullanarak bir tane `ForeColor` özelliği ve diğer kullanma `BackColor` özelliği. Geçici bir `CBrush` nesne denetim dikdörtgenine boyamak için kullanılan ardından ve kullanarak metin rengini ayarlama `ForeColor` özelliği.

[!code-cpp[NVC_MFC_AxUI#24](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_3.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: Özellikler](../mfc/mfc-activex-controls-properties.md)<br/>
[MFC ActiveX Denetimleri: Yöntemler](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl Sınıfı](../mfc/reference/colecontrol-class.md)
