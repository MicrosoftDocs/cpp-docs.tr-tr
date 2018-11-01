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
ms.openlocfilehash: fe239f864f4b7730d28372ee3fc9d298131d28d9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462107"
---
# <a name="mfc-activex-controls-using-pictures-in-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetiminde Resim Kullanma

Bu makalede, yaygın resim türünü ve ActiveX denetiminizin nasıl açıklar. Konular şunlardır:

- [Özel Resim Özellikleri'ne genel bakış](#_core_overview_of_custom_picture_properties)

- [ActiveX denetiminizin özel resim özelliği uygulama](#_core_implementing_a_custom_picture_property_in_your_activex_control)

- [Denetim projenize ekleme](#_core_additions_to_your_control_project)

##  <a name="_core_overview_of_custom_picture_properties"></a> Özel Resim Özellikleri'ne genel bakış

Resim türü, bazı ActiveX denetimleri için ortak türü biridir. Resim türü, meta dosyaları, bit eşlemler ve simgeleri işler ve ActiveX denetiminde görüntülenecek resim belirtmesini sağlar. Resim nesnesi ve kullanıcı erişimini denetlemek için resim özelliği sağlayan Get/Set işlevleri kullanarak özel resim özellikleri uygulanır. Denetim kullanıcılar hisse senedi resim özellik sayfasını kullanarak özel resim özelliği erişir.

Ek olarak standart resim türü, yazı tipi ve renk türleri de mevcuttur. ActiveX denetiminizin standart yazı tipini kullanarak daha fazla bilgi için bkz [MFC ActiveX denetimleri: yazı tiplerini kullanarak](../mfc/mfc-activex-controls-using-fonts.md).

ActiveX denetim sınıfları denetiminde resim özelliği uygulamak için kullanabileceğiniz çeşitli bileşenleri sağlar. Bu bileşenler şunlardır:

- [CPictureHolder](../mfc/reference/cpictureholder-class.md) sınıfı.

   Bu sınıf özel bir resim özelliği tarafından görüntülenen öğe için işlevselliği ve resim nesnesi için kolay erişim sağlar.

- Tür özellikleri için destek **LPPICTUREDISP**, Get/Set işlevleri ile uygulanan.

   Sınıfı, hızla özel bir özellik veya özellikler ekleyebilirsiniz görünümünü kullanarak, resim türünü destekler. Sınıf Görünümü ile ActiveX denetimi Özellikler ekleme ile ilgili daha fazla bilgi için bkz [MFC ActiveX denetimleri: Özellikler](../mfc/mfc-activex-controls-properties.md).

- Bir denetimin resim özelliği veya özellikleri işleyen bir özellik sayfası.

   Bu özellik sayfası stok özellik sayfalarını ActiveX denetimleri için kullanılabilir bir grubun bir parçasıdır. ActiveX denetimi özellik sayfaları hakkında daha fazla bilgi için bkz [MFC ActiveX denetimleri: stok özellik sayfalarını kullanma](../mfc/mfc-activex-controls-using-stock-property-pages.md)

##  <a name="_core_implementing_a_custom_picture_property_in_your_activex_control"></a> ActiveX denetiminizin özel resim özelliği uygulama

Bu bölümde açıklanan adımları tamamladıktan sonra denetimin, kullanıcı tarafından seçmiş resimleri görüntüleyebilirsiniz. Kullanıcının geçerli resim gösterir ve seçim farklı resimleri kullanıcıya izin veren bir Gözat düğmesi olan bir özellik sayfasını kullanarak bir resmin değiştirebilirsiniz.

Özel Resim özelliği, özel özellik türü resim desteklemelidir olmasına temel fark diğer özellikleri uygulamak için kullanılan benzer bir işlem kullanılarak uygulanır. ActiveX denetiminde resim özelliği öğesinin çizilmesi olduğundan, tam olarak uygulanabilir önce birkaç eklemelerinizi ve değişikliklerinizi özelliğini yapılmalıdır.

Özel Resim özelliği uygulamak için aşağıdakileri yapmanız gerekir:

- [Kod denetimi projenize ekleyin](#_core_additions_to_your_control_project).

   Bir standart resim özelliği sayfa kimliği, bir veri üyesi türünün `CPictureHolder`ve türünde bir özel özellik **LPPICTUREDISP** Get/Set ile uygulama eklenmesi gerekir.

- [Çeşitli işlevler denetim sınıfınızdaki değiştirme](#_core_modifications_to_your_control_project).

   Bu değişiklikler, ActiveX denetiminizin çizim için sorumlu olan çeşitli işlevler sunulacaktır.

##  <a name="_core_additions_to_your_control_project"></a> Denetim projenize ekleme

Standart resim özellik sayfası için özellik sayfa kimliği eklemek için Denetim uygulama dosyasında begın_proppageıds makrosu sonra aşağıdaki satırı ekleyin (. CPP):

[!code-cpp[NVC_MFC_AxPic#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_1.cpp)]

Ayrıca bir sayısı parametresi, begın_proppageıds makrosu artırmalısınız. Aşağıdaki satırı bunu göstermektedir:

[!code-cpp[NVC_MFC_AxPic#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_2.cpp)]

Eklenecek `CPictureHolder` denetim sınıf veri üyesi denetimi üstbilgi dosyasında denetim sınıf bildiriminin korunan bölümünde aşağıdaki satırı ekleyin (. H):

[!code-cpp[NVC_MFC_AxPic#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_3.h)]

Ad, veri üyesi gerekli değildir *m_pic*; herhangi bir ad yeterli olacaktır.

Ardından, bir resim türünü destekleyen özel bir özellik ekleyin:

#### <a name="to-add-a-custom-picture-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak bir özel resim özelliği eklemek için

1. Denetiminizin proje yükleyin.

1. Sınıf Görünümü'nde denetim kitaplığı düğümünü genişletin.

1. Arabirim (ikinci düğüm kitaplığı düğümünün) denetlemek için kısayol menüsünü açmak için düğümü.

1. Kısayol menüsünden **Ekle** ardından **Özellik Ekle**.

1. İçinde **özellik adı** özellik adı yazın. Örneğin amaçları `ControlPicture` bu yordamda kullanılır.

1. İçinde **özellik türü** kutusunda **IPictureDisp** <strong>\*</strong> özellik türü.

1. İçin **uygulama türü**, tıklayın **Get/Set yöntemleri**.

1. Get ve işlevler kümesi için benzersiz adlarını yazın veya varsayılan adı kabul edin. (Bu örnekte, varsayılan adları `GetControlPicture` ve `SetControlPicture` kullanılır.)

9. **Son**'a tıklayın.

Özellik Ekleme Sihirbazı'nı control üst bilgisi gönderme harita açıklamalarda arasına aşağıdaki kodu ekler (. H) dosyası:

[!code-cpp[NVC_MFC_AxPic#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_4.h)]

Ayrıca, aşağıdaki kod denetimi uygulama gönderme haritasını eklendi (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxPic#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_5.cpp)]

Özellik Ekleme Sihirbazı'nı, ayrıca denetimi uygulama dosyasında aşağıdaki iki saplama işlevleri ekler:

[!code-cpp[NVC_MFC_AxPic#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_6.cpp)]

> [!NOTE]
>  Denetim sınıf ve işlev adları, yukarıdaki örnekten farklı olabilir.

###  <a name="_core_modifications_to_your_control_project"></a> Denetim projenize değişiklikler

Gerekli Eklentiler denetimi projenize yaptıktan sonra ActiveX denetiminizin işlenmesini etkileyen çeşitli işlevler değiştirmeniz gerekir. Bu işlevler `OnResetState`, `OnDraw`, ve özel resim özelliği Get/Set işlevlerini denetimi uygulama dosyasında bulunur. (Bu örnekte control sınıfı çağrıldığını unutmayın `CSampleCtrl`, `CPictureHolder` veri üyesi çağrıldığında *m_pic*, ve özel resim özelliği adı `ControlPicture`.)

Denetimdeki `OnResetState` işlev, aşağıdaki isteğe bağlı satırı çağrısından sonra ekleyin `COleControl::OnResetState`:

[!code-cpp[NVC_MFC_AxPic#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_7.cpp)]

Bu, boş bir resme denetimin resmini ayarlar.

Resmi düzgün bir şekilde çizmek için çağrı yapmak [CPictureHolder::Render](../mfc/reference/cpictureholder-class.md#render) denetiminde `OnDraw` işlevi. İşlevinizi aşağıdaki örneğe benzer şekilde değiştirin:

[!code-cpp[NVC_MFC_AxPic#8](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_8.cpp)]

Denetimin özel resim özelliği Al işlevinde, aşağıdaki satırı ekleyin:

[!code-cpp[NVC_MFC_AxPic#9](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_9.cpp)]

Denetimin özel resim özelliği ayarlama işlevinde, aşağıdaki satırları ekleyin:

[!code-cpp[NVC_MFC_AxPic#10](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_10.cpp)]

Tasarım zamanında eklenen çalışma zamanında gösterilir böylece resim özelliği kalıcı olarak yapılmalıdır. Aşağıdaki satırı ekleyin `COleControl`-derived class'ın `DoPropExchange` işlevi:

[!code-cpp[NVC_MFC_AxPic#11](../mfc/codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_11.cpp)]

> [!NOTE]
>  Sınıf ve işlev adları, yukarıdaki örnekten farklı olabilir.

Değişiklikleri tamamladıktan sonra özel resim özelliğinin yeni işlevsellikler eklemek ve yeni özelliği test etmek için Test kapsayıcı kullanmak için projenizi yeniden derleyin. Bkz: [Test kapsayıcısı ile test etme özellikleri ve olayları](../mfc/testing-properties-and-events-with-test-container.md) test kapsayıcı erişim hakkında daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: Yazı Tiplerini Kullanma](../mfc/mfc-activex-controls-using-fonts.md)<br/>
[MFC ActiveX Denetimleri: Özellik Sayfaları](../mfc/mfc-activex-controls-property-pages.md)

