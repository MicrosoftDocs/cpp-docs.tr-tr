---
title: 'ActiveX denetimi kapsayıcıları: ActiveX denetimindeki etkinlikleri işleme | Microsoft Docs'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7bd8c505c857082732e56ff2b4bf1a5bed76647
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420315"
---
# <a name="activex-control-containers-handling-events-from-an-activex-control"></a>ActiveX Denetimi Kapsayıcıları: ActiveX Denetimindeki Etkinlikleri İşleme

Bu makalede, bir ActiveX denetimi kapsayıcısı ActiveX denetimleri için olay işleyicileri yüklemek için Özellikler penceresini kullanarak açıklanmaktadır. Olay işleyicileri, belirli olaylar (denetiminden) bildirimleri almak ve yanıt olarak bazı eylemleri gerçekleştirmek için kullanılır. Bu bildirim, "olayı tetiklenmekte" adı verilir.

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerini modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).


> [!NOTE]
>  Bu makalede, kapsayıcı ve yordamları ve kod örnekleri olarak Dai adlı bir katıştırılmış denetime adlı bir iletişim kutusu tabanlı ActiveX denetimi kapsayıcısı proje kullanır.

Özellikler penceresinde olayları düğmesini kullanarak ActiveX denetimi kapsayıcısı uygulamanızda oluşabilecek olayları haritasını oluşturabilirsiniz. Bir "olay havuzu eşlemesi,'' adlı bu harita, oluşturulur ve denetim kapsayıcısı sınıfına olay işleyicisi eklediğinizde, Visual C++ tarafından korunur. Olay eşleme girişi ile uygulanan, her bir olay işleyicisi, bir kapsayıcı olay işleyicisi üye işlevi için belirli bir olay eşler. ActiveX denetim nesnesi tarafından belirtilen olay tetiklendiğinde bu olay işleyicisi işlevi çağrılır.

Olay iç havuz eşlemeleri hakkında daha fazla bilgi için bkz. [olay iç havuz eşlemeleri](../mfc/reference/event-sink-maps.md) içinde *sınıf kitaplığı başvurusu*.

##  <a name="_core_event_handler_modifications_to_the_project"></a> Olay işleyicisi değişiklikleri projeye

Olay işleyicileri eklemek için Özellikler penceresini kullandığınızda, bir olay havuzu eşlemesi bildirildi ve projenizde tanımlanan. Aşağıdaki deyimleri denetimi eklenir. CPP dosyasına ilk kez bir olay işleyicisi eklenir. Bu kod, iletişim kutusu sınıfı için bir olay havuzu eşlemesi bildirir. (Bu durumda, `CContainerDlg`):

[!code-cpp[NVC_MFC_AxCont#8](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_1.cpp)]
[!code-cpp[NVC_MFC_AxCont#9](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_2.cpp)]

Olay eklemek için Özellikler penceresini kullanın gibi bir olay eşleme girişi (`ON_EVENT`) eklendiğinde olay havuzu eşlemesi ve bir olay işleyicisi işlevi kapsayıcının uygulamasına eklendi (. CPP) dosyası.

Aşağıdaki örnek adlı bir olay işleyicisi bildirir `OnClickInCircCtrl`, Dai denetimin için `ClickIn` olay:

[!code-cpp[NVC_MFC_AxCont#10](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_3.cpp)]

Ayrıca, aşağıdaki şablon eklenir `CContainerDlg` sınıf uygulama (. Olay işleyicisi üye işlev için CPP) dosyası:

[!code-cpp[NVC_MFC_AxCont#11](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_4.cpp)]

Olay havuzu makrolar hakkında daha fazla bilgi için bkz. [olay iç havuz eşlemeleri](../mfc/reference/event-sink-maps.md) içinde *sınıf kitaplığı başvurusu*.

#### <a name="to-create-an-event-handler-function"></a>Bir olay işleyici işlevi oluşturmak için

1. Sınıf Görünümü'ndeki ActiveX denetimini içeren bir iletişim kutusu sınıfı seçin. Bu örneğin `CContainerDlg`.

1. Özellikler penceresinde tıklayın **olayları** düğmesi.

1. Özellikler penceresinde, katıştırılmış ActiveX denetimi denetim Kimliğini seçin. Bu örneğin `IDC_CIRCCTRL1`.

     Özellikler penceresinde katıştırılmış ActiveX denetimi tarafından tetiklenen olayların listesini görüntüler. Hiçbir üye işlevini kalın yazılarak gösterilmiştir zaten atanmış işleyici işlevleri vardır.

1. İşlemek için iletişim kutusu sınıfı istediğiniz olayı seçin. Bu örnekte, seçin **tıklayın**.

1. Sağdaki aşağı açılan liste kutusundan seçin  **\<Ekle > ClickCircctrl1**.

1. Uygulama olay işleyici kodunun atlamak için sınıf görünümünden yeni işleyici işlevi çift tıklayın (. CPP) dosyası `CContainerDlg`.

## <a name="see-also"></a>Ayrıca Bkz.

[ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)

