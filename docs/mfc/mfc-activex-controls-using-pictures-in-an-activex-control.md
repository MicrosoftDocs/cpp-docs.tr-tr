---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: ActiveX denetiminde resim kullanma'
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
ms.openlocfilehash: 9c9989be7503eb449b969fbbf37d92f26c165131
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133087"
---
# <a name="mfc-activex-controls-using-pictures-in-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetiminde Resim Kullanma

Bu makalede, ortak resim türü ve ActiveX denetimi nasıl uygulanacağı açıklanır. Konu başlıkları şunlardır:

- [Özel resim özelliklerine genel bakış](#_core_overview_of_custom_picture_properties)

- [ActiveX denetimi özel bir resim özelliği uygulama](#_core_implementing_a_custom_picture_property_in_your_activex_control)

- [Denetim projenize eklemeler](#_core_additions_to_your_control_project)

## <a name="overview-of-custom-picture-properties"></a><a name="_core_overview_of_custom_picture_properties"></a> Özel resim özelliklerine genel bakış

Resim türü, bazı ActiveX denetimleri için ortak bir tür grubundan biridir. Resim türü, meta dosyaları, bit eşlemleri veya simgeleri işler ve kullanıcının ActiveX denetiminde görüntülenmek üzere bir resim belirtmesini sağlar. Özel resim özellikleri bir resim nesnesi kullanılarak uygulanır ve denetimin kullanıcı tarafından resim özelliğine erişmesine izin veren işlevleri alır/ayarlar. Kullanıcıların, hisse senedi resmi özellik sayfasını kullanarak özel resim özelliğine erişmesini denetleme.

Standart resim türüne ek olarak, yazı tipi ve renk türleri de mevcuttur. ActiveX denetiinizdeki standart yazı tipi türünü kullanma hakkında daha fazla bilgi için [MFC ActiveX denetimleri: yazı tiplerini kullanma](mfc-activex-controls-using-fonts.md)makalesine bakın.

ActiveX denetim sınıfları, denetimin içindeki resim özelliğini uygulamak için kullanabileceğiniz çeşitli bileşenler sağlar. Bu bileşenler şunlardır:

- [Cpictureş](reference/cpictureholder-class.md) sınıfı.

   Bu sınıf, özel resim özelliği tarafından görünen öğe için resim nesnesine ve işlevlere kolay erişim sağlar.

- Get/Set işlevleriyle uygulanan **Lppicturedisp** türündeki özellikler için destek.

   Sınıf Görünümü kullanarak, resim türünü destekleyen özel bir özelliği veya özellikleri hızlıca ekleyebilirsiniz. Sınıf Görünümü ile ActiveX denetim özellikleri ekleme hakkında daha fazla bilgi için [MFC ActiveX denetimleri: Özellikler](mfc-activex-controls-properties.md)makalesine bakın.

- Bir denetimin resim özelliğini veya özelliklerini işleyen bir özellik sayfası.

   Bu özellik sayfası, ActiveX denetimleri için kullanılabilen bir hisse senedi özellik sayfaları grubunun parçasıdır. ActiveX denetimi özellik sayfaları hakkında daha fazla bilgi için bkz. [MFC ActiveX denetimleri: stok özellik sayfalarını kullanma](mfc-activex-controls-using-stock-property-pages.md)

## <a name="implementing-a-custom-picture-property-in-your-activex-control"></a><a name="_core_implementing_a_custom_picture_property_in_your_activex_control"></a> ActiveX denetimi özel bir resim özelliği uygulama

Bu bölümde özetlenen adımları tamamladığınızda denetim, Kullanıcı tarafından seçilen resimleri görüntüleyebilir. Kullanıcı, geçerli resmi gösteren bir özellik sayfası kullanarak görüntülenen resmi değiştirebilir ve kullanıcının farklı resimler seçmesine izin veren bir tarama düğmesi vardır.

Özel resim özelliği, diğer özellikleri uygulamak için kullanılmasına benzer bir işlem kullanılarak uygulanır, özel özelliğin bir resim türünü desteklemesi gerekir. Resim özelliğinin öğesi ActiveX denetimi tarafından çizilmelidir, çünkü tamamen uygulanmadan önce özellikte bir dizi ekleme ve değişiklik yapılmalıdır.

Özel bir resim özelliği uygulamak için aşağıdakileri yapmanız gerekir:

- [Denetim projenize kod ekleyin](#_core_additions_to_your_control_project).

   Standart resim özellik sayfası KIMLIĞI, türünün bir veri üyesi `CPictureHolder` ve bir get/set uygulamasıyla **Lppicturedisp** türünde özel bir özellik eklenmelidir.

- [Denetim sınıfınızın çeşitli Işlevlerini değiştirin](#_core_modifications_to_your_control_project).

   Bu değişiklikler, ActiveX denetiminizin çiziminden sorumlu olan çeşitli işlevlerde yapılır.

## <a name="additions-to-your-control-project"></a><a name="_core_additions_to_your_control_project"></a> Denetim projenize eklemeler

Standart resim özellik sayfası için özellik sayfası KIMLIĞINI eklemek için, denetim uygulama dosyasında BEGIN_PROPPAGEIDS makrodan sonra aşağıdaki satırı ekleyin (. CPP):

[!code-cpp[NVC_MFC_AxPic#1](codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_1.cpp)]

Ayrıca, BEGIN_PROPPAGEIDS makrolarınızın Count parametresini bir de artırmalısınız. Aşağıdaki satırda bu gösterilmektedir:

[!code-cpp[NVC_MFC_AxPic#2](codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_2.cpp)]

`CPictureHolder`Veri üyesini denetim sınıfına eklemek için, denetim üst bilgisi dosyasındaki denetim sınıfı bildiriminin korumalı bölümünün altına aşağıdaki satırı ekleyin (. H):

[!code-cpp[NVC_MFC_AxPic#3](codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_3.h)]

Veri üye *m_pic* adlandırmak gerekli değildir; herhangi bir ad yeterli olacaktır.

Sonra, bir resim türünü destekleyen özel bir özellik ekleyin:

#### <a name="to-add-a-custom-picture-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı 'Nı kullanarak özel bir resim özelliği eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü, denetiminizin kitaplık düğümünü genişletin.

1. Kısayol menüsünü açmak için denetiminizin arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünde **Ekle** ' yi ve ardından **Özellik Ekle**' yi seçin.

1. **Özellik adı** kutusuna özellik adını yazın. Örneğin, `ControlPicture` Bu yordamda kullanılır.

1. **Özellik türü** kutusunda, özellik türü Için **IPictureDisp** ' ı seçin <strong>\*</strong> .

1. **Uygulama türü** Için, **get/set yöntemleri**' ne tıklayın.

1. Get ve set işlevleriniz için benzersiz adlar yazın veya varsayılan adları kabul edin. (Bu örnekte, varsayılan adları `GetControlPicture` ve `SetControlPicture` kullanılır.)

1. **Finish (Son)** düğmesine tıklayın.

Özellik Ekleme Sihirbazı, denetim üstbilgisindeki dağıtım Haritası açıklamaları arasına aşağıdaki kodu ekler (. H) dosyası:

[!code-cpp[NVC_MFC_AxPic#4](codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_4.h)]

Ayrıca, aşağıdaki kod denetim uygulamasının dağıtım eşlemesine eklenmiştir (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxPic#5](codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_5.cpp)]

Özellik Ekleme Sihirbazı ayrıca denetim uygulama dosyasında aşağıdaki iki saplama işlevini de ekler:

[!code-cpp[NVC_MFC_AxPic#6](codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_6.cpp)]

> [!NOTE]
> Denetim sınıfınız ve işlev adlarınızı Yukarıdaki örnekte farklılık gösterebilir.

### <a name="modifications-to-your-control-project"></a><a name="_core_modifications_to_your_control_project"></a> Denetim projenizde yapılan değişiklikler

Denetim projenize gerekli eklemeleri yaptıktan sonra, ActiveX denetiminizi işlemeyi etkileyen birkaç işlevi değiştirmeniz gerekir. Bu işlevler, `OnResetState` , `OnDraw` ve özel resim özelliğinin Get/Set işlevleri denetim uygulama dosyasında bulunur. (Bu örnekte denetim sınıfı çağrılır `CSampleCtrl` , `CPictureHolder` veri üyesine *m_pic* denir ve özel resim özelliği adı olduğunu unutmayın `ControlPicture` .)

Denetim `OnResetState` işlevinde, öğesine yapılan çağrıdan sonra aşağıdaki isteğe bağlı satırı ekleyin `COleControl::OnResetState` :

[!code-cpp[NVC_MFC_AxPic#7](codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_7.cpp)]

Bu, denetimin resmini boş bir resme ayarlar.

Resmi düzgün bir şekilde çizmek için denetim işlevindeki [Cpicturetutucusu:: Render](reference/cpictureholder-class.md#render) öğesine bir çağrı yapın `OnDraw` . İşlevinizi aşağıdaki örneğe benzer şekilde değiştirin:

[!code-cpp[NVC_MFC_AxPic#8](codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_8.cpp)]

Denetimin özel resim özelliğinin al işlevinde aşağıdaki satırı ekleyin:

[!code-cpp[NVC_MFC_AxPic#9](codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_9.cpp)]

Denetimin özel resim özelliğinin ayarla işlevinde aşağıdaki satırları ekleyin:

[!code-cpp[NVC_MFC_AxPic#10](codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_10.cpp)]

Tasarım zamanında eklenen bilgilerin çalışma zamanında görünmesi için resim özelliği kalıcı yapılmalıdır. Aşağıdaki satırı, `COleControl` -türetilmiş sınıfın `DoPropExchange` işlevine ekleyin:

[!code-cpp[NVC_MFC_AxPic#11](codesnippet/cpp/mfc-activex-controls-using-pictures-in-an-activex-control_11.cpp)]

> [!NOTE]
> Sınıfınız ve işlev adlarınızı Yukarıdaki örnekte farklılık gösterebilir.

Değişiklikleri tamamladıktan sonra, özel resim özelliğinin yeni işlevlerini eklemek için projenizi yeniden derleyin ve yeni özelliği test etmek için test kapsayıcısını kullanın. Test kapsayıcısına erişme hakkında bilgi için bkz. test [kapsayıcı Ile özellikleri ve olayları test etme](testing-properties-and-events-with-test-container.md) .

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)<br/>
[MFC ActiveX denetimleri: yazı tiplerini kullanma](mfc-activex-controls-using-fonts.md)<br/>
[MFC ActiveX denetimleri: Özellik sayfaları](mfc-activex-controls-property-pages.md)
