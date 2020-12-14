---
description: 'Daha fazla bilgi edinin: kayıt'
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
ms.openlocfilehash: 8254f4b1ab8a005623650794adc8be0bd06cfdff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218127"
---
# <a name="registration"></a>Kayıt

Bir Kullanıcı bir uygulamaya OLE öğesi eklemek istediğinde OLE, aralarından seçim yapabileceğiniz nesne türlerinin bir listesini sunar. OLE bu listeyi tüm sunucu uygulamaları tarafından sunulan bilgileri içeren sistem kayıt veritabanından alır. Bir sunucu kendisini kaydettiğinde, sistem kayıt veritabanına (kayıt defteri) sahip olduğu girişler, diğer bilgiler arasında, sağladığı her nesne türünü, dosya uzantılarını ve onun yolunu anlatmaktadır.

Framework ve OLE sistem dinamik bağlantı kitaplıkları (DLL), sistemde hangi tür OLE öğelerinin kullanılabilir olduğunu belirlemek için bu kayıt defterini kullanır. OLE sistem dll 'Leri bu kayıt defterini Ayrıca, bağlantılı veya katıştırılmış bir nesne etkinleştirildiğinde sunucu uygulamasının nasıl başlatılaleceğini tespit etmek için de kullanır.

Bu makalede her bir sunucu uygulamasının, yüklendiğinde ve her yürütüldüğünde yapması gerekenler açıklanmaktadır.

Sistem kayıt veritabanı ve bu dosyayı güncelleştirmek için kullanılan. reg dosyalarının biçimi hakkında ayrıntılı bilgi için bkz. *OLE Programcı başvurusu*.

## <a name="server-installation"></a><a name="_core_server_installation"></a> Sunucu yüklemesi

Sunucu uygulamanızı ilk kez yüklediğinizde, desteklediği tüm OLE öğesi türlerini kaydetmesi gerekir. Ayrıca, sunucunun tek başına bir uygulama olarak her yürütüldüğünde sistem kayıt veritabanını güncelleştirmesini de sağlayabilirsiniz. Bu, sunucunun yürütülebilir dosyası taşındığında kayıt veritabanını güncel tutar.

> [!NOTE]
> Uygulama Sihirbazı tarafından oluşturulan MFC uygulamaları, tek başına uygulamalar olarak çalıştırıldıklarında otomatik olarak kendilerini kaydeder.

Uygulamanızı yükleme sırasında kaydetmek istiyorsanız RegEdit.exe programını kullanın. Uygulamanıza sahip bir kurulum programı eklerseniz, Kurulum programının "RegEdit/S *appname*. reg" çalıştırmasını sağlayabilirsiniz. (/S bayrağı sessiz işlemi gösterir, diğer bir deyişle, komutun başarıyla tamamlandığını bildiren iletişim kutusunu göstermez.) Aksi takdirde, kullanıcıdan RegEdit 'i el ile çalıştırmasını isteyin.

> [!NOTE]
> Uygulama Sihirbazı tarafından oluşturulan. reg dosyası yürütülebilir dosyanın tüm yolunu içermez. Yükleme programınız, yürütülebilir dosyanın tüm yolunu içerecek şekilde. reg dosyasını değiştirmeli ya da PATH ortam değişkenini yükleme dizinini içerecek şekilde değiştirecek.

RegEdit,. reg metin dosyasının içeriğini kayıt veritabanıyla birleştirir. Veritabanını doğrulamak veya onarmak için kayıt defteri düzenleyicisini kullanın. Önemli OLE girdilerini silmekten kaçının.

## <a name="server-initialization"></a><a name="_core_server_initialization"></a> Sunucu başlatma

Uygulama Sihirbazı ile bir sunucu uygulaması oluşturduğunuzda, sihirbaz tüm başlatma görevlerini sizin için otomatik olarak tamamlar. Bu bölümde, bir sunucu uygulamasını el ile yazarsanız yapmanız gerekenler açıklanmaktadır.

Bir sunucu uygulaması bir kapsayıcı uygulama tarafından başlatıldığında OLE sistem dll 'Leri sunucunun komut satırına "/katıştırma" seçeneğini ekler. Sunucu uygulamasının davranışı bir kapsayıcı tarafından başlatılıp başlatıldığına bağlı olarak farklılık gösterir. bu nedenle, uygulamanın yürütme başladığında yapması gereken ilk şey, komut satırında "/gömme" veya "-gömme" seçeneğini denetler. Bu anahtar varsa, sunucuyu yerinde etkin veya tam açık olarak gösteren farklı bir kaynak kümesi yükleyin. Daha fazla bilgi için bkz. [menüler ve kaynaklar: sunucu eklemeleri](../mfc/menus-and-resources-server-additions.md).

Sunucu uygulamanız `CWinApp::RunEmbedded` , komut satırını ayrıştırmak için işlevini de çağırmalıdır. Sıfır dışında bir değer döndürürse, uygulamanın, tek başına bir uygulama olarak değil bir kapsayıcı uygulamasından çalıştırıldığı için, pencereyi göstermemelidir. Bu işlev, sistem kayıt veritabanındaki sunucu girişini güncelleştirir ve `RegisterAll` örnek kaydı gerçekleştirerek, sizin için üye işlevini çağırır.

Sunucu uygulamanız başlatıldığında, örnek kayıt işlemini gerçekleştire, emin olmanız gerekir. Örnek kaydı, OLE sistem dll 'Lerine sunucunun etkin olduğunu ve kapsayıcılardan istekleri almaya hazırlı olduğunu bildirir. Kayıt veritabanına giriş eklemez. Tarafından tanımlanan üye işlevini çağırarak sunucunun örnek kaydını gerçekleştirin `ConnectTemplate` `COleTemplateServer` . Bu, `CDocTemplate` nesnesini `COleTemplateServer` nesnesine bağlar.

`ConnectTemplate`İşlev üç parametre alır: sunucunun *CLSID 'si*, `CDocTemplate` nesne işaretçisi ve sunucunun birden çok örneği destekleyip desteklemediğini belirten bir bayrak. Bir minıver, birden çok örneği destekleyebilmelidir, yani her bir kapsayıcı için sunucunun birden çok örneğinin aynı anda çalıştırılması mümkün olmalıdır. Sonuç olarak, bir minıver başlatılırken bu bayrak için **true** geçirin.

Tanım olarak bir minıver yazıyorsanız, her zaman bir kapsayıcı tarafından başlatılır. "/Katıştırma" seçeneğini denetlemek için yine de komut satırını ayrıştırmalısınız. Bu seçeneğin komut satırında yokluğu, kullanıcının minıver 'i tek başına bir uygulama olarak başlatmaya çalıştığı anlamına gelir. Bu durum oluşursa, sunucuyu sistem kayıt veritabanına kaydedin ve sonra kullanıcıya bir kapsayıcı uygulamadan minıver 'i başlatması konusunda bilgilendiren bir ileti kutusu görüntüleyin.

## <a name="see-also"></a>Ayrıca bkz.

[OLE](../mfc/ole-in-mfc.md)<br/>
[Sunucular](../mfc/servers.md)<br/>
[CWinApp:: RunAutomated](../mfc/reference/cwinapp-class.md#runautomated)<br/>
[CWinApp:: RunEmbedded](../mfc/reference/cwinapp-class.md#runembedded)<br/>
[Cotatemplateserver sınıfı](../mfc/reference/coletemplateserver-class.md)
