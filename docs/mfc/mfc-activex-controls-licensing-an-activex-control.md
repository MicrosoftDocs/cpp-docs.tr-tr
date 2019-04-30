---
title: 'MFC ActiveX denetimleri: ActiveX denetimini lisanslama'
ms.date: 11/19/2018
f1_keywords:
- COleObjectFactory
helpviewer_keywords:
- COleObjectFactory class [MFC], licensing controls
- MFC ActiveX controls [MFC], licensing
- VerifyLicenseKey method [MFC]
- VerifyUserLicense method [MFC]
- GetLicenseKey method [MFC]
- licensing ActiveX controls
ms.assetid: cacd9e45-701a-4a1f-8f1f-b0b39f6ac303
ms.openlocfilehash: eda2ea08c6bd3526befb71c704aa20eba6935b04
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392771"
---
# <a name="mfc-activex-controls-licensing-an-activex-control"></a>MFC ActiveX denetimleri: ActiveX denetimini lisanslama

Destek lisanslama, ActiveX denetimlerinin, isteğe bağlı bir özellik sayesinde kullanın veya denetim dağıtmak mümkün olan denetim. (Lisans sorunları ek açıklaması için bkz: Lisans sorunları [varolan bir ActiveX denetimini güncelleştirme](../mfc/upgrading-an-existing-activex-control.md).)

> [!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerine geçen modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).

Bu makalede, aşağıdaki konular ele alınmaktadır:

- [ActiveX denetimini lisanslama genel bakış](#_core_overview_of_activex_control_licensing)

- [Lisanslı bir denetim oluşturma](#_core_creating_a_licensed_control)

- [Lisans desteği](#_core_licensing_support)

- [Bir ActiveX denetimini lisanslama özelleştirme](#_core_customizing_the_licensing_of_an_activex_control)

Lisanslama uygulayan ActiveX denetimleri, diğer kişilerin ActiveX denetimini nasıl kullanacağını belirleme denetim geliştiriciyseniz izin verin. Denetim yerleştirmesi denetimle sağlayın ve. LİS dosyasıyla satın alan denetimi dağıtacağını ancak sözleşme. Denetimi kullanan bir uygulama ile lisans sözleşmesi dosyası. Bu denetim, Denetim ilk lisans olmadan kullanan yeni uygulamalar yazma, uygulamanın kullanıcıları engeller.

##  <a name="_core_overview_of_activex_control_licensing"></a> ActiveX denetimini lisanslama genel bakış

ActiveX denetimleri için lisanslama destek sağlamak üzere [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) SAX içinde çeşitli işlevler için bir uygulama `IClassFactory2` arabirimi: `IClassFactory2::RequestLicKey`, `IClassFactory2::GetLicInfo`, ve `IClassFactory2::CreateInstanceLic`. Kapsayıcı uygulama geliştiricisinin denetimi, bir çağrı örneğini oluşturma isteği yapar ne zaman `GetLicInfo` doğrulamak için yapılan denetim. Lisans Sözleşmesi dosya yok. Denetim lisanslanmışsa denetim örneği oluşturulabilir ve kapsayıcıda yerleştirilir. Geliştirici kapsayıcı uygulaması oluşturma işlemini tamamladıktan sonra başka bir işlev çağrısı, şu anda `RequestLicKey`, yapılır. Bu işlev, kapsayıcılı bir uygulama bir lisans anahtarı (Basit karakter dizesi) döndürür. Döndürülen anahtar ardından uygulamada katıştırılır.

Aşağıdaki şekilde, lisans doğrulama, kapsayıcılı bir uygulama geliştirme sırasında kullanılacak bir ActiveX denetimi gösterir. Daha önce belirtildiği gibi kapsayıcı uygulama geliştiricisinin uygun olması gerekir. LİS dosyası denetimi örneğini oluşturmak için geliştirme makinenizde yüklü.

![ActiveX denetimi geliştirme için doğrulanmış lisanslı](../mfc/media/vc374d1.gif "geliştirme için doğrulanmış lisanslı bir ActiveX denetimi") <br/>
Geliştirme sırasında doğrulama lisanslı bir ActiveX denetimi

Son kullanıcı kapsayıcı uygulama çalışırken aşağıdaki şekilde gösterilen sonraki işlemi gerçekleşir.

Uygulama başlatıldığında denetim örneği genellikle oluşturulması gerekir. Kapsayıcı bu çağrı yaparak gerçekleştirir. `CreateInstanceLic`, katıştırılmış lisans anahtarı bir parametre olarak geçirerek. Dize karşılaştırması, sonra katıştırılmış lisans anahtarı ve lisans anahtarı denetimin kendi kopyasını arasında yapılır. Eşleşmenin başarılı olursa, denetim bir örneği oluşturulur ve uygulama normal çalışmasına devam eder. Dikkat edin. Lisans Sözleşmesi dosya denetim kullanıcının makinede mevcut olması gerekmez.

![ActiveX denetimi yürütmeyi doğrulandı lisanslı](../mfc/media/vc374d2.gif "yürütmeyi doğrulandı lisanslı bir ActiveX denetimi") <br/>
Yürütme sırasında doğrulama lisanslı bir ActiveX denetimi

Denetimini lisanslama, iki temel bileşenden oluşur: DLL denetimi uygulamada belirli kod ve lisans dosyası. Kod, iki (veya büyük olasılıkla üç) işlev çağrıları ve bundan sonra "Telif hakkı bildirimi içeren bir lisans dize olarak" başvurulan bir karakter dizesi oluşur. Bu çağrılar ve lisans dize denetim uygulamasında bulunur (. CPP) dosyası. ActiveX Denetim Sihirbazı tarafından üretilen lisans dosyası, telif hakkı bildirimini içeren bir metin dosyasıdır. Proje adı ile kullanarak adlı bir. Lisans Sözleşmesi uzantısı, örneğin örnek. LİSANS SÖZLEŞMESİ. Tasarım zamanında kullanımı gerekirse lisanslı bir denetim tarafından bir lisans dosyası bulunmalıdır.

##  <a name="_core_creating_a_licensed_control"></a> Lisanslı bir denetim oluşturma

ActiveX Denetim Sihirbazı'nı denetim çerçevesi oluşturmak için kullandığınız zaman desteği içeren çok daha kolaydır. Denetimi bir çalışma zamanı Lisansı olmalıdır belirttiğinizde, ActiveX Denetim Sihirbazı'nı lisanslama desteklemek için denetim sınıfı için kod ekler. Lisans doğrulama için bir anahtar ve lisansın dosyası kullanan işlevler kod oluşur. Bu işlevler, aynı zamanda denetimini lisanslama özelleştirmek için değiştirilebilir. Lisans özelleştirme hakkında daha fazla bilgi için bkz. [bir ActiveX denetimini lisanslama özelleştirme](#_core_customizing_the_licensing_of_an_activex_control) bu makalenin ilerleyen bölümlerinde.

#### <a name="to-add-support-for-licensing-with-the-activex-control-wizard-when-you-create-your-control-project"></a>Denetim projenizi oluşturduğunuzda ile ActiveX Denetim Sihirbazı'nı lisanslama için destek eklemek için

1. Yönergeleri kullanın [MFC ActiveX denetimi oluşturma](../mfc/reference/creating-an-mfc-activex-control.md). **Uygulama ayarları** ActiveX Denetim Sihirbazı'nın sayfa denetimi ile çalışma zamanı lisansı oluşturmak için bu seçeneği içerir.

ActiveX Denetim Sihirbazı'nı temel lisans desteği içeren bir ActiveX denetimi çerçeve şimdi oluşturur. Lisans kodu ayrıntılı bir açıklaması için sonraki konusuna bakın.

##  <a name="_core_licensing_support"></a> Lisans desteği

Bir ActiveX denetimine lisanslama desteği eklemek için ActiveX Denetim Sihirbazı'nı kullandığınızda, ActiveX Denetim Sihirbazı'nı bildirir ve lisans özelliği uygulayan kodu control üst bilgisi ve uygulama dosyaları eklenir ekler. Bu kod çağrılardan oluşan bir `VerifyUserLicense` üye işlevi ve bir `GetLicenseKey` bulunan varsayılan uygulamaları geçersiz üye işlevini [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) . Bu işlevler, almak ve denetim lisans doğrulayın.

> [!NOTE]
>  Üçüncü üye işlevi, `VerifyLicenseKey` ActiveX Denetim Sihirbazı tarafından oluşturulmaz, ancak lisans anahtarı doğrulama davranışını özelleştirmek için geçersiz kılınabilir.

Bu üye işlevleri şunlardır:

- [VerifyUserLicense](../mfc/reference/coleobjectfactory-class.md#verifyuserlicense)

   Denetimin denetimi lisans dosyasının varlığı için sistemi kontrol ederek tasarım zamanı kullanım izin doğrular. Bu işlev, işleme bir parçası olarak çerçeve tarafından çağrılır `IClassFactory2::GetLicInfo` ve `IClassFactory::CreateInstanceLic`.

- [GetLicenseKey](../mfc/reference/coleobjectfactory-class.md#getlicensekey)

   Benzersiz bir anahtar DLL denetiminden ister. Bu anahtar kapsayıcısı uygulamaya ve daha sonra birlikte kullanılan `VerifyLicenseKey`, denetimin bir örneği oluşturulamadı. Bu işlev, işleme bir parçası olarak çerçeve tarafından çağrılır `IClassFactory2::RequestLicKey`.

- [VerifyLicenseKey](../mfc/reference/coleobjectfactory-class.md#verifylicensekey)

   Katıştırılmış anahtar ve denetimin benzersiz anahtar aynı olduğunu doğrular. Bu denetim kullanımı için bir örneğini oluşturmak kapsayıcı sağlar. Bu işlev, işleme bir parçası olarak çerçeve tarafından çağrılır `IClassFactory2::CreateInstanceLic` ve özelleştirilmiş lisans anahtarı sağlamak için geçersiz kılınabilir. Varsayılan uygulama, bir dize karşılaştırma gerçekleştirir. Daha fazla bilgi için [bir ActiveX denetimini lisanslama özelleştirme](#_core_customizing_the_licensing_of_an_activex_control), bu makalenin ilerleyen bölümlerinde.

###  <a name="_core_header_file_modifications"></a> Üstbilgi dosya değişiklikleri

ActiveX Denetim Sihirbazı'nı aşağıdaki kodu denetimi üstbilgi dosyasına yerleştirir. Bu örnekte, iki üye işlevleri `CSampleCtrl`kullanıcının nesne `factory` bildirildiğinde, bir denetimin varlığını doğrular. Lisans Sözleşmesi dosya ve diğeri de denetimi içeren uygulama lisans anahtarı alır:

[!code-cpp[NVC_MFC_AxUI#39](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_1.h)]

###  <a name="_core_implementation_file_modifications"></a> Uygulama dosya değişiklikleri

ActiveX Denetim Sihirbazı'nı aşağıdaki iki deyimi lisans filename ve lisans dize bildirmek için denetim uygulaması dosyasına yerleştirir:

[!code-cpp[NVC_MFC_AxUI#40](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_2.cpp)]

> [!NOTE]
>  Değiştirirseniz `szLicString` herhangi bir yolla da denetimin ilk satırı değiştirmeniz gerekir. Lisans Sözleşmesi dosya ya da lisans düzgün çalışmaz.

ActiveX Denetim Sihirbazı'nı aşağıdaki kodu denetimi sınıfını tanımlamak için denetim uygulaması dosyasına yerleştirir. `VerifyUserLicense` ve `GetLicenseKey` İşlevler:

[!code-cpp[NVC_MFC_AxUI#41](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_3.cpp)]

Son olarak, **ActiveX Denetim Sihirbazı'nı** denetimi projeyi değiştirir. IDL dosyası. **Lisanslı** anahtar sözcüğü, aşağıdaki örnekte olduğu gibi denetim coclass'ı bildirimi eklenir:

[!code-cpp[NVC_MFC_AxUI#42](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_4.idl)]

##  <a name="_core_customizing_the_licensing_of_an_activex_control"></a> Bir ActiveX denetimini lisanslama özelleştirme

Çünkü `VerifyUserLicense`, `GetLicenseKey`, ve `VerifyLicenseKey` bildirilir denetim fabrika sınıfı sanal üye işlevleri denetimin lisans davranışını özelleştirebilirsiniz.

Örneğin, denetim için geçersiz kılarak lisanslama çeşitli düzeylerde sağlayabilir `VerifyUserLicense` veya `VerifyLicenseKey` üye işlevleri. Bu işlev içinde hangi özelliklerinin veya yöntemlerin algıladığınız lisans düzeyinize kullanıcıya sunulan ayarlamak.

Kod ayrıca ekleyebilirsiniz `VerifyLicenseKey` işlevi oluşturma denetleyen kullanıcı bildiren başarısız oldu, özelleştirilmiş bir yöntem sağlar. Örneğin, uygulamanızın `VerifyLicenseKey` üye işlevi bir ileti görüntüler kutusu denetim başlatılamadı belirten ve neden.

> [!NOTE]
>  ActiveX denetimi lisans doğrulama özelleştirmek için başka bir yöntem çağırmak yerine, belirli kayıt defteri anahtarı için kayıt defteri veritabanında denetlemektir `AfxVerifyLicFile`. Varsayılan uygulama örneği için bkz: [uygulama dosya değişiklikleri](#_core_implementation_file_modifications) bu makalenin.

Lisanslama sorunları lisans sorunları ek açıklaması için bkz. [varolan bir ActiveX denetimini güncelleştirme](../mfc/upgrading-an-existing-activex-control.md).

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md)
