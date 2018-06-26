---
title: Kayıt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- servers [MFC], initializing
- initializing servers [MFC]
- OLE, registration
- installing servers [MFC]
- registry [MFC], OLE item database
- registration databases [MFC]
- servers [MFC], installing
- OLE server applications [MFC], registering servers
ms.assetid: 991d5684-72c1-4f9e-a09a-9184ed12bbb9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6d51589d9261d497c4c1f9185bd90b889e46eb34
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930696"
---
# <a name="registration"></a>Kayıt
Bir kullanıcı bir uygulamaya bir OLE öğesi eklemek istediğinde OLE Seçilecek nesne türlerinin bir listesini gösterir. OLE bu listedeki tüm sunucu uygulamaları tarafından sağlanan bilgileri içeren sistem kayıt veritabanından alır. Bir sunucu için kendisini kaydettiğinde, sistem kayıt veritabanına (kayıt defteri) koyar girişler her onu sağlayan nesnesi türünü açıklar, dosya uzantıları ve yolunu kendisi, diğer bilgilerin yanı.  
  
 OLE öğeleri ne tür sistem üzerinde kullanılabilir olduğunu belirlemek için bu kayıt defteri framework ve OLE sistemi dinamik bağlantı kitaplığı (DLL)'ı kullanın. OLE sistem DLL'leri de bu kayıt defteri bağlantılı veya katıştırılmış bir nesneyi etkinleştirildiğinde, bir sunucu uygulaması başlatmak nasıl belirlemek için kullanın.  
  
 Her sunucu uygulaması yüklendiğinde yapması gereken açıklanmakta ve her zaman yürütülür.  
  
 Sistem kayıt veritabanı ve güncelleştirmek için kullanılan .reg dosyaları biçimi hakkında ayrıntılı bilgi için bkz: *OLE Programcı Başvurusu*.  
  
##  <a name="_core_server_installation"></a> Sunucu yükleme  
 Sunucu uygulamasının ilk kez yüklediğinizde, onu destekleyen OLE öğelerinin tüm türleri kaydetmelisiniz. Bağımsız bir uygulama olarak yürütülmeden her zaman sistem kaydı veritabanı güncelleştirme Sunucusu'nu da sahip olabilirsiniz. Sunucunun yürütülebilir dosya taşınırsa kaydı veritabanı güncel tutar.  
  
> [!NOTE]
>  Bağımsız uygulamalar çalıştırdığınızda MFC Uygulama Sihirbazı tarafından otomatik olarak oluşturulan uygulamaları kendilerini kaydedin.  
  
 Yükleme sırasında uygulamanız kaydetmek istiyorsanız, RegEdit.exe programı kullanın. Uygulamanızla birlikte bir Kurulum programı eklerseniz, Kurulum programı çalıştır sahip "RegEdit /S *appname*.reg". (Diğer bir deyişle, komutun başarılı tamamlanma bildirimi iletişim kutusu görüntülemez, sessiz işlemi /S bayrağı gösterir.) Aksi takdirde, RegEdit el ile çalıştırmak için kullanıcıdan isteyin.  
  
> [!NOTE]
>  Uygulama Sihirbazı tarafından oluşturulan .reg dosyasını yürütülebilir dosyanın tam yolunu içermez. Yükleme programı ya da çalıştırılabilir dosyanın tam yolunu içerir veya PATH ortam değişkeni yükleme dizini içerecek şekilde değiştirmek için .reg dosyasını değiştirmeniz gerekir.  
  
 RegEdit kayıt veritabanına .reg metin dosyasının içeriğini birleştirir. Veritabanı doğrulamak veya onarmak için Kayıt Defteri Düzenleyicisi'ni kullanın. Temel OLE girdileri silme kaçınmaya dikkat edin.  
  
##  <a name="_core_server_initialization"></a> Sunucu başlatma  
 Uygulama Sihirbazı'nı bir sunucu uygulaması oluşturduğunuzda, sihirbazın tüm başlatma görevlerini sizin yerinize otomatik olarak tamamlar. Bu bölümde, bir sunucu uygulaması el ile yazarsanız yapmanız gerekir açıklanmaktadır.  
  
 Bir kapsayıcı uygulama tarafından bir sunucu uygulaması başlatıldığında, OLE sistem DLL'leri "/ katıştırma" seçeneği sunucunun komut satırı ekleyin. Bir sunucu uygulamanın davranışını denetleme uygulama yapılmalı mı yürütme başladığında ilk şey olacak şekilde olup, bir kapsayıcı tarafından başlatıldı bağlı olarak farklı "/ katıştırma" veya "-katıştırma" komut satırı seçeneği. Bu anahtarı varsa, sunucu ya da yerinde etkin olarak göstermek kaynakları farklı bir kümesini yüklemek veya tam olarak açın. Daha fazla bilgi için bkz: [menüler ve kaynaklar: sunucu ekleme](../mfc/menus-and-resources-server-additions.md).  
  
 Sunucu uygulamanız da çağırmalıdır kendi `CWinApp::RunEmbedded` komut satırında ayrıştırma işlevi. Sıfır olmayan bir değer döndürürse, bağımsız bir uygulama olarak değil, bir kapsayıcı uygulamasından çalıştırıldığından uygulama onun penceresi göstermelidir değil. Bu işlev çağrıları ve sistem kaydı veritabanı sunucunun girişini güncelleştirir `RegisterAll` , örnek kayıt gerçekleştirmek için üye işlevi.  
  
 Sunucu uygulamanız başlatılırken örneği kayıt gerçekleştirebilirsiniz emin olmalısınız. Örnek kayıt OLE sistem DLL'leri sunucunun etkin ve kapsayıcılardan istekleri almaya hazır olduğunu bildirir. Bir giriş kayıt veritabanına eklemez. Örnek kayıt sunucusunun çağırarak gerçekleştirmek `ConnectTemplate` üye fonksiyonu tarafından tanımlanan `COleTemplateServer`. Bu bağlar `CDocTemplate` nesnesini `COleTemplateServer` nesne.  
  
 `ConnectTemplate` İşlev üç parametreleri alır: sunucunun *CLSID*, bir işaretçi `CDocTemplate` nesne ve sunucuyu birden çok örneği destekleyip desteklemediğini belirten bir bayrak. Bir miniserver birden çok örneği destekleyebilmesi gerekir, diğer bir deyişle, aynı anda, her kapsayıcı için bir tane çalıştırmak için sunucunun birden çok örneği için olası olmalıdır. Sonuç olarak, geçirmek **doğru** bir miniserver başlatılırken Bu bayrak için.  
  
 Her zaman bir kapsayıcı tarafından başlatılan tanımı tarafından bir miniserver yazıyorsanız. Hala "/ katıştırma" seçeneğini denetlemek için komut satırında ayrıştırma. Bu seçenek komut satırında yokluğu kullanıcı bağımsız bir uygulama olarak miniserver başlatmaya çalıştı anlamına gelir. Bu durumda, sistem kayıt veritabanıyla sunucuyu kaydetmek ve kullanıcıya bir kapsayıcı uygulamasından miniserver başlatma bildiren bir ileti kutusu görüntüler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE](../mfc/ole-in-mfc.md)   
 [Sunucuları](../mfc/servers.md)   
 [CWinApp::RunAutomated](../mfc/reference/cwinapp-class.md#runautomated)   
 [CWinApp::RunEmbedded](../mfc/reference/cwinapp-class.md#runembedded)   
 [COleTemplateServer Sınıfı](../mfc/reference/coletemplateserver-class.md)
