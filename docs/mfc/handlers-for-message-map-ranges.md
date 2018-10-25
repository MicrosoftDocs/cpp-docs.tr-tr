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
ms.openlocfilehash: 738d441cf88b41740cb0cff933916489cac683f2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50073103"
---
# <a name="handlers-for-message-map-ranges"></a>İleti Eşleme Aralıkları için İşleyiciler

Bu makalede, bir dizi ileti (bir ileti için yalnızca bir işlev eşlemesi) yerine bir tek ileti işleyici işlevi eşleştirmek açıklanmaktadır.

Birden fazla ileti veya denetim bildirimi tam olarak aynı şekilde işlem gerektiğinde zamanlar vardır. Böyle zamanlarda, tüm iletiler için bir tek işleyici işlevi eşleştirmek isteyebilir. İleti eşleme aralıkları iletileri bitişik bir dizi için bunu izin ver:

- Komut kimlikleri aralıklarını eşleyebilirsiniz:

   - Bir komut işleyici işlevi.

   - Komut güncelleştirme işleyicisi işlevi.

- Denetim bildirimi iletileri Denetim kimliklerinin bir dizi için bir ileti işleyici işlevine eşleyebilirsiniz.

Bu makalede ele alınan konular:

- [İleti eşleme girişi yazma](#_core_writing_the_message.2d.map_entry)

- [İşleyici işlevi bildirme](#_core_declaring_the_handler_function)

- [Örnek aralığı için komut kimlikleri](#_core_example_for_a_range_of_command_ids)

- [Denetim kimliklerinin bir aralık için örneği](#_core_example_for_a_range_of_control_ids)

##  <a name="_core_writing_the_message.2d.map_entry"></a> İleti eşleme girişi yazma

İçinde. CPP dosyasında, aşağıdaki örnekte gösterildiği gibi ileti eşleme girişi ekleyin:

[!code-cpp[NVC_MFCMessageHandling#6](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_1.cpp)]

İleti eşleme girişi şu öğelerden oluşur:

- İleti eşleme aralığı makrosu:

   - [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range)

   - [ON_UPDATE_COMMAND_UI_RANGE](reference/message-map-macros-mfc.md#on_update_command_ui_range)

   - [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range)

- Makro parametrelerini:

   İlk iki makroları, üç parametre alır:

   - Aralığın başladığı komut kimliği

   - Aralığı bitiren komut kimliği

   - İleti işleyici işlevinin adı

   Komut kimlikleri dizi bitişik olması gerekir.

   Üçüncü makrosu `ON_CONTROL_RANGE`, ek bir ilk parametre alır: gibi bir denetim bildirimi iletisi **EN_CHANGE**.

##  <a name="_core_declaring_the_handler_function"></a> İşleyici işlevi bildirme

İşleyici işlev bildirimi ekleyin. H dosyası. Aşağıdaki kod nasıl bu görünebileceği, aşağıda gösterildiği gibi gösterir:

[!code-cpp[NVC_MFCMessageHandling#7](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_2.h)]

Tek bir komut işleyici işlevlerini normalde hiç parametre almamalıdır. Güncelleştirme işleyici işlevleri hariç olmak üzere ek bir parametre işleyici işlevleri ileti eşleme aralıkları için gerektiren *nID*, türü **UINT**. Bu parametre ilk parametre içindir. Aslında kullanıcının seçtiği hangi komutu belirtmek için gereken ek komut kimliği ekstra parametresiyle kapsar.

Güncelleştirme işleyici işlevleri için parametre gereksinimleri hakkında daha fazla bilgi için bkz. [örneği için bir aralık, komut kimlikleri](#_core_example_for_a_range_of_command_ids).

##  <a name="_core_example_for_a_range_of_command_ids"></a> Örneğin, bir aralık komut kimlikleri

Kullandığınızda bir örnektir komutları gibi MFC örnek yakınlaştırma komutu işlenirken aralıkları [HIERSVR](../visual-cpp-samples.md). Bu komutu normal boyutunun %300 ve % 25 arasında ölçeklendirme görünümü yakınlaştırır. HIERSVR'ın görünüm sınıfı bu benzeyen bir ileti eşleme girişi ile yakınlaştırma komutları işlemek için bir aralık kullanır:

[!code-cpp[NVC_MFCMessageHandling#8](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_3.cpp)]

İleti eşleme girişi yazdığınızda, aşağıdakileri belirtmeniz gerekir:

- İki bitişik aralık tarihleri arasında kimlikleri komutu.

   Bunlar şunlardır **ID_VIEW_ZOOM25** ve **ID_VIEW_ZOOM300**.

- Komutlar için işleyici işlevinin adı.

   Burada sahip `OnZoom`.

İşlev bildirimi bu benzeyecektir:

[!code-cpp[NVC_MFCMessageHandling#9](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_4.h)]

Güncelleştirme işleyici işlevlerine benzer ve daha geniş bir kullanışlı olması büyük olasılıkla durumudur. Yazma oldukça yaygındır `ON_UPDATE_COMMAND_UI` komutlarının sayısı için işleyiciler ve kendiniz yazmak veya kopyalama, aynı kodu tekrar tekrar bulun. Çözüm, bir dizi komut kimlikleri bir güncelleştirme işleyici işlevi kullanarak eşlemektir `ON_UPDATE_COMMAND_UI_RANGE` makrosu. Komut kimlikleri, bir aralıktaki oluşturması gerekir. Bir örnek için bkz. `OnUpdateZoom` işleyicisi ve kendi `ON_UPDATE_COMMAND_UI_RANGE` ileti eşleme girişi HIERSVR örneğe ait görünüm sınıfı.

İşleyici işlevleri tek komutları genellikle tek bir parametre almak için güncelleştirme *pCmdUI*, türü `CCmdUI*`. İşleyici işlevleri güncelleştirme işleyici işlevleri ileti eşleme aralıkları için ek bir parametre gerektirmeyen *nID*, türü **UINT**. Aslında kullanıcının seçtiği hangi komutu belirtmek için gereken komut kimliği bulunur `CCmdUI` nesne.

##  <a name="_core_example_for_a_range_of_control_ids"></a> Örneğin, aralığı denetim kimlikleri

Başka bir ilgi çekici çalışması Denetim kimliklerinin bir dizi denetimi bildirim iletileri için tek bir işleyici eşliyor. Kullanıcının herhangi bir 10 düğmeleri tıklayabileceği varsayalım. İleti eşleme giriş için bir işleyici tüm 10 düğmeleri eşlemek için şöyle görünebilir:

[!code-cpp[NVC_MFCMessageHandling#10](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_5.cpp)]

Yazdığınızda `ON_CONTROL_RANGE` makro, ileti eşlemesi içinde belirttiğiniz:

- Bir özel denetim bildirimi iletisi.

   Burada sahip **BN_CLICKED**.

- Denetim Kimliği bitişik aralığını denetimleri ile ilişkili değerler.

   Bunlar burada **IDC_BUTTON1** ve **IDC_BUTTON10**.

- İleti işleyici işlevinin adı.

   Burada sahip `OnButtonClicked`.

İşleyici işlevi yazdığınızda, fazladan belirtin **UINT** aşağıda gösterildiği gibi parametre:

[!code-cpp[NVC_MFCMessageHandling#11](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_6.cpp)]

`OnButtonClicked` Tek bir işleyici **BN_CLICKED** ileti herhangi bir parametre alır. Düğmeler çeşitli aynı işleyiciyi alır **UINT**. Üreten özel denetim tanımlamak için ekstra parametresiyle sağlayan **BN_CLICKED** ileti.

Örnekte gösterilen kod tipik: geçirilen değeri dönüştürme bir `int` ileti aralığı ve sunduğundan bu durum geçerlidir. Ardından hangi düğmeye tıkladı bazı farklı bir eylem sürebilir.

## <a name="see-also"></a>Ayrıca Bkz.

[İleti İşleyici İşlevlerini Bildirme](../mfc/declaring-message-handler-functions.md)
