---
title: 'Menüler ve kaynaklar: Kapsayıcı ekleme'
ms.date: 11/04/2016
f1_keywords:
- IDP_OLE_INIT_FAILED
- IDP_FAILED_TO_CREATE
- VK_ESCAPE
helpviewer_keywords:
- application accelerator table [MFC]
- VK_ESCAPE key [MFC]
- IDP_FAILED_TO_CREATE macro [MFC]
- visual editing, application menus and resources
- OLE containers [MFC], menus and resources
- accelerator tables [MFC], container applications
- IDP_OLE_INIT_FAILED macro [MFC]
- CONTAIN tutorial [MFC]
- Links menu item [MFC]
ms.assetid: 425448be-8ca0-412e-909a-a3a9ce845288
ms.openlocfilehash: b1a74fef743592d3d052226dac926fc7ddc58578
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58770349"
---
# <a name="menus-and-resources-container-additions"></a>Menüler ve kaynaklar: Kapsayıcı ekleme

Bu makalede, menüler ve görsel düzenleme kapsayıcısı uygulamasında diğer kaynaklar için yapılması gereken değişiklikleri açıklar.

Kapsayıcı uygulamalar, iki tür değişiklik yapılması gereken: OLE görsel düzenleme ve yerinde etkinleştirme için kullanılan yeni kaynaklar desteklemek için mevcut kaynaklar yapılan değişiklikler. Kapsayıcı uygulamanızı oluşturmak için Uygulama Sihirbazı'nı kullanırsanız aşağıdaki adımları sizin yerinize yapılır, ancak bunların bazı özelleştirme gerektirebilir.

Uygulama Sihirbazı'nı kullanmıyorsanız OCLIENT aramak isteyebilirsiniz. RC, bu değişiklikleri nasıl uygulandığını görmek için OCLIENT örnek uygulama için kaynak betiği. MFC OLE örnek görmek [OCLIENT](../overview/visual-cpp-samples.md).

Bu makalede ele alınan konular:

- [Kapsayıcı menü ekleme](#_core_container_menu_additions)

- [Hızlandırıcı tablo ekleme](#_core_container_application_accelerator_table_additions)

- [Dize tablosu ekleme](#_core_string_table_additions_for_container_applications)

##  <a name="_core_container_menu_additions"></a> Kapsayıcı menü ekleme

Aşağıdaki öğeler için düzenleme menüsünü eklemeniz gerekir:

|Öğe|Amaç|
|----------|-------------|
|**Yeni Nesne Ekle**|Belgeye bağlantılı veya katıştırılmış bir öğe eklemek için OLE Insert Object iletişim kutusu açılır.|
|**Yapıştır**|Öğenin bağlantısını panoya belgenin içine yapıştırır.|
|**OLE fiili**|Seçilen öğenin birincil fiil çağırır. Seçilen öğenin birincil fiil yansıtmak üzere bu menü öğesi değişikliklerini metni.|
|**Bağlantılar**|Mevcut bağlantılı öğeleri değiştirmek için OLE Edit Links iletişim kutusu açılır.|

Bu makalede listelenen değişiklikleri ek olarak, kaynak dosyanız AFXOLECL içermelidir. RC için Microsoft Foundation Class Kitaplığı uygulaması gereklidir. Yeni nesne eklemeyi, yalnızca gerekli menü ektir. Diğer öğeler eklenebilir, ancak burada listelenen yaygın olanlardır.

İçerilen öğelerin yerinde etkinleştirmeyi desteklemek istiyorsanız, kapsayıcı uygulamanız için yeni menü oluşturmanız gerekir. Bu menü aynı dosya menüsü ve dosya açıksa, ancak iki ayırıcılar aralarına yerleştirilmiş sahip kullanılan penceresi açılır menüler oluşur. Bu ayırıcı (uygulama) sunucu (Bileşen) öğesi menülerini yerinde etkinleştirildiğinde nereye belirtmek için kullanılır. Bu menü birleştirme teknik hakkında daha fazla bilgi için bkz. [menüler ve kaynaklar: Menü birleştirme](../mfc/menus-and-resources-menu-merging.md).

##  <a name="_core_container_application_accelerator_table_additions"></a> Kapsayıcı uygulama Hızlandırıcı tablosu ekleme

Yerinde etkinleştirme destekleniyorsa, bir kapsayıcı uygulama Hızlandırıcı tablosu kaynaklarına küçük değişiklikler gereklidir. İlk değişiklik kaçış yerinde düzenleme moduna iptal (ESC) tuşuna izin verir. Ana Hızlandırıcı tablosunu şu girişi ekleyin:

|Kimlik|Anahtar|Tür|
|--------|---------|----------|
|ID_CANCEL_EDIT_CNTR|VK_ESCAPE|**VIRTKEY'E**|

İkinci değişiklik yerinde etkinleştirme için oluşturulan yeni menü kaynağı karşılık gelen yeni bir Hızlandırıcı tablosu oluşturmaktır. Bu tablo, yukarıdaki VK_ESCAPE giriş yanı sıra dosya ve pencere menüleri girişlerine sahiptir. Aşağıdaki örnek, yerinde etkinleştirme MFC örneğinde oluşturulan Hızlandırıcı tablo [KAPSAYICI](../overview/visual-cpp-samples.md):

|Kimlik|Anahtar|Tür|
|--------|---------|----------|
|ID_FILE_NEW|CTRL+N|**VIRTKEY'E**|
|ID_FILE_OPEN|CTRL+O|**VIRTKEY'E**|
|ID_FILE_SAVE|CTRL+S|**VIRTKEY'E**|
|ID_FILE_PRINT|CTRL+P|**VIRTKEY'E**|
|ID_NEXT_PANE|VK_F6|**VIRTKEY'E**|
|ID_PREV_PANE|SHIFT+VK_F6|**VIRTKEY'E**|
|ID_CANCEL_EDIT_CNTR|VK_ESCAPE|**VIRTKEY'E**|

##  <a name="_core_string_table_additions_for_container_applications"></a> Kapsayıcı uygulamaları için dize tablosu ekleme

Dize tabloları kapsayıcı uygulamaları için yapılan çoğu karşılık gelen belirtilen ek menü öğelerine [kapsayıcı menü eklemeleri](#_core_container_menu_additions). Bunlar, her bir menü öğesi görüntülendiğinde durum çubuğunda gösterilen metin sağlayın. Örneğin, Uygulama Sihirbazı oluşturur dize tablo girişleri şunlardır:

|Kimlik|Dize|
|--------|------------|
|IDP_OLE_INIT_FAILED|OLE başlatma başarısız oldu. OLE kitaplıklarının doğru sürümde olduğundan emin olun.|
|IDP_FAILED_TO_CREATE|Nesne oluşturulamadı. Nesnenin sistem kayıt defterine girildiğinden emin olun.|

## <a name="see-also"></a>Ayrıca bkz.

[Menüler ve Kaynaklar (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Menüler ve kaynaklar: Sunucu ekleme](../mfc/menus-and-resources-server-additions.md)
