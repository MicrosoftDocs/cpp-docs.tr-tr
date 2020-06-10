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
ms.openlocfilehash: 0ff9178679792929bbd6eb92bb6148cfa008dcad
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621689"
---
# <a name="handlers-for-message-map-ranges"></a>İleti Eşleme Aralıkları için İşleyiciler

Bu makalede bir ileti aralığının tek bir ileti işleyicisi işlevine nasıl eşlendiği açıklanmaktadır (bir iletiyi yalnızca bir işlevle eşlemek yerine).

Birden fazla ileti veya denetim bildirimini tamamen aynı şekilde işleyebilmeniz gereken zamanlar vardır. Bu gibi zamanlarda, tüm iletileri tek bir işleyici işlevine eşlemek isteyebilirsiniz. İleti eşleme aralıkları bunu bitişik bir ileti aralığı için yapmanıza olanak sağlar:

- Komut kimliği aralıklarını şu şekilde eşleyebilirsiniz:

  - Bir komut işleyici işlevi.

  - Bir komut güncelleştirme işleyicisi işlevi.

- Bir denetim kimliği aralığı için denetim bildirimi iletilerini bir ileti işleyicisi işlevine eşleyebilirsiniz.

Bu makalede ele alınan konular şunları içerir:

- [İleti eşleme girdisini yazma](#_core_writing_the_message.2d.map_entry)

- [Handler işlevini bildirme](#_core_declaring_the_handler_function)

- [Bir dizi komut kimliği için örnek](#_core_example_for_a_range_of_command_ids)

- [Bir dizi denetim kimliği için örnek](#_core_example_for_a_range_of_control_ids)

## <a name="writing-the-message-map-entry"></a><a name="_core_writing_the_message.2d.map_entry"></a>Ileti eşleme girdisini yazma

İçinde. Aşağıdaki örnekte gösterildiği gibi, CPP dosyası, ileti eşleme girdinizi ekleyin:

[!code-cpp[NVC_MFCMessageHandling#6](codesnippet/cpp/handlers-for-message-map-ranges_1.cpp)]

İleti eşleme girişi aşağıdaki öğelerden oluşur:

- İleti eşleme aralığı makrosu:

  - [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range)

  - [ON_UPDATE_COMMAND_UI_RANGE](reference/message-map-macros-mfc.md#on_update_command_ui_range)

  - [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range)

- Makroya yönelik parametreler:

  İlk iki makro üç parametre alır:

  - Aralığı başlatan komut KIMLIĞI

  - Aralığı sonlandıran komut KIMLIĞI

  - İleti işleyici işlevinin adı

  Komut kimlikleri aralığı bitişik olmalıdır.

  Üçüncü makro `ON_CONTROL_RANGE` ek bir ilk parametre alır: **EN_CHANGE**gibi bir denetim bildirimi iletisi.

## <a name="declaring-the-handler-function"></a><a name="_core_declaring_the_handler_function"></a>Handler Işlevini bildirme

İşleyicisine işleyici işlev bildirimini ekleyin. H dosyası. Aşağıdaki kod, aşağıda gösterildiği gibi bunun nasıl görünebileceğini göstermektedir:

[!code-cpp[NVC_MFCMessageHandling#7](codesnippet/cpp/handlers-for-message-map-ranges_2.h)]

Tek komutların işleyici işlevleri normalde hiçbir parametre almaz. Güncelleştirme işleyicisi işlevleri dışında, ileti eşleme aralıkları için işleyici işlevleri, **UINT**türünde ek bir parametre ( *NID*) gerektirir. Bu parametre ilk parametredir. Ek parametre, kullanıcının gerçekten seçtiği komutu belirtmek için gereken ek komut KIMLIĞINI karşılar.

İşleyici işlevlerinin güncelleştirilmesi için parametre gereksinimleri hakkında daha fazla bilgi için bkz. [bir dizi komut kimliği Için örnek](#_core_example_for_a_range_of_command_ids).

## <a name="example-for-a-range-of-command-ids"></a><a name="_core_example_for_a_range_of_command_ids"></a>Bir dizi komut kimliği için örnek

Aralıkları ne zaman kullanabilirsiniz bir örnek, MFC örnek [Hiersvr](../overview/visual-cpp-samples.md)içindeki yakınlaştırma komutu gibi komutları işlemek. Bu komut görünümü büyütür, normal boyutunun %25 ve %300 arasında ölçeklendirin. HIERSVR 'ın View sınıfı, şu şekilde bir ileti eşleme girişi ile Yakınlaştırma komutlarını işlemek için bir Aralık kullanır:

[!code-cpp[NVC_MFCMessageHandling#8](codesnippet/cpp/handlers-for-message-map-ranges_3.cpp)]

İleti eşleme girişini yazdığınızda şunu belirtirsiniz:

- İki komut kimliği, bitişik bir aralığın başlangıcı ve sonu.

   Burada **ID_VIEW_ZOOM25** ve **ID_VIEW_ZOOM300**.

- Komutların işleyici işlevinin adı.

   İşte bu `OnZoom` .

İşlev bildirimi şuna benzer:

[!code-cpp[NVC_MFCMessageHandling#9](codesnippet/cpp/handlers-for-message-map-ranges_4.h)]

Güncelleştirme işleyici işlevlerinin durumu benzerdir ve büyük olasılıkla daha yaygın olarak yararlı olabilir. `ON_UPDATE_COMMAND_UI`Bir dizi komut için işleyiciler yazmak ve aynı kodu üzerine ve üzerine yazmak ya da kopyalamak için oldukça yaygındır. Çözüm, makro kullanarak bir dizi komut kimliğini tek bir güncelleştirme işleyici işlevine eşlemedir `ON_UPDATE_COMMAND_UI_RANGE` . Komut kimlikleri bitişik bir Aralık olarak ayarlanmalıdır. Bir örnek için, `OnUpdateZoom` `ON_UPDATE_COMMAND_UI_RANGE` HIERSVR örneğinin görünüm sınıfındaki işleyicisine ve onun ileti eşleme girdisine bakın.

Tek komutların güncelleştirme işleyici işlevleri normalde tek bir parametreyi alır, *pCmdUI* `CCmdUI*` . İşleyici işlevlerinin aksine, ileti eşleme aralıkları için güncelleştirme işleyici işlevleri, **UINT**türünde ek bir parametre ( *NID*) gerektirmez. Kullanıcının gerçekten seçtiği komutu belirtmek için gereken komut KIMLIĞI, `CCmdUI` nesnesinde bulunur.

## <a name="example-for-a-range-of-control-ids"></a><a name="_core_example_for_a_range_of_control_ids"></a>Bir dizi denetim kimliği için örnek

Başka bir ilgi çekici durum, denetim kimliği aralığı için tek bir işleyiciye yönelik denetim bildirimi iletilerini eşleme. Kullanıcının 10 ' un üzerinde herhangi bir düğmeye tıklabildiğini varsayalım. Tüm 10 düğmelerini tek bir işleyiciye eşlemek için ileti eşleme girdiniz şöyle görünür:

[!code-cpp[NVC_MFCMessageHandling#10](codesnippet/cpp/handlers-for-message-map-ranges_5.cpp)]

`ON_CONTROL_RANGE`Makroyu ileti haritanızda yazdığınızda şunu belirtirsiniz:

- Belirli bir denetim bildirimi iletisi.

   İşte **BN_CLICKED**.

- Denetimlerin bitişik aralığıyla ilişkili denetim KIMLIĞI değerleri.

   Burada **IDC_BUTTON1** ve **IDC_BUTTON10**.

- İleti işleyici işlevinin adı.

   İşte bu `OnButtonClicked` .

İşleyici işlevini yazdığınızda, aşağıdaki şekilde gösterildiği gibi ek **UINT** parametresini belirtin:

[!code-cpp[NVC_MFCMessageHandling#11](codesnippet/cpp/handlers-for-message-map-ranges_6.cpp)]

`OnButtonClicked`Tek bir **BN_CLICKED** ileti için işleyici parametre alır. Bir dizi düğme için aynı işleyici bir **UINT**alır. Ek parametre, **BN_CLICKED** iletisini oluşturmaktan sorumlu belirli bir denetimi tanımlamaya olanak sağlar.

Örnekte gösterilen kod tipik bir durumdur: ileti aralığı içinde bir öğesine geçirilen değeri dönüştürme `int` ve bu durumun bu olduğunu ele alıyoruz. Ardından, hangi düğmeye tıklandığına bağlı olarak bazı farklı eylemlere sahip olabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[İleti İşleyici İşlevlerini Bildirme](declaring-message-handler-functions.md)
