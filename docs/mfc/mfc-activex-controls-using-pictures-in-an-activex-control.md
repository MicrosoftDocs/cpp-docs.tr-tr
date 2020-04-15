---
title: 'MFC ActiveX Denetimleri: ActiveX Denetiminde Resim Kullanma'
ms.date: 11/04/2016
f1_keywords:
- LPPICTUREDISP
helpviewer_keywords:
- OnDraw method, MFC ActiveX controls
- MFC ActiveX controls [MFC], pictures
- OnDraw method [MFC]
- OnResetState method [MFC]
- CLSID_CPicturePropPage [MFC]
ms.assetid: 2e49735c-21b9-4442-bb3d-c82ef258eec9
ms.openlocfilehash: 1f78823f39417ff6928a1b915d83507bc1ac9526
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358288"
---
# <a name="mfc-activex-controls-using-pictures-in-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetiminde Resim Kullanma

Bu makalede, ortak Resim türünü ve ActiveX denetiminizde nasıl uygulanacağı açıklanmaktadır. Konu başlıkları şunlardır:

- [Özel Resim Özelliklerine Genel Bakış](#_core_overview_of_custom_picture_properties)

- [ActiveX Denetiminizde Özel Resim Özelliği Uygulama](#_core_implementing_a_custom_picture_property_in_your_activex_control)

- [Kontrol Projenize Eklemeler](#_core_additions_to_your_control_project)

## <a name="overview-of-custom-picture-properties"></a><a name="_core_overview_of_custom_picture_properties"></a>Özel Resim Özelliklerine Genel Bakış

Resim türü, bazı ActiveX denetimleri için ortak olan türlerden biridir. Resim türü meta dosyaları, bit eşlemleri veya simgeleri işler ve kullanıcının ActiveX denetiminde görüntülenecek bir resmi belirtmesine olanak tanır. Özel Resim özellikleri, bir resim nesnesi kullanılarak uygulanır ve denetim kullanıcısının Resim özelliğine erişmesine izin veren Get/Set işlevleri. Denetim kullanıcıları, stok Resim özelliği sayfasını kullanarak özel Resim özelliğine erişin.

Standart Resim türüne ek olarak, Yazı Tipi ve Renk türleri de mevcuttur. ActiveX denetiminizdeki standart Yazı Tipi türünü kullanma hakkında daha fazla bilgi için [MFC ActiveX Denetimleri makalesine bakın: Yazı Tiplerini Kullanma.](../mfc/mfc-activex-controls-using-fonts.md)

ActiveX denetim sınıfları, denetim içinde Resim özelliğini uygulamak için kullanabileceğiniz birkaç bileşen sağlar. Bu bileşenler şunlardır:

- [CPictureHolder](../mfc/reference/cpictureholder-class.md) sınıfı.

   Bu sınıf, resim nesnesine kolay erişim ve özel Resim özelliği tarafından görüntülenen öğe için işlevsellik sağlar.

- Get/Set işlevleri ile uygulanan **LPPICTUREDISP**tipi özellikleri için destek.

   Sınıf Görünümü'ni kullanarak, Resim türünü destekleyen özel bir özellik veya özellik ekleyebilirsiniz. Sınıf Görünümü ile ActiveX denetim özellikleri ekleme hakkında daha fazla bilgi için [MFC ActiveX Denetimleri makalesine bakın: Özellikler.](../mfc/mfc-activex-controls-properties.md)

- Denetimin Resim özelliğini veya özelliklerini manipüle eden bir özellik sayfası.

   Bu özellik sayfası, ActiveX denetimleri için kullanılabilen stok özelliği sayfaları grubunun bir parçasıdır. ActiveX denetim özelliği sayfaları hakkında daha fazla bilgi için [MFC ActiveX Denetimleri makalesine bakın: Stok Mülkiyet Sayfalarını Kullanma](../mfc/mfc-activex-controls-using-stock-property-pages.md)

## <a name="implementing-a-custom-picture-property-in-your-activex-control"></a><a name="_core_implementing_a_custom_picture_property_in_your_activex_control"></a>ActiveX Denetiminizde Özel Resim Özelliği Uygulama

Bu bölümde özetlenen adımları tamamladığınızda, denetim kullanıcısı tarafından seçilen resimleri görüntüleyebilir. Kullanıcı, görüntülenen resmi geçerli resmi gösteren ve kullanıcının farklı resimleri seçmesine olanak tanıyan bir Gözat düğmesine sahip bir özellik sayfasını kullanarak değiştirebilir.

Özel Resim özelliği, diğer özellikleri uygulamak için kullanılana benzer bir işlem kullanılarak uygulanır, temel fark, özel özelliğin Resim türünü desteklemesi gerektiğidir. Resim özelliğinin öğesinin ActiveX denetimi tarafından çizilmesi gerektiğinden, tam olarak uygulanabilmesi için önce özellik için bir dizi ekleme ve değişiklik yapılması gerekir.

Özel bir Resim özelliği uygulamak için aşağıdakileri yapmanız gerekir:

- [Denetim projenize kod ekleyin.](#_core_additions_to_your_control_project)

   Standart bir Resim özelliği sayfası kimliği, `CPictureHolder`bir veri üyesi ve Get/Set uygulamasına sahip **LPPICTUREDISP** türünden özel bir özellik eklenmelidir.

- [Denetim sınıfınızdaki çeşitli işlevleri değiştirin.](#_core_modifications_to_your_control_project)

   Bu değişiklikler ActiveX denetiminizin çiziminden sorumlu olan çeşitli işlevlerde yapılacaktır.

## <a name="additions-to-your-control-project"></a><a name="_core_additions_to_your_control_project"></a>Kontrol Projenize Eklemeler

Standart Resim özelliği sayfası için özellik sayfası kimliğini eklemek için, denetim uygulama dosyasındaki BEGIN_PROPPAGEIDS makrosundan sonra aşağıdaki satırı ekleyin (. CPP:

[!code-cpp[NVC_MFC_AxPic#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_1.cpp)]

Ayrıca, BEGIN_PROPPAGEIDS makronuzun sayım parametresini de birer birer artımgerekir. Aşağıdaki satır bunu göstermektedir:

[!code-cpp[NVC_MFC_AxPic#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_2.cpp)]

Veri üyesini `CPictureHolder` denetim sınıfına eklemek için, denetim üstbilgi dosyasındaki denetim sınıfı bildiriminin korumalı bölümünün altına aşağıdaki satırı ekleyin (. H):

[!code-cpp[NVC_MFC_AxPic#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_3.h)]

Veri üyenize *m_pic*adlandırmanız gerekmez; herhangi bir isim yeterli olacaktır.

Ardından, Resim türünü destekleyen özel bir özellik ekleyin:

#### <a name="to-add-a-custom-picture-property-using-the-add-property-wizard"></a>Özellik Ekle Sihirbazı'nı kullanarak özel resim özelliği eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü'nde, denetiminizin kitaplık düğümunu genişletin.

1. Kısayol menüsünü açmak için denetiminiz için arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünden Ekle ve ardından **Özellik Ekle'yi**seçin. **Add**

1. Özellik **Adı** kutusuna özellik adını yazın. Örneğin amaçlar `ControlPicture` için, bu yordamda kullanılır.

1. Özellik **Türü** kutusunda, özellik türü için **IPictureDisp'i** <strong>\*</strong> seçin.

1. **Uygulama Türü** **için, Yöntemleri Al/Ayarla'yı**tıklatın.

1. İşlevleri Al ve Ayarla'nız için benzersiz adlar yazın veya varsayılan adları kabul edin. (Bu örnekte, varsayılan `GetControlPicture` `SetControlPicture` adlar ve kullanılır.)

1. **Son**'a tıklayın.

Özellik Ekle Sihirbazı, denetim üstbilgisindeki gönderme haritası açıklamaları arasına aşağıdaki kodu ekler (. H) dosya:

[!code-cpp[NVC_MFC_AxPic#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_4.h)]

Buna ek olarak, aşağıdaki kod denetim uygulamasının sevk haritasına eklenmiştir (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxPic#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_5.cpp)]

Özellik Ekle Sihirbazı ayrıca denetim uygulama dosyasına aşağıdaki iki saplama işlevi ekler:

[!code-cpp[NVC_MFC_AxPic#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_6.cpp)]

> [!NOTE]
> Denetim sınıfınız ve işlev adlarınız yukarıdaki örnekten farklı olabilir.

### <a name="modifications-to-your-control-project"></a><a name="_core_modifications_to_your_control_project"></a>Kontrol Projenizde Yapılan Değişiklikler

Denetim projenize gerekli eklemeleri yaptıktan sonra ActiveX denetiminizin işlenmesini etkileyen çeşitli işlevleri değiştirmeniz gerekir. Bu işlevler, `OnResetState`ve `OnDraw`özel resim özelliğinin Get/Set işlevleri denetim uygulama dosyasında bulunur. (Bu örnekte denetim sınıfının `CSampleCtrl`çağrıldığını `CPictureHolder` unutmayın, veri üyesi *m_pic*olarak adlandırılır `ControlPicture`ve özel resim özelliği adı dır.)

Denetim `OnResetState` işlevinde, çağrıdan sonra aşağıdaki isteğe bağlı satırı `COleControl::OnResetState`ekleyin:

[!code-cpp[NVC_MFC_AxPic#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_7.cpp)]

Bu, denetimin resmini boş bir resme ayarlar.

Resmi düzgün çizmek için [CPictureHolder'ı arayın::Denetim](../mfc/reference/cpictureholder-class.md#render) `OnDraw` işlevinde işleme. İşlevinizi aşağıdaki örneğe benzeyecek şekilde değiştirin:

[!code-cpp[NVC_MFC_AxPic#8](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_8.cpp)]

Denetimin özel resim özelliğinin Al işlevine aşağıdaki satırı ekleyin:

[!code-cpp[NVC_MFC_AxPic#9](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_9.cpp)]

Denetimin özel Resim özelliğinin Ayarla işlevinde aşağıdaki satırları ekleyin:

[!code-cpp[NVC_MFC_AxPic#10](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_10.cpp)]

Tasarım zamanında eklenen bilgilerin çalışma zamanında görüneceği için resim özelliği kalıcı hale getirilmelidir. `COleControl`Türemiş sınıfın `DoPropExchange` işlevine aşağıdaki satırı ekleyin:

[!code-cpp[NVC_MFC_AxPic#11](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_11.cpp)]

> [!NOTE]
> Sınıf ve işlev adlarınız yukarıdaki örnekten farklı olabilir.

Değişiklikleri tamamladıktan sonra, özel Resim özelliğinin yeni işlevselliğini birleştirmek için projenizi yeniden oluşturun ve yeni özelliği sınamak için Test Kapsayıcısı'nı kullanın. Test kapsayıcısına nasıl erişireceksiniz hakkında bilgi almak için [Test Kapsayıcısı ile Test Özellikleri ve Olayları'na](../mfc/testing-properties-and-events-with-test-container.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: Yazı Tiplerini Kullanma](../mfc/mfc-activex-controls-using-fonts.md)<br/>
[MFC ActiveX Denetimleri: Özellik Sayfaları](../mfc/mfc-activex-controls-property-pages.md)
