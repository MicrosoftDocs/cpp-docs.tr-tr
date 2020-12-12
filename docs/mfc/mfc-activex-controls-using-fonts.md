---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: yazı tiplerini kullanma'
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
ms.openlocfilehash: 5f0c495ee92dbcfcb27627628f3bcf92982f719f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206012"
---
# <a name="mfc-activex-controls-using-fonts"></a>MFC ActiveX Denetimleri: Yazı Tiplerini Kullanma

ActiveX denetiminiz metin görüntülüyorsa, denetim kullanıcısının bir yazı tipi özelliğini değiştirerek metin görünümünü değiştirmesine izin verebilirsiniz. Yazı tipi özellikleri, yazı tipi nesneleri olarak uygulanır ve iki türden biri olabilir: Stock veya Custom. Hisse senedi yazı tipi özellikleri Özellik Ekleme Sihirbazı 'Nı kullanarak ekleyebileceğiniz önceden uygulanmış yazı tipi özelliklerdir. Özel yazı tipi özellikleri önceden uygulanmamıştır ve denetim geliştiricisi özelliğin davranışını ve kullanımını belirler.

Bu makalede aşağıdaki konular ele alınmaktadır:

- [Hisse senedi yazı tipi özelliğini kullanma](#_core_using_the_stock_font_property)

- [Denetiinizdeki özel yazı tipi özelliklerini kullanma](#_core_implementing_a_custom_font_property)

## <a name="using-the-stock-font-property"></a><a name="_core_using_the_stock_font_property"></a> Hisse senedi yazı tipi özelliğini kullanma

Hisse senedi yazı tipi özellikleri sınıf [Coelcontrol](reference/colecontrol-class.md)tarafından önceden uygulanır. Ayrıca, standart bir yazı tipi özellik sayfası da kullanılabilir ve kullanıcının adı, boyutu ve stili gibi yazı tipi nesnesinin çeşitli özniteliklerini değiştirmesine olanak tanır.

Yazı tipi nesnesine [GetFont](reference/colecontrol-class.md#getfont), [SetFont](reference/colecontrol-class.md#setfont)ve [InternalGetFont](reference/colecontrol-class.md#internalgetfont) işlevleri aracılığıyla erişin `COleControl` . Denetim kullanıcısı, ve işlevleri aracılığıyla yazı tipi nesnesine `GetFont` `SetFont` diğer get/set özelliğiyle aynı şekilde erişir. Bir denetimin içinden yazı tipi nesnesine erişim gerekliyse, `InternalGetFont` işlevini kullanın.

[MFC ActiveX denetimlerinde açıklandığı gibi: Özellikler](mfc-activex-controls-properties.md), stok özelliklerinin eklenmesi [Özellik Ekleme Sihirbazı](../ide/adding-a-property-visual-cpp.md#names-add-property-wizard)ile kolaydır. Yazı tipi özelliğini seçtiğinizde, Özellik Ekleme Sihirbazı otomatik olarak denetimin dağıtım haritasına hisse senedi yazı tipi girişini ekler.

#### <a name="to-add-the-stock-font-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı 'nı kullanarak hisse senedi yazı tipi özelliğini eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü, denetiminizin kitaplık düğümünü genişletin.

1. Kısayol menüsünü açmak için denetiminizin arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **Özellik Ekle**' ye tıklayın.

   Bu, Özellik Ekleme Sihirbazı ' nı açar.

1. **Özellik adı** kutusunda **yazı tipi**' ne tıklayın.

1. **Finish (Son)** düğmesine tıklayın.

Özellik Ekleme Sihirbazı, denetim sınıfı uygulama dosyasında bulunan denetimin dağıtım eşlemesine aşağıdaki satırı ekler:

[!code-cpp[NVC_MFC_AxFont#1](codesnippet/cpp/mfc-activex-controls-using-fonts_1.cpp)]

Ayrıca Özellik Ekleme Sihirbazı, denetime aşağıdaki satırı ekler. IDL dosyası:

[!code-cpp[NVC_MFC_AxFont#2](codesnippet/cpp/mfc-activex-controls-using-fonts_2.idl)]

Hisse senedi başlığı özelliği, hisse senedi yazı tipi özellik bilgileri kullanılarak çizilemeyen bir metin özelliğine örnektir. Denetime hisse senedi başlık özelliğinin eklenmesi, stok yazı tipi özelliği için kullanılanlarla aynı adımları kullanır.

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı 'nı kullanarak hisse senedi başlık özelliğini eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü, denetiminizin kitaplık düğümünü genişletin.

1. Kısayol menüsünü açmak için denetiminizin arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **Özellik Ekle**' ye tıklayın.

   Bu, Özellik Ekleme Sihirbazı ' nı açar.

1. **Özellik adı** kutusunda, **başlık**' a tıklayın.

1. **Finish (Son)** düğmesine tıklayın.

Özellik Ekleme Sihirbazı, denetim sınıfı uygulama dosyasında bulunan denetimin dağıtım eşlemesine aşağıdaki satırı ekler:

[!code-cpp[NVC_MFC_AxFont#3](codesnippet/cpp/mfc-activex-controls-using-fonts_3.cpp)]

## <a name="modifying-the-ondraw-function"></a><a name="_core_modifying_the_ondraw_function"></a> OnDraw Işlevini değiştirme

Varsayılan uygulama, `OnDraw` denetimde görünen tüm metinler Için Windows sistem yazı tipini kullanır. Diğer bir deyişle, `OnDraw` yazı tipi nesnesini cihaz bağlamına seçerek kodu değiştirmeniz gerekir. Bunu yapmak için [Cotacontrol:: SelectStockFont](reference/colecontrol-class.md#selectstockfont) ' ı çağırın ve aşağıdaki örnekte gösterildiği gibi denetimin cihaz bağlamını geçirin:

[!code-cpp[NVC_MFC_AxFont#4](codesnippet/cpp/mfc-activex-controls-using-fonts_4.cpp)]

İşlev, `OnDraw` yazı tipi nesnesini kullanacak şekilde değiştirildikten sonra Denetim içindeki herhangi bir metin denetimin hisse senedi yazı tipi özelliğindeki özelliklerle birlikte görüntülenir.

## <a name="using-custom-font-properties-in-your-control"></a><a name="_core_using_custom_font_properties_in_your_control"></a> Denetiinizdeki özel yazı tipi özelliklerini kullanma

Stok yazı tipi özelliğine ek olarak, ActiveX denetimi özel yazı tipi özelliklerine sahip olabilir. Özel bir yazı tipi özelliği eklemek için şunları yapmanız gerekir:

- Özel yazı tipi özelliğini uygulamak için Özellik Ekleme Sihirbazı 'nı kullanın.

- [Yazı tipi bildirimleri işleniyor](#_core_processing_font_notifications).

- [Yeni bir yazı tipi bildirim arabirimi uygulama](#_core_implementing_a_new_font_notification_interface).

### <a name="implementing-a-custom-font-property"></a><a name="_core_implementing_a_custom_font_property"></a> Özel bir yazı tipi özelliği uygulama

Özel bir yazı tipi özelliği uygulamak için özelliği eklemek ve ardından kodda bazı değişiklikler yapmak için Özellik Ekleme Sihirbazı ' nı kullanın. Aşağıdaki bölümlerde, örnek denetimine özel özelliğin nasıl ekleneceği açıklanır `HeadingFont` .

##### <a name="to-add-the-custom-font-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı 'Nı kullanarak özel yazı tipi özelliğini eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü, denetiminizin kitaplık düğümünü genişletin.

1. Kısayol menüsünü açmak için denetiminizin arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **Özellik Ekle**' ye tıklayın.

   Bu, Özellik Ekleme Sihirbazı ' nı açar.

1. **Özellik adı** kutusuna özellik için bir ad yazın. Bu örnek için **HeadingFont** kullanın.

1. **Uygulama türü** Için, **get/set yöntemleri**' ne tıklayın.

1. **Özellik türü** kutusunda, özelliğin türü için **IDispatch** ' i seçin <strong>\*</strong> .

1. **Finish (Son)** düğmesine tıklayın.

Özellik Ekleme Sihirbazı, `HeadingFont` özel özelliği sınıfına ve örneğe eklemek için kodu oluşturur `CSampleCtrl` . IDL dosyası. `HeadingFont`Bir get/set özellik türü olduğundan, Özellik Ekleme Sihirbazı `CSampleCtrl` sınıfın dağıtım eşlemesini bir DISP_PROPERTY_EX_ID[DISP_PROPERTY_EX](reference/dispatch-maps.md#disp_property_ex) makro girişi içerecek şekilde değiştirir:

[!code-cpp[NVC_MFC_AxFont#5](codesnippet/cpp/mfc-activex-controls-using-fonts_5.cpp)]

DISP_PROPERTY_EX makrosu, `HeadingFont` özellik adını karşılık gelen `CSampleCtrl` sınıf get ve set yöntemleri ve ile ilişkilendirir `GetHeadingFont` `SetHeadingFont` . Özellik değerinin türü de belirtilir; Bu durumda VT_FONT.

Özellik Ekleme Sihirbazı ayrıca denetim üst bilgisi dosyasına (. H) `GetHeadingFont` ve işlevleri için `SetHeadingFont` ve işlev şablonlarını denetim uygulama dosyasına (. CPP):

[!code-cpp[NVC_MFC_AxFont#6](codesnippet/cpp/mfc-activex-controls-using-fonts_6.cpp)]

Son olarak, Özellik Ekleme Sihirbazı denetimi değiştirir. Özelliği için bir giriş ekleyerek IDL dosyası `HeadingFont` :

[!code-cpp[NVC_MFC_AxFont#7](codesnippet/cpp/mfc-activex-controls-using-fonts_7.idl)]

### <a name="modifications-to-the-control-code"></a>Denetim kodunda yapılan değişiklikler

Özelliği denetime eklediğine göre `HeadingFont` , yeni özelliği tam olarak desteklemek için denetim üst bilgisinde ve uygulama dosyalarında bazı değişiklikler yapmanız gerekir.

Denetim üst bilgisi dosyasında (. H), korumalı bir üye değişkeninin aşağıdaki bildirimini ekleyin:

[!code-cpp[NVC_MFC_AxFont#8](codesnippet/cpp/mfc-activex-controls-using-fonts_8.h)]

Denetim uygulama dosyasında (. CPP) şunları yapın:

- Denetim oluşturucusunda *m_fontHeading* başlatın.

   [!code-cpp[NVC_MFC_AxFont#9](codesnippet/cpp/mfc-activex-controls-using-fonts_9.cpp)]

- Yazı tipinin varsayılan özniteliklerini içeren bir statik FONTDESC yapısı bildirin.

   [!code-cpp[NVC_MFC_AxFont#10](codesnippet/cpp/mfc-activex-controls-using-fonts_10.cpp)]

- Denetim `DoPropExchange` üyesi işlevinde, işleve bir çağrı ekleyin `PX_Font` . Bu, özel yazı tipi özelliği için başlatma ve kalıcılık sağlar.

   [!code-cpp[NVC_MFC_AxFont#11](codesnippet/cpp/mfc-activex-controls-using-fonts_11.cpp)]

- Denetim `GetHeadingFont` üyesi işlevini uygulamayı tamamlama.

   [!code-cpp[NVC_MFC_AxFont#12](codesnippet/cpp/mfc-activex-controls-using-fonts_12.cpp)]

- Denetim `SetHeadingFont` üyesi işlevini uygulamayı tamamlama.

   [!code-cpp[NVC_MFC_AxFont#13](codesnippet/cpp/mfc-activex-controls-using-fonts_13.cpp)]

- Denetim `OnDraw` üyesi işlevini, daha önce seçilen yazı tipini tutacak bir değişken tanımlamak üzere değiştirin.

   [!code-cpp[NVC_MFC_AxFont#14](codesnippet/cpp/mfc-activex-controls-using-fonts_14.cpp)]

- `OnDraw`Yazı tipinin kullanılacağı her yerde aşağıdaki satırı ekleyerek, denetim üyesi işlevini, cihaz bağlamına özel yazı tipini seçmek üzere değiştirin.

   [!code-cpp[NVC_MFC_AxFont#15](codesnippet/cpp/mfc-activex-controls-using-fonts_15.cpp)]

- `OnDraw`Yazı tipi kullanıldıktan sonra aşağıdaki satırı ekleyerek önceki yazı tipini cihaz bağlamına yeniden seçmek için denetim üyesi işlevini değiştirin.

   [!code-cpp[NVC_MFC_AxFont#16](codesnippet/cpp/mfc-activex-controls-using-fonts_16.cpp)]

Özel yazı tipi özelliği uygulandıktan sonra, standart yazı tipi özellik sayfası uygulanmalı ve kullanıcıların denetimin geçerli yazı tipini değiştirmesine izin verir. Standart yazı tipi özellik sayfası için özellik sayfası KIMLIĞINI eklemek için, BEGIN_PROPPAGEIDS makrodan sonra aşağıdaki satırı ekleyin:

[!code-cpp[NVC_MFC_AxFont#17](codesnippet/cpp/mfc-activex-controls-using-fonts_17.cpp)]

Ayrıca, BEGIN_PROPPAGEIDS makrolarınızın Count parametresini bir de artırmalısınız. Aşağıdaki satırda bu gösterilmektedir:

[!code-cpp[NVC_MFC_AxFont#18](codesnippet/cpp/mfc-activex-controls-using-fonts_18.cpp)]

Bu değişiklikler yapıldıktan sonra, ek işlevselliği içerecek şekilde tüm projeyi yeniden derleyin.

### <a name="processing-font-notifications"></a><a name="_core_processing_font_notifications"></a> Yazı tipi bildirimleri işleniyor

Çoğu durumda, denetimin yazı tipi nesnesinin özellikleri değiştirildiğinde bu denetimin bilmeleri gerekir. Her yazı tipi nesnesi `IFontNotification` , tarafından uygulanan arabirimin üye işlevini çağırarak değiştiğinde bildirim sağlayabilme özelliğine sahiptir `COleControl` .

Denetim hisse senedi yazı tipi özelliğini kullanıyorsa, bildirimleri `OnFontChanged` öğesinin üye işlevi tarafından işlenir `COleControl` . Özel yazı tipi özellikleri eklediğinizde, bunların aynı uygulamayı kullanmasını sağlayabilirsiniz. Önceki bölümdeki örnekte, bu, *m_fontHeading* üye değişkeni başlatılırken &*m_xFontNotification* geçirilerek gerçekleştirildi.

![Birden çok yazı tipi nesne arabirimi uygulama](../mfc/media/vc373q1.gif "Birden çok yazı tipi nesne arabirimi uygulama") <br/>
Birden çok yazı tipi nesne arabirimi uygulama

Yukarıdaki şekilde bulunan düz çizgiler, her iki yazı tipi nesnesinin de aynı uygulamasını kullandığını gösterir `IFontNotification` . Bu, hangi yazı tipinin değiştirildiğini ayırt etmek istediğinizde soruna neden olabilir.

Denetimin yazı tipi nesne bildirimleri arasında ayrım yapmanın bir yolu, `IFontNotification` denetimdeki her bir yazı tipi nesnesi için ayrı bir arabirim uygulama oluşturmaktır. Bu teknik, yalnızca son değiştirilen yazı tipini kullanan dize veya dizeleri güncelleştirerek çizim kodunuzu iyileştirmenize olanak tanır. Aşağıdaki bölümlerde, ikinci bir yazı tipi özelliği için ayrı bildirim arabirimlerini uygulamak için gereken adımlar gösterilmektedir. İkinci yazı tipi özelliğinin `HeadingFont` önceki bölüme eklenen özellik olduğu varsayılır.

### <a name="implementing-a-new-font-notification-interface"></a><a name="_core_implementing_a_new_font_notification_interface"></a> Yeni bir yazı tipi bildirim arabirimi uygulama

İki veya daha fazla yazı tipinin bildirimlerini ayırt etmek için, denetimde kullanılan her bir yazı tipi için yeni bir bildirim arabirimi uygulanmalıdır. Aşağıdaki bölümlerde, denetim üst bilgisi ve uygulama dosyalarını değiştirerek yeni bir yazı tipi bildirim arabiriminin nasıl uygulanacağı açıklanır.

### <a name="additions-to-the-header-file"></a>Üst bilgi dosyasının eklemeleri

Denetim üst bilgisi dosyasında (. H), sınıf bildirimine aşağıdaki satırları ekleyin:

[!code-cpp[NVC_MFC_AxFont#19](codesnippet/cpp/mfc-activex-controls-using-fonts_19.h)]

Bu, adlı arabirimin bir uygulamasını oluşturur `IPropertyNotifySink` `HeadingFontNotify` . Bu yeni arabirim adlı bir yöntemi içerir `OnChanged` .

### <a name="additions-to-the-implementation-file"></a>Uygulama dosyasına eklemeler

Başlık yazı tipini Başlatan kodda (denetim oluşturucusunda) &*m_xFontNotification* &*m_xHeadingFontNotify* olarak değiştirin. Ardından aşağıdaki kodu ekleyin:

[!code-cpp[NVC_MFC_AxFont#20](codesnippet/cpp/mfc-activex-controls-using-fonts_20.cpp)]

`AddRef`Arabirimindeki ve `Release` yöntemleri, `IPropertyNotifySink` ActiveX denetim nesnesi için başvuru sayısını izler. Denetim, arabirim işaretçisine erişim aldığında, Denetim `AddRef` başvuru sayısını artırmak için çağırır. Denetim işaretçiyle tamamlandığında, `Release` `GlobalFree` bir genel bellek bloğunu serbest bırakmak için çağrılabilir şekilde, çağırır. Bu arabirim için başvuru sayısı sıfır olduğunda, arabirim uygulama serbest bırakılmış olabilir. Bu örnekte, `QueryInterface` işlevi belirli bir nesne üzerindeki bir arabirime bir işaretçi döndürür `IPropertyNotifySink` . Bu işlev, ActiveX denetiminin desteklediği arabirimleri belirlemek için bir nesneyi sorgulamasına olanak sağlar.

Projenizde bu değişiklikler yapıldıktan sonra, projeyi yeniden derleyin ve arabirimi test etmek için test kapsayıcısını kullanın. Test kapsayıcısına erişme hakkında bilgi için bkz. test [kapsayıcı Ile özellikleri ve olayları test etme](testing-properties-and-events-with-test-container.md) .

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)<br/>
[MFC ActiveX denetimleri: ActiveX denetiminde resim kullanma](mfc-activex-controls-using-pictures-in-an-activex-control.md)<br/>
[MFC ActiveX denetimleri: stok özellik sayfalarını kullanma](mfc-activex-controls-using-stock-property-pages.md)
