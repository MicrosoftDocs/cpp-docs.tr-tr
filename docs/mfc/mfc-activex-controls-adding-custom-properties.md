---
title: 'MFC ActiveX denetimleri: Özel özellikler ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], properties
- properties [MFC], custom
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98cf8a0532c3b1f2044ba0338d3f2f2bf8e73813
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390995"
---
# <a name="mfc-activex-controls-adding-custom-properties"></a>MFC ActiveX Denetimleri: Özel Özellikler Ekleme

Özel özellikler stok özelliklerini içeren özel özellikler tarafından zaten uygulanmadı farklı `COleControl` sınıfı. Özel bir özellik, belirli bir durumu veya bir ActiveX denetimine denetimini kullanarak Programcı görünümünü göstermek için kullanılır.

Bu makalede, Özellik Ekleme Sihirbazı'nı kullanarak bir ActiveX denetimi için bir özel özellik ekleyeceğinizi açıklar ve sonuçta elde edilen kod değişikliklerini açıklar. Konular şunlardır:

- [Özel bir özellik eklemek için Özellik Ekleme Sihirbazı'nı kullanma](#_core_using_classwizard_to_add_a_custom_property)

- [Özel özellikler için özellik Sihirbazı değişiklikleri ekleyin](#_core_classwizard_changes_for_custom_properties)

Özel özellikler gelen uygulama dört çeşitleri: üye değişkeni, üye değişken bildirimi, Get/Set yöntemleri ve Parameterized.

- Üye değişkeni uygulama

     Bu uygulama, bir üye değişkeni denetimi sınıfında özelliğin durumunu temsil eder. Üye değişkeni uygulama özellik değeri değiştiğinde bilmek önemli olmadığı durumlarda kullanın. Üç tür, bu uygulama, en az bir özellik için destek kodunu oluşturur. Üye değişkeni uygulama gönderme eşleme girişi makro [dısp_property](../mfc/reference/dispatch-maps.md#disp_property).

- Üye değişkeni bildirimi uygulama

     Bu uygulama bir üye değişkeni ve Özellik Ekleme Sihirbazı tarafından oluşturulan bir bildirim işlevini oluşur. Bildirim işlevi, sonra özellik değeri değiştiğinde framework tarafından otomatik olarak çağrılır. Üye değişkeni, bir özellik değeri değiştikten sonra bildirilmesi gerektiğinde bildirim uygulamasıyla kullanın. Bu uygulama, bir işlev çağrısı gerektirdiğinden daha uzun sürer. Bu uygulama için gönderme eşleme girişi makro [dısp_property_notıfy](../mfc/reference/dispatch-maps.md#disp_property_notify).

- Get/Set yöntemleri uygulaması

     Bu uygulama denetim sınıf üyesi işlevleri bir çiftinden oluşur. Denetimin kullanıcı özelliği değiştirilmesi istediğinde Get/Set yöntemleri uygulaması denetimin kullanıcı özelliğinin geçerli değeri istediğinde işlevi ve kümesi üye işlevi otomatik olarak Get üyeyi çağırır. Bu uygulama, çalışma zamanı sırasında bir özelliğin değerini hesaplamak için gerçek özellik değiştirmeden önce denetimin kullanıcı tarafından geçirilen bir değeri doğrulamak veya okuma - veya salt yazılır özellik türü uygulama kullanın. Bu uygulama için gönderme eşleme girişi makro [dısp_property_ex](../mfc/reference/dispatch-maps.md#disp_property_ex). Aşağıdaki bölümde [özel bir özellik eklemek için Özellik Ekleme Sihirbazı'nı kullanarak](#_core_using_classwizard_to_add_a_custom_property), CircleOffset özel özellik bu uygulama göstermek için kullanır.

- Parametreli uygulama

     Parametreli uygulama Özellik Ekleme Sihirbazı tarafından desteklenir. Bir parametreli özelliği (özellik dizisi olarak da adlandırılır), bir değerler kümesi tek bir denetim özelliği üzerinden erişmek için kullanılabilir. Bu uygulama için dağıtım eşleme girişi makrosu dısp_property_param ' dir. Bu tür uygulama konusunda daha fazla bilgi için bkz. [uygulayan bir parametreli özellik](../mfc/mfc-activex-controls-advanced-topics.md) makalede ActiveX denetimleri: Gelişmiş Konular.

##  <a name="_core_using_classwizard_to_add_a_custom_property"></a> Kullanarak özel bir özellik eklemek için Özellik Ekleme Sihirbazı

Aşağıdaki yordam, özel bir özellik Get/Set yöntemleri uygulaması kullanan CircleOffset ekleme göstermektedir. Denetimin denetimin sınırlayıcı dikdörtgeni ortasından daire uzaklığı kullanıcıya CircleOffset özel özellik sağlar. Get/Set yöntemleri dışında bir uygulama ile özel özellikler ekleme yordamı çok benzer.

Bu yordamı, istediğiniz diğer özel özelliklerini eklemek için de kullanılabilir. Özel özellik adınızı CircleOffset özellik adı ve parametreler için değiştirin.

#### <a name="to-add-the-circleoffset-custom-property-using-the-add-property-wizard"></a>Özellik Ekleme Sihirbazı'nı kullanarak CircleOffset özel özellik eklemek için

1. Denetiminizin proje yükleyin.

1. Sınıf Görünümü'nde denetim kitaplığı düğümünü genişletin.

1. Arabirim (ikinci düğüm kitaplığı düğümünün) denetlemek için kısayol menüsünü açmak için düğümü.

1. Kısayol menüsünden tıklayın **Ekle** ve ardından **Özellik Ekle**.

     Bu açılır [Özellik Ekleme Sihirbazı'nı](../ide/names-add-property-wizard.md).

1. İçinde **özellik adı** kutusuna *CircleOffset*.

1. İçin **uygulama türü**, tıklayın **Get/Set yöntemleri**.

1. İçinde **özellik türü** kutusunda **kısa**.

1. Get ve işlevler kümesi için benzersiz adlar yazın veya varsayılan adı kabul edin.

9. **Son**'a tıklayın.

##  <a name="_core_classwizard_changes_for_custom_properties"></a> Özellik Sihirbazı değişiklikleri için özel özellikler ekleme

Özellik Ekleme Sihirbazı'nı CircleOffset özel özellik eklediğinizde, üst değişiklikleri yapar (. H) ve uygulama (. Denetim sınıf CPP) dosyaları.

Aşağıdaki satırları eklenir. Adlı iki işlevi bildirmek için H dosya `GetCircleOffset` ve `SetCircleOffset`:

[!code-cpp[NVC_MFC_AxUI#25](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_1.h)]

Aşağıdaki satırı, denetimin eklenir. IDL dosyası:

[!code-cpp[NVC_MFC_AxUI#26](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_2.idl)]

Bu satırı CircleOffset özelliği yöntemin konumundan Özellik Ekleme Sihirbazı'nı yöntemler ve özellikler listesinde gerçekleştirilen belirli bir kimlik numarası atar.

Ayrıca, aşağıdaki satırı gönderme eşlemesine eklenen (içinde. CPP dosyasına denetim sınıf) denetimin iki işleyici işlevleri CircleOffset özelliğini eşleştirmek için:

[!code-cpp[NVC_MFC_AxUI#27](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_3.cpp)]

Son olarak, uygulamaları `GetCircleOffset` ve `SetCircleOffset` işlevleri, denetimin sonuna eklenir. CPP dosyasına. Çoğu durumda Get işlevi özelliğinin değerini döndürecek şekilde değiştirir. Set işlevi genellikle önce veya sonra özellik değişikliklerinin yürütülmesi gereken kodu içerir.

[!code-cpp[NVC_MFC_AxUI#28](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_4.cpp)]

Özellik Ekleme Sihirbazı'nı otomatik olarak bir çağrı çok dikkat edin [SetModifiedFlag](../mfc/reference/colecontrol-class.md#setmodifiedflag), kümesi işlevinin gövdesi için. Bu işlev çağırma denetimi değiştirilmiş olarak işaretlenir. Bir denetim değiştirilmişse, yeni durumuna kapsayıcı kaydedildiğinde kaydedilir. Bu işlev, denetimin kalıcı durum bir parçası olarak kaydedilmiş bir özellik değeri değiştiğinde çağrılmalıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: Özellikler](../mfc/mfc-activex-controls-properties.md)<br/>
[MFC ActiveX Denetimleri: Yöntemler](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl Sınıfı](../mfc/reference/colecontrol-class.md)
