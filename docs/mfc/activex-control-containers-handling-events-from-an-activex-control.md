---
title: 'ActiveX denetim kapsayıcıları: ActiveX denetiminden olayları işleme'
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
ms.openlocfilehash: 7487792fbc9fe6775640f40755a7f725543fb9f3
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907767"
---
# <a name="activex-control-containers-handling-events-from-an-activex-control"></a>ActiveX denetim kapsayıcıları: ActiveX denetiminden olayları işleme

Bu makalede, ActiveX denetim kapsayıcısındaki ActiveX denetimleri için olay işleyicilerini yüklemek üzere **Özellikler** penceresi ( **sınıf görünümü**) kullanılarak açıklanır. Olay işleyicileri, belirli olayların bildirimlerini almak için kullanılır ve yanıt olarak bazı eylemler gerçekleştirir. Bu bildirim, olayı "tetikme" olarak adlandırılır.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

> [!NOTE]
>  Bu makalede, kapsayıcı adlı bir iletişim kutusu tabanlı ActiveX Denetim kapsayıcısı projesi ve farklı Circ adlı bir katıştırılmış denetim, yordamlar ve kodda örnek olarak kullanılır.

**Özellikler** penceresindeki olaylar düğmesini kullanarak ( **sınıf görünümü**), ActiveX Denetim kapsayıcısı uygulamanızda gerçekleşebileceğini olayların haritasını oluşturabilirsiniz. "Olay havuzu eşleme, ' ' adlı bu harita, denetim kapsayıcı sınıfına olay işleyicileri eklediğinizde görsel C++ tarafından oluşturulur ve sürdürülür. Bir olay eşleme girdisiyle uygulanan her olay işleyicisi, belirli bir olayı bir kapsayıcı olay işleyicisi üye işlevine eşler. Bu olay işleyicisi işlevi, belirtilen olay ActiveX denetim nesnesi tarafından tetiklendiğinde çağrılır.

Olay havuzu eşlemeleri hakkında daha fazla bilgi için bkz. *sınıf kitaplığı başvurusunda* [olay havuzu eşlemeleri](../mfc/reference/event-sink-maps.md) .

##  <a name="_core_event_handler_modifications_to_the_project"></a>Projede olay Işleyicisi değişiklikleri

Olay işleyicileri eklemek için **Özellikler** penceresini kullandığınızda, projenizde bir olay havuzu eşlemesi bildirilmiştir ve tanımlanır. Aşağıdaki deyimler denetime eklenir. İlk kez bir olay işleyici eklendiğinde CPP dosyası. Bu kod, iletişim kutusu sınıfı için bir olay havuzu eşlemesi bildirir (Bu durumda, `CContainerDlg`):

[!code-cpp[NVC_MFC_AxCont#8](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_1.cpp)]
[!code-cpp[NVC_MFC_AxCont#9](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_2.cpp)]

Olayları eklemek için **Özellikler** penceresini kullanırken, olay havuzu eşlemesine bir olay eşleme girişi (`ON_EVENT`) eklenir ve kapsayıcının uygulamasına bir olay işleyici işlevi eklenir (. CPP) dosyası.

Aşağıdaki örnek, Circ `OnClickInCircCtrl` `ClickIn` denetiminin olayı için adlı bir olay işleyicisini bildirir:

[!code-cpp[NVC_MFC_AxCont#10](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_3.cpp)]

Ayrıca, aşağıdaki şablon `CContainerDlg` sınıf uygulamasına eklenir (. CPP) dosyası olay işleyicisi üye işlevi için:

[!code-cpp[NVC_MFC_AxCont#11](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_4.cpp)]

Olay havuzu makroları hakkında daha fazla bilgi için bkz. *sınıf kitaplığı başvurusunda* [olay havuzu eşlemeleri](../mfc/reference/event-sink-maps.md) .

#### <a name="to-create-an-event-handler-function"></a>Bir olay işleyicisi işlevi oluşturmak için

1. Sınıf Görünümü, ActiveX denetimini içeren iletişim kutusu sınıfını seçin. Bu örnek için kullanın `CContainerDlg`.

1. **Özellikler** penceresinde **Olaylar** düğmesine tıklayın.

1. **Özellikler** penceresinde, katıştırılmış ActiveX DENETIMININ denetim kimliğini seçin. Bu örnek için kullanın `IDC_CIRCCTRL1`.

   **Özellikler** penceresi, katıştırılmış ActiveX denetimi tarafından tetiklenebilir olayların bir listesini görüntüler. Kalın olarak gösterilen herhangi bir üye işlevine atanmış işleyici işlevleri zaten var.

1. İletişim kutusu sınıfının işlemesini istediğiniz olayı seçin. Bu örnek için **tıklama ' yi**seçin.

1. Sağdaki aşağı açılan liste kutusundan  **\<Ekle > ClickCircctrl1**' ı seçin.

1. Uygulamadaki olay işleyicisi koduna geçmek için Sınıf Görünümü yeni işleyici işlevine çift tıklayın (. CPP) dosyası `CContainerDlg`.

## <a name="see-also"></a>Ayrıca bkz.

[ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)
