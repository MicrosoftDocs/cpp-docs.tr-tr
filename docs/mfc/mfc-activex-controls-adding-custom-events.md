---
title: 'MFC ActiveX denetimleri: Özel olaylar ekleme'
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
ms.openlocfilehash: 48c5ddbc8a3bcf6f74c251820e83cdebcef05bc9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400740"
---
# <a name="mfc-activex-controls-adding-custom-events"></a>MFC ActiveX denetimleri: Özel olaylar ekleme

Özel olaylar, bunlar otomatik olarak bir sınıf tarafından tetiklenen değil, stok olaylardan farklı `COleControl`. Özel olay, olay olarak denetim geliştiricisi tarafından belirlenen belirli bir eylem, tanır. Özel olaylar için olay eşleme girişleri EVENT_CUSTOM makrosu tarafından temsil edilir. Aşağıdaki bölümde, ActiveX Denetim Sihirbazı'nı kullanarak oluşturulan bir ActiveX denetimi projesi için özel bir olay uygular.

##  <a name="_core_adding_a_custom_event_with_classwizard"></a> Özel bir olay ile ekleme olay Ekleme Sihirbazı

Aşağıdaki yordam, belirli özel olay, Clickın ekler. Özel diğer olay eklemek için bu yordamı kullanabilirsiniz. Özel olay adınız ve parametreleri için parametreler ve Clickın olayı adını değiştirin.

#### <a name="to-add-the-clickin-custom-event-using-the-add-event-wizard"></a>Olay Ekleme Sihirbazı'nı kullanarak Clickın özel olay eklemek için

1. Denetiminizin proje yükleyin.

1. Sınıf Görünümü'nde sağ tıklayın, ActiveX denetim sınıfı kısayol menüsünü açın.

1. Kısayol menüsünden tıklayın **Ekle** ve ardından **olay Ekle**.

   Bu olay Ekleme Sihirbazı'nı açar.

1. İçinde **olay adı** kutusuna, ilk var olan herhangi bir olay seçin ve ardından tıklayarak **özel** radyo düğmesini ve ardından yazın *Clickın*.

1. İçinde **iç adı** olay tetikleyicisinin tetikleme işlevin adını yazın. Bu örnekte, olay Ekleme Sihirbazı tarafından sağlanan varsayılan değeri kullanın (`FireClickIn`).

1. Adlı bir parametreyi ekleyin *xCoord* (tür *OLE_XPOS_PIXELS*) kullanarak **parametre adı** ve **parametre türü** kontrol eder.

1. Adlı ikinci bir parametre ekleyin *yCoord* (tür *OLE_YPOS_PIXELS*).

1. Tıklayın **son** olay oluşturamadı.

##  <a name="_core_classwizard_changes_for_custom_events"></a> Etkinlik Sihirbazı değişiklikleri için özel olaylar ekleme

Özel olay eklediğinizde, olay Ekleme Sihirbazı'nı denetim sınıfına değişiklik yapar. H. CPP ve. IDL dosyaları. Aşağıdaki kod örnekleri için Clickın olayı özgüdür.

Aşağıdaki satırları için üst bilgi eklenir (. H) denetim sınıfınızın dosyası:

[!code-cpp[NVC_MFC_AxUI#7](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_1.h)]

Bu kod çağrılan bir satır içi işlev bildirir `FireClickIn` çağrılarının [COleControl::FireEvent](../mfc/reference/colecontrol-class.md#fireevent) Clickın olayı ve parametreleri ile olay Ekleme Sihirbazı'nı kullanarak tanımlanmış.

Ayrıca, olay eşlemesi uygulamasında bulunan denetim için aşağıdaki satırı eklenir (. Denetim sınıfınızın CPP) dosyası:

[!code-cpp[NVC_MFC_AxUI#8](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_2.cpp)]

Bu kod Clickın olayı satır içi işleve eşlenir `FireClickIn`, tanımlanan olay Ekleme Sihirbazı'nı kullanarak parametre geçirme.

Son olarak, aşağıdaki satırı, denetimin eklenir. IDL dosyası:

[!code-cpp[NVC_MFC_AxUI#9](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_3.idl)]

Bu satırı Clickın olayı olay Ekleme Sihirbazı'nı olay listesindeki olayın konumdan gerçekleştirilen belirli bir kimlik numarası atar. Giriş olayı olay tahmin için bir kapsayıcı sağlar. Örneğin, bu olay harekete yürütülecek işleyici kodu sağlayabilir.

##  <a name="_core_calling_fireclickin"></a> Fireclickın çağırma

Olay Ekleme Sihirbazı'nı kullanarak Clickın özel olay ekledik, bu olay başlatılmasına izin olduğunda, karar vermeniz gerekir. Çağrı yaparak bunu `FireClickIn` uygun eylemi olduğunda gerçekleşir. Bu tartışma için denetimi kullanan `InCircle` işlev içinde kullanıcı elips veya döngüsel bir bölgenin içinde tıkladığında Clickın olayı ateşlenmesine WM_LBUTTONDOWN ileti işleyicisi. Aşağıdaki yordam, WM_LBUTTONDOWN işleyici ekler.

#### <a name="to-add-a-message-handler-with-the-add-event-wizard"></a>Olay Ekleme Sihirbazı'nı bir ileti işleyicisi eklemek için

1. Denetiminizin proje yükleyin.

1. Sınıf Görünümü'nde, ActiveX denetim sınıfı seçin.

1. Özellikler penceresinde tıklayın **iletileri** düğmesi.

   Özellikler penceresinde, bir ActiveX denetimi tarafından işlenebilen iletilerinin listesini görüntüler. Herhangi bir ileti kalın yazılarak gösterilmiştir zaten kendisine atanmış bir işleyici işlevi vardır.

1. Özellikler penceresinde, kullanmak istediğiniz iletiyi seçin. Bu örnekte, WM_LBUTTONDOWN seçin.

1. Sağdaki aşağı açılan liste kutusundan seçin  **\<Ekle > OnLButtonDown**.

1. Yeni işleyici işlevi uygulamasında ileti işleyicinizin kodunu atlamak için Sınıf Görünümü'nde çift tıklayın (. ActiveX denetiminizin CPP) dosyası.

Aşağıdaki kod örneği çağrıları `InCircle` denetim pencereye farenin sol düğmesine tıklandığında her zaman çalışması. Bu örnek WM_LBUTTONDOWN işleyici işlevi içinde bulunabilir `OnLButtonDown`, [Dai örnek](../overview/visual-cpp-samples.md) soyut.

[!code-cpp[NVC_MFC_AxUI#10](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_4.cpp)]

> [!NOTE]
>  Olay Ekleme Sihirbazı'nı ileti işleyicileri farenin düğme eylemleri oluşturduğunda, temel sınıfın aynı ileti işleyicisi çağrısı otomatik olarak eklenir. Bu çağrı kaldırmayın. Denetiminiz fare stok iletilerini kullanıyorsa, temel sınıfta ileti işleyicileri fare yakalamayı doğru şekilde işlediğinden emin olmak için çağrılmalıdır.

Aşağıdaki örnekte, yalnızca tıklayarak denetiminde elips veya döngüsel bir bölge içinde oluştuğunda olay tetiklenir. Bu davranışı elde etmek için yerleştirebilirsiniz `InCircle` işlevi denetiminizin uygulamasında (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxUI#11](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_5.cpp)]

Ayrıca aşağıdaki bildirimi eklemeniz gerekir `InCircle` denetiminizin başlığına işlevi (. H) dosyası:

[!code-cpp[NVC_MFC_AxUI#12](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_6.h)]

##  <a name="_core_custom_events_with_stock_names"></a> Stok adları ile özel olaylar

Ancak, hem de aynı denetimi uygulayamazsınız stok olaylar, aynı ada sahip özel olaylar oluşturabilirsiniz. Örneğin, stok olayı tıklatın normalde tetiklendiğinde başlatılmıyor Click adlı özel bir olay oluşturmak isteyebilirsiniz. Açmadığınızda işlevini çağırarak herhangi bir zamanda ardından Click olayını harekete.

Aşağıdaki yordamda özel bir tıklama ekler olay.

#### <a name="to-add-a-custom-event-that-uses-a-stock-event-name"></a>Stok olayı adı kullanan özel bir olay eklemek için

1. Denetiminizin proje yükleyin.

1. Sınıf Görünümü'nde sağ tıklayın, ActiveX denetim sınıfı kısayol menüsünü açın.

1. Kısayol menüsünden tıklayın **Ekle** ve ardından **olay Ekle**.

   Bu olay Ekleme Sihirbazı'nı açar.

1. İçinde **olay adı** aşağı açılan listesinde, bir stok olayı adını seçin. Bu örnekte, seçin **tıklayın**.

1. İçin **olay türü**seçin **özel**.

1. Tıklayın **son** olay oluşturamadı.

1. Çağrı `FireClick` uygun yerlerde kodunuzu.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: Yöntemler](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl Sınıfı](../mfc/reference/colecontrol-class.md)
