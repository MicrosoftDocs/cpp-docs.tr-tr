---
title: 'ActiveX Denetimi Kapsayıcıları: ActiveX Denetimindeki Etkinlikleri İşleme'
ms.date: 09/12/2018
helpviewer_keywords:
- event handlers [MFC], ActiveX controls
- ActiveX control containers [MFC], event sinks
- event handling [MFC], ActiveX controls
- ON_EVENT macro [MFC]
- ActiveX controls [MFC], events [MFC]
- END_EVENTSINK_MAP macro, using
- events [MFC], ActiveX controls
- BEGIN_EVENTSINK_MAP macro
ms.assetid: f9c106db-052f-4e32-82ad-750646aa760b
ms.openlocfilehash: ae623ee0973e78db3b542646dd6bdec58cc2dfc8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367947"
---
# <a name="activex-control-containers-handling-events-from-an-activex-control"></a>ActiveX Denetimi Kapsayıcıları: ActiveX Denetimindeki Etkinlikleri İşleme

Bu makalede, ActiveX denetim kapsayıcısına ActiveX denetimleri için olay işleyicileri yüklemek için **Özellikler** penceresi **(Sınıf Görünümünde)** kullanılarak açıklanabilir. Olay işleyicileri, belirli olayların bildirimlerini (denetimden) almak ve yanıt olarak bazı eylemler gerçekleştirmek için kullanılır. Bu bildirime olay "ateş" olarak adlandırılır.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. ActiveX'in yerini alabilecek modern teknolojiler hakkında daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

> [!NOTE]
> Bu makalede, kapsayıcı adlı iletişim kutusu tabanlı activex denetim kapsayıcı sı ve yordamlar ve kodörnekleri olarak Circ adlı katıştırılmış denetim kullanır.

**Özellikler** penceresindeki Olaylar düğmesini kullanarak **(Sınıf**Görünümü'nde), ActiveX denetim kapsayıcısı uygulamanızda oluşabilecek olayların bir haritasını oluşturabilirsiniz. "Olay lavabo haritası" olarak adlandırılan bu harita, denetim kapsayıcısı sınıfına olay işleyicileri eklediğinizde Visual C++ tarafından oluşturulur ve korunur. Olay eşlemi girişiyle uygulanan her olay işleyicisi, belirli bir olayı kapsayıcı olay işleyicisi üye işleviyle eşler. Belirtilen olay ActiveX denetim nesnesi tarafından ateşlendiğinde bu olay işleyicisi işlevi çağrılır.

Olay lavabo haritaları hakkında daha fazla bilgi için *Sınıf Kitaplığı Başvurusu'ndaki* [Olay Lavabo Haritaları'na](../mfc/reference/event-sink-maps.md) bakın.

## <a name="event-handler-modifications-to-the-project"></a><a name="_core_event_handler_modifications_to_the_project"></a>Projede Olay İşleyicisi Modifikasyonları

Olay işleyicileri eklemek için **Özellikler** penceresini kullandığınızda, projenizde bir olay lavabo haritası bildirilir ve tanımlanır. Denetime aşağıdaki ifadeler eklenir. CPP dosyası ilk kez bir olay işleyicisi eklenir. Bu kod iletişim kutusu sınıfı için bir olay lavabo eşlemesi bildirir (bu durumda, `CContainerDlg`):

[!code-cpp[NVC_MFC_AxCont#8](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_1.cpp)]
[!code-cpp[NVC_MFC_AxCont#9](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_2.cpp)]

Olay eklemek için **Özellikler** penceresini kullandığınızda,`ON_EVENT`olay eşleme haritasına bir olay eşlemi girişi ( ) eklenir ve bir olay işleyicisi işlevi kapsayıcının uygulamasına eklenir (. CPP) dosyası.

Aşağıdaki örnek, Circ denetiminin `OnClickInCircCtrl` `ClickIn` olayı için çağrılan bir olay işleyicisi bildirir:

[!code-cpp[NVC_MFC_AxCont#10](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_3.cpp)]

Buna ek olarak, aşağıdaki şablon `CContainerDlg` sınıf uygulamasına eklenir (. CPP) olay işleyicisi üye işlevi için dosya:

[!code-cpp[NVC_MFC_AxCont#11](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_4.cpp)]

Olay lavabo makroları hakkında daha fazla bilgi için *Sınıf Kitaplığı Başvurusu'ndaki* [Olay Lavabo Haritaları'na](../mfc/reference/event-sink-maps.md) bakın.

#### <a name="to-create-an-event-handler-function"></a>Olay işleyicisi işlevi oluşturmak için

1. Sınıf Görünümü'nden ActiveX denetimini içeren iletişim sınıfını seçin. Bu örnekiçin, `CContainerDlg`kullanın.

1. **Özellikler** **penceresinde, Etkinlikler** düğmesini tıklatın.

1. **Özellikler** penceresinde, gömülü ActiveX denetiminin denetim kimliğini seçin. Bu örnekiçin, `IDC_CIRCCTRL1`kullanın.

   **Özellikler** penceresi, katıştırılmış ActiveX denetimi tarafından ateşlenebilen olayların listesini görüntüler. Kalın olarak gösterilen herhangi bir üye işlev, zaten ona atanmış işleyici işlevlerine sahiptir.

1. İletişim sınıfının işlemesini istediğiniz olayı seçin. Bu örnek **için, 'yi tıklatın'i**seçin.

1. Sağdaki açılan liste kutusundan> ** \<ClickCircctrl1 ekle'yi**seçin.

1. Uygulamadaki olay işleyicisi koduna atlamak için Sınıf Görünümü'nden yeni işleyici işlevini çift tıklatın (. CPP) dosyası. `CContainerDlg`

## <a name="see-also"></a>Ayrıca bkz.

[ActiveX Kontrol Kapları](../mfc/activex-control-containers.md)
