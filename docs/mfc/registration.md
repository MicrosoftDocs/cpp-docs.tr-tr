---
title: Kayıt
ms.date: 11/04/2016
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
ms.openlocfilehash: 0bc606acfba26d27d0ab36045e4772593e760e98
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309104"
---
# <a name="registration"></a>Kayıt

OLE öğesini bir uygulamaya eklemek bir kullanıcı istediği zaman, OLE Seçilecek nesne türlerinin bir listesini sunar. OLE bu liste tüm sunucu uygulamaları tarafından sağlanan bilgiler içeren sistem kayıt veritabanından alır. Bir sunucu kendisini kaydeder olduğunda girişleri sistem kayıt veritabanına (kayıt defteri) koyar her bunu sağlayan nesne türünü açıklayan, dosya uzantıları ve diğer bilgileri arasında kendisi yolu.

OLE öğeleri ne tür sisteminde kullanılabilir olduğunu belirlemek için bu kayıt defteri framework ve OLE Sistem dinamik bağlantı kitaplıklarını (DLL)'ı kullanın. OLE sistem DLL'leri de bu kayıt defteri bağlantılı veya katıştırılmış nesne etkinleştirildiğinde, bir sunucu uygulaması başlatmak nasıl belirlemek için kullanır.

Bu makalede her sunucu uygulamasının yüklü olduğunda yapmak gereken açıklar ve her zaman yürütülür.

Sistem kayıt veritabanı ve güncelleştirmek için kullanılan .reg dosyalarının biçimi hakkında ayrıntılı bilgi için bkz. *OLE Programcı Başvurusu*.

##  <a name="_core_server_installation"></a> Sunucu yükleme

Sunucu uygulamasının ilk kez yüklediğinizde, onu destekleyen OLE öğelerinin tüm türleri kaydetmeniz. Ayrıca, bağımsız bir uygulama olarak her çalıştırıldığında sistem kayıt veritabanı güncelleştirme sunucusu olabilir. Sunucu yürütülebilir dosyası taşınırsa kayıt veritabanı güncel tutar.

> [!NOTE]
>  MFC uygulamaları Uygulama Sihirbazı tarafından otomatik olarak oluşturulan, tek başına uygulamalar olarak çalıştırdığınızda kendilerini kaydedin.

Yükleme sırasında uygulamanızı kaydetmek istiyorsanız, RegEdit.exe programı kullanın. Uygulamanızla bir Kurulum programı eklerseniz, Kurulum programını çalıştırın sahip "RegEdit /S *appname*.reg". (Sessiz işlemi /S bayrağı gösterir, diğer bir deyişle, komut başarılı olarak tamamlanmasına bildirimi iletişim kutusu görüntülemez.) Aksi takdirde, RegEdit el ile çalıştırmak için kullanıcıdan isteyin.

> [!NOTE]
>  Uygulama Sihirbazı tarafından oluşturulan .reg dosyası, yürütülebilir dosyanın tam yolunu içermez. Yükleme programınızı ya da yürütülebilir dosyanın tam yolunu içerir veya yol ortam değişkenine yükleme dizini içerecek şekilde değiştirmek için .reg dosyasını değiştirmeniz gerekir.

RegEdit kayıt veritabanına .reg metin dosyasının içeriğini birleştirir. Veritabanını doğrulayabilir veya onarmak için Kayıt Defteri Düzenleyicisi'ni kullanın. Temel OLE girdileri silme kaçınmak için dikkatli olun.

##  <a name="_core_server_initialization"></a> Sunucu başlatma

Uygulama Sihirbazı'nı sunucu uygulaması oluşturduğunuzda, sihirbaz tüm başlatma görevlerini sizin için otomatik olarak tamamlar. El ile bir sunucu uygulaması yazıyorsanız yapmanız gerekir, bu bölümde açıklanmaktadır.

Bir kapsayıcı uygulama tarafından bir sunucu uygulaması başlatıldığında, OLE sistem DLL'lerini "/ ekleme" seçeneği sunucunun komut satırına ekleyin. Bir sunucu uygulamanın davranışını onay için bir uygulama yapılmalı mı yürütme başladığında ilk şey, bu nedenle olup, bir kapsayıcı tarafından başlatıldı bağlı olarak farklılık gösterir. "/ ekleme" veya "-katıştırma" komut satırı seçeneği. Bu anahtarı varsa, sunucu ya da yerinde etkin olarak gösteren kaynakları farklı bir kümesini yüklemek veya tam olarak açın. Daha fazla bilgi için [menüler ve kaynaklar: Sunucu ekleme](../mfc/menus-and-resources-server-additions.md).

Sunucu uygulamasının de çağırmalı, `CWinApp::RunEmbedded` komut satırını Ayrıştır için işlevi. Sıfır olmayan bir değer döndürürse, tek başına bir uygulama olarak değil, bir kapsayıcı uygulamasından çalıştırıldığından uygulama penceresi göstermelidir değil. Bu işlev çağrıları ve sistem kayıt veritabanı sunucusunun girişini güncelleştirir `RegisterAll` , örnek kayıt gerçekleştirmek için üye işlevi.

Sunucu uygulamanız başlatılırken örneği kaydı gerçekleştirebilirsiniz emin olmanız gerekir. Örnek kayıt OLE sistem DLL'lerini sunucunun etkin ve kapsayıcılardan isteklerini almak hazır olduğunu bildirir. Kayıt veritabanı için bir giriş eklemez. Sunucu örneğinin kaydını çağırarak gerçekleştirmek `ConnectTemplate` üye işlevi tarafından tanımlanan `COleTemplateServer`. Bu bağlar `CDocTemplate` nesnesini `COleTemplateServer` nesnesi.

`ConnectTemplate` İşlevi üç parametreleri alır: sunucunun *CLSID*, işaretçi `CDocTemplate` nesne ve sunucunun birden çok örneği destekleyip desteklemediğini belirten bir bayrak. Bir miniserver birden çok örneği destekleyebilen, diğer bir deyişle, olası bir her kapsayıcı için eşzamanlı olarak çalışacak şekilde sunucusunun birden çok örnek için olmalıdır. Sonuç olarak, geçirmek **TRUE** bir miniserver başlatırken bu bayrağı için.

Her zaman bir kapsayıcı tarafından başlatılan tanımına göre bir miniserver yazıyorsanız. "/ Ekleme" seçeneğini denetlemek için komut satırı hala çözümlenmelidir. Bu seçeneğin komut satırında olmaması, kullanıcı tek başına bir uygulama olarak miniserver başlatmaya çalıştı anlamına gelir. Bu meydana gelirse, sistem kayıt veritabanı ile sunucu kaydedin ve ardından bir kapsayıcı uygulamasından miniserver başlatmak için kullanıcı bildiren bir ileti kutusu görüntüler.

## <a name="see-also"></a>Ayrıca bkz.

[OLE](../mfc/ole-in-mfc.md)<br/>
[Sunucular](../mfc/servers.md)<br/>
[CWinApp::RunAutomated](../mfc/reference/cwinapp-class.md#runautomated)<br/>
[CWinApp::RunEmbedded](../mfc/reference/cwinapp-class.md#runembedded)<br/>
[COleTemplateServer Sınıfı](../mfc/reference/coletemplateserver-class.md)
