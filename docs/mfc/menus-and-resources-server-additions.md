---
title: 'Menüler ve kaynaklar: sunucu ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IDP_OLE_INIT_FAILED
dev_langs:
- C++
helpviewer_keywords:
- OLE visual editing servers [MFC]
- accelerator tables [MFC], server applications
- visual editing [MFC], application menus and resources
- server applications [MFC], accelerator table
- string tables [MFC], visual editing applications
- servers [MFC], menu additions
- resources [MFC], server applications
- OLE server applications [MFC], menus and resources
- string editing [MFC], visual editing applications
- IDP_OLE_INIT_FAILED macro [MFC]
- server applications [MFC], OLE menus and resources
- OLE initialization failure [MFC]
ms.assetid: 56ce9e8d-8f41-4db8-8dee-e8b0702d057c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14a7ae414c9cd3015d1f70b779a2c19ea1329ed4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388062"
---
# <a name="menus-and-resources-server-additions"></a>Menüler ve Kaynaklar: Sunucu Ekleme

Bu makalede, menüler ve diğer kaynakları görsel düzenleme sunucu (Bileşen) uygulaması, yapılması gereken değişiklikleri açıklar. Sunucu uygulaması, birçok ekleme menüsü yapısı ve diğer kaynaklara gerektirir, çünkü bu üç moddan birini başlatılabilir: tek başına, katıştırılmış, ya da yerinde bekleyin. Bölümünde anlatıldığı gibi [menüler ve kaynaklar (OLE)](../mfc/menus-and-resources-ole.md) makalesi, en fazla dört menüleri kümesi vardır. Dört yalnızca üç bir miniserver için kullanılan bir MDI tam sunucu uygulaması için kullanılabilir. Uygulama Sihirbazı'nı menüsü düzeni için kullanmak istediğiniz sunucu türünü oluşturur. Bazı özelleştirme gerekli olabilir.

Uygulama Sihirbazı'nı kullanmıyorsanız HIERSVR aramak isteyebilirsiniz. RC, MFC örnek uygulama için kaynak betiği [HIERSVR](../visual-cpp-samples.md)bu değişiklikleri nasıl uygulandığını görmek için.

Bu makalede ele alınan konular:

- [Sunucu menü ekleme](#_core_server_menu_additions)

- [Hızlandırıcı tablo ekleme](#_core_server_application_accelerator_table_additions)

- [Dize tablosu ekleme](../mfc/menus-and-resources-container-additions.md)

- [Miniserver eklemeleri](#_core_mini.2d.server_additions)

##  <a name="_core_server_menu_additions"></a> Sunucu menü ekleme

Sunucu (Bileşen) uygulamalarının OLE görsel düzenleme desteklemek için eklenen menüsü kaynaklarını olması gerekir. Tek başına modunda uygulama çalıştırıldığında kullanılan menülerde değiştirilmesi gerekmez, ancak uygulamayı oluşturmadan önce iki yeni menü kaynağı eklemeniz gerekir: bir yerinde etkinleştirme ve tam olarak açık olan sunucusunu desteklemek için bir destek. Her iki menüsü kaynaklarını tam ve miniserver uygulamalar tarafından kullanılır.

- Yerinde etkinleştirmeyi desteklemek için tek başına modunda çalıştırdığınızda kullanılan menü kaynağı çok benzer bir menü kaynağı oluşturmanız gerekir. Bu menüde Dosya ve pencere öğelerini (ve uygulama ve veri ile ilgilenirken siz herhangi bir menü öğeleri) eksik olduğunu farktır. Bu menü öğeleri kapsayıcı uygulamasını kullanacaksınız. Daha fazla bilgi ve örnek olarak, bu menü birleştirme teknik için bkz [menüler ve kaynaklar: menü birleştirme](../mfc/menus-and-resources-menu-merging.md).

- Tamamen açık etkinleştirmeyi desteklemek için tek başına modunda çalıştırıldığında bir menü kaynağı kullanılan menü kaynağı neredeyse aynı oluşturmanız gerekir. Yalnızca bu menü kaynağı güncelleştirdiğinde, bazı öğeler bir bileşik belgeye gömülü bir öğe üzerinde sunucu işletim olgu yansıtacak şekilde yeniden ifade edilen emin olur.

Bu makalede listelenen değişikliklerin yanı sıra kaynak dosyanızı AFXOLESV içermesi gerekir. RC için Microsoft Foundation Class Kitaplığı uygulaması gereklidir. MFC\Include alt dizinde dosyasıdır.

##  <a name="_core_server_application_accelerator_table_additions"></a> Sunucu uygulama Hızlandırıcı tablosu ekleme

Sunucu uygulamaları için iki yeni Hızlandırıcı tablo kaynaklarını eklenmesi gerekir; Bunlar, daha önce açıklanan doğrudan yeni menü kaynaklarına karşılık gelir. Sunucu uygulaması yerinde etkin olduğunda, ilk Hızlandırıcı tablosu kullanılır. Bu dosya ve pencere menü bağlı dışında görünümün Hızlandırıcı tablosu içindeki tüm girişleri oluşur.

İkinci tabloda görünümün Hızlandırıcı tablosu neredeyse tam bir kopyası var. Belirtilen tamamen açık menüsünde yapılan değişikliklerin farkları paralel [sunucu menü eklemeleri](#_core_server_menu_additions).

Bu Hızlandırıcı tablosu değişiklikleri örneği için IDR_HIERSVRTYPE_SRVR_IP ve IDR_HIERSVRTYPE_SRVR_EMB Hızlandırıcı tablolarını IDR_MAINFRAME HIERSVR içinde ile karşılaştırın. MFC OLE örnekte bulunan RC dosyası [HIERSVR](../visual-cpp-samples.md). Dosya ve pencere Hızlandırıcıları yerinde tablosundan eksik ve bunları tam kopyalarını katıştırılmış tabloda yer alan.

##  <a name="_core_string_table_additions_for_server_applications"></a> Sunucu uygulamaları için dize tablosu ekleme

Yalnızca bir dize tablosu ek bir sunucu uygulamasında gereklidir; OLE başlatması başarısız olduğunu belirtmek için bir dize. Örneğin, Uygulama Sihirbazı oluşturur dize tablosu girişini İşte:

|Kimlik|Dize|
|--------|------------|
|IDP_OLE_INIT_FAILED|OLE başlatma başarısız oldu. OLE kitaplıklarının doğru sürümde olduğundan emin olun.|

##  <a name="_core_mini.2d.server_additions"></a> Miniserver eklemeleri

Aynı eklemeleri miniservers Yukarıda listelenenler olarak geçerli tam sunucuları için. Tek başına modunda bir miniserver çalıştırılamadığı ana menüsü çok daha küçüktür. Uygulama Sihirbazı tarafından oluşturulan ana menü yalnızca bir dosya menüsü, yalnızca çıkış öğeleri içeren vardır ve ilgili. Katıştırılmış ve yerinde menülerini ve Hızlandırıcı miniservers için bu tam sunucu için aynıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[Menüler ve Kaynaklar (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Menüler ve Kaynaklar: Menü Birleştirme](../mfc/menus-and-resources-menu-merging.md)

