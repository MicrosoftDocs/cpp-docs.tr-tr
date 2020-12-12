---
description: 'Hakkında daha fazla bilgi edinin: sihirbazlar ve kaynak düzenleyicileri'
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
ms.openlocfilehash: b493746365809ca6fd193a31d0e7f53917a9646f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284921"
---
# <a name="wizards-and-the-resource-editors"></a>Sihirbazlar ve Kaynak Düzenleyicileri

Visual C++, birçok Tümleşik kaynak düzenleyicisiyle birlikte MFC programlamasında kullanılmak üzere çeşitli sihirbazlar içerir. ActiveX denetimleri programlamasına yönelik olarak, [ActiveX denetim SIHIRBAZı](../mfc/reference/mfc-activex-control-wizard.md) MFC Uygulama sihirbazından çok benzer şekilde çalışır. Bu araçların çoğuna gerek kalmadan MFC uygulamaları yazabilirsiniz, ancak bu araçlar işinizi önemli ölçüde basitleştirir ve hızlandırır.

## <a name="use-the-mfc-application-wizard-to-create-an-mfc-application"></a><a name="_core_use_appwizard_to_create_an_mfc_application"></a> MFC uygulaması oluşturmak için MFC Uygulama Sihirbazı 'Nı kullanma

Visual C++ içinde OLE ve veritabanı desteği içerebilen bir MFC projesi oluşturmak için [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md) ' nı kullanın. Projedeki dosyalar, uygulamanızı, belgenizi, görünümü ve çerçeve penceresi sınıflarını içerir; menüler ve isteğe bağlı bir araç çubuğu gibi standart kaynaklar; diğer gerekli Windows dosyaları; ve programınızın Yardım dosyasını oluşturmak için düzeltebileceğiniz ve daha sonra kullanabileceğiniz standart Windows Yardım konularını içeren isteğe bağlı. rtf dosyaları.

## <a name="use-class-view-to-manage-classes-and-windows-messages"></a><a name="_core_use_classwizard_to_manage_classes_and_windows_messages"></a> Sınıfları ve Windows Iletilerini yönetmek için Sınıf Görünümü kullanma

Sınıf Görünümü, Windows iletileri ve komutları için işleyici işlevleri oluşturmanıza, sınıflar oluşturmanıza ve yönetmenize, sınıf üye değişkenleri oluşturmanıza, Otomasyon yöntemleri ve özellikleri oluşturmanıza, veritabanı sınıfları oluşturmanıza ve daha fazlasını yapmanıza yardımcı olur.

> [!NOTE]
> Sınıf Görünümü, MFC sınıflarında sanal işlevleri geçersiz kılmanıza de yardımcı olur. Geçersiz kılmak için sınıfı ve sanal işlevi seçin. İşlemin geri kalanı, aşağıdaki paragraflarda açıklandığı gibi ileti işlemeye benzer.

Windows altında çalışan uygulamalar [ileti odaklı](../mfc/message-handling-and-mapping.md). Çalışan programda oluşan Kullanıcı eylemleri ve diğer olaylar Windows 'un programda Windows 'a ileti göndermesini sağlar. Örneğin, Kullanıcı bir pencerede fareyle tıklarsa, fare düğmesine basıldığında Windows WM_LBUTTONDOWN bir ileti gönderir ve düğme serbest bırakıldığında WM_LBUTTONUP bir ileti gönderilir. Ayrıca, Kullanıcı menü çubuğundan komutları seçtiğinde Windows WM_COMMAND iletiler gönderir.

MFC çerçevesinde belgeler, görünümler, çerçeve pencereleri, belge şablonları ve uygulama nesnesi gibi çeşitli nesneler "işleyebilir" iletilerini alabilir. Böyle bir nesne, üye işlevlerinden biri olarak bir "işleyici işlevi" sağlar ve çerçeve gelen iletiyi işleyicisine eşler.

Programlama göreviniz için büyük bir bölüm, hangi iletilerin hangi nesnelere eşlendiğini ve ardından bu eşlemeyi uygulamayı seçtedir. Bunu yapmak için Sınıf Görünümü ve [sınıf Sihirbazı](reference/mfc-class-wizard.md)' nı kullanırsınız.

[Sınıf Sihirbazı](reference/mfc-class-wizard.md) boş ileti işleyici üye işlevleri oluşturacak ve işleyicinin gövdesini uygulamak için kaynak kodu düzenleyicisini kullanıyorsunuz. Ayrıca, sınıfları (MFC sınıflarından türetilmeyen, kendi sınıfları dahil olmak üzere) ve Sınıf Görünümü olan üyelerini oluşturabilir veya düzenleyebilirsiniz. Sınıf Görünümü kullanma hakkında daha fazla bilgi ve bir projeye kod ekleyen sihirbazlar hakkında daha fazla bilgi için bkz. [kod sihirbazları Ile Işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md).

## <a name="use-the-resource-editors-to-create-and-edit-resources"></a><a name="_core_use_the_resource_editors_to_create_and_edit_resources"></a> Kaynak düzenleyicilerini kullanarak kaynak oluşturma ve düzenleme

Menüler, iletişim kutuları, özel denetimler, hızlandırıcı tuşları, bit eşlemler, simgeler, imleçler, dizeler ve sürüm kaynakları oluşturmak ve düzenlemek için Visual C++ [kaynak düzenleyicilerini](../windows/resource-editors.md) kullanın. Visual C++ sürüm 4,0 itibariyle bir araç çubuğu Düzenleyicisi, araç çubuklarını oluşturmayı çok daha kolay hale getirir.

Daha da fazla yardımcı olması için Microsoft Foundation Class Kitaplığı, ortak adlı bir dosya sağlar. ORTAK içinden kopyalayabileceğiniz "küçük resim" kaynaklarını içeren RES. Kaynak dosyanıza kay ve yapıştırın. Birçok. RES araç çubuğu düğmeleri, ortak imleçler, simgeler ve daha fazlasını içerir. Uygulamanızda bu kaynakları kullanabilir, değiştirebilir ve yeniden dağıtabilirsiniz. ORTAK hakkında daha fazla bilgi için. RES, bkz. [clipart örneği](../overview/visual-cpp-samples.md).

MFC Uygulama Sihirbazı, Visual C++ sihirbazları, kaynak düzenleyicileri ve MFC çerçevesi sizin için çok sayıda iş yapar ve kodunuzu yönetmeyi çok daha kolay hale getirir. Uygulamanıza özgü kodunuzun toplu olarak belge ve Görünüm sınıfları bulunur.

## <a name="see-also"></a>Ayrıca bkz.

[Windows uygulamaları yazmak için sınıfları kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md)
