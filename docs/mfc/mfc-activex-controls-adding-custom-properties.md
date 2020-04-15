---
title: 'MFC ActiveX Denetimleri: Özel Özellikler Ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], properties
- properties [MFC], custom
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
ms.openlocfilehash: 00f7a879582bca562ce626fe224206094fd19bc7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364698"
---
# <a name="mfc-activex-controls-adding-custom-properties"></a>MFC ActiveX Denetimleri: Özel Özellikler Ekleme

Özel özellikler, özel özelliklerizaten `COleControl` sınıf tarafından uygulanmamış stok özellikleri farklıdır. Özel bir özellik, denetimi kullanan bir programcıya activex denetiminin belirli bir durumunu veya görünümünü ortaya çıkarmak için kullanılır.

Bu makalede, Özellik Ekle Sihirbazı'nı kullanarak ActiveX denetimine özel bir özellik nasıl ekleyeceğiniz açıklanır ve ortaya çıkan kod değişikliklerini açıklar. Konu başlıkları şunlardır:

- [Özel bir özellik eklemek için Özellik Ekle Sihirbazı'nı kullanma](#_core_using_classwizard_to_add_a_custom_property)

- [Özel özellikler için Özellik Sihirbazı değişiklikleri ekleme](#_core_classwizard_changes_for_custom_properties)

Özel özellikler dört çeşit uygulama da gelir: Üye Değişken, Bildirimli Üye Değişken, Alma/Ayarla Yöntemleri ve Parametreli.

- Üye Değişken Uygulaması

   Bu uygulama, denetim sınıfında bir üye değişken olarak özelliğin durumunu temsil eder. Özellik değerinin ne zaman değiştiğini bilmek önemli değilse Üye Değişken uygulamasını kullanın. Üç tür, bu uygulama özelliği için destek kodu en az miktarda oluşturur. Üye değişken uygulaması için sevk haritası giriş [makrosu DISP_PROPERTY.](../mfc/reference/dispatch-maps.md#disp_property)

- Bildirim Uygulaması ile Üye Değişkeni

   Bu uygulama, bir üye değişken ve Özellik Ekle Sihirbazı tarafından oluşturulan bir bildirim işlevi oluşur. Bildirim işlevi, özellik değeri değiştikten sonra çerçeve tarafından otomatik olarak çağrılır. Bir özellik değeri değiştikten sonra bildirimde bulunulması gerektiğinde Bildirim uygulaması ile Üye Değişkenini kullanın. Bir işlev çağrısı gerektirdiğinden, bu uygulama daha fazla zaman gerektirir. Bu uygulama için sevk haritası giriş [makrosu DISP_PROPERTY_NOTIFY.](../mfc/reference/dispatch-maps.md#disp_property_notify)

- Alma/Ayarlama Yöntemleri Uygulaması

   Bu uygulama, denetim sınıfındaki bir çift üye işlevden oluşur. Yöntemleri Al/Ayarla uygulaması, denetimin kullanıcısı mülkün geçerli değerini ve denetimin kullanıcısı özelliğin değiştirilmesini istediğinde Set üye işlevini istediğinde üye al işlevini otomatik olarak çağırır. Çalışma süresi boyunca bir özelliğin değerini hesaplamanız, gerçek özelliği değiştirmeden önce denetim kullanıcısı tarafından geçirilen bir değeri doğrulamanız veya salt okunur veya yazma özelliği türünü uygulamanız gerektiğinde bu uygulamayı kullanın. Bu uygulama için sevk haritası giriş [makrosu DISP_PROPERTY_EX.](../mfc/reference/dispatch-maps.md#disp_property_ex) Aşağıdaki bölümde, [Özel Özellik Eklemek için Özellik Ekle Sihirbazı'nı kullanarak,](#_core_using_classwizard_to_add_a_custom_property)bu uygulamayı göstermek için CircleOffset özel özelliğini kullanır.

- Parametreli Uygulama

   Parametreli uygulama Özellik Ekle Sihirbazı tarafından desteklenir. Parametrelendirilmiş bir özellik (bazen özellik dizisi olarak da adlandırılır), denetiminizin tek bir özelliği aracılığıyla bir değer kümesine erişmek için kullanılabilir. Bu uygulama için sevk haritası giriş makrosu DISP_PROPERTY_PARAM. Bu tür uygulama hakkında daha fazla bilgi için ActiveX Denetimleri: Gelişmiş Konular makalesinde [Parametreli Bir Özellik Uygulama](../mfc/mfc-activex-controls-advanced-topics.md) konusuna bakın.

## <a name="using-the-add-property-wizard-to-add-a-custom-property"></a><a name="_core_using_classwizard_to_add_a_custom_property"></a>Özel Özellik Eklemek Için Özellik Ekle Sihirbazı'nı Kullanma

Aşağıdaki yordam, Get/Set Metodları uygulamasını kullanan özel bir özellik olan CircleOffset'in eklenmesini gösterir. CircleOffset özel özelliği, denetimin kullanıcısının daireyi denetimin sınırlayıcı dikdörtgeninin ortasından dengelemesine olanak tanır. Get/Set Yöntemleri dışında bir uygulama ile özel özellikler ekleme yordamı çok benzer.

Aynı yordam, istediğiniz diğer özel özellikleri eklemek için de kullanılabilir. Özel özellik adınızı CircleOffset özellik adı ve parametreleri ile değiştirin.

#### <a name="to-add-the-circleoffset-custom-property-using-the-add-property-wizard"></a>Özellik Ekle Sihirbazı'nı kullanarak CircleOffset özel özelliğini eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü'nde, denetiminizin kitaplık düğümunu genişletin.

1. Kısayol menüsünü açmak için denetiminiz için arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünden **Ekle'yi** tıklatın ve ardından **Özellik Ekle'yi**tıklatın.

   Bu Özellik [Ekle Sihirbazı'nı](../ide/names-add-property-wizard.md)açar.

1. Özellik **Adı** kutusuna *CircleOffset*yazın.

1. **Uygulama Türü** **için, Yöntemleri Al/Ayarla'yı**tıklatın.

1. Özellik **Türü** kutusunda, **kısa'yı**seçin.

1. İşlevleri Al ve Ayarla'nız için benzersiz adlar yazın veya varsayılan adları kabul edin.

1. **Son**'a tıklayın.

## <a name="add-property-wizard-changes-for-custom-properties"></a><a name="_core_classwizard_changes_for_custom_properties"></a>Özel Özellikler için Özellik Sihirbazı Değişiklikleri Ekleme

CircleOffset özel özelliğini eklediğinizde, Özellik Ekle Sihirbazı üstbilgide değişiklik yapar (. H) ve uygulama (. CPP) denetim sınıfının dosyaları.

Aşağıdaki satırlar eklenir. H dosyası adlı `GetCircleOffset` iki `SetCircleOffset`işlevi bildirmek için ve:

[!code-cpp[NVC_MFC_AxUI#25](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_1.h)]

Aşağıdaki satır denetiminizin. IDL dosyası:

[!code-cpp[NVC_MFC_AxUI#26](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_2.idl)]

Bu satır, CircleOffset özelliğine, metnin özellik ekle sihirbazı yöntemleri ve özellikleri listesindeyöntem konumundan alınan belirli bir kimlik numarası atar.

Buna ek olarak, aşağıdaki satır gönderme haritasına eklenir (. Kontrol sınıfının CPP dosyası) CircleOffset özelliğini denetimin iki işleyici işleviyle eşlemek için:

[!code-cpp[NVC_MFC_AxUI#27](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_3.cpp)]

Son olarak, ve `GetCircleOffset` `SetCircleOffset` işlevlerin uygulamaları denetimin sonuna eklenir. CPP dosyası. Çoğu durumda, özelliğin değerini döndürmek için Get işlevini değiştirirsiniz. Set işlevi genellikle özellik değişmeden önce veya sonra yürütülmesi gereken kod içerir.

[!code-cpp[NVC_MFC_AxUI#28](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_4.cpp)]

Özellik Ekle Sihirbazı'nın [SetModifiedFlag'a](../mfc/reference/colecontrol-class.md#setmodifiedflag), Set işlevinin gövdesine otomatik olarak bir çağrı ekleyeceğini unutmayın. Bu işlevi çağırmak denetimi değiştirilmiş olarak işaretler. Denetim değiştirildiyse, kapsayıcı kaydedildiğinde yeni durumu kaydedilir. Bu işlev, denetimin kalıcı durumunun bir parçası olarak kaydedilen bir özellik değeri değiştirdiğinde çağrılmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: Özellikler](../mfc/mfc-activex-controls-properties.md)<br/>
[MFC ActiveX Denetimleri: Yöntemler](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl Sınıfı](../mfc/reference/colecontrol-class.md)
