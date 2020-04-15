---
title: 'MFC ActiveX Denetimleri: ActiveX Denetimini Lisanslama'
ms.date: 11/19/2018
helpviewer_keywords:
- COleObjectFactory class [MFC], licensing controls
- MFC ActiveX controls [MFC], licensing
- VerifyLicenseKey method [MFC]
- VerifyUserLicense method [MFC]
- GetLicenseKey method [MFC]
- licensing ActiveX controls
ms.assetid: cacd9e45-701a-4a1f-8f1f-b0b39f6ac303
ms.openlocfilehash: aaab4ae3bb13790784a66d53b41dbc3a7cdaec89
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364611"
---
# <a name="mfc-activex-controls-licensing-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetimini Lisanslama

ActiveX denetimlerinin isteğe bağlı bir özelliği olan lisans desteği, denetimi kimin kullanabileceğini veya dağıtabildiğini denetlemenize olanak tanır. (Lisans sorunlarının ek olarak tartışılması için, [Varolan ActiveX Denetimini Yükseltmede](../mfc/upgrading-an-existing-activex-control.md)Lisans Sorunları bölümüne bakın.)

> [!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. ActiveX'in yerini alabilecek modern teknolojiler hakkında daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

Bu makalede aşağıdaki konular tartışılmaktadır:

- [ActiveX Kontrol Lisansına Genel Bakış](#_core_overview_of_activex_control_licensing)

- [Lisanslı Denetim Oluşturma](#_core_creating_a_licensed_control)

- [Lisans Desteği](#_core_licensing_support)

- [ActiveX Denetiminin Lisansını Özelleştirme](#_core_customizing_the_licensing_of_an_activex_control)

Lisanslama yı uygulayan ActiveX denetimleri, denetim geliştiricisi olarak diğer kişilerin ActiveX denetimini nasıl kullanacağını belirlemenize olanak sağlar. Kontrol alıcıya kontrol sağlar ve. LIC dosyası, alıcı nın denetimi dağıtabileceği, ancak ' ın . LIC dosyası, denetimi kullanan bir uygulama ile. Bu, bu uygulamanın kullanıcılarının denetimi sizden lisanslamadan denetimi kullanan yeni uygulamalar yazmalarını engeller.

## <a name="overview-of-activex-control-licensing"></a><a name="_core_overview_of_activex_control_licensing"></a>ActiveX Kontrol Lisansına Genel Bakış

ActiveX denetimleri için lisans desteği sağlamak [için, COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) sınıfı `IClassFactory2` arabirimdeki `IClassFactory2::GetLicInfo`çeşitli `IClassFactory2::CreateInstanceLic`işlevler için bir uygulama sağlar: `IClassFactory2::RequestLicKey`, , ve . Kapsayıcı uygulama geliştiricisi denetimin bir örneğini oluşturmak için `GetLicInfo` bir istekte bulununca, denetimin. LIC dosyası hazır. Denetim lisanslanırsa, denetimin bir örneği oluşturulabilir ve kapsayıcıya yerleştirilebilir. Geliştirici kapsayıcı uygulamasını oluşturmayı bitirdikten sonra, başka bir `RequestLicKey`işlev çağrısı, bu kez , yapılır. Bu işlev, kapsayıcı uygulamasına bir lisans anahtarı (basit bir karakter dizesi) döndürür. Döndürülen anahtar daha sonra uygulamaya katıştırılır.

Aşağıdaki şekil, bir konteyner uygulamasının geliştirilmesi sırasında kullanılacak bir ActiveX denetiminin lisans doğrulamasını göstermektedir. Daha önce de belirtildiği gibi, konteyner uygulama geliştiricisi uygun olmalıdır. Denetimin bir örneğini oluşturmak için geliştirme makinesine yüklenen LIC dosyası.

![Lisanslı ActiveX denetimi geliştirme de doğrulandı](../mfc/media/vc374d1.gif "Lisanslı ActiveX denetimi geliştirme de doğrulandı") <br/>
Geliştirme Sırasında Lisanslı ActiveX Kontrolünün Doğrulanması

Aşağıdaki şekilde gösterilen sonraki işlem, son kullanıcı kapsayıcı uygulamasını çalıştırdığında oluşur.

Uygulama başlatıldığında, denetimin bir örneğinin oluşturulması genellikle gerekir. Kapsayıcı, gömülü lisans anahtarını `CreateInstanceLic`parametre olarak geçirerek bir arama yaparak bunu gerçekleştirir. Daha sonra katıştırılmış lisans anahtarı ile denetimin lisans anahtarının kendi kopyası arasında bir dize karşılaştırması yapılır. Eşleşme başarılı olursa, denetimin bir örneği oluşturulur ve uygulama normal şekilde yürütmeye devam edilir. Unutmayın. LIC dosyasının kontrol kullanıcısının makinesinde bulunması gerekmez.

![Lisanslı ActiveX denetimi yürütme de doğrulandı](../mfc/media/vc374d2.gif "Lisanslı ActiveX denetimi yürütme de doğrulandı") <br/>
Yürütme Sırasında Lisanslı ActiveX Denetiminin Doğrulanması

Denetim lisanslama iki temel bileşenden oluşur: denetim uygulaması DLL ve lisans dosyasında belirli kod. Kod, bundan sonra bir telif hakkı bildirimi içeren bir "lisans dizesi" olarak adlandırılan iki (veya muhtemelen üç) işlev çağrısı ve bir karakter dizelerinden oluşur. Bu aramalar ve lisans dizesi denetim uygulamasında bulunur (. CPP) dosyası. ActiveX Denetim Sihirbazı tarafından oluşturulan lisans dosyası, telif hakkı bildirimi içeren bir metin dosyasıdır. Proje adı kullanılarak bir . LIC uzantısı, örneğin ÖRNEK. Lisansı. Tasarım zamanı kullanımı gerekiyorsa, lisanslı bir denetime lisans dosyası eşlik etmelidir.

## <a name="creating-a-licensed-control"></a><a name="_core_creating_a_licensed_control"></a>Lisanslı Denetim Oluşturma

Denetim çerçevesini oluşturmak için ActiveX Denetim Sihirbazı'nı kullandığınızda, lisans desteği eklemek kolaydır. Denetimin çalışma zamanı lisansıolması gerektiğini belirttiğiniz zaman, ActiveX Denetim Sihirbazı lisanslamayı desteklemek için denetim sınıfına kod ekler. Kod, lisans doğrulaması için anahtar ve lisans dosyası kullanan işlevlerden oluşur. Bu işlevler, denetim lisansını özelleştirmek için de değiştirilebilir. Lisans özelleştirme hakkında daha fazla bilgi için, bu makalenin ilerleyen saatlerinde [ActiveX Denetiminin Lisansını Özelleştirme](#_core_customizing_the_licensing_of_an_activex_control) bölümüne bakın.

#### <a name="to-add-support-for-licensing-with-the-activex-control-wizard-when-you-create-your-control-project"></a>Denetim projenizi oluştururken ActiveX Denetim Sihirbazı ile lisanslama desteği eklemek için

1. [MFC ActiveX Denetimi Oluştururken](../mfc/reference/creating-an-mfc-activex-control.md)yönergeleri kullanın. ActiveX Denetim Sihirbazı'nın **Uygulama Ayarları** sayfası, çalışma zamanı lisansıyla denetimi oluşturma seçeneğini içerir.

ActiveX Denetim Sihirbazı artık temel lisans desteği içeren bir ActiveX denetim çerçevesi oluşturur. Lisans kodunun ayrıntılı bir açıklaması için bir sonraki konuya bakın.

## <a name="licensing-support"></a><a name="_core_licensing_support"></a>Lisans Desteği

ActiveX Denetim Sihirbazı'nı activex denetimine lisans desteği eklemek için kullandığınızda, ActiveX Denetim Sihirbazı denetim üstbilgisine ve uygulama dosyalarına lisanslama özelliğinin eklendiğinde ve uygulayan kod ekler. Bu kod, `VerifyUserLicense` [COleObjectFactory'de](../mfc/reference/coleobjectfactory-class.md) bulunan varsayılan uygulamaları geçersiz kılınan bir üye işlev ve üye `GetLicenseKey` işlevden oluşur. Bu işlevler denetim lisansını alır ve doğrular.

> [!NOTE]
> Üçüncü bir üye `VerifyLicenseKey` işlev, ActiveX Denetim Sihirbazı tarafından oluşturulmamalıdır, ancak lisans anahtarı doğrulama davranışını özelleştirmek için geçersiz kılınabilir.

Bu üye işlevler şunlardır:

- [VerifyUserLicense](../mfc/reference/coleobjectfactory-class.md#verifyuserlicense)

   Denetimin, sistemin denetim lisansı dosyasının varlığını denetleyerek tasarım zamanı kullanımına izin verdiğini doğrular. Bu işlev, işlemenin `IClassFactory2::GetLicInfo` bir parçası `IClassFactory::CreateInstanceLic`olarak çerçeve tarafından çağrılır ve.

- [Lisans Anahtarı](../mfc/reference/coleobjectfactory-class.md#getlicensekey)

   Denetim DLL benzersiz bir anahtar ister. Bu anahtar kapsayıcı uygulamasına gömülür ve daha `VerifyLicenseKey`sonra, denetimin bir örneğini oluşturmak için birlikte kullanılır. Bu işlev, işlemenin `IClassFactory2::RequestLicKey`bir parçası olarak çerçeve tarafından çağrılır.

- [DoğrulamaLisans Anahtarı](../mfc/reference/coleobjectfactory-class.md#verifylicensekey)

   Katıştılmış anahtar la denetimin benzersiz anahtarının aynı olduğunu doğrular. Bu, kapsayıcının kullanımı için denetimin bir örneğini oluşturmasına olanak tanır. Bu işlev, işlemenin `IClassFactory2::CreateInstanceLic` bir parçası olarak çerçeve tarafından çağrılır ve lisans anahtarının özelleştirilmiş doğrulamasını sağlamak için geçersiz kılınabilir. Varsayılan uygulama bir dize karşılaştırması gerçekleştirir. Daha fazla bilgi için, bu makalenin ilerleyen saatlerinde [ActiveX Denetiminin Lisansını Özelleştirme](#_core_customizing_the_licensing_of_an_activex_control)bölümüne bakın.

### <a name="header-file-modifications"></a><a name="_core_header_file_modifications"></a>Üstbilgi Dosya Modifikasyonları

ActiveX Denetim Sihirbazı denetim üstbilgi dosyasına aşağıdaki kodu yerleştirir. Bu örnekte, ''ın nesnesinin `CSampleCtrl` `factory` iki üye işlevi, denetimin varlığını doğrulayan bir kişi olarak bildirilir. LIC dosyası ve denetimi içeren uygulamada kullanılacak lisans anahtarını alan başka bir dosya:

[!code-cpp[NVC_MFC_AxUI#39](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_1.h)]

### <a name="implementation-file-modifications"></a><a name="_core_implementation_file_modifications"></a>Uygulama Dosyası Modifikasyonları

ActiveX Denetim Sihirbazı, lisans dosya adını ve lisans dizesini bildirmek için denetim uygulama dosyasına aşağıdaki iki deyimi yerleştirir:

[!code-cpp[NVC_MFC_AxUI#40](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_2.cpp)]

> [!NOTE]
> Herhangi bir `szLicString` şekilde değiştirirseniz, denetimdeki ilk satırı da değiştirmeniz gerekir. LIC dosyası veya lisanslama düzgün çalışmaz.

ActiveX Denetim Sihirbazı, denetim sınıfının `VerifyUserLicense` ve `GetLicenseKey` işlevlerini tanımlamak için denetim uygulama dosyasına aşağıdaki kodu yerleştirir:

[!code-cpp[NVC_MFC_AxUI#41](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_3.cpp)]

Son olarak, **ActiveX Denetim Sihirbazı** denetim projesini değiştirir. IDL dosyası. **Lisanslı** anahtar kelime aşağıdaki örnekte olduğu gibi, denetimin coclass bildirimine eklenir:

[!code-cpp[NVC_MFC_AxUI#42](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_4.idl)]

## <a name="customizing-the-licensing-of-an-activex-control"></a><a name="_core_customizing_the_licensing_of_an_activex_control"></a>ActiveX Denetiminin Lisansını Özelleştirme

Denetim fabrikası `VerifyLicenseKey` sınıfının sanal üye işlevleri olarak beyan edildiğinden, denetimin lisanslama davranışını özelleştirebilirsiniz. `GetLicenseKey` `VerifyUserLicense`

Örneğin, `VerifyUserLicense` denetim `VerifyLicenseKey` için veya üye işlevleri geçersiz kılarak çeşitli lisans düzeyleri sağlayabilirsiniz. Bu işlevin içinde, tespit ettiğiniz lisans düzeyine göre kullanıcıya hangi özelliklerin veya yöntemlerin maruz kaldığını ayarlayabilirsiniz.

Ayrıca, kullanıcıya denetim `VerifyLicenseKey` oluşturmanın başarısız olduğunu bildirmek için özelleştirilmiş bir yöntem sağlayan işleve kod ekleyebilirsiniz. Örneğin, üye `VerifyLicenseKey` işlevinizde, denetimin başlatılmasını ve neden başlattığını belirten bir ileti kutusu görüntüleyebilirsiniz.

> [!NOTE]
> ActiveX denetim lisans doğrulamasını özelleştirmenin başka bir yolu da, 'yi aramak `AfxVerifyLicFile`yerine belirli bir kayıt defteri anahtarı için kayıt veritabanını denetlemektir. Varsayılan uygulama örneği için, bu makalenin [Uygulama Dosyası Değişiklikleri](#_core_implementation_file_modifications) bölümüne bakın.

Lisans sorunlarının ek olarak tartışılması için, [Varolan ActiveX Denetimini Yükseltmede](../mfc/upgrading-an-existing-activex-control.md)Lisans Sorunları'na bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md)
