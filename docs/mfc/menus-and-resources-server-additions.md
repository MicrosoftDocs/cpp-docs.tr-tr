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
ms.openlocfilehash: f67212dc7d4e2ab90421c7b2eee48acae4745940
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626179"
---
# <a name="menus-and-resources-server-additions"></a>Menüler ve Kaynaklar: Sunucu Ekleme

Bu makalede, bir görsel görüntü sunucusu (bileşen) uygulamasındaki menülerde ve diğer kaynaklarda yapılması gereken değişiklikler açıklanmaktadır. Bir sunucu uygulaması, üç moddan birinde başlatılabildiğinden, menü yapısına ve diğer kaynaklara çok sayıda ekleme gerektirir: tek başına, katıştırılmış veya yerinde. [Menüler ve kaynaklar (OLE)](menus-and-resources-ole.md) makalesinde açıklandığı gibi, en fazla dört menü kümesi vardır. Tüm dört, bir MDI tam sunucu uygulaması için kullanılır, ancak bir minıver için yalnızca üç kullanılır. Uygulama Sihirbazı, istediğiniz sunucu türü için gereken menü yerleşimini oluşturacaktır. Bazı özelleştirmeler gerekli olabilir.

Uygulama Sihirbazı 'nı kullanmıyorsanız, HIERSVR 'e bakmak isteyebilirsiniz. RC, bu değişikliklerin nasıl uygulandığını görmek için MFC örnek [uygulaması için](../overview/visual-cpp-samples.md)kaynak betiği.

Bu makalede ele alınan konular şunları içerir:

- [Sunucu menüsü eklemeleri](#_core_server_menu_additions)

- [Hızlandırıcı tablo eklemeleri](#_core_server_application_accelerator_table_additions)

- [Dize tablosu eklemeleri](menus-and-resources-container-additions.md)

- [Minıver eklemeleri](#_core_mini.2d.server_additions)

## <a name="server-menu-additions"></a><a name="_core_server_menu_additions"></a>Sunucu menüsü eklemeleri

Sunucu (bileşen) uygulamalarında OLE görsel düzenlemesini desteklemek için menü kaynakları eklenmiş olmalıdır. Uygulamanın tek başına modunda çalıştırıldığı zaman kullanılan menülerin değiştirilmesi gerekmez, ancak uygulamayı oluşturmadan önce iki yeni menü kaynağı eklemeniz gerekir: bunlardan biri yerinde etkinleştirmeyi desteklemek için ve diğeri tamamen açık olan sunucuyu destekler. Her iki menü kaynağı da tam ve minıver uygulamaları tarafından kullanılır.

- Yerinde etkinleştirmeyi desteklemek için, tek başına modda çalıştırıldığında kullanılan menü kaynağına çok benzeyen bir menü kaynağı oluşturmanız gerekir. Bu menüdeki fark, dosya ve Pencere öğelerinin (ve veri değil uygulamayla ilgilenen diğer menü öğelerinin) eksik olması olur. Kapsayıcı uygulaması bu menü öğelerini sağlayacak. Hakkında daha fazla bilgi ve bu menü birleştirme tekniğinin bir örneği için, [menüler ve kaynaklar: menü birleştirme](menus-and-resources-menu-merging.md)makalesine bakın.

- Tam açık etkinleştirmeyi desteklemek için, tek başına modda çalıştırıldığında kullanılan menü kaynağıyla neredeyse özdeş bir menü kaynağı oluşturmanız gerekir. Bu menü kaynağına yapılan tek değişiklik, bazı öğelerin bir bileşik belgeye katıştırılmış bir öğe üzerinde çalışan bir olguyu yansıtacak şekilde yeniden gösterilmelerdir.

Bu makalede listelenen değişikliklere ek olarak, kaynak dosyanızın AFXOLESV içermesi gerekir. RC, Microsoft Foundation Class Kitaplığı uygulama için gereklidir. Bu dosya Mfc\ınclude alt dizininde yer alır.

## <a name="server-application-accelerator-table-additions"></a><a name="_core_server_application_accelerator_table_additions"></a>Sunucu uygulama Hızlandırıcısı tablo eklemeleri

Sunucu uygulamalarına iki yeni Hızlandırıcı tablo kaynağı eklenmelidir; daha önce açıklanan yeni menü kaynaklarına doğrudan karşılık gelir. İlk Hızlandırıcı tablosu, sunucu uygulaması yerinde etkinleştirildiğinde kullanılır. Bu, dosya ve pencere menülerine bağlı olanlar hariç, görünümün Hızlandırıcı tablosundaki tüm girdilerden oluşur.

İkinci tablo, görünümün Hızlandırıcı tablosunun neredeyse tam bir kopyasıdır. [Sunucu menüsü eklemeleri](#_core_server_menu_additions)bölümünde bahsedilen tam açık menüde yapılan tüm farklılıklar, paralel değişiklikler.

Bu Hızlandırıcı tablo değişikliklerinin bir örneği için IDR_HIERSVRTYPE_SRVR_IP ve IDR_HIERSVRTYPE_SRVR_EMB Hızlandırıcı tablolarını HIERSVR içindeki IDR_MAINFRAME karşılaştırın. RC dosyası MFC OLE örnek [Hiersvr](../overview/visual-cpp-samples.md)'a dahildir. Dosya ve pencere Hızlandırıcılar, yerinde tabloda yok ve bunların tam kopyaları katıştırılmış tabloda.

## <a name="string-table-additions-for-server-applications"></a><a name="_core_string_table_additions_for_server_applications"></a>Sunucu uygulamaları için dize tablosu eklemeleri

Sunucu uygulamasında yalnızca bir dize tablosu eklemesi gerekir — OLE başlatmanın başarısız olduğunu belirten bir dize. Örnek olarak, Uygulama Sihirbazının oluşturduğu dize tablosu girdisi aşağıda verilmiştir:

|ID|Dize|
|--------|------------|
|IDP_OLE_INIT_FAILED|OLE başlatması başarısız oldu. OLE kitaplıklarının doğru sürümde olduğundan emin olun.|

## <a name="miniserver-additions"></a><a name="_core_mini.2d.server_additions"></a>Minıver eklemeleri

Aynı eklemeler, daha önce tam sunucular için listelenenler gibi minıse 'ler için de geçerlidir. Bir minıver, tek başına modda çalıştırılabilmesi için ana menü çok daha küçüktür. Uygulama Sihirbazı tarafından oluşturulan ana menü yalnızca çıkış ve hakkında öğeleri içeren bir dosya menüsüne sahiptir. Daha önce gömülü ve yerinde menüler ve Hızlandırıcılar, tam sunucularla aynı olanlardır.

## <a name="see-also"></a>Ayrıca bkz.

[Menüler ve kaynaklar (OLE)](menus-and-resources-ole.md)<br/>
[Menüler ve Kaynaklar: Menü Birleştirme](menus-and-resources-menu-merging.md)
