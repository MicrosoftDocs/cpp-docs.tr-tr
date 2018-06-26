---
title: 'ActiveX denetimi kapsayıcıları: ActiveX denetimindeki etkinlikleri işleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 3a3844788330cfe79366221ee215c437fc4aefc8
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930667"
---
# <a name="activex-control-containers-handling-events-from-an-activex-control"></a>ActiveX Denetimi Kapsayıcıları: ActiveX Denetimindeki Etkinlikleri İşleme
Bu makalede, bir ActiveX denetimi kapsayıcısı ActiveX denetimleri için olay işleyicileri yüklemek için Özellikler penceresini kullanarak anlatılmaktadır. Olay işleyicileri belirli olaylar (denetiminden ek olarak) bildirimlerini almak ve yanıt olarak bazı eylemleri gerçekleştirmek için kullanılır. Bu bildirim, "olay tetikleme" adı verilir.  
  
> [!NOTE]
>  Bu makalede, kapsayıcı ve yordamları ve kod örnekleri olarak Dai adlı bir katıştırılmış denetimi adlı iletişim tabanlı ActiveX denetimi kapsayıcısı projesi kullanır.  
  
 Özellikler penceresinde Events düğmesini kullanarak ActiveX denetimi kapsayıcısı uygulamanızda oluşabilir olayları haritasını oluşturabilirsiniz. Bir "olay havuz eşlemesi,'' adlandırılan bu harita oluşturulur ve denetim kapsayıcı sınıfına olay işleyicileri eklediğinizde Visual C++ tarafından korunur. Bir olay eşleme girişi ile uygulanan her olay işleyicisi belirli bir olay bir kapsayıcı olay işleyicisi üye işlevine eşler. ActiveX denetim nesnesi tarafından belirtilen olay başlatıldığında bu olay işleyicisi işlevi çağrılır.  
  
 Olay iç havuz eşlemeleri hakkında daha fazla bilgi için bkz: [olay iç havuz eşlemeleri](../mfc/reference/event-sink-maps.md) içinde *sınıf kitaplığı başvurusu*.  
  
##  <a name="_core_event_handler_modifications_to_the_project"></a> Olay işleyici değişiklikler projeye  
 Olay işleyicileri eklemek için Özellikler penceresini kullandığınızda, bir olay havuz eşlemesi bildirilen ve projenizde tanımlı. Aşağıdaki deyimleri denetimine eklenir. CPP dosya ilk kez bir olay işleyicisi eklenir. Bu kod, bir olay havuz eşlemesi iletişim kutusu sınıfı için bildirir (Bu durumda, `CContainerDlg`):  
  
 [!code-cpp[NVC_MFC_AxCont#8](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_1.cpp)]  
[!code-cpp[NVC_MFC_AxCont#9](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_2.cpp)]  
  
 Olay eklemek için Özellikler penceresini kullanın gibi bir olay eşleme girişi (`ON_EVENT`) eklenir olay havuz eşlemesi ve bir olay işleyicisi işlevi kapsayıcının uygulamasına eklenir (. CPP) dosyası.  
  
 Aşağıdaki örnek adlı bir olay işleyicisi bildirir `OnClickInCircCtrl`, Dai denetimin için `ClickIn` olay:  
  
 [!code-cpp[NVC_MFC_AxCont#10](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_3.cpp)]  
  
 Ayrıca, aşağıdaki şablonu eklenen `CContainerDlg` sınıf uygulama (. Olay işleyici üye işlevi için CPP) dosyası:  
  
 [!code-cpp[NVC_MFC_AxCont#11](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_4.cpp)]  
  
 Olay iç havuz makroları hakkında daha fazla bilgi için bkz: [olay iç havuz eşlemeleri](../mfc/reference/event-sink-maps.md) içinde *sınıf kitaplığı başvurusu*.  
  
#### <a name="to-create-an-event-handler-function"></a>Bir olay işleyicisi işlevi oluşturmak için  
  
1.  Sınıf görünümünden ActiveX denetimini içeren iletişim kutusu sınıfı seçin. Bu örneğin `CContainerDlg`.  
  
2.  Özellikler penceresinde **olayları** düğmesi.  
  
3.  Özellikler penceresinde katıştırılmış ActiveX denetiminin denetim kimliği seçin. Bu örneğin `IDC_CIRCCTRL1`.  
  
     Özellikler penceresini katıştırılmış ActiveX denetimi tarafından tetiklenen olaylar listesini görüntüler. Zaten kalın olarak gösterilen herhangi bir üye işlevini atanmış işleyici işlevleri vardır.  
  
4.  İşlemek için iletişim kutusu sınıfı istediğiniz olayı seçin. Bu örnek için select **tıklatın**.  
  
5.  Sağdaki aşağı açılan liste kutusundan seçin  **\<Ekle > ClickCircctrl1**.  
  
6.  Olay işleyicisi kodunu uygulamalarında atlamak için sınıf görünümünden yeni işleyici işlevi çift tıklatın (. CPP) dosyasının `CContainerDlg`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)

