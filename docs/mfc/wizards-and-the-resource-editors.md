---
title: Sihirbazlar ve Kaynak Düzenleyicileri
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [MFC], and MFC
- MFC, resource editors
- resource editors, MFC
- MFC Application Wizard
- editors [MFC], resource
- wizards [MFC]
- wizards [MFC], MFC programming
- MFC, wizards
- Class View tool, managing Windows messages
ms.assetid: f5dd4d13-9dc1-4a49-b6bf-5b3cb45fa8ba
ms.openlocfilehash: 04d9f2cf615636b151af93a3c3880f7357496048
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365271"
---
# <a name="wizards-and-the-resource-editors"></a>Sihirbazlar ve Kaynak Düzenleyicileri

Visual C++, MFC programlamada kullanılmak üzere birçok sihirbazın yanı sıra birçok tümleşik kaynak düzenleyicisi içerir. ActiveX denetimleri programlamaiçin [ActiveX Denetim Sihirbazı,](../mfc/reference/mfc-activex-control-wizard.md) MFC Uygulama Sihirbazı'na çok benzer bir amaca hizmet eder. Bu araçların çoğu olmadan MFC uygulamaları yazabilirsiniz, ancak araçlar büyük ölçüde basitleştirmek ve işinizi hızlandırmak.

## <a name="use-the-mfc-application-wizard-to-create-an-mfc-application"></a><a name="_core_use_appwizard_to_create_an_mfc_application"></a>MFC Uygulaması Oluşturmak için MFC Uygulama Sihirbazını kullanma

Visual C++'da OLE ve veritabanı desteği içerebilen bir MFC projesi oluşturmak için [MFC Uygulama](../mfc/reference/mfc-application-wizard.md) Sihirbazı'nı kullanın. Projedeki dosyalar uygulamanızı, belgenizi, görünümünüzü ve çerçeve pencere sınıflarınızı içerir; menüler ve isteğe bağlı araç çubuğu da dahil olmak üzere standart kaynaklar; diğer gerekli Windows dosyaları; ve programınızın yardım dosyasını oluşturmak için gözden geçirebileceğiniz ve artırabileceğiniz standart Windows Yardım konularını içeren isteğe bağlı .rtf dosyaları.

## <a name="use-class-view-to-manage-classes-and-windows-messages"></a><a name="_core_use_classwizard_to_manage_classes_and_windows_messages"></a>Sınıfları ve Windows İletilerini Yönetmek için Sınıf Görünümünü Kullanma

Sınıf Görünümü, Windows iletileri ve komutları için işleyici işlevleri oluşturmanıza, sınıflar oluşturmanıza ve yönetmenize, sınıf üye değişkenleri oluşturmanıza, Otomasyon yöntemleri ve özellikleri oluşturmanıza, veritabanı sınıfları oluşturmanıza ve daha fazlanıza yardımcı olur.

> [!NOTE]
> Sınıf Görünümü, MFC sınıflarında sanal işlevleri geçersiz kılmanıza da yardımcı olur. Geçersiz kılmak için sınıfı ve sanal işlevi seçin. İşlemin geri kalanı, aşağıdaki paragraflarda açıklandığı gibi ileti işlemeye benzer.

Windows altında çalışan uygulamalar [ileti sürülür.](../mfc/message-handling-and-mapping.md) Çalışan programda gerçekleşen kullanıcı eylemleri ve diğer olaylar, Windows'un programdaki pencerelere ileti göndermesine neden olur. Örneğin, kullanıcı bir pencerede fareyi tıklatarsa, Windows sol fare düğmesine basıldığında WM_LBUTTONDOWN bir ileti ve düğme serbest bırakıldığında bir WM_LBUTTONUP ileti gönderir. Windows, kullanıcı menü çubuğundan komutları seçtiğinde WM_COMMAND iletileri de gönderir.

MFC çerçevesinde, belgeler, görünümler, çerçeve pencereleri, belge şablonları ve uygulama nesnesi gibi çeşitli nesneler iletileri "işleyebilir". Böyle bir nesne, üye işlevlerinden biri olarak bir "işleyici işlevi" sağlar ve çerçeve gelen iletiyi işleyicisine eşler.

Programlama görevinizin büyük bir bölümü, hangi nesnelerin eşleneceğini seçmek ve bu eşlemeyi uygulamaktır. Bunu yapmak için Sınıf Görünümü ve [Sınıf Sihirbazı'nı](reference/mfc-class-wizard.md)kullanırsınız.

[Sınıf Sihirbazı](reference/mfc-class-wizard.md) boş ileti işleyicisi üye işlevleri oluşturur ve işleyicinin gövdesini uygulamak için kaynak kodu düzenleyicisini kullanırsınız. Sınıf Görünümü'ne sahip sınıfları (MFC sınıflarından türetilmiş olmayan kendi sınıfları dahil) ve bunların üyelerini de oluşturabilir veya edebilirsiniz. Sınıf Görünümü'nü kullanma ve projeye kod ekleyen sihirbazlar hakkında daha fazla bilgi için kod [sihirbazlarıyla İşlevsellik Ekleme'ye](../ide/adding-functionality-with-code-wizards-cpp.md)bakın.

## <a name="use-the-resource-editors-to-create-and-edit-resources"></a><a name="_core_use_the_resource_editors_to_create_and_edit_resources"></a>Kaynak Oluşturmak ve Bunları Yeniden Oluşturmak için Kaynak Düzenleyicileri'ni kullanın

Menüler, iletişim kutuları, özel denetimler, hızlandırıcı tuşları, bit eşlemler, simgeler, imleçler, dizeleri ve sürüm kaynakları oluşturmak ve bunları yapmak için Visual C++ [kaynak düzenleyicilerini](../windows/resource-editors.md) kullanın. Visual C++ sürüm 4.0 itibariyle, araç çubuğu düzenleyicisi araç çubukları oluşturmayı çok daha kolaylaştırır.

Microsoft Hazırlık Sınıfı Kitaplığı, size daha fazla yardımcı olmak için ORTAK adlı bir dosya sağlar. COMMON'dan kopyalayabileceğiniz "küçük resim" kaynaklarını içeren RES. RES ve yapıştırın kendi kaynak dosyanıza. Ortak. RES araç çubuğu düğmeleri, ortak imleçler, simgeler ve daha fazlasını içerir. Bu kaynakları uygulamanızda kullanabilir, değiştirebilir ve yeniden dağıtabilirsiniz. COMMON hakkında daha fazla bilgi için. RES, [Clipart örneğine](../overview/visual-cpp-samples.md)bakın.

MFC Uygulama Sihirbazı, Visual C++ sihirbazları, kaynak düzenleyicilerve MFC çerçevesi sizin için çok fazla iş yapar ve kodunuzu yönetmenizi çok daha kolay hale getirir. Uygulamaya özel kodunuzun büyük bölümü belge ve görünüm sınıflarınızdadır.

## <a name="see-also"></a>Ayrıca bkz.

[Windows Uygulamaları Yazmak için Sınıfları Kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md)
