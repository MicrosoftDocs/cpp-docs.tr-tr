---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: özel özellikler ekleme'
title: 'MFC ActiveX Denetimleri: Özel Özellikler Ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], properties
- properties [MFC], custom
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
ms.openlocfilehash: efae1c7cedc2202a2a40974393be881466442b84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202944"
---
# <a name="mfc-activex-controls-adding-custom-properties"></a>MFC ActiveX Denetimleri: Özel Özellikler Ekleme

Özel özellikler, sınıf tarafından zaten uygulanmamış olan özel özellikler stok özelliklerinden farklıdır `COleControl` . Özel bir özellik, bir ActiveX denetiminin belirli bir durumunu veya görünümünü, bu denetimi kullanarak bir programcıya göstermek için kullanılır.

Bu makalede, Özellik Ekleme Sihirbazı kullanılarak ActiveX denetimine nasıl özel bir özellik ekleneceği ve sonuçta elde edilen kod değişiklikleri açıklanmaktadır. Konu başlıkları şunlardır:

- [Özel özellik eklemek için Özellik Ekleme Sihirbazı 'Nı kullanma](#_core_using_classwizard_to_add_a_custom_property)

- [Özel özellikler için Özellik Ekleme Sihirbazı değişiklikleri](#_core_classwizard_changes_for_custom_properties)

Özel özellikler, uygulama değişkeni, bildirim içeren üye değişkeni, get/set yöntemleri ve Parametreleştirme gibi dört tür uygulamaya gelir.

- Üye değişkeni uygulama

   Bu uygulama, özelliğin durumunu denetim sınıfındaki üye değişkeni olarak temsil eder. Özellik değerinin ne zaman değişeceğimizi bilmemiz için önemli olmadığında üye değişkeni uygulamasını kullanın. Bu uygulama, üç türden özellik için en az destek kodu oluşturur. Üye değişkeni uygulamasına ait dağıtım Haritası giriş makrosu [DISP_PROPERTY](reference/dispatch-maps.md#disp_property).

- Bildirim uygulamasıyla üye değişkeni

   Bu uygulama bir üye değişkeni ve Özellik Ekleme Sihirbazı tarafından oluşturulan bir bildirim işlevinden oluşur. Bildirim işlevi, özellik değeri değiştirildikten sonra otomatik olarak Framework tarafından çağırılır. Bir özellik değeri değiştirildikten sonra bildirilmesi gerektiğinde bildirim uygulamasıyla üye değişkenini kullanın. Bu uygulama, bir işlev çağrısı gerektirdiğinden daha fazla zaman gerektirir. Bu uygulama için dağıtım Haritası giriş makrosu [DISP_PROPERTY_NOTIFY](reference/dispatch-maps.md#disp_property_notify).

- Yöntem uygulamasını al/ayarla

   Bu uygulama, denetim sınıfındaki bir dizi üye işlevden oluşur. Get/set yöntemleri, denetimin kullanıcı özelliğin geçerli değerini istediğinde ve denetimin kullanıcısı özelliğin değiştirilmesini istediğinde üye işlevini ayarla işlevini otomatik olarak çağırır. Çalışma zamanı sırasında bir özelliğin değerini hesaplamanız gerektiğinde, gerçek özelliği değiştirmeden önce denetimin kullanıcısı tarafından geçirilen bir değeri doğrulamak veya bir salt yazılır özellik türü uygulamak için bu uygulamayı kullanın. Bu uygulama için dağıtım Haritası giriş makrosu [DISP_PROPERTY_EX](reference/dispatch-maps.md#disp_property_ex). Aşağıdaki bölümde, [özel bir özellik eklemek Için Özellik Ekleme Sihirbazı kullanılarak](#_core_using_classwizard_to_add_a_custom_property), bu uygulamayı göstermek Için circlesapmasını Custom özelliği kullanılır.

- Parametreli uygulama

   Parametreli uygulama Özellik Ekleme Sihirbazı tarafından desteklenir. Parametreli bir Özellik (bazen Özellik dizisi olarak adlandırılır), denetiminizin tek bir özelliği aracılığıyla bir dizi değere erişmek için kullanılabilir. Bu uygulama için dağıtım Haritası giriş makrosu DISP_PROPERTY_PARAM. Bu türü uygulama hakkında daha fazla bilgi için bkz. ActiveX denetimleri: gelişmiş konular makalesindeki [parametreli özellik uygulama](mfc-activex-controls-advanced-topics.md) .

## <a name="using-the-add-property-wizard-to-add-a-custom-property"></a><a name="_core_using_classwizard_to_add_a_custom_property"></a> Özel özellik eklemek için Özellik Ekleme Sihirbazı 'Nı kullanma

Aşağıdaki yordamda, get/set yöntemleri uygulamasını kullanan bir özel özellik, Circlesapmayı ekleme gösterilmektedir. Circlesapmayı Custom özelliği, denetimin kullanıcı tarafından denetimin sınırlayıcı dikdörtgeninin merkezinden daireyi kaydırmasına olanak tanır. Get/set yöntemleri dışında bir uygulamayla özel özellikler ekleme yordamı çok benzerdir.

Bu yordam, istediğiniz diğer özel özellikleri eklemek için de kullanılabilir. Circlesapmayı Özellik adı ve parametreleri için özel özellik adınızı değiştirin.

#### <a name="to-add-the-circleoffset-custom-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı 'nı kullanarak Circlesapmayı özel özelliğini eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü, denetiminizin kitaplık düğümünü genişletin.

1. Kısayol menüsünü açmak için denetiminizin arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **Özellik Ekle**' ye tıklayın.

   Bu, [Özellik Ekleme Sihirbazı](../ide/adding-a-property-visual-cpp.md#names-add-property-wizard)' nı açar.

1. **Özellik adı** kutusuna *circlekayması* yazın.

1. **Uygulama türü** Için, **get/set yöntemleri**' ne tıklayın.

1. **Özellik türü** kutusunda, öğesini seçin **`short`** .

1. Get ve set işlevleriniz için benzersiz adlar yazın veya varsayılan adları kabul edin.

1. **Finish (Son)** düğmesine tıklayın.

## <a name="add-property-wizard-changes-for-custom-properties"></a><a name="_core_classwizard_changes_for_custom_properties"></a> Özel özellikler için Özellik Ekleme Sihirbazı değişiklikleri

Circlesapmasını özel özelliğini eklediğinizde Özellik Ekleme Sihirbazı üst bilgide değişiklik yapar (. H) ve uygulama (. CPP) denetim sınıfının dosyaları.

Aşağıdaki satırlar öğesine eklenir. H dosyası ve olarak adlandırılan iki işlevi `GetCircleOffset` bildirir `SetCircleOffset` :

[!code-cpp[NVC_MFC_AxUI#25](codesnippet/cpp/mfc-activex-controls-adding-custom-properties_1.h)]

Aşağıdaki satır, denetiminizin öğesine eklenir. IDL dosyası:

[!code-cpp[NVC_MFC_AxUI#26](codesnippet/cpp/mfc-activex-controls-adding-custom-properties_2.idl)]

Bu satır, Özellik Ekle sihirbazının Yöntemler ve Özellikler listesindeki konumundan alınan Circlesapmayı özelliğine belirli bir KIMLIK numarası atar.

Ayrıca, aşağıdaki satır dağıtım haritasına eklenir (içinde. Denetim sınıfının CPP dosyası), Circlesapmayı özelliğini denetimin iki işleyici işlevleriyle eşlemek için:

[!code-cpp[NVC_MFC_AxUI#27](codesnippet/cpp/mfc-activex-controls-adding-custom-properties_3.cpp)]

Son olarak, `GetCircleOffset` ve `SetCircleOffset` işlevlerinin uygulamaları denetimin sonuna eklenir. CPP dosyası. Çoğu durumda, özelliğin değerini döndürmek için Get işlevini değiştirirsiniz. Set işlevi, genellikle, özellik değişikliklerinden önce veya sonra yürütülmesi gereken kodu içerir.

[!code-cpp[NVC_MFC_AxUI#28](codesnippet/cpp/mfc-activex-controls-adding-custom-properties_4.cpp)]

Özellik Ekle sihirbazının, set işlevinin gövdesine otomatik olarak [SetModifiedFlag](reference/colecontrol-class.md#setmodifiedflag)öğesine bir çağrı ekleyeceğini unutmayın. Bu işlevi çağırmak, denetimi değiştirilmiş olarak işaretler. Bir denetim değiştirilmişse, kapsayıcı kaydedildiğinde yeni durumu kaydedilir. Bu işlev, denetimin kalıcı durumunun bir parçası olarak kaydedildiği her bir özellik, değiştiğinde değeri olarak çağrılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)<br/>
[MFC ActiveX denetimleri: Özellikler](mfc-activex-controls-properties.md)<br/>
[MFC ActiveX denetimleri: Yöntemler](mfc-activex-controls-methods.md)<br/>
[Coelcontrol sınıfı](reference/colecontrol-class.md)
