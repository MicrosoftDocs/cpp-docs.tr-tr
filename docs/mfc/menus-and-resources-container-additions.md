---
title: 'Menüler ve Kaynaklar: Kapsayıcı Ekleme'
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
ms.openlocfilehash: c8da58316f471f7b7d26e142cc1dd1ccaa6ad8b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364789"
---
# <a name="menus-and-resources-container-additions"></a>Menüler ve Kaynaklar: Kapsayıcı Ekleme

Bu makalede, görsel düzenleme kapsayıcı uygulamasında menülerde ve diğer kaynaklarda yapılması gereken değişiklikler açıklanmaktadır.

Kapsayıcı uygulamalarında iki tür değişiklik yapılması gerekir: OLE görsel düzenlemeyi desteklemek için varolan kaynaklarda yapılan değişiklikler ve yerinde etkinleştirme için kullanılan yeni kaynakların eklenmesi. Kapsayıcı uygulamanızı oluşturmak için uygulama sihirbazını kullanırsanız, bu adımlar sizin için yapılır, ancak bazı özelleştirme gerektirebilir.

Uygulama sihirbazını kullanmazsanız, OCLIENT'a bakmak isteyebilirsiniz. RC, bu değişikliklerin nasıl uygulandığını görmek için OCLIENT örnek uygulaması için kaynak komut dosyası. MFC OLE örneği [OCLIENT'a](../overview/visual-cpp-samples.md)bakın.

Bu makalede ele alınan konular şunlardır:

- [Konteyner Menü Eklemeleri](#_core_container_menu_additions)

- [Hızlandırıcı Tablo Eklemeleri](#_core_container_application_accelerator_table_additions)

- [String Tablo Eklemeleri](#_core_string_table_additions_for_container_applications)

## <a name="container-menu-additions"></a><a name="_core_container_menu_additions"></a>Konteyner Menü Eklemeleri

Edit menüsüne aşağıdaki öğeleri eklemeniz gerekir:

|Öğe|Amaç|
|----------|-------------|
|**Yeni Nesne Ekle**|Belgeye bağlantılı veya katıştılı bir öğe eklemek için OLE Insert Object iletişim kutusunu açar.|
|**Bağlantıyı Yapıştır**|Panodaki öğeye bağlantı yıtaşarak belgeye yapıştırır.|
|**OLE Fiili**|Seçili öğenin birincil fiilini çağırır. Bu menü öğesinin metni, seçili öğenin birincil fiilini yansıtacak şekilde değişir.|
|**Bağlantılar**|Varolan bağlantılı öğeleri değiştirmek için OLE Edit Bağlantıları iletişim kutusunu açar.|

Bu makalede listelenen değişikliklere ek olarak, kaynak dosyanız AFXOLECL içermelidir. Microsoft Hazırlık Sınıfı Kitaplığı uygulaması için gerekli olan RC. Yeni Nesne Ekle tek gerekli menü ektir. Diğer öğeler eklenebilir, ancak burada listelenenler en yaygın olanlardır.

İçerdeki öğelerin yerinde etkinleştirmesini desteklemek istiyorsanız, kapsayıcı uygulamanız için yeni bir menü oluşturmanız gerekir. Bu menü, dosyalar açıkken kullanılan aynı Dosya menüsü ve Pencere açılır menülerinden oluşur, ancak aralarında iki ayırıcı bulunur. Bu ayırıcılar, sunucu (bileşen) öğesinin (uygulamanın) etkinleştirildiğinde menülerini nereye yerleştirmesi gerektiğini belirtmek için kullanılır. Bu menü birleştirme tekniği hakkında daha fazla bilgi için [Menüler ve Kaynaklar: Menü Birleştirme'ye](../mfc/menus-and-resources-menu-merging.md)bakın.

## <a name="container-application-accelerator-table-additions"></a><a name="_core_container_application_accelerator_table_additions"></a>Konteyner Uygulama Hızlandırıcı Tablo Eklemeleri

Yerinde etkinleştirme destekliyorsanız, kapsayıcı uygulamasının hızlandırıcı tablosu kaynaklarında küçük değişiklikler yapılması gerekir. İlk değişiklik, kullanıcının yerinde düzenleme modunu iptal etmek için kaçış tuşuna (ESC) basmasına olanak tanır. Ana hızlandırıcı tablosuna aşağıdaki girişi ekleyin:

|Kimlik|Anahtar|Tür|
|--------|---------|----------|
|ID_CANCEL_EDIT_CNTR|VK_ESCAPE|**VIRTKEY**|

İkinci değişiklik, yerinde etkinleştirme için oluşturulan yeni menü kaynağına karşılık gelen yeni bir hızlandırıcı tablosu oluşturmaktır. Bu tablo, yukarıdaki VK_ESCAPE girişine ek olarak Dosya ve Pencere menüleri için girişlere sahiptir. Aşağıdaki örnek, MFC örnek [CONTAINER'ta](../overview/visual-cpp-samples.md)yerinde etkinleştirme için oluşturulan hızlandırıcı tablosudur:

|Kimlik|Anahtar|Tür|
|--------|---------|----------|
|ID_FILE_NEW|CTRL+N|**VIRTKEY**|
|ID_FILE_OPEN|CTRL+O|**VIRTKEY**|
|ID_FILE_SAVE|CTRL+S|**VIRTKEY**|
|ID_FILE_PRINT|CTRL+P|**VIRTKEY**|
|ID_NEXT_PANE|VK_F6|**VIRTKEY**|
|ID_PREV_PANE|SHIFT+VK_F6|**VIRTKEY**|
|ID_CANCEL_EDIT_CNTR|VK_ESCAPE|**VIRTKEY**|

## <a name="string-table-additions-for-container-applications"></a><a name="_core_string_table_additions_for_container_applications"></a>Kapsayıcı Uygulamaları için String Tablo Eklemeleri

Kapsayıcı uygulamaları için dize tablolarındaki değişikliklerin [çoğu, Kapsayıcı Menü Eklemeleri'nde](#_core_container_menu_additions)belirtilen ek menü öğelerine karşılık gelir. Her menü öğesi görüntülendiğinde durum çubuğunda görüntülenen metni verirler. Örnek olarak, uygulama sihirbazı oluşturur dize tablo girişleri şunlardır:

|Kimlik|Dize|
|--------|------------|
|IDP_OLE_INIT_FAILED|OLE başlatma başarısız oldu. OLE kitaplıklarının doğru sürüm olduğundan emin olun.|
|IDP_FAILED_TO_CREATE|Nesne oluşturmak için başarısız oldu. Nesnenin sistem kayıt defterine girilen emin olun.|

## <a name="see-also"></a>Ayrıca bkz.

[Menüler ve Kaynaklar (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Menüler ve Kaynaklar: Sunucu Ekleme](../mfc/menus-and-resources-server-additions.md)
