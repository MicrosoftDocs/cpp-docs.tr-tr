---
title: "MFC ActiveX denetimleri: Özel olaylar ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6bbf62500d3aaca21e9b01401e839d08fa56755c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-adding-custom-events"></a>MFC ActiveX Denetimleri: Özel Olaylar Ekleme
Özel olaylar, bunlar otomatik olarak bir sınıf tarafından tetiklenen değil, stok olayları farklı `COleControl`. Özel bir olay bir olay olarak denetim geliştirici tarafından belirlenen belirli bir eylemi, tanır. Özel olaylar için olay eşleme girdilerini tarafından temsil edilen `EVENT_CUSTOM` makrosu. Aşağıdaki bölümde ActiveX Denetim Sihirbazı kullanılarak oluşturulmuş bir ActiveX denetimi projesi için özel bir olay uygular.  
  
##  <a name="_core_adding_a_custom_event_with_classwizard"></a>Özel bir olay ile ekleyerek olay Ekleme Sihirbazı  
 Aşağıdaki yordam, belirli bir özel olay Clickın ekler. Diğer özel olaylar eklemek için bu yordamı kullanın. Özel olay adınızı ve parametreleri Clickın olayı adını ve parametreleri için yerleştirin.  
  
#### <a name="to-add-the-clickin-custom-event-using-the-add-event-wizard"></a>Olay Ekleme Sihirbazı'nı kullanarak Clickın özel olay eklemek için  
  
1.  Denetiminizin proje yükleyin.  
  
2.  Sınıf Görünümü'nde ActiveX denetim sınıfınıza kısayol menüsünü açmak için sağ tıklatın.  
  
3.  Kısayol menüsünden tıklatın **Ekle** ve ardından **olay Ekle**.  
  
     Olay Ekleme Sihirbazı'nı açar.  
  
4.  İçinde **olay adı** kutusunda, önce varolan herhangi bir olay seçin, ardından tıklayın **özel** radyo düğmesine tıklayın ve ardından yazın `ClickIn`.  
  
5.  İçinde **iç adı** olay tetikleme işlevin adını yazın. Bu örnekte, olay Ekleme Sihirbazı tarafından sağlanan varsayılan değeri kullanın (`FireClickIn`).  
  
6.  Adlı bir parametre eklemek `xCoord` (tür `OLE_XPOS_PIXELS`) kullanarak **parametre adı** ve **parametre türü** kontrol eder.  
  
7.  Adlı ikinci bir parametre eklemek `yCoord` (tür `OLE_YPOS_PIXELS`).  
  
8.  Tıklatın **son** olay oluşturamadı.  
  
##  <a name="_core_classwizard_changes_for_custom_events"></a>Olay Sihirbazı değişiklikleri için özel olaylar ekleme  
 Özel bir olay eklediğinizde, olay Ekleme Sihirbazı'nı denetim sınıfına değişiklikleri yapar. H. CPP, ve. IDL dosyaları. Aşağıdaki kod örnekleri Clickın olayı özgüdür.  
  
 Aşağıdaki satırları üstbilgiye eklenir (. H) denetim sınıfınıza dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#7](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_1.h)]  
  
 Bu kod olarak adlandırılan bir satır içi işlev bildirir `FireClickIn` çağrısı [COleControl::FireEvent](../mfc/reference/colecontrol-class.md#fireevent) Clickın olayı ve parametreleri ile olay Ekleme Sihirbazı'nı kullanarak tanımlanmış.  
  
 Ayrıca, aşağıdaki satırı uygulamasında bulunan denetiminde, olay eşlemesi eklenme (. Denetim sınıfınıza CPP) dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#8](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_2.cpp)]  
  
 Bu kod Clickın olayı için satır içi işlev eşlemeleri `FireClickIn`, tanımlanan olay Ekleme Sihirbazı'nı kullanarak parametreleri geçirme.  
  
 Son olarak, aşağıdaki satırı, denetimin eklenir. IDL dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#9](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_3.idl)]  
  
 Bu satırı Clickın olayı olay Ekleme Sihirbazı'nı olay listesinde olayın konumdan gerçekleştirilen belirli bir kimlik numarası atar. Olay listesi girişi olay düşündüğünüz için bir kapsayıcı sağlar. Örneğin, olay başlatıldığında çalıştırılacak işleyici kodu sağlayabilir.  
  
##  <a name="_core_calling_fireclickin"></a>Fireclickın çağırma  
 Olay Ekleme Sihirbazı'nı kullanarak Clickın özel olayı eklediyseniz, bu olay harekete olduğunda, karar vermeniz gerekir. Çağırarak bunu `FireClickIn` uygun eylemi oluştuğunda. Bu tartışma için denetim kullanır `InCircle` içinde işlev bir `WM_LBUTTONDOWN` bir kullanıcı bir dairesel veya Oval bölge içinde tıkladığında Clickın olayı tetiklenecek ileti işleyicisi. Aşağıdaki yordam ekler `WM_LBUTTONDOWN` işleyicisi.  
  
#### <a name="to-add-a-message-handler-with-the-add-event-wizard"></a>Olay Ekleme Sihirbazı'nı bir ileti işleyicisini eklemek için  
  
1.  Denetiminizin proje yükleyin.  
  
2.  Sınıf Görünümü'nde, ActiveX denetimi sınıfı seçin.  
  
3.  Özellikler penceresinde **iletileri** düğmesi.  
  
     Özellikler penceresini ActiveX denetimi tarafından işlenen iletilerin listesini görüntüler. Zaten kalın olarak gösterilen herhangi bir iletisi, kendisine atanmış bir işleyici işlevi vardır.  
  
4.  Özellikler penceresinden işlemek istediğiniz iletiyi seçin. Bu örnek için select `WM_LBUTTONDOWN`.  
  
5.  Sağdaki aşağı açılan liste kutusundan seçin  **\<Ekle > OnLButtonDown**.  
  
6.  İleti işleyici kodu uygulamasında atlamak için Sınıf Görünümü'nde yeni işleyici işlevi çift tıklatın (. ActiveX denetimi CPP) dosyası.  
  
 Aşağıdaki kod örnek çağrıları **Incircle** sol fare düğmesini denetim pencereye tıklandığında her zaman işlev. Bu örnek bulunabilir `WM_LBUTTONDOWN` işleyici işlevi `OnLButtonDown`, [Dai örnek](../visual-cpp-samples.md) Özet.  
  
 [!code-cpp[NVC_MFC_AxUI#10](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_4.cpp)]  
  
> [!NOTE]
>  Olay Ekleme Sihirbazı'nı fare düğmesini eylemler için ileti işleyicileri oluşturduğunda, temel sınıfın aynı ileti işleyicisi için bir çağrı otomatik olarak eklenir. Bu çağrı kaldırmayın. Denetim stok fare iletilerinden birini kullanıyorsa, fare yakalama düzgün şekilde işlendiğinden emin olmak için temel sınıf ileti işleyicileri çağrılmalıdır.  
  
 Aşağıdaki örnekte, yalnızca tıklatın denetimi içinde bir dairesel veya Oval bölge içinde meydana geldiğinde olay gönderir. Bu davranış elde etmek için yerleştirebilirsiniz `InCircle` denetiminizin uygulamasında işlevi (. CPP) dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#11](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_5.cpp)]  
  
 Ayrıca aşağıdaki bildirimi eklemeniz gerekir `InCircle` denetiminizin başlığına işlevi (. H) dosyası:  
  
 [!code-cpp[NVC_MFC_AxUI#12](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_6.h)]  
  
##  <a name="_core_custom_events_with_stock_names"></a>Stok adlarıyla özel olaylar  
 Hem de aynı denetimi uygulayabileceğiniz değil ancak stok olaylar, aynı ada sahip özel olaylar oluşturabilirsiniz. Örneğin, stok olay tıklatın normalde tetiklendiğinde başlatılmıyor Click adlı özel bir olay oluşturmak isteyebilirsiniz. Kendi tetikleme işlevini çağırarak herhangi bir zamanda sonra Click olayını ateşle.  
  
 Aşağıdaki yordamda özel bir tıklatma ekler olay.  
  
#### <a name="to-add-a-custom-event-that-uses-a-stock-event-name"></a>Stok olay adı kullanan özel bir olay eklemek için  
  
1.  Denetiminizin proje yükleyin.  
  
2.  Sınıf Görünümü'nde ActiveX denetim sınıfınıza kısayol menüsünü açmak için sağ tıklatın.  
  
3.  Kısayol menüsünden tıklatın **Ekle** ve ardından **olay Ekle**.  
  
     Olay Ekleme Sihirbazı'nı açar.  
  
4.  İçinde **olay adı** aşağı açılan listesinde, bir stok olay adı seçin. Bu örnek için select **tıklatın**.  
  
5.  İçin **olay türü**seçin **özel**.  
  
6.  Tıklatın **son** olay oluşturamadı.  
  
7.  Çağrı `FireClick` kodunuzu uygun yerlerde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX denetimleri: yöntemler](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Sınıfı](../mfc/reference/colecontrol-class.md)
