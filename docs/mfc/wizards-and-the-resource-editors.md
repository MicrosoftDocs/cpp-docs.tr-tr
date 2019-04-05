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
ms.openlocfilehash: 41cbb86b4245bd78baecd222b5573ba5e877243a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58773833"
---
# <a name="wizards-and-the-resource-editors"></a>Sihirbazlar ve Kaynak Düzenleyicileri

Visual C++ MFC programlamada, birçok tümleşik kaynak düzenleyicileri ile birlikte kullanmak için çeşitli sihirbazlar içerir. ActiveX denetimlerini programlama için [ActiveX Denetim Sihirbazı'nı](../mfc/reference/mfc-activex-control-wizard.md) , MFC Uygulama Sihirbazı benzer bir amaca hizmet eder. MFC uygulamaları bu araçların çoğu olmadan yazabilirsiniz, ancak Araçlar büyük ölçüde basitleştirin ve iş hızlandırın.

##  <a name="_core_use_appwizard_to_create_an_mfc_application"></a> Bir MFC uygulaması oluşturmak için MFC Uygulama Sihirbazı'nı kullanma

Kullanım [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md) Visual OLE içerir ve veritabanı desteği C++'da, bir MFC projesi oluşturmak için. Proje dosyaları, uygulama, belge, Görünüm ve çerçeve penceresi sınıfları içerir; menüler ve isteğe bağlı bir araç da dahil olmak üzere standart kaynakları; diğer gerekli Windows dosyaları; ve birlikte düzeltebilir, standart Windows Yardım konularını ve ayırma programınızın Yardım dosyası oluşturmak için isteğe bağlı .rtf dosyaları içeren.

##  <a name="_core_use_classwizard_to_manage_classes_and_windows_messages"></a> Sınıf Görünümü sınıfları ve Windows iletilerini yönetmek için kullanın

Windows iletiler ve komutlar için işleyici işlevleri oluşturma, oluşturun ve sınıfları yönetmek sınıf görünümü yardımcı sınıf üyesi değişkenleri oluşturma, Otomasyon yöntemleri ve özellikleri oluşturma, veritabanı sınıfları ve daha fazlasını oluşturun.

> [!NOTE]
>  Sınıf Görünümü, MFC sınıflardaki sanal işlevleri geçersiz kılmak için de yardımcı olur. Sınıf ve sanal işlevi geçersiz kılmak için seçin. İşleminin geri kalanı, aşağıdaki paragrafta açıklandığı gibi ileti işleme için benzerdir.

Windows altında çalışan uygulamalar [temelli ileti](../mfc/message-handling-and-mapping.md). Kullanıcı eylemlerini ve çalışan programa meydana gelen diğer olayları program windows iletileri göndermek Windows neden olur. Kullanıcı fareyi bir pencerede tıklarsa düğmesi bırakıldığında Örneğin, Windows farenin sol düğmesine basıldığında WM_LBUTTONDOWN ileti ve WM_LBUTTONUP ileti gönderir. Kullanıcı komutları menü çubuğundan seçtiğinde Windows WM_COMMAND iletileri de gönderir.

MFC çerçevesi belgeler, görünümler, çerçeve pencereleri, belge şablonları ve uygulama nesnesi gibi çeşitli nesneleri "iletileri işleyebilir". Böyle bir nesnenin "işleyici işlevi" bir üye işlevleri sağlar ve framework gelen ileti işleyicisine eşler.

Programlama göreviniz büyük bir bölümünü hangi nesnelerin eşlemek için hangi iletileri seçerek ve ardından bu eşlemenin uygulama. Bunu yapmak için sınıf görünümü ve Özellikler penceresini kullanın.

Özellikler penceresinde boş ileti işleyicisi üye işlevleri oluşturur ve işleyicisinin gövdesi uygulamak için kaynak kod Düzenleyicisi'ni kullanın. Ayrıca, oluşturma veya sınıfları (MFC sınıflarından türetilmiş değil sınıfları kendi dahil) ve üyeleri sınıf görünümü ile düzenleyebilirsiniz. Sınıf görünümü kullanarak ve bir proje için kod ekleme sihirbazları hakkında daha fazla bilgi için bkz. [kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md).

##  <a name="_core_use_the_resource_editors_to_create_and_edit_resources"></a> Oluşturma ve kaynakları düzenlemek için kaynak düzenleyicileri kullanma

Visual c++'ta kullanmak [kaynak düzenleyicileri](../windows/resource-editors.md) oluşturmak ve menüler, iletişim kutuları, özel denetimler, Hızlandırıcı tuşları, bit eşlemler, simgeler, işaretçiler, dizeleri ve sürüm kaynakları düzenlemek için. Visual C++ sürüm 4.0 itibariyle bir araç çubuğu Düzenleyicisi oluşturulurken araç çubukları kolaylaştırır.

Daha fazla yardımcı olmak için Microsoft Foundation Class Kitaplığı ortak adlı bir dosya sağlar. RES gelen ortak kopyalayabilirsiniz "küçük resim" kaynakları içerir. RES ve kendi kaynak dosyasına yapıştırın. ORTAK. RES araç çubuğu düğmeleri, ortak imleçler, simgeler ve daha fazlasını içerir. Kullanın, değiştirebilir ve bu kaynakları uygulamanızda yeniden dağıtabilirsiniz. Ortak hakkında daha fazla bilgi için. RES, bkz: [küçük örnek](../overview/visual-cpp-samples.md).

MFC Uygulama Sihirbazı, Visual C++ sihirbazları, kaynak düzenleyicileri ve MFC çerçevesi sizin için çok fazla iş yapın ve kodunuzu çok daha kolay yönetme yapın. Uygulamaya özel kodunuzun toplu, belge ve görünüm sınıfları ' dir.

## <a name="see-also"></a>Ayrıca bkz.

[Windows Uygulamaları Yazmak için Sınıfları Kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md)
