---
description: 'Daha fazla bilgi edinin: menüler ve kaynaklar: kapsayıcı eklemeleri'
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
ms.openlocfilehash: e32167e66693587a32732c1c20fc6d85d3010ecb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253370"
---
# <a name="menus-and-resources-container-additions"></a>Menüler ve Kaynaklar: Kapsayıcı Ekleme

Bu makalede, görsel olarak düzenlenen bir kapsayıcı uygulamasında menülerde ve diğer kaynaklarda yapılması gereken değişiklikler açıklanmaktadır.

Kapsayıcı uygulamalarında iki tür değişiklik yapılması gerekir: OLE görsel düzenlemesini ve yerinde etkinleştirme için kullanılan yeni kaynakların eklenmesini desteklemek için mevcut kaynaklarda yapılan değişiklikler. Kapsayıcı uygulamanızı oluşturmak için uygulama Sihirbazı 'nı kullanırsanız, bu adımlar sizin için yapılır ancak bazı özelleştirmeler gerektirebilir.

Uygulama Sihirbazı 'nı kullanmıyorsanız, OCLIENT 'a bakmak isteyebilirsiniz. RC, bu değişikliklerin nasıl uygulandığını görmek için OCLIENT örnek uygulamasına yönelik kaynak betiği. Bkz. MFC OLE örnek [Oclient](../overview/visual-cpp-samples.md).

Bu makalede ele alınan konular şunları içerir:

- [Kapsayıcı menüsü eklemeleri](#_core_container_menu_additions)

- [Hızlandırıcı tablo eklemeleri](#_core_container_application_accelerator_table_additions)

- [Dize tablosu eklemeleri](#_core_string_table_additions_for_container_applications)

## <a name="container-menu-additions"></a><a name="_core_container_menu_additions"></a> Kapsayıcı menüsü eklemeleri

Düzenleme menüsüne aşağıdaki öğeleri eklemeniz gerekir:

|Öğe|Amaç|
|----------|-------------|
|**Yeni nesne Ekle**|Belgeye bağlantılı veya katıştırılmış bir öğe eklemek için OLE nesne Ekle iletişim kutusunu açar.|
|**Bağlantıyı Yapıştır**|Panodaki öğenin bağlantısını belgeye yapıştırır.|
|**OLE fiili**|Seçilen öğenin birincil fiilini çağırır. Bu menü öğesinin metni, seçilen öğenin birincil fiilini yansıtacak şekilde değişir.|
|**Bağlantılar**|Varolan bağlantılı öğeleri değiştirmek için OLE düzenleme bağlantıları iletişim kutusunu açar.|

Bu makalede listelenen değişikliklere ek olarak, kaynak dosyanız AFXOLECL içermelidir. RC, Microsoft Foundation Class Kitaplığı uygulama için gereklidir. Yeni nesne Ekle, tek gerekli menü eklemedir. Diğer öğeler eklenebilir, ancak burada listelenenler en yaygın olanlardır.

Kapsanan öğelerin yerinde etkinleştirilmesini desteklemek istiyorsanız, kapsayıcı uygulamanız için yeni bir menü oluşturmalısınız. Bu menü, dosyalar açıkken aynı dosya menüsünden ve pencere açılır menülerinden oluşur, ancak aralarında iki ayırıcı yer alır. Bu ayırıcılar, sunucu (bileşen) öğesinin (uygulama) yerinde etkinleştirildiğinde menülerini Nereye yerleşeceğini belirtmek için kullanılır. Bu menü birleştirme tekniği hakkında daha fazla bilgi için bkz. [menüler ve kaynaklar: menü birleştirme](menus-and-resources-menu-merging.md).

## <a name="container-application-accelerator-table-additions"></a><a name="_core_container_application_accelerator_table_additions"></a> Kapsayıcı uygulama Hızlandırıcısı tablo eklemeleri

Yerinde etkinleştirmeyi destekliyorsanız bir kapsayıcı uygulamasının Hızlandırıcı tablo kaynaklarında küçük değişiklikler yapmanız gerekir. İlk değişiklik, kullanıcının yerinde Düzenle modunu iptal etmek için kaçış tuşuna (ESC) basışını sağlar. Ana Hızlandırıcı tablosuna aşağıdaki girişi ekleyin:

|ID|Anahtar|Tür|
|--------|---------|----------|
|ID_CANCEL_EDIT_CNTR|VK_ESCAPE|**VıRTKEY**|

İkinci değişiklik, yerinde etkinleştirme için oluşturulan yeni menü kaynağına karşılık gelen yeni bir Hızlandırıcı tablosu oluşturmaktır. Bu tabloda, yukarıdaki VK_ESCAPE girdinin yanı sıra dosya ve pencere menüleri için girişler bulunur. Aşağıdaki örnek, MFC örnek [kapsayıcısında](../overview/visual-cpp-samples.md)yerinde etkinleştirme için oluşturulan Hızlandırıcı tablosudur:

|ID|Anahtar|Tür|
|--------|---------|----------|
|ID_FILE_NEW|CTRL + N|**VıRTKEY**|
|ID_FILE_OPEN|CTRL+O|**VıRTKEY**|
|ID_FILE_SAVE|CTRL+S|**VıRTKEY**|
|ID_FILE_PRINT|CTRL + P|**VıRTKEY**|
|ID_NEXT_PANE|VK_F6|**VıRTKEY**|
|ID_PREV_PANE|SHıFT + VK_F6|**VıRTKEY**|
|ID_CANCEL_EDIT_CNTR|VK_ESCAPE|**VıRTKEY**|

## <a name="string-table-additions-for-container-applications"></a><a name="_core_string_table_additions_for_container_applications"></a> Kapsayıcı uygulamaları için dize tablosu eklemeleri

Kapsayıcı uygulamalarına yönelik dize tablolarında yapılan değişikliklerin çoğu [kapsayıcı menüsü eklemeleri](#_core_container_menu_additions)bölümünde bahsedilen ek menü öğelerine karşılık gelir. Her menü öğesi görüntülenirken durum çubuğunda görünen metni sağlarlar. Örnek olarak, Uygulama Sihirbazının oluşturduğu dize tablosu girdileri aşağıda verilmiştir:

|ID|Dize|
|--------|------------|
|IDP_OLE_INIT_FAILED|OLE başlatması başarısız oldu. OLE kitaplıklarının doğru sürümde olduğundan emin olun.|
|IDP_FAILED_TO_CREATE|Nesne oluşturulamadı. Nesnenin sistem kayıt defterine girildiğinden emin olun.|

## <a name="see-also"></a>Ayrıca bkz.

[Menüler ve kaynaklar (OLE)](menus-and-resources-ole.md)<br/>
[Menüler ve kaynaklar: sunucu eklemeleri](menus-and-resources-server-additions.md)
