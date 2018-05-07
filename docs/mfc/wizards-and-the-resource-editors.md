---
title: Sihirbazlar ve kaynak düzenleyicileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33fb1caa496c34111de133a113433a614ff5eb22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="wizards-and-the-resource-editors"></a>Sihirbazlar ve Kaynak Düzenleyicileri
Visual C++ MFC programlama birçok tümleşik kaynak düzenleyicileri birlikte kullanmak için bazı sihirbazlar içerir. Programlama, ActiveX denetimleri için [ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md) , MFC Uygulama Sihirbazı'nın benzer bir amaca hizmet eder. Bu araçların çoğu olmadan MFC uygulamaları yazma sırasında araçları büyük ölçüde basitleştirebilir ve çalışmanızı hızlandırmak.  
  
##  <a name="_core_use_appwizard_to_create_an_mfc_application"></a> MFC Uygulama oluşturmak için MFC Uygulama Sihirbazı'nı kullanın  
 Kullanım [MFC Uygulama Sihirbazı'nı](../mfc/reference/mfc-application-wizard.md) OLE içerir ve veritabanı desteği'te Visual C++, bir MFC projesi oluşturmak için. Projedeki dosyaları, uygulama, belge, Görünüm ve çerçeve penceresi sınıfları içerir; menüleri ve isteğe bağlı bir araç çubuğu dahil olmak üzere standart kaynakları; diğer gerekli Windows dosyaları; ve isteğe bağlı .rtf dosyaları gözden geçirebilirsiniz, standart Windows Yardım konularını ve programınızın Yardım dosyası oluşturmak için ayırma içeren.  
  
##  <a name="_core_use_classwizard_to_manage_classes_and_windows_messages"></a> Sınıf Görünümü sınıfları ve Windows iletilerini yönetmek için kullanın  
 İşleyici işlevleri Windows iletiler ve komutlar için oluşturma, oluşturma ve sınıfları yönetme sınıfı görünüm yardımcı sınıf üyesi değişkenleri oluşturma, Otomasyon yöntemleri ve özellikleri oluşturma ve veritabanı sınıfları oluşturma.  
  
> [!NOTE]
>  Sınıf görünümü de MFC sınıfları içinde sanal işlevleri geçersiz kılma yardımcı olur. Sınıf ve sanal işlevi geçersiz kılmak için seçin. Aşağıdaki paragrafta açıklanan işleminin geri kalanında ileti işleme için benzer.  
  
 Windows altında çalışan uygulamalar [ileti güdümlü](../mfc/message-handling-and-mapping.md). Kullanıcı eylemleri ve çalışan programa meydana gelen diğer olayları program windows iletileri göndermek Windows neden olur. Örneğin, kullanıcının fare penceresinde tıklarsa, Windows gönderir bir `WM_LBUTTONDOWN` ileti sol fare düğmesine basıldığında ve `WM_LBUTTONUP` düğmesi serbest bırakıldığında iletisi. Ayrıca Windows gönderir **WM_COMMAND** kullanıcı menü çubuğundan komutları seçtiğinde iletileri.  
  
 MFC çerçevesi belgeler, görünümler, çerçeve pencereleri, belge şablonları ve uygulama nesnesi gibi çeşitli nesneleri "iletileri işleyebilir". Böyle bir nesnenin "işleyicisi işlevi" kendi üyesi biri olarak işlevleri sağlar ve framework gelen ileti işleyicisine eşler.  
  
 Programlama göreviniz büyük bir bölümünü hangi nesnelerin eşlemek için hangi iletilerin seçme ve bu eşlemenin uygulama. Bunu yapmak için sınıf görünümü ve Özellikler penceresini kullanın.  
  
 Özellikler penceresini boş ileti işleyicisi üye işlevleri oluşturacak ve işleyici gövdesi uygulamak için kaynak kod Düzenleyicisi'ni kullanın. Ayrıca oluşturabilir veya (MFC sınıfları türetilmemiş sınıflar, kendi dahil) sınıflar ve üyeleri sınıf görünümü ile düzenleyebilirsiniz. Sınıf görünümü kullanarak ve projeye kod ekleme sihirbazları hakkında daha fazla bilgi için bkz: [kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md).  
  
##  <a name="_core_use_the_resource_editors_to_create_and_edit_resources"></a> Kaynak düzenleyicileri oluşturmak ve kaynakları düzenlemek için kullanın  
 Visual C++ kullanma [kaynak düzenleyicileri](../windows/resource-editors.md) menüleri, iletişim kutuları, özel denetimler, Hızlandırıcı tuşları, bit eşlemler, simgeler, imleçler, dizeleri ve sürüm kaynakları oluşturmak ve düzenlemek için. Visual C++ sürüm 4.0 itibariyle bir araç çubuğu Düzenleyicisi oluşturma araç çubukları çok daha kolay hale getirir.  
  
 Daha fazla yardımcı olmak için Microsoft Foundation Class Kitaplığı ortak adlı bir dosya sağlar. RES gelen ortak kopyalayabilirsiniz "küçük resim" kaynakları içerir. RES ve kendi kaynak dosyasına yapıştırın. ORTAK. RES araç çubuğu düğmeleri, ortak imleçler, simgeler ve daha fazlasını içerir. Kullanın, değiştirmek ve bu kaynakları uygulamanızda yeniden dağıtabilir. Ortak hakkında daha fazla bilgi için. RES, bkz: [küçük örnek](../visual-cpp-samples.md).  
  
 MFC Uygulama Sihirbazı'nı, Visual C++ sihirbazları, kaynak düzenleyicileri ve MFC çerçevesi çok fazla iş yapmanız ve kodunuzu çok daha kolay hale. Uygulamaya özgü kod toplu, belge ve görünüm sınıfları ' dir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Uygulamaları Yazmak için Sınıfları Kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md)
