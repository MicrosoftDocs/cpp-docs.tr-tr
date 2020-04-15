---
title: 'Menüler ve Kaynaklar: Sunucu Ekleme'
ms.date: 11/04/2016
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
ms.openlocfilehash: 8366cd8b0376766b7914c94a24cef6598761a805
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375985"
---
# <a name="menus-and-resources-server-additions"></a>Menüler ve Kaynaklar: Sunucu Ekleme

Bu makalede, görsel düzenleme sunucusu (bileşen) uygulamasında menülerde ve diğer kaynaklarda yapılması gereken değişiklikler açıklanmaktadır. Sunucu uygulaması, üç moddan birinde başlatılabildiği için menü yapısına ve diğer kaynaklara birçok ekleme gerektirir: tek başına, gömülü veya yerinde durun. [Menüler ve Kaynaklar (OLE)](../mfc/menus-and-resources-ole.md) makalesinde açıklandığı gibi, en fazla dört menü kümesi vardır. Dördü de MDI tam sunucu uygulaması için kullanılırken, yalnızca üçü bir mini sunucu için kullanılır. Uygulama sihirbazı, istediğiniz sunucu türü için gerekli menü düzenini oluşturur. Bazı özelleştirme gerekli olabilir.

Uygulama sihirbazını kullanmazsanız, HIERSVR'a bakmak isteyebilirsiniz. RC, MFC örnek uygulama [HIERSVR](../overview/visual-cpp-samples.md)için kaynak komut dosyası , bu değişikliklerin nasıl uygulandığını görmek için.

Bu makalede ele alınan konular şunlardır:

- [Sunucu Menüsü Eklemeleri](#_core_server_menu_additions)

- [Hızlandırıcı Tablo Eklemeleri](#_core_server_application_accelerator_table_additions)

- [String Tablo Eklemeleri](../mfc/menus-and-resources-container-additions.md)

- [Miniserver Eklemeler](#_core_mini.2d.server_additions)

## <a name="server-menu-additions"></a><a name="_core_server_menu_additions"></a>Sunucu Menüsü Eklemeleri

Sunucu (bileşen) uygulamaları, OLE görsel düzenlemeyi desteklemek için menü kaynaklarına eklenmelidir. Uygulama tek başına modda çalıştırıldığında kullanılan menülerin değiştirilmesi gerekmez, ancak uygulamayı oluşturmadan önce iki yeni menü kaynağı eklemeniz gerekir: biri yerinde etkinleştirme desteklemek ve diğeri sunucunun tamamen açık olmasını desteklemek için. Her iki menü kaynağı da tam ve mini sunucu uygulamaları tarafından kullanılır.

- Yerinde etkinleştirme desteklemek için, tek başına modda çalıştırıldığında kullanılan menü kaynağına çok benzeyen bir menü kaynağı oluşturmanız gerekir. Bu menüdeki fark, Dosya ve Pencere öğelerinin (ve verilerle değil, uygulamayla ilgili diğer menü öğelerinin) eksik olmasıdır. Kapsayıcı uygulaması bu menü öğelerini sağlayacaktır. Bu menü birleştirme tekniği hakkında daha fazla bilgi ve örnek için [Menüler ve Kaynaklar: Menü Birleştirme](../mfc/menus-and-resources-menu-merging.md)makalesine bakın.

- Tam açık etkinleştirme desteklemek için, tek başına modda çalıştırıldığında kullanılan menü kaynağıyla neredeyse aynı bir menü kaynağı oluşturmanız gerekir. Bu menü kaynağında yapılan tek değişiklik, bazı öğelerin sunucunun bileşik bir belgede katıştırılmış bir öğe üzerinde çalıştığı gerçeğini yansıtacak şekilde yeniden ifade edilmesidir.

Bu makalede listelenen değişikliklere ek olarak, kaynak dosyanızın AFXOLESV içermesi gerekir. Microsoft Hazırlık Sınıfı Kitaplığı uygulaması için gerekli olan RC. Bu dosya MFC\Include alt dizinindedir.

## <a name="server-application-accelerator-table-additions"></a><a name="_core_server_application_accelerator_table_additions"></a>Sunucu Uygulama Hızlandırıcı Tablo Eklemeleri

Sunucu uygulamalarına iki yeni hızlandırıcı tablosu kaynağı eklenmelidir; bunlar daha önce açıklanan yeni menü kaynaklarına doğrudan karşılık gelir. Sunucu uygulaması yerinde etkinleştirildiğinde ilk hızlandırıcı tablosu kullanılır. Dosya ve Pencere menülerine bağlı olanlar hariç, görünümün hızlandırıcı tablosundaki tüm girişlerden oluşur.

İkinci tablo, görünümün hızlandırıcı tablosunun neredeyse tam bir kopyasıdır. [Server Menü Eklemeleri'nde](#_core_server_menu_additions)belirtilen tamamen açık menüde yapılan farklılıklara paralel değişiklikler.

Bu hızlandırıcı tablosu değişikliklerine örnek olarak, IDR_HIERSVRTYPE_SRVR_IP ve IDR_HIERSVRTYPE_SRVR_EMB hızlandırıcı tablolarını HIERSVR'daki IDR_MAINFRAME karşılaştırın. RC dosyası MFC OLE örnek [HIERSVR](../overview/visual-cpp-samples.md)dahil. Dosya ve Pencere hızlandırıcıları yerinde tabloda eksik tir ve bunların tam kopyaları gömülü tablodadır.

## <a name="string-table-additions-for-server-applications"></a><a name="_core_string_table_additions_for_server_applications"></a>Sunucu Uygulamaları için String Tablo Eklemeleri

Bir sunucu uygulamasında yalnızca bir dize tablosu eklenmesi gereklidir — OLE başlatmanın başarısız olduğunu belirtmek için bir dize. Örnek olarak, uygulama sihirbazı oluşturur dize tablo girişi aşağıdaverilmiştir:

|Kimlik|Dize|
|--------|------------|
|IDP_OLE_INIT_FAILED|OLE başlatma başarısız oldu. OLE kitaplıklarının doğru sürüm olduğundan emin olun.|

## <a name="miniserver-additions"></a><a name="_core_mini.2d.server_additions"></a>Miniserver Eklemeler

Aynı eklemeler, tam sunucular için yukarıda listelenenler gibi mini sunucular için de geçerlidir. Bir mini sunucu tek başına modda çalıştırılamadığından, ana menüsü çok daha küçüktür. Uygulama sihirbazı tarafından oluşturulan ana menüde yalnızca Çıkış ve Hakkında öğelerini içeren bir Dosya menüsü vardır. Mini sunucular için gömülü ve yerinde menüler ve hızlandırıcılar tam sunucular için olanlarla aynıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Menüler ve Kaynaklar (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[Menüler ve Kaynaklar: Menü Birleştirme](../mfc/menus-and-resources-menu-merging.md)
