---
title: 'MFC ActiveX denetimleri: Yazı tiplerini kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OnFontChanged
- HeadingFont
- InternalFont
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b14adec8d601778e255ae7e4242fc552fc820e64
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396707"
---
# <a name="mfc-activex-controls-using-fonts"></a>MFC ActiveX Denetimleri: Yazı Tiplerini Kullanma

ActiveX denetimi metin görüntülüyorsa, denetimi kullanıcısı bir yazı tipi özelliğini değiştirerek metni görünümünü değiştirmek izin verebilirsiniz. Yazı tipi özellikleri yazı tipi nesneleri olarak uygulanır ve iki türden biri olabilir: kullanıma hazır veya özel. Stok yazı tipi özellikleri, Özellik Ekleme Sihirbazı'nı kullanarak ekleyebilirsiniz preimplemented yazı tipi özelliklerdir. Özel yazı tipi özellikleri değil preimplemented ve özelliğin davranışlarını ve kullanım denetimi Geliştirici belirler.

Bu makalede, aşağıdaki konular ele alınmaktadır:

- [Stock Font özelliğini kullanma](#_core_using_the_stock_font_property)

- [Denetiminizi özel yazı tipi özelliklerini kullanma](#_core_implementing_a_custom_font_property)

##  <a name="_core_using_the_stock_font_property"></a> Stok yazı tipi özelliğini kullanma

Stok yazı tipi özellikleri sınıfı tarafından preimplemented [COleControl](../mfc/reference/colecontrol-class.md). Ayrıca, standart bir yazı tipi özellik sayfası yazı tipi nesnesinin adı, boyutu ve stilini gibi çeşitli özniteliklerini değiştirmesine izin verme, de kullanılabilir.

Yazı tipi nesnesi aracılığıyla erişmesine [GetFont](../mfc/reference/colecontrol-class.md#getfont), [SetFont](../mfc/reference/colecontrol-class.md#setfont), ve [InternalGetFont](../mfc/reference/colecontrol-class.md#internalgetfont) işlevlerini `COleControl`. Yazı tipi nesnesinin aracılığıyla denetim kullanıcı erişecek `GetFont` ve `SetFont` herhangi bir Get/Set özelliği ile aynı şekilde işlevleri. Yazı nesnesine erişim gelen denetim gerekli olduğunda kullanın `InternalGetFont` işlevi.

Bölümünde açıklandığı gibi [MFC ActiveX denetimleri: Özellikler](../mfc/mfc-activex-controls-properties.md), stok Özellikler ekleme ile kolay [Özellik Ekleme Sihirbazı'nı](../ide/names-add-property-wizard.md). Font özelliği seçin ve Özellik Ekleme Sihirbazı'nı denetimin dağıtım eşlemesi stok yazı tipi girişine otomatik olarak ekler.

#### <a name="to-add-the-stock-font-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak stok yazı tipi özellik eklemek için

1. Denetiminizin proje yükleyin.

1. Sınıf Görünümü'nde denetim kitaplığı düğümünü genişletin.

1. Arabirim (ikinci düğüm kitaplığı düğümünün) denetlemek için kısayol menüsünü açmak için düğümü.

1. Kısayol menüsünden tıklayın **Ekle** ve ardından **Özellik Ekle**.

     Bu özellik Ekleme Sihirbazı'nı açar.

1. İçinde **özellik adı** kutusunun **yazı tipi**.

1. **Son**'a tıklayın.

Özellik Ekleme Sihirbazı'nı denetimin dağıtım eşlemesi, denetim sınıf uygulama dosyasında bulunan aşağıdaki satırı ekler:

[!code-cpp[NVC_MFC_AxFont#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_1.cpp)]

Ayrıca, Özellik Ekleme Sihirbazı'nı aşağıdaki satırı denetimine ekler. IDL dosyası:

[!code-cpp[NVC_MFC_AxFont#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_2.idl)]

Stok resim yazısı özelliğini, stok yazı tipi özellik bilgileri kullanarak çizilmiş bir Text örneğidir. Resim yazısı özelliğini stok denetime ekleme adımları stock Font özelliği için kullanılan benzer kullanır.

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak stok resim yazısı özelliğini eklemek için

1. Denetiminizin proje yükleyin.

1. Sınıf Görünümü'nde denetim kitaplığı düğümünü genişletin.

1. Arabirim (ikinci düğüm kitaplığı düğümünün) denetlemek için kısayol menüsünü açmak için düğümü.

1. Kısayol menüsünden tıklayın **Ekle** ve ardından **Özellik Ekle**.

     Bu özellik Ekleme Sihirbazı'nı açar.

1. İçinde **özellik adı** kutusunun **açıklamalı alt yazı**.

1. **Son**'a tıklayın.

Özellik Ekleme Sihirbazı'nı denetimin dağıtım eşlemesi, denetim sınıf uygulama dosyasında bulunan aşağıdaki satırı ekler:

[!code-cpp[NVC_MFC_AxFont#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_3.cpp)]

##  <a name="_core_modifying_the_ondraw_function"></a> OnDraw işlevi değiştirme

Varsayılan uygulaması `OnDraw` denetimde görüntülenen tüm metni için Windows sistem yazı tipi kullanır. Yani, değiştirmelisiniz `OnDraw` cihaz bağlamına yazı tipi nesnesinin seçerek kod. Bunu yapmak için [COleControl::SelectStockFont](../mfc/reference/colecontrol-class.md#selectstockfont) ve denetimin cihaz bağlamı, aşağıdaki örnekte gösterildiği gibi geçirin:

[!code-cpp[NVC_MFC_AxFont#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_4.cpp)]

Sonra `OnDraw` işlevi, yazı tipi nesnesini kullanmak için değiştirilmiş, denetimin stok yazı tipi özelliğinden özelliklerle denetim içindeki herhangi bir metin görüntülenir.

##  <a name="_core_using_custom_font_properties_in_your_control"></a> Denetiminizi özel yazı tipi özelliklerini kullanma

Stok yazı tipi özellik yanı sıra özel yazı tipi özellikleri ActiveX denetimini olabilir. Özel yazı tipi özellik eklemek için yapmanız gerekir:

- Özel yazı tipi özellik uygulamak için Özellik Ekleme Sihirbazı'nı kullanın.

- [Yazı tipi bildirimlerini işleme](#_core_processing_font_notifications).

- [Yeni bir yazı tipi bildirim arabirimini uygulayan](#_core_implementing_a_new_font_notification_interface).

###  <a name="_core_implementing_a_custom_font_property"></a> Özel yazı tipi özellik uygulama

Özel bir yazı tipi özellik uygulamak için özellik ekleyin ve ardından kodu bazı değişiklikler yapmak için Özellik Ekleme Sihirbazı'nı kullanın. Aşağıdaki bölümlerde özel ekleme `HeadingFont` örnek denetim özelliği.

##### <a name="to-add-the-custom-font-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak özel yazı tipi özellik eklemek için

1. Denetiminizin proje yükleyin.

1. Sınıf Görünümü'nde denetim kitaplığı düğümünü genişletin.

1. Arabirim (ikinci düğüm kitaplığı düğümünün) denetlemek için kısayol menüsünü açmak için düğümü.

1. Kısayol menüsünden tıklayın **Ekle** ve ardından **Özellik Ekle**.

     Bu özellik Ekleme Sihirbazı'nı açar.

1. İçinde **özellik adı** özellik için bir ad yazın. Bu örneğin **HeadingFont**.

1. İçin **uygulama türü**, tıklayın **Get/Set yöntemleri**.

1. İçinde **özellik türü** kutusunda **IDispatch** <strong>\*</strong> özelliğin türü.

1. **Son**'a tıklayın.

Özellik Ekleme Sihirbazı'nı eklemek için kod oluşturur `HeadingFont` için özel özellik `CSampleCtrl` sınıf ve örnek. IDL dosyası. Çünkü `HeadingFont` Get/Set özellik türü, Özellik Ekleme Sihirbazı'nı değiştirir `CSampleCtrl` bir DISP_PROPERTY_EX_ID eklenecek sınıfın dağıtım eşlemesi[dısp_property_ex](../mfc/reference/dispatch-maps.md#disp_property_ex) makro girişi:

[!code-cpp[NVC_MFC_AxFont#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_5.cpp)]

Dısp_property_ex makrosu ilişkilendirir `HeadingFont` özellik adı ile karşılık gelen `CSampleCtrl` sınıfı almanıza ve ayarlamanıza yöntemleri, `GetHeadingFont` ve `SetHeadingFont`. Özellik değeri türü da belirtilir; Bu durumda, VT_FONT.

Özellik Ekleme Sihirbazı'nı, ayrıca bir bildirim denetimi üstbilgi dosyasında ekler (. H) için `GetHeadingFont` ve `SetHeadingFont` işlevler ve kendi işlev şablonları ekler denetimi uygulama dosyasında (. CPP):

[!code-cpp[NVC_MFC_AxFont#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_6.cpp)]

Son olarak, Özellik Ekleme Sihirbazı'nı Denetim değiştirir. IDL dosyası için bir giriş ekleyerek `HeadingFont` özelliği:

[!code-cpp[NVC_MFC_AxFont#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_7.idl)]

### <a name="modifications-to-the-control-code"></a>Denetim kodu değişiklikleri

Eklediğiniz göre `HeadingFont` denetim özelliğini, yeni özelliği tam olarak desteklemek için denetim üst bilgi ve uygulama dosyaları için bazı değişiklikler olmalısınız.

Denetimi üst bilgi dosyasının (. H), bir korumalı üye değişkeni aşağıdaki bildirimi ekleyin:

[!code-cpp[NVC_MFC_AxFont#8](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_8.h)]

Denetim uygulama dosyasında (. CPP), aşağıdakileri yapın:

- Başlatma *m_fontHeading* denetim oluşturucuda.

     [!code-cpp[NVC_MFC_AxFont#9](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_9.cpp)]

- Varsayılan yazı tipi özniteliklerini içeren bir statik FONTDESC yapısı bildirin.

     [!code-cpp[NVC_MFC_AxFont#10](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_10.cpp)]

- Denetimdeki `DoPropExchange` üye işlev, bir çağrı ekleyin `PX_Font` işlevi. Bu, başlatma ve özel yazı tipi özelliğinizi kalıcılığını sağlar.

     [!code-cpp[NVC_MFC_AxFont#11](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_11.cpp)]

- Denetimi uygulamak son `GetHeadingFont` üye işlevi.

     [!code-cpp[NVC_MFC_AxFont#12](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_12.cpp)]

- Denetimi uygulamak son `SetHeadingFont` üye işlevi.

     [!code-cpp[NVC_MFC_AxFont#13](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_13.cpp)]

- Denetimi değiştirme `OnDraw` üye işlevini daha önce seçilen yazı tipi tutacak bir değişken tanımlayın.

     [!code-cpp[NVC_MFC_AxFont#14](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_14.cpp)]

- Denetimi değiştirme `OnDraw` kullanılacak yazı tipini olduğu yerlerde aşağıdaki satırı ekleyerek cihaz bağlamına özel yazı tipi seçmek için üye işlevi.

     [!code-cpp[NVC_MFC_AxFont#15](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_15.cpp)]

- Denetimi değiştirme `OnDraw` önceki yazı tipini, yazı tipi kullanıldıktan sonra aşağıdaki satırı ekleyerek cihaz bağlamına seçmek için üye işlevi.

     [!code-cpp[NVC_MFC_AxFont#16](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_16.cpp)]

Özel yazı tipi özellik uygulamıştır sonra denetimin geçerli yazı tipini değiştirmek denetim kullanıcıların standart yazı tipi özellik sayfası uygulanmalıdır. Standart yazı tipi özellik sayfası için özellik sayfa kimliği eklemek için begın_proppageıds makrosu sonra aşağıdaki satırı ekleyin:

[!code-cpp[NVC_MFC_AxFont#17](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_17.cpp)]

Ayrıca bir sayısı parametresi, begın_proppageıds makrosu artırmalısınız. Aşağıdaki satırı bunu göstermektedir:

[!code-cpp[NVC_MFC_AxFont#18](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_18.cpp)]

Bu değişiklikleri yaptıktan sonra ek işlevsellik eklemek için tüm projeyi yeniden derleyin.

###  <a name="_core_processing_font_notifications"></a> Yazı tipi bildirimlerini işleme

Çoğu durumda, Denetim yazı tipi nesnesinin özellikleri değiştirildiğinde bilmesi gerekir. Her bir yazı tipi nesnesinin bir üye işlevini çağırarak değiştiğinde bildirimleri sağlama yeteneğine `IFontNotification` tarafından uygulanan arabirimi `COleControl`.

Denetim stok yazı tipi özelliğini kullanıyorsa, bildirim tarafından işlenen `OnFontChanged` üye işlevini `COleControl`. Özel yazı tipi özellikleri eklediğinizde, bunları aynı uygulaması kullanmak olabilir. Önceki bölümdeki örnekte, bu geçirerek gerçekleştirilmiştir &*m_xFontNotification* başlatılırken *m_fontHeading* üye değişkeni.

![Birden çok yazı tipi nesne arabirimleri uygulama](../mfc/media/vc373q1.gif "vc373q1") uygulama birden çok yazı tipi nesnesi arabirimleri

Yazı tipi her iki nesnenin aynı uygulamasını kullanıyorsanız yukarıdaki şekilde düz çizgiler Göster `IFontNotification`. Yazı tipi değiştirilen ayırmak istiyorsanız bu sorunlara neden.

Denetim yazı tipi nesne bildirimler arasında ayrım yapmak için bir yoludur, ayrı bir uygulama oluşturmak için `IFontNotification` her denetiminde yazı tipi nesne için arabirim. Bu teknik, yalnızca dize veya yakın zamanda değiştirilmiş yazı tipini kullan dizeleri, güncelleştirerek çizim kodunuz iyileştirmenize imkan sağlar. Aşağıdaki bölümlerde, ikinci bir yazı tipi özellik için ayrı bildirim arabirimleri de uygulamak gerekli adımları gösterilmektedir. İkinci font özelliği varsayılır `HeadingFont` önceki bölümde eklendikten sonra özelliği.

###  <a name="_core_implementing_a_new_font_notification_interface"></a> Yeni bir yazı tipi bildirim arabirimini uygulama

İki veya daha fazla yazı tipi bildirimler arasında ayrım yapmak için yeni bir bildirim arabirimi denetimde kullanılan her bir yazı tipinin uygulanmalıdır. Aşağıdaki bölümlerde nasıl denetimi üst bilgi ve uygulama dosyalarını değiştirerek yeni bir yazı tipi bildirim arabirimi uygulanacağı açıklanmaktadır.

### <a name="additions-to-the-header-file"></a>Üst bilgi dosyası eklemeler

Denetimi üst bilgi dosyasının (. H), sınıf bildirimi için aşağıdaki satırları ekleyin:

[!code-cpp[NVC_MFC_AxFont#19](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_19.h)]

Bu, bir uygulama oluşturur `IPropertyNotifySink` adlı arabirim `HeadingFontNotify`. Bu yeni arabirim adlı yöntemi içeren `OnChanged`.

### <a name="additions-to-the-implementation-file"></a>Uygulama dosyasına ekleme

Başlık yazı tipi (Denetim oluşturucuda) başlatır kodda değişiklik &*m_xFontNotification* için &*m_xHeadingFontNotify*. Ardından aşağıdaki kodu ekleyin:

[!code-cpp[NVC_MFC_AxFont#20](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_20.cpp)]

`AddRef` Ve `Release` yöntemleri `IPropertyNotifySink` arabirimi ActiveX denetimi nesne başvuru sayımını izler. Arabirim işaretçisi için erişim denetimi aldığında, Denetim çağrıları `AddRef` başvuru sayısı artırılamıyor. Denetim ve işaretçiyle tamamlandığında çağırdığı `Release`, çok aynı şekilde `GlobalFree` genel bellek öbeğini serbest olarak adlandırılabilir. Bu arabirim için başvuru sayısı sıfıra gittiğinde arabirimi uygulaması serbest bırakılabilir. Bu örnekte, `QueryInterface` işlevi için bir işaretçi döndüren bir `IPropertyNotifySink` belirli bir nesne üzerinde arabirimi. Bu işlev, hangi arabirimlerin belirlemek için bir nesneyi sorgulamak bir ActiveX denetimi sağlar.

Projenize bu değişiklikler yapıldıktan sonra projeyi yeniden derleyin ve arabirimi testi için Test kapsayıcısını kullanın. Bkz: [Test kapsayıcısı ile test etme özellikleri ve olayları](../mfc/testing-properties-and-events-with-test-container.md) test kapsayıcı erişim hakkında daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: ActiveX Denetiminde Resim Kullanma](../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)<br/>
[MFC ActiveX Denetimleri: Stok Özellik Sayfalarını Kullanma](../mfc/mfc-activex-controls-using-stock-property-pages.md)

