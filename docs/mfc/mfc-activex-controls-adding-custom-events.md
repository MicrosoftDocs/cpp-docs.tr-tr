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
ms.openlocfilehash: 8d464e5d7c9731e158e44d66d569fd1555401e17
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364724"
---
# <a name="mfc-activex-controls-adding-custom-events"></a>MFC ActiveX Denetimleri: Özel Olaylar Ekleme

Özel olaylar, sınıfa `COleControl`göre otomatik olarak ateşlendirilmeyecek şekilde stok olaylarından farklıdır. Özel bir olay, denetim geliştiricisi tarafından belirlenen belirli bir eylemi bir olay olarak tanır. Özel olaylar için olay haritası girişleri EVENT_CUSTOM makro tarafından temsil edilir. Aşağıdaki bölüm ActiveX Denetim Sihirbazı kullanılarak oluşturulan activex denetim projesi için özel bir olay uygular.

## <a name="adding-a-custom-event-with-the-add-event-wizard"></a><a name="_core_adding_a_custom_event_with_classwizard"></a>Olay Ekle Sihirbazı ile Özel Etkinlik Ekleme

Aşağıdaki yordam belirli bir özel olay, ClickIn ekler. Diğer özel olaylar eklemek için bu yordamı kullanabilirsiniz. Özel etkinlik adınızı ve parametrelerini ClickIn olay adı ve parametreleri ile değiştirin.

#### <a name="to-add-the-clickin-custom-event-using-the-add-event-wizard"></a>Olay Ekle Sihirbazı'nı kullanarak ClickIn özel etkinliğini eklemek için

1. Denetiminizin projesini yükleyin.

1. **Sınıf**Görünümü'nde, kısayol menüsünü açmak için ActiveX denetim sınıfınızı sağ tıklatın.

1. Kısayol menüsünden **Ekle'yi** tıklatın ve ardından **Olay Ekle'yi**tıklatın.

   Bu, Olay Ekle Sihirbazı'nı açar.

1. Olay **ad** kutusunda, önce varolan herhangi bir olayı seçin, ardından **Özel** radyo düğmesine tıklayın, ardından *ClickIn*yazın.

1. İç **ad** kutusuna, olayın ateşleme işlevinin adını yazın. Bu örnekiçin, Olay Ekle Sihirbazı tarafından`FireClickIn`sağlanan varsayılan değeri kullanın ( ).

1. **Parametre Adı** ve **Parametre Türü** denetimlerini kullanarak *xCoord* (tip *OLE_XPOS_PIXELS)* adı verilen bir parametre ekleyin.

1. *yCoord* (tür *OLE_YPOS_PIXELS)* olarak adlandırılan ikinci bir parametre ekleyin.

1. Etkinliği oluşturmak için **Bitir'i** tıklatın.

## <a name="add-event-wizard-changes-for-custom-events"></a><a name="_core_classwizard_changes_for_custom_events"></a>Özel Etkinlikler için Olay Sihirbazı Değişiklikleri Ekleme

Özel bir olay eklediğinizde, Olay Ekle Sihirbazı denetim sınıfında değişiklik yapar. H. CPP, ve. IDL dosyaları. Aşağıdaki kod örnekleri ClickIn olayına özgüdir.

Aşağıdaki satırlar üstbilgiye eklenir (. H) kontrol sınıfının dosyası:

[!code-cpp[NVC_MFC_AxUI#7](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_1.h)]

Bu kod, `FireClickIn` [COleControl::FireEvent](../mfc/reference/colecontrol-class.md#fireevent) adlı bir satır lı işlev, ClickIn olayı ve Olay Ekle Sihirbazı'nı kullanarak tanımladığınız parametrelerle birlikte bildirir.

Buna ek olarak, uygulamada bulunan denetim için olay haritasına aşağıdaki satır eklenir (. CPP) denetim sınıfının dosyası:

[!code-cpp[NVC_MFC_AxUI#8](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_2.cpp)]

Bu kod, Olay Ekle Sihirbazı'nı kullanarak tanımladığınız parametreleri geçerek olay ClickIn'i satır içinde işlevle `FireClickIn`eşler.

Son olarak, aşağıdaki satır denetiminizin. IDL dosyası:

[!code-cpp[NVC_MFC_AxUI#9](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_3.idl)]

Bu satır, Olay Sihirbazı Ekle etkinlik listesinde etkinliğin konumundan alınan belirli bir kimlik numarasını ClickIn olayını atar. Olay listesindeki giriş, bir kapsayıcının olayı tahmin etmesine olanak tanır. Örneğin, olay çalıştırıldığında yürütülecek işleyici kodu sağlayabilir.

## <a name="calling-fireclickin"></a><a name="_core_calling_fireclickin"></a>Fireclickin'i arama

Olay Ekle Sihirbazı'nı kullanarak ClickIn özel etkinliğini eklediğinize göre, bu olayın ne zaman başlatılacağına karar vermelisiniz. Uygun eylem gerçekleştiğinde arayarak `FireClickIn` bunu yaparsınız. Bu tartışma için denetim, `InCircle` kullanıcı `WM_LBUTTONDOWN` dairesel veya eliptik bir bölgenin içini tıklattığında ClickIn olayını görüntülemek için ileti işleyicisinin içindeki işlevi kullanır. Aşağıdaki yordam işleyiciekler. `WM_LBUTTONDOWN`

#### <a name="to-add-a-message-handler-with-the-add-event-wizard"></a>Olay Ekle Sihirbazı ile ileti işleyicisi eklemek için

1. Denetiminizin projesini yükleyin.

1. **Sınıf Görünümü'nde**ActiveX denetim sınıfınızı seçin.

1. **Özellikler** penceresinde, ActiveX denetimi tarafından işlenebilen iletilerin listesini görürsünüz. Kalın olarak gösterilen herhangi bir iletinin zaten atanmış bir işleyici işlevi vardır.

1. Işlemek istediğiniz iletiyi seçin. Bu örnek için, seçin. `WM_LBUTTONDOWN`

1. Sağdaki açılan liste kutusundan> ** \<OnLButtonDown'a ekle'yi**seçin.

1. Uygulamadaki ileti işleyicisi koduna atlamak için **Sınıf Görünümü'ndeki** yeni işleyici işlevini çift tıklatın (. ActiveX denetiminizin CPP) dosyası.

Aşağıdaki kod örneği, `InCircle` sol fare düğmesine her tıklandığında denetim penceresi içinde işlevi çağırır. Bu örnek işleyici `WM_LBUTTONDOWN` işlevinde, `OnLButtonDown` [Circ örnek](../overview/visual-cpp-samples.md) soyut bulunabilir.

[!code-cpp[NVC_MFC_AxUI#10](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_4.cpp)]

> [!NOTE]
> Olay Ekle Sihirbazı fare düğmesi eylemleri için ileti işleyicileri oluşturduğunda, taban sınıfın aynı ileti işleyicisine yapılan çağrı otomatik olarak eklenir. Bu aramayı kaldırmayın. Denetiminiz stok fare mesajlarından herhangi birini kullanıyorsa, fare yakalamanın düzgün şekilde işlendiğinden emin olmak için taban sınıftaki ileti işleyicileri çağrılmalıdır.

Aşağıdaki örnekte, olay yalnızca tıklama denetim içinde dairesel veya eliptik bir bölge içinde oluştuğunda yangınlar. Bu davranışı elde etmek `InCircle` için, işlevi denetiminizin uygulamasına yerleştirebilirsiniz (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxUI#11](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_5.cpp)]

Ayrıca, denetimüstbilginize işlevin `InCircle` aşağıdaki bildirimini eklemeniz gerekir (. H) dosya:

[!code-cpp[NVC_MFC_AxUI#12](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_6.h)]

## <a name="custom-events-with-stock-names"></a><a name="_core_custom_events_with_stock_names"></a>Stok Adlarıyla Özel Etkinlikler

Stok olayları ile aynı ada sahip özel olaylar oluşturabilirsiniz, ancak her ikisini de aynı denetimde uygulayamazsınız. Örneğin, stok olayı Click normalde ateş ettiğinde çalışmıyor Tıklama adlı özel bir olay oluşturmak isteyebilirsiniz. Daha sonra, click olayını ateşleme işlevini çağırarak istediğiniz zaman ateşleyebilirsiniz.

Aşağıdaki yordam özel bir Click olayı ekler.

#### <a name="to-add-a-custom-event-that-uses-a-stock-event-name"></a>Stok olay adı kullanan özel bir olay eklemek için

1. Denetiminizin projesini yükleyin.

1. **Sınıf**Görünümü'nde, kısayol menüsünü açmak için ActiveX denetim sınıfınızı sağ tıklatın.

1. Kısayol menüsünden **Ekle'yi** tıklatın ve ardından **Olay Ekle'yi**tıklatın.

   Bu, Olay Ekle Sihirbazı'nı açar.

1. Olay **Adı** açılır listesinde bir stok olay adı seçin. Bu örnek **için, 'yi tıklatın'i**seçin.

1. **Olay Türü**için **Özel'i**seçin.

1. Etkinliği oluşturmak için **Bitir'i** tıklatın.

1. Kodunuzda uygun yerlerden arayın. `FireClick`

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: Yöntemler](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl Sınıfı](../mfc/reference/colecontrol-class.md)
