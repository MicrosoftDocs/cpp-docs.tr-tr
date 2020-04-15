---
title: İleti Eşleme Aralıkları için İşleyiciler
ms.date: 11/04/2016
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
ms.openlocfilehash: fc33df6957beab6e4e8de3093dfc00cf2651780e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370517"
---
# <a name="handlers-for-message-map-ranges"></a>İleti Eşleme Aralıkları için İşleyiciler

Bu makalede, ileti aralığının tek bir ileti işleyicisi işleviyle nasıl eşleneniz açıklanmaktadır (bir iletiyi yalnızca bir işleve eşlemek yerine).

Birden fazla iletiyi işlemeniz veya bildirimi tam olarak aynı şekilde denetlemeniz gereken zamanlar vardır. Bu gibi zamanlarda, tüm iletileri tek bir işleyici işleviyle eşlemek isteyebilirsiniz. İleti eşlemi aralıkları, bitişik bir ileti aralığı için bunu yapmanıza olanak sağlar:

- Komut işleri aralarını şeşeşe şeyilerle haritalayabilirsiniz:

  - Komut işleyici işlevi.

  - Komut güncelleştirme işleyicisi işlevi.

- Denetim bildirimleri iletilerini bir ileti işleyicisi işleviyle eşleyebilirsiniz.

Bu makalede ele alınan konular şunlardır:

- [İleti-eş-giriş yazma](#_core_writing_the_message.2d.map_entry)

- [İşleyici işlevini bildirme](#_core_declaring_the_handler_function)

- [Bir dizi komut işlisi için çatış](#_core_example_for_a_range_of_command_ids)

- [Bir dizi denetim işletmek için çatış](#_core_example_for_a_range_of_control_ids)

## <a name="writing-the-message-map-entry"></a><a name="_core_writing_the_message.2d.map_entry"></a>İleti-Harita Girişi yazma

İçinde. CPP dosyası, aşağıdaki örnekte gösterildiği gibi, ileti-harita girişi ekleyin:

[!code-cpp[NVC_MFCMessageHandling#6](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_1.cpp)]

İleti-eşlemi girişi aşağıdaki öğelerden oluşur:

- İleti-eşlemi aralığı makrosu:

  - [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range)

  - [ON_UPDATE_COMMAND_UI_RANGE](reference/message-map-macros-mfc.md#on_update_command_ui_range)

  - [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range)

- Makroparametreleri:

  İlk iki makro üç parametre alır:

  - Aralığı başlatan komut kimliği

  - Aralığı sona erdirebilen komut kimliği

  - İleti işleyicisi işlevinin adı

  Komut işleri diziliMi bitişik olmalıdır.

  Üçüncü makro, `ON_CONTROL_RANGE`ek bir ilk parametre alır: **EN_CHANGE**gibi bir denetim bildirim iletisi.

## <a name="declaring-the-handler-function"></a><a name="_core_declaring_the_handler_function"></a>İşleyici Işlevini Bildirme

İşleyici işlev bildirgenizi . H dosyası. Aşağıdaki kod, aşağıda gösterildiği gibi, bunun nasıl görünebileceğini gösterir:

[!code-cpp[NVC_MFCMessageHandling#7](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_2.h)]

Tek komutlar için işleyici işlevleri normalde hiçbir parametre alır. Güncelleştirme işleyicisi işlevleri dışında, ileti eşleme aralıkları için işleyici işlevleri ekstra bir parametre, *nID*, tip **UINT**gerektirir. Bu parametre ilk parametredir. Ek parametre, kullanıcının gerçekte hangi komutu seçtiğini belirtmek için gereken ek komut kimliğini barındırır.

İşleyici işlevlerini güncelleştirmek [için](#_core_example_for_a_range_of_command_ids)parametre gereksinimleri hakkında daha fazla bilgi için bkz.

## <a name="example-for-a-range-of-command-ids"></a><a name="_core_example_for_a_range_of_command_ids"></a>Komut Dizileri için örnek

Aralıkları ne zaman kullanabilirsiniz Bir örnek MFC örnek [HIERSVR](../overview/visual-cpp-samples.md)Zoom komutu gibi komutları işleme olduğunu. Bu komut görünümü yakınlaştırır ve normal boyutunun %25 ila %300'ü arasında ölçekler. HIERSVR'ın görünüm sınıfı, Yakınlaştırma komutlarını buna benzeyen bir ileti eşlemi girişiyle işlemek için bir aralık kullanır:

[!code-cpp[NVC_MFCMessageHandling#8](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_3.cpp)]

İleti-eş-eş girişi yazarken şunları belirtirsiniz:

- İki komut işlisi, bitişik bir dizinin başlatılıp sona ermesi.

   Burada **ID_VIEW_ZOOM25** ve **ID_VIEW_ZOOM300.**

- Komutlar için işleyici işlevinin adı.

   İşte `OnZoom`burada.

İşlev bildirimi buna benzer:

[!code-cpp[NVC_MFCMessageHandling#9](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_4.h)]

Güncelleştirme işleyiciişlevleri nin durumu benzerdir ve daha yaygın olarak yararlı olma olasılığı yüksektir. Bir dizi komut için `ON_UPDATE_COMMAND_UI` işleyiciler yazmak ve kendinizi aynı kodu tekrar tekrar yazarken veya kopyalamak oldukça yaygındır. Çözüm, makroyu kullanarak bir güncelleştirme işleyicisi işleviyle `ON_UPDATE_COMMAND_UI_RANGE` bir dizi komut iD eşlenebilmektir. Komut işleri bitişik bir araç oluşturması gerekir. Örneğin, HIERSVR `OnUpdateZoom` örneğinin `ON_UPDATE_COMMAND_UI_RANGE` görünüm sınıfında işleyicive ileti eşlem girişine bakın.

Tek komutlar için güncelleştirme işleyicisi işlevleri normalde tek bir parametre, *pCmdUI*, türü `CCmdUI*`. İşleyici işlevlerinin aksine, ileti eşleme aralıkları için güncelleştirme işleyicisi işlevleri ekstra bir parametre, *nID*, **uint**türü gerektirmez. Kullanıcının gerçekte hangi komutu seçtiğini belirtmek için gereken komut `CCmdUI` kimliği nesnede bulunur.

## <a name="example-for-a-range-of-control-ids"></a><a name="_core_example_for_a_range_of_control_ids"></a>Denetim II Aralığı örneği

Başka bir ilginç durum, denetim işlemi diziliMi için denetim bildirim iletilerini tek bir işleyiciye günüyorum. Kullanıcının 10 düğmeden herhangi birini tıklatabileceğini varsayalım. 10 düğmenin tümini tek bir işleyiciyle eşlemek için, ileti-harita girişiniz şu şekilde görünür:

[!code-cpp[NVC_MFCMessageHandling#10](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_5.cpp)]

İleti haritanıza `ON_CONTROL_RANGE` makroyu yazarken şunları belirtirsiniz:

- Belirli bir denetim bildirimi iletisi.

   İşte **BN_CLICKED.**

- Bitişik denetim aralığıyla ilişkili denetim kimliği değerleri.

   Burada **IDC_BUTTON1** ve **IDC_BUTTON10**.

- İleti işleyicisi işlevinin adı.

   İşte `OnButtonClicked`burada.

İşleyici işlevini yazarken, aşağıdakilerde gösterildiği gibi ekstra **UINT** parametresini belirtin:

[!code-cpp[NVC_MFCMessageHandling#11](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_6.cpp)]

Tek `OnButtonClicked` bir **BN_CLICKED** iletinin işleyicisi parametre almaz. Düğmeleri bir dizi için aynı işleyici bir **UINT**alır. Ek **parametre, BN_CLICKED** iletisi oluşturmaktan sorumlu belirli denetimi tanımlamaya olanak tanır.

Örnekte gösterilen kod tipiktir: ileti aralığında geçirilen `int` değeri dönüştürme ve bunun böyle olduğunu ileri sürün. Ardından, hangi düğmenin tıklandığına bağlı olarak farklı bir eylemde olabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[İleti İşleyici İşlevlerini Bildirme](../mfc/declaring-message-handler-functions.md)
