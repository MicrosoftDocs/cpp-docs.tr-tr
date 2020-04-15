---
title: 'MFC ActiveX Denetimleri: Yazı Tiplerini Kullanma'
ms.date: 11/19/2018
f1_keywords:
- OnFontChanged
- HeadingFont
- InternalFont
helpviewer_keywords:
- notifications [MFC], MFC ActiveX controls fonts
- OnDraw method, MFC ActiveX controls
- InternalFont method [MFC]
- SetFont method [MFC]
- OnFontChanged method [MFC]
- IPropertyNotifySink class [MFC]
- MFC ActiveX controls [MFC], fonts
- Stock Font property [MFC]
- HeadingFont property [MFC]
- GetFont method [MFC]
- SelectStockFont method [MFC]
- fonts [MFC], ActiveX controls
ms.assetid: 7c51d602-3f5a-481d-84d1-a5d8a3a71761
ms.openlocfilehash: c336ec6c29b5478655ca8f19f71378a2b446ac64
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358265"
---
# <a name="mfc-activex-controls-using-fonts"></a>MFC ActiveX Denetimleri: Yazı Tiplerini Kullanma

ActiveX denetiminiz metni görüntüleniyorsa, bir yazı tipi özelliğini değiştirerek denetim kullanıcısının metin görünümünü değiştirmesine izin verebilirsiniz. Yazı tipi özellikleri yazı tipi nesneleri olarak uygulanır ve iki türden biri olabilir: stok veya özel. Stok Yazı Tipi özellikleri, Özellik Ekle Sihirbazı'nı kullanarak ekleyebileceğiniz önceden uygulanmış yazı tipi özellikleridir. Özel Yazı Tipi özellikleri önceden uygulanmaz ve denetim geliştiricisi özelliğin davranışını ve kullanımını belirler.

Bu makalede aşağıdaki konular ele:

- [Stok Font özelliğini kullanma](#_core_using_the_stock_font_property)

- [Denetiminizde Özel Yazı Tipi Özelliklerini Kullanma](#_core_implementing_a_custom_font_property)

## <a name="using-the-stock-font-property"></a><a name="_core_using_the_stock_font_property"></a>Stok Font Özelliğini Kullanma

Stok Font özellikleri [COleControl](../mfc/reference/colecontrol-class.md)sınıfı tarafından önceden uygulanır. Ayrıca, kullanıcının yazı tipi nesnesinin adı, boyutu ve stili gibi çeşitli özniteliklerini değiştirmesine olanak tanıyan standart bir Yazı Tipi özelliği sayfası da kullanılabilir.

[GetFont, SetFont](../mfc/reference/colecontrol-class.md#getfont)ve [SetFont](../mfc/reference/colecontrol-class.md#setfont) [InternalGetFont](../mfc/reference/colecontrol-class.md#internalgetfont) işlevleri aracılığıyla yazı `COleControl`tipi nesnesi erişin. Denetim kullanıcısı yazı tipi nesnesi üzerinden erişecek `GetFont` ve `SetFont` diğer Get/Set özelliğiyle aynı şekilde işlev görür. Bir denetim içinden yazı tipi nesnesine erişim `InternalGetFont` gerektiğinde, işlevi kullanın.

[MFC ActiveX Denetimleri'nde](../mfc/mfc-activex-controls-properties.md)anlatıldığı gibi: Özellikler, stok özellikleri ekleme [Özelliği Sihirbazı](../ide/names-add-property-wizard.md)ile kolaydır. Yazı Tipi özelliğini seçersiniz ve Özellik Ekle Sihirbazı, denetimin sevk haritasına stok Font girişini otomatik olarak ekler.

#### <a name="to-add-the-stock-font-property-using-the-add-property-wizard"></a>Özellik Ekle Sihirbazı'nı kullanarak stok Yazı Tipi özelliğini eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü'nde, denetiminizin kitaplık düğümunu genişletin.

1. Kısayol menüsünü açmak için denetiminiz için arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünden **Ekle'yi** tıklatın ve ardından **Özellik Ekle'yi**tıklatın.

   Bu özellik ekle sihirbazı açılır.

1. Özellik **Adı** kutusunda **Yazı Tipi'ni**tıklatın.

1. **Son**'a tıklayın.

Özellik Ekle Sihirbazı, denetim sınıfı uygulama dosyasında bulunan denetimin sevk haritasına aşağıdaki satırı ekler:

[!code-cpp[NVC_MFC_AxFont#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_1.cpp)]

Buna ek olarak, Özellik Ekle Sihirbazı denetime aşağıdaki satırı ekler. IDL dosyası:

[!code-cpp[NVC_MFC_AxFont#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_2.idl)]

Stok Resim Yazısı özelliği, stok Font özelliği bilgileri kullanılarak çizilebilen bir metin özelliğiörneğidir. Denetime stok Resim Yazısı özelliğinin eklenmesi, stok Font özelliği için kullanılanlara benzer adımlar kullanır.

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>Özellik Ekle Sihirbazı'nı kullanarak stok Resim Yazısı özelliğini eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü'nde, denetiminizin kitaplık düğümunu genişletin.

1. Kısayol menüsünü açmak için denetiminiz için arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünden **Ekle'yi** tıklatın ve ardından **Özellik Ekle'yi**tıklatın.

   Bu özellik ekle sihirbazı açılır.

1. Özellik **Adı** kutusunda **Resim Yazısı'nı**tıklatın.

1. **Son**'a tıklayın.

Özellik Ekle Sihirbazı, denetim sınıfı uygulama dosyasında bulunan denetimin sevk haritasına aşağıdaki satırı ekler:

[!code-cpp[NVC_MFC_AxFont#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_3.cpp)]

## <a name="modifying-the-ondraw-function"></a><a name="_core_modifying_the_ondraw_function"></a>OnDraw Işlevini Değiştirme

Denetimde görüntülenen `OnDraw` tüm metin için Windows sistem yazı tipinin varsayılan uygulaması kullanır. Bu, yazı tipi `OnDraw` nesnesini aygıt bağlamına seçerek kodu değiştirmeniz gerektiği anlamına gelir. Bunu yapmak için [COleControl::SelectStockFont'u](../mfc/reference/colecontrol-class.md#selectstockfont) arayın ve aşağıdaki örnekte gösterildiği gibi denetimin aygıt bağlamını geçirin:

[!code-cpp[NVC_MFC_AxFont#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_4.cpp)]

`OnDraw` Işlev yazı tipi nesnesini kullanmak üzere değiştirildikten sonra, denetim içindeki tüm metinler denetimin stok Font özelliğinden özelliklerle görüntülenir.

## <a name="using-custom-font-properties-in-your-control"></a><a name="_core_using_custom_font_properties_in_your_control"></a>Denetiminizde Özel Yazı Tipi Özelliklerini Kullanma

Stok Font özelliğine ek olarak, ActiveX denetimi özel Yazı Tipi özelliklerine sahip olabilir. Özel bir yazı tipi özelliği eklemek için şunları anlamanız gerekir:

- Özel Yazı Tipi özelliğini uygulamak için Özellik Ekle Sihirbazı'nı kullanın.

- [Yazı tipi bildirimlerini işleme.](#_core_processing_font_notifications)

- [Yeni bir yazı tipi bildirim arabirimi uygulama.](#_core_implementing_a_new_font_notification_interface)

### <a name="implementing-a-custom-font-property"></a><a name="_core_implementing_a_custom_font_property"></a>Özel Yazı Tipi Özelliği Uygulama

Özel bir Yazı Tipi özelliği uygulamak için, özelliği eklemek ve ardından kodda bazı değişiklikler yapmak için Özellik Ekle Sihirbazı'nı kullanırsınız. Aşağıdaki bölümlerde Örnek denetimine `HeadingFont` özel özelliğin nasıl ekleyeceğiniaçıklanmıştır.

##### <a name="to-add-the-custom-font-property-using-the-add-property-wizard"></a>Özellik Ekle Sihirbazı'nı kullanarak özel Yazı Tipi özelliğini eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü'nde, denetiminizin kitaplık düğümunu genişletin.

1. Kısayol menüsünü açmak için denetiminiz için arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünden **Ekle'yi** tıklatın ve ardından **Özellik Ekle'yi**tıklatın.

   Bu özellik ekle sihirbazı açılır.

1. Özellik **Adı** kutusuna, özellik için bir ad yazın. Bu **örnekte, HeadingFont'u**kullanın.

1. **Uygulama Türü** **için, Yöntemleri Al/Ayarla'yı**tıklatın.

1. Özellik **Türü** kutusunda, özelliğin türü için **IDispatch'i** <strong>\*</strong> seçin.

1. **Son**'a tıklayın.

Özellik Ekle Sihirbazı, `HeadingFont` `CSampleCtrl` özel özelliği sınıfa ve ÖRNEK'e eklemek için kodu oluşturur. IDL dosyası. Özellik `HeadingFont` Ekle özelliği türü olduğundan, Özellik Ekle Sihirbazı `CSampleCtrl` sınıfın gönderim eşlesini DISP_PROPERTY_EX_ID[DISP_PROPERTY_EX](../mfc/reference/dispatch-maps.md#disp_property_ex) makro girişi içerecek şekilde değiştirir:

[!code-cpp[NVC_MFC_AxFont#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_5.cpp)]

DISP_PROPERTY_EX `HeadingFont` makrosu, özellik adını `CSampleCtrl` ilgili sınıf Al `GetHeadingFont` ve `SetHeadingFont`Ayarla yöntemleriyle ilişkilendirer ve . Özellik değerinin türü de belirtilir; Bu durumda, VT_FONT.

Özellik Ekle Sihirbazı da denetim üstbilgi dosyasına bir bildirim ekler (. H) `GetHeadingFont` ve `SetHeadingFont` işlevleri için ve kontrol uygulama dosyasına işlev şablonları ekler (. CPP:

[!code-cpp[NVC_MFC_AxFont#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_6.cpp)]

Son olarak, Özellik Ekle Sihirbazı denetimi değiştirir. `HeadingFont` Özellik için bir giriş ekleyerek IDL dosyası:

[!code-cpp[NVC_MFC_AxFont#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_7.idl)]

### <a name="modifications-to-the-control-code"></a>Kontrol Kodunda Yapılan Değişiklikler

Özelliği denetime eklediğinize `HeadingFont` göre, yeni özelliği tam olarak desteklemek için denetim üstbilgisi ve uygulama dosyalarında bazı değişiklikler yapmalısınız.

Denetim üstbilgi dosyasında (. H) korunan üye değişkenin aşağıdaki bildirimiekleyin:

[!code-cpp[NVC_MFC_AxFont#8](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_8.h)]

Denetim uygulama dosyasında (. CPP), aşağıdakileri yapın:

- *M_fontHeading'ı* kontrol oluşturucuya ait hale ürünle baş harfe edin.

   [!code-cpp[NVC_MFC_AxFont#9](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_9.cpp)]

- Yazı tipinin varsayılan özniteliklerini içeren statik bir FONTDESC yapısını bildirin.

   [!code-cpp[NVC_MFC_AxFont#10](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_10.cpp)]

- Denetim `DoPropExchange` üyesi işlevinde, işleve `PX_Font` bir çağrı ekleyin. Bu, özel Font özelliğiniz için başlatma ve kalıcılık sağlar.

   [!code-cpp[NVC_MFC_AxFont#11](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_11.cpp)]

- Denetim `GetHeadingFont` üyesi işlevini uygulamayı bitirin.

   [!code-cpp[NVC_MFC_AxFont#12](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_12.cpp)]

- Denetim `SetHeadingFont` üyesi işlevini uygulamayı bitirin.

   [!code-cpp[NVC_MFC_AxFont#13](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_13.cpp)]

- Daha önce `OnDraw` seçili yazı tipini tutmak için bir değişken tanımlamak için denetim üyesi işlevini değiştirin.

   [!code-cpp[NVC_MFC_AxFont#14](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_14.cpp)]

- Yazı tipinin kullanılacağı yere aşağıdaki satırı ekleyerek aygıt bağlamına özel yazı tipini seçmek için denetim `OnDraw` üyesi işlevini değiştirin.

   [!code-cpp[NVC_MFC_AxFont#15](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_15.cpp)]

- Yazı tipi `OnDraw` kullanıldıktan sonra aşağıdaki satırı ekleyerek önceki yazı tipini aygıt bağlamına geri seçmek için denetim üyesi işlevini değiştirin.

   [!code-cpp[NVC_MFC_AxFont#16](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_16.cpp)]

Özel Yazı Tipi özelliği uygulandıktan sonra, denetim kullanıcılarının denetimin geçerli yazı tipini değiştirmesine olanak tanıyan standart Font özelliği sayfası uygulanmalıdır. Standart Font özelliği sayfası için özellik sayfası kimliği eklemek için, BEGIN_PROPPAGEIDS makrosonra aşağıdaki satırı ekleyin:

[!code-cpp[NVC_MFC_AxFont#17](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_17.cpp)]

Ayrıca, BEGIN_PROPPAGEIDS makronuzun sayım parametresini de birer birer artımgerekir. Aşağıdaki satır bunu göstermektedir:

[!code-cpp[NVC_MFC_AxFont#18](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_18.cpp)]

Bu değişiklikler yapıldıktan sonra, ek işlevselliği birleştirmek için tüm projeyi yeniden oluşturun.

### <a name="processing-font-notifications"></a><a name="_core_processing_font_notifications"></a>Yazı Tipi Bildirimlerini Işleme

Çoğu durumda denetimin yazı tipi nesnesinin özelliklerinin ne zaman değiştirildiğini bilmesi gerekir. Her yazı tipi nesnesi, `IFontNotification` `COleControl`'.

Denetim stok Font özelliğini kullanıyorsa, `OnFontChanged` bildirimleri . `COleControl` Özel yazı tipi özellikleri eklediğinizde, aynı uygulamayı kullanmalarını sağlayabilirsiniz. Önceki bölümdeki örnekte, *m_fontHeading* üye değişkeni başolarak &*m_xFontNotification* geçirilerek gerçekleştirilmiştir.

![Birden çok yazı tipi nesne arabirimi uygulama](../mfc/media/vc373q1.gif "Birden çok yazı tipi nesne arabirimi uygulama") <br/>
Birden Çok Yazı Tipi Nesne Arabirimi Uygulama

Yukarıdaki şekildeki düz çizgiler, her iki yazı tipi nesnesinin `IFontNotification`de aynı uygulamayı kullandığını göstermektedir. Hangi yazı tipinin değiştiğini ayırt etmek isterseniz, bu sorunlara neden olabilir.

Denetimin yazı tipi nesnesi bildirimleri arasında ayrım yapmanın bir `IFontNotification` yolu, denetimdeki her yazı tipi nesnesi için arabirimin ayrı bir uygulamasını oluşturmaktır. Bu teknik, son değiştirilen yazı tipini kullanan yalnızca dize veya dizeleri güncelleştirerek çizim kodunuzu en iyi duruma getirmenizi sağlar. Aşağıdaki bölümler, ikinci bir Font özelliği için ayrı bildirim arabirimleri uygulamak için gereken adımları gösterir. İkinci yazı tipi özelliği, `HeadingFont` önceki bölümde eklenen özellik olarak kabul edilir.

### <a name="implementing-a-new-font-notification-interface"></a><a name="_core_implementing_a_new_font_notification_interface"></a>Yeni Yazı Tipi Bildirim Arabirimi Uygulama

İki veya daha fazla yazı tipinin bildirimlerini ayırt etmek için denetimde kullanılan her yazı tipi için yeni bir bildirim arabirimi uygulanması gerekir. Aşağıdaki bölümlerde, denetim üstbilgisini ve uygulama dosyalarını değiştirerek yeni bir yazı tipi bildirim arabirimi nasıl uygulanacağı açıklanmıştır.

### <a name="additions-to-the-header-file"></a>Üstbilgi Dosyasına Eklemeler

Denetim üstbilgi dosyasında (. H) sınıf bildirimine aşağıdaki satırları ekleyin:

[!code-cpp[NVC_MFC_AxFont#19](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_19.h)]

Bu, adı verilen `IPropertyNotifySink` `HeadingFontNotify`arabirimin bir uygulamasını oluşturur. Bu yeni arabirim `OnChanged`adı verilen bir yöntem içerir.

### <a name="additions-to-the-implementation-file"></a>Uygulama Dosyasına Eklemeler

Başlık yazı tipini (denetim oluşturucuda) başladay olarak açan kodda, *&m_xFontNotification* &*m_xHeadingFontNotify*değiştirin. Ardından aşağıdaki kodu ekleyin:

[!code-cpp[NVC_MFC_AxFont#20](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_20.cpp)]

Arabirimdeki `AddRef` `Release` `IPropertyNotifySink` ve yöntemler ActiveX denetim nesnesinin başvuru sayısını izler. Denetim arabirim işaretçisine erişim elde `AddRef` ettiğinde, denetim başvuru sayısını artım için çağırır. Denetim işaretçiyle tamamlandığında, genel `Release`bellek bloğunu serbest `GlobalFree` etmek için çağrılanlarla aynı şekilde çağırır. Bu arabirimin başvuru sayısı sıfıra gittiğinde, arabirim uygulaması serbest bırakılabilir. Bu örnekte, `QueryInterface` işlev belirli bir `IPropertyNotifySink` nesne üzerinde bir arabirime bir işaretçi döndürür. Bu işlev, activex denetiminin neyi desteklediğini belirlemek için nesneyi sorgulamasına olanak tanır.

Projenizde bu değişiklikler yapıldıktan sonra, projeyi yeniden oluşturun ve arabirimi sınamak için Test Kapsayıcısı'nı kullanın. Test kapsayıcısına nasıl erişireceksiniz hakkında bilgi almak için [Test Kapsayıcısı ile Test Özellikleri ve Olayları'na](../mfc/testing-properties-and-events-with-test-container.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: ActiveX Denetiminde Resim Kullanma](../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)<br/>
[MFC ActiveX Denetimleri: Stok Özellik Sayfalarını Kullanma](../mfc/mfc-activex-controls-using-stock-property-pages.md)
