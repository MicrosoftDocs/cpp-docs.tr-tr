---
title: İleti eşleme aralıkları için işleyiciler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handlers [MFC]
- handlers [MFC], message-map ranges
- message maps [MFC], message handler functions
- message maps [MFC], ranges
- control-notification messages [MFC]
- command IDs [MFC], message mapping
- message-map ranges [MFC]
- handlers [MFC]
- message handling [MFC], message handler functions
- mappings [MFC], message ranges
- command handling [MFC], command update handlers
- controls [MFC], notifications
- handler functions [MFC], message-map ranges
- handler functions [MFC]
- command update handlers [MFC]
- command routing [MFC], command update handlers
- message ranges [MFC]
- handler functions [MFC], declaring
- message ranges [MFC], mapping
ms.assetid: a271478b-5e1c-46f5-9f29-e5be44b27d08
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be596ea38a8d0a3919ed43d9c5478bb0127032d9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351728"
---
# <a name="handlers-for-message-map-ranges"></a>İleti Eşleme Aralıkları için İşleyiciler
Bu makalede, bir dizi iletileri (yerine tek bir ileti için yalnızca bir işlev eşleme) tek bir ileti işleyicisi işlevi eşlemek açıklanmaktadır.  
  
 Birden fazla ileti veya denetim bildirim tam olarak aynı şekilde işlem gerektiğinde zamanlar vardır. Böyle zamanlarda tüm iletileri bir tek işleyici işlevi eşleme isteyebilir. İleti eşleme aralıkları iletileri bitişik aralığı için bunu izin ver:  
  
-   Komut kimlikleri aralıklarına eşleyebilirsiniz:  
  
    -   Bir komut işleyici işlevi.  
  
    -   Komut güncelleştirme işleyici işlevi.  
  
-   Denetim bildirimi iletileri Denetim kimliklerinin aralığı için bir ileti işleyicisi işleve eşleyebilirsiniz.  
  
 Bu makalede ele alınan konular şunlardır:  
  
-   [İleti eşleme girişi yazma](#_core_writing_the_message.2d.map_entry)  
  
-   [İşleyici işlevi bildirme](#_core_declaring_the_handler_function)  
  
-   [Komut kimlikleri için bir aralığı örneği](#_core_example_for_a_range_of_command_ids)  
  
-   [Denetim kimliklerinin aralığı örneği](#_core_example_for_a_range_of_control_ids)  
  
##  <a name="_core_writing_the_message.2d.map_entry"></a> İleti eşleme girişi yazma  
 İçinde. CPP dosya, aşağıdaki örnekte gösterildiği gibi ileti eşleme girişi ekleyin:  
  
 [!code-cpp[NVC_MFCMessageHandling#6](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_1.cpp)]  
  
 İleti eşleme girişi aşağıdaki öğelerden oluşur:  
  
-   İleti eşleme aralığı makrosu:  
  
    -   [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range)  
  
    -   [ON_UPDATE_COMMAND_UI_RANGE](reference/message-map-macros-mfc.md#on_update_command_ui_range)  
  
    -   [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range)  
  
-   Makro parametrelerini:  
  
     İlk iki makroları üç parametre alın:  
  
    -   Aralığın başladığı komut kimliği  
  
    -   Aralığın bittiği komut kimliği  
  
    -   İleti işleyici işlevin adı  
  
     Komut kimlikleri aralığını bitişik olmalıdır.  
  
     Üçüncü makrosu `ON_CONTROL_RANGE`, ek bir ilk parametre alır: denetim bildirim iletisi, gibi **EN_CHANGE**.  
  
##  <a name="_core_declaring_the_handler_function"></a> İşleyici işlevi bildirme  
 İşleyici işlevi bildiriminde ekleyin. H dosyası. Aşağıdaki kodu nasıl bu görünebileceği, aşağıda gösterildiği gibi gösterilir:  
  
 [!code-cpp[NVC_MFCMessageHandling#7](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_2.h)]  
  
 İşleyici işlevleri tek komutlar için normalde hiç parametre almaz. Güncelleştirme işleyici işlevleri dışında işleyici işlevleri ileti eşleme aralıkları için fazladan bir parametre gerektiren `nID`, türü **UINT**. Bu parametre ilk parametre olur. Ek parametre kullanıcının gerçekten seçtiği hangi komutu belirtmek için gereken ek komut kimliği düzenler.  
  
 İşleyici işlevleri güncelleştirmek için parametre gereksinimleri hakkında daha fazla bilgi için bkz: [örnek için bir aralığı, komut kimlikleri](#_core_example_for_a_range_of_command_ids).  
  
##  <a name="_core_example_for_a_range_of_command_ids"></a> Örneğin, bir aralığı komut kimlikleri  
 Kullandığınızda, bir örnektir yakınlaştırma komutu MFC örnekteki gibi komutları işlenirken aralıkları [HIERSVR](../visual-cpp-samples.md). Bu komut, normal boyutunun %300 ve % 25 arasında ölçeklendirme görünümü büyütür. HIERSVR'ın view sınıfı bu benzeyen bir ileti eşleme girdisi ile Yakınlaştırma komutlarını işlemek için bir aralığı kullanır:  
  
 [!code-cpp[NVC_MFCMessageHandling#8](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_3.cpp)]  
  
 İleti eşleme girdisi yazarken aşağıdakileri belirtmeniz gerekir:  
  
-   Başlangıç ve bitiş bir aralıktaki iki komut kimlikleri.  
  
     Burada oldukları `ID_VIEW_ZOOM25` ve `ID_VIEW_ZOOM300`.  
  
-   Komutlar için işleyici işlevi adı.  
  
     Burada sahip `OnZoom`.  
  
 İşlev bildirimi bu benzeyecektir:  
  
 [!code-cpp[NVC_MFCMessageHandling#9](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_4.h)]  
  
 Güncelleştirme işleyici işlevlerin benzer ve yaygın olarak daha kullanışlı olması olası bir durumdur. Yazma oldukça yaygındır `ON_UPDATE_COMMAND_UI` komutlarının sayısı için işleyiciler kendiniz yazmak veya kopyalama, aynı kodu tekrar tekrar bulun. Komut kimlikleri bir güncelleştirme işleyici işlevini kullanarak bir dizi eşlemek için çözümdür `ON_UPDATE_COMMAND_UI_RANGE` makrosu. Komut kimlikleri bir aralıktaki oluşturması gerekir. Bir örnek için bkz: **OnUpdateZoom** işleyici ve onun `ON_UPDATE_COMMAND_UI_RANGE` HIERSVR örnek ait görünüm sınıfı ileti eşleme girişi.  
  
 İşleyici işlevleri tek komutları normal olarak tek bir parametre alan için güncelleştirme `pCmdUI`, türü **Ccmduı\***. İşleyici işlevleri, güncelleştirme işleyici işlevleri ileti eşleme aralıkları için fazladan bir parametre gerektirmez `nID`, türü **UINT**. Kullanıcı gerçekte seçti komutu belirtmek için gereken komut kimliği bulunan `CCmdUI` nesnesi.  
  
##  <a name="_core_example_for_a_range_of_control_ids"></a> Örneğin, bir denetim aralığı kimlikleri  
 Başka bir ilginç örneği Denetim kimliklerinin bir dizi denetim bildirimi iletileri tek bir işleyicisine eşlemek anlamına gelir. Kullanıcı'nın 10 düğmesinden herhangi birini tıklatın varsayalım. Tüm 10 düğmeleri bir işleyicisine eşlemek için ileti eşlemesi girişinizin şöyle olabilir:  
  
 [!code-cpp[NVC_MFCMessageHandling#10](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_5.cpp)]  
  
 Yazdığınız zaman `ON_CONTROL_RANGE` makro ileti eşlemesi içinde belirtin:  
  
-   Bir özel denetim bildirim iletisi.  
  
     Burada sahip **BN_CLICKED**.  
  
-   Denetim Kimliği denetimleri bitişik aralığı ile ilişkili değerler.  
  
     Bunlar burada `IDC_BUTTON1` ve `IDC_BUTTON10`.  
  
-   İleti işleyici işlevin adı.  
  
     Burada sahip `OnButtonClicked`.  
  
 İşleyici işlev yazdığınızda, ek belirtin **UINT** aşağıda gösterildiği gibi parametre:  
  
 [!code-cpp[NVC_MFCMessageHandling#11](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_6.cpp)]  
  
 `OnButtonClicked` Tek bir işleyici **BN_CLICKED** ileti hiçbir parametre alır. Bir dizi düğmeleri için aynı işleyici alır **UINT**. Belirli denetimi oluşturmak için sorumlu tanımlamak için ek parametresi verir **BN_CLICKED** ileti.  
  
 Örnekte gösterilen kodu tipik: geçirilen değerini dönüştürme bir `int` ileti aralığı ve bu durumda olduğunu belirten içinde. Ardından hangi düğmesi tıklandığını bazı farklı eylem sürebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İleti İşleyici İşlevlerini Bildirme](../mfc/declaring-message-handler-functions.md)
