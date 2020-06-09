---
title: 'MFC ActiveX Denetimleri: Özel Olaylar Ekleme'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], events [MFC]
- EVENT_CUSTOM prefix [MFC]
- custom events [MFC], adding to ActiveX controls
- EVENT_CUSTOM macro [MFC]
- InCircle method [MFC]
- ClickIn event
- FireClickIn event
- COleControl class [MFC], custom events [MFC]
- Click event, custom events [MFC]
- events [MFC], ActiveX controls
- custom events [MFC]
- FireEvent method, adding custom events
ms.assetid: c584d053-1e34-47aa-958e-37d3e9b85892
ms.openlocfilehash: 70b0e08bc638b5f630d423ec0db8a169a0119175
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619946"
---
# <a name="mfc-activex-controls-adding-custom-events"></a>MFC ActiveX Denetimleri: Özel Olaylar Ekleme

Özel olaylar, otomatik olarak sınıf tarafından tetiklendikleri için stok olaylarından farklıdır `COleControl` . Özel bir olay, denetim geliştiricisi tarafından bir olay olarak belirlenen belirli bir eylemi algılar. Özel olaylara yönelik olay eşlemesi girdileri EVENT_CUSTOM makro tarafından temsil edilir. Aşağıdaki bölüm, ActiveX Denetim Sihirbazı kullanılarak oluşturulan bir ActiveX denetim projesi için özel bir olay uygular.

## <a name="adding-a-custom-event-with-the-add-event-wizard"></a><a name="_core_adding_a_custom_event_with_classwizard"></a>Olay Ekleme Sihirbazı ile özel olay ekleme

Aşağıdaki yordam belirli bir özel olay ekler ve sonra da. Diğer özel olayları eklemek için bu yordamı kullanabilirsiniz. Özel olay adınızı ve parametrelerini, Click olay adı ve parametreleri için değiştirin.

#### <a name="to-add-the-clickin-custom-event-using-the-add-event-wizard"></a>Olay Ekleme Sihirbazı 'Nı kullanarak Click özel olayını eklemek için

1. Denetiminizin projesini yükleyin.

1. **Sınıf görünümü**menüsünde, ActiveX denetim sınıfınızı sağ tıklayıp kısayol menüsünü açın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **olay Ekle**' ye tıklayın.

   Bu, olay Ekleme Sihirbazı ' nı açar.

1. **Olay adı** kutusunda, önce var olan herhangi bir olayı seçin, sonra **özel** radyo düğmesine tıklayın ve ardından ENTER tuşuna basın *.*

1. **İç ad** kutusunda, etkinliğin tetikleme işlevinin adını yazın. Bu örnek için, olay Ekleme Sihirbazı () tarafından sunulan varsayılan değeri kullanın `FireClickIn` .

1. **Parametre adı** ve **parametre türü** denetimlerini kullanarak *xcozı* (tür *OLE_XPOS_PIXELS*) adlı bir parametre ekleyin.

1. İkinci bir parametre *ekleyin (tür* *OLE_YPOS_PIXELS*).

1. Olayı oluşturmak için **son** ' a tıklayın.

## <a name="add-event-wizard-changes-for-custom-events"></a><a name="_core_classwizard_changes_for_custom_events"></a>Özel olaylar için olay Sihirbazı değişiklikleri ekleme

Özel bir olay eklediğinizde, olay Ekleme Sihirbazı denetim sınıfında değişiklikler yapar. H,. CPP ve. IDL dosyaları. Aşağıdaki kod örnekleri, Click olayına özeldir.

Üst bilgiye aşağıdaki satırlar eklenir (. H) denetim sınıfınızın dosyası:

[!code-cpp[NVC_MFC_AxUI#7](codesnippet/cpp/mfc-activex-controls-adding-custom-events_1.h)]

Bu kod, `FireClickIn` olay Ekleme Sihirbazı 'nı kullanarak tanımladığınız Click olayı ve parametreleri Ile [Cotacontrol:: FireEvent](reference/colecontrol-class.md#fireevent) çağıran adlı bir satır içi işlev bildirir.

Ayrıca, uygulamada bulunan denetim için olay haritasına aşağıdaki satır eklenir (. CPP) denetim sınıfınızın dosyası:

[!code-cpp[NVC_MFC_AxUI#8](codesnippet/cpp/mfc-activex-controls-adding-custom-events_2.cpp)]

Bu kod, olay `FireClickIn` Ekle Sihirbazı ' nı kullanarak tanımladığınız parametreleri geçirerek, olayı satır içi işlev ile eşler.

Son olarak, aşağıdaki satır denetiminizin öğesine eklenir. IDL dosyası:

[!code-cpp[NVC_MFC_AxUI#9](codesnippet/cpp/mfc-activex-controls-adding-custom-events_3.idl)]

Bu satır, olay Ekle Sihirbazı olay listesi ' nde olayın konumundan alınan belirli bir KIMLIK numarası olan Click olayını atar. Olay listesindeki giriş, bir kapsayıcının olayı tahmin etmesine izin verir. Örneğin, olay harekete geçirildiğinde yürütülecek işleyici kodu sağlayabilir.

## <a name="calling-fireclickin"></a><a name="_core_calling_fireclickin"></a>Firei 'yi çağırma

Olay Ekleme Sihirbazı 'nı kullanarak ister özel olayını ekletireceğinize göre, bu olayın ne zaman tetiklendiğine karar vermelisiniz. Bunu `FireClickIn` , uygun eylem gerçekleştiğinde çağırarak yapabilirsiniz. Bu tartışma için denetim, bir `InCircle` `WM_LBUTTONDOWN` Kullanıcı dairesel veya eliptik bir bölgenin içini tıklattığında, bu olayı bir ileti işleyicisi içinde kullanır. Aşağıdaki yordam `WM_LBUTTONDOWN` işleyiciyi ekler.

#### <a name="to-add-a-message-handler-with-the-add-event-wizard"></a>Olay Ekleme Sihirbazı ile bir ileti işleyicisi eklemek için

1. Denetiminizin projesini yükleyin.

1. **Sınıf görünümü**' de, ActiveX denetim sınıfınızı seçin.

1. **Özellikler** penceresinde, ActiveX denetimi tarafından işlenebilen iletilerin bir listesini görürsünüz. Kalın olarak gösterilen herhangi bir ileti zaten kendisine atanmış bir işleyici işlevi içerir.

1. İşlemek istediğiniz iletiyi seçin. Bu örnek için, öğesini seçin `WM_LBUTTONDOWN` .

1. Sağdaki aşağı açılan liste kutusundan ** \<Add> onlbuttonlist**' i seçin.

1. Uygulamadaki ileti işleyici koduna geçmek için **sınıf görünümü** yeni işleyici işlevine çift tıklayın (. CPP) dosyası.

Aşağıdaki kod örneği, `InCircle` sol fare düğmesine denetim penceresi içinde tıklandığı her seferinde işlevini çağırır. Bu örnek, `WM_LBUTTONDOWN` `OnLButtonDown` [Circ örnek](../overview/visual-cpp-samples.md) soyut öğesinde, işleyici işlevinde bulunabilir.

[!code-cpp[NVC_MFC_AxUI#10](codesnippet/cpp/mfc-activex-controls-adding-custom-events_4.cpp)]

> [!NOTE]
> Olay Ekleme Sihirbazı fare düğmesi eylemleri için ileti işleyicileri oluşturduğunda, temel sınıfın aynı ileti işleyicisine yönelik bir çağrı otomatik olarak eklenir. Bu çağrıyı kaldırmayın. Denetiminiz, hisse senedi fare mesajlarının herhangi birini kullanıyorsa, fare yakalamanın düzgün şekilde işlendiğinden emin olmak için temel sınıftaki ileti işleyicileri çağrılmalıdır.

Aşağıdaki örnekte, olay yalnızca tıklama denetimin içindeki bir dairesel veya eliptik bölge içinde gerçekleştiğinde ateşlenir. Bu davranışı başarmak için, `InCircle` işlevini denetimin uygulamasına yerleştirebilirsiniz (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxUI#11](codesnippet/cpp/mfc-activex-controls-adding-custom-events_5.cpp)]

Ayrıca, denetimin üstbilgisine () işlevin aşağıdaki bildirimini eklemeniz gerekir `InCircle` (. H) dosyası:

[!code-cpp[NVC_MFC_AxUI#12](codesnippet/cpp/mfc-activex-controls-adding-custom-events_6.h)]

## <a name="custom-events-with-stock-names"></a><a name="_core_custom_events_with_stock_names"></a>Hisse senedi adlarıyla özel olaylar

Hisse senedi olaylarıyla aynı ada sahip özel olaylar oluşturabilirsiniz, ancak her ikisini de aynı denetimde uygulayamamalıdır. Örneğin, bir özel olay oluşturmak isteyebilirsiniz. Bu, stok olayı tıklaması normalde başlatıldığında harekete geçmeyecektir. Ardından, tetikleme işlevini çağırarak istediğiniz zaman Click olayını tetikleyerek yapabilirsiniz.

Aşağıdaki yordam özel bir tıklama olayı ekler.

#### <a name="to-add-a-custom-event-that-uses-a-stock-event-name"></a>Hisse senedi olay adı kullanan özel bir olay eklemek için

1. Denetiminizin projesini yükleyin.

1. **Sınıf görünümü**menüsünde, ActiveX denetim sınıfınızı sağ tıklayıp kısayol menüsünü açın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **olay Ekle**' ye tıklayın.

   Bu, olay Ekleme Sihirbazı ' nı açar.

1. **Olay adı** açılır listesinde bir stok olay adı seçin. Bu örnek için **tıklama ' yi**seçin.

1. **Olay türü**için **özel**' i seçin.

1. Olayı oluşturmak için **son** ' a tıklayın.

1. `FireClick`Kodunuzda uygun yerlere çağrı yapın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: Yöntemler](mfc-activex-controls-methods.md)<br/>
[Coelcontrol sınıfı](reference/colecontrol-class.md)
