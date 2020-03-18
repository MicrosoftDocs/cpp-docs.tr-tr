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
ms.openlocfilehash: b08abdc0e2c17cb61c0c6a14cd712ec32ea816bd
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438011"
---
# <a name="mfc-activex-controls-licensing-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetimini Lisanslama

ActiveX denetimlerinin isteğe bağlı bir özelliği olan lisanslama desteği, denetimi kullanabilecek veya dağıtabilecek kişileri denetlemenize olanak tanır. (Lisanslama sorunları hakkında daha fazla bilgi için bkz. [var olan bir ActiveX denetimini yükseltmekte olan](../mfc/upgrading-an-existing-activex-control.md)lisans sorunları.)

> [!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

Bu makalede, aşağıdaki konular ele alınmaktadır:

- [ActiveX denetimi lisanslamaya genel bakış](#_core_overview_of_activex_control_licensing)

- [Lisanslı denetim oluşturma](#_core_creating_a_licensed_control)

- [Lisanslama desteği](#_core_licensing_support)

- [ActiveX denetimi lisansını özelleştirme](#_core_customizing_the_licensing_of_an_activex_control)

Lisanslama uygulayan ActiveX denetimleri, diğer kişilerin ActiveX denetimini nasıl kullanacağını belirlemede size denetim geliştiricisi olarak izin verir. Denetim satınalmacının denetimi ve ile sağlarsınız. LIK dosyası, satınalmacının denetimi dağıtabilecek, ancak olmasa da anlaşmasıyla birlikte. LIK dosyası, denetimi kullanan bir uygulamayla birlikte. Bu, söz konusu uygulamanın, denetimi sizin görüntülemeden lisanslamadan denetimi kullanan yeni uygulamalar yazmasını engeller.

##  <a name="_core_overview_of_activex_control_licensing"></a>ActiveX denetimi lisanslamaya genel bakış

ActiveX denetimleri için lisans desteği sağlamak üzere [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) sınıfı, `IClassFactory2` arabirimindeki birkaç işlev için bir uygulama sağlar: `IClassFactory2::RequestLicKey`, `IClassFactory2::GetLicInfo`ve `IClassFactory2::CreateInstanceLic`. Kapsayıcı uygulama geliştiricisi, denetimin bir örneğini oluşturmak için bir istek yaptığında, denetimin doğrulanması için bir `GetLicInfo` çağrısı yapılır. LIK dosyası var. Denetim lisanslıysa, denetimin bir örneği kapsayıcıya oluşturulup kapsayıcıya yerleştirilebilir. Geliştirici kapsayıcı uygulamasını oluşturma işlemi tamamlandıktan sonra, bu kez `RequestLicKey`başka bir işlev çağrısı yapılır. Bu işlev, kapsayıcı uygulamasına bir lisans anahtarı (basit bir karakter dizesi) döndürür. Döndürülen anahtar daha sonra uygulamaya katıştırılır.

Aşağıdaki şekilde, bir kapsayıcı uygulamasının geliştirilmesi sırasında kullanılacak bir ActiveX denetiminin lisans doğrulaması gösterilmektedir. Daha önce belirtildiği gibi, kapsayıcı uygulama geliştiricisi doğru olmalıdır. Bir denetimin örneğini oluşturmak için geliştirme makinesine yüklenmiş bir dosya dosyası.

![Lisanslı ActiveX denetimi, geliştirme sırasında doğrulandı](../mfc/media/vc374d1.gif "Lisanslı ActiveX denetimi, geliştirme sırasında doğrulandı") <br/>
Geliştirme sırasında lisanslı bir ActiveX denetiminin doğrulanması

Aşağıdaki şekilde gösterilen sonraki işlem, Son Kullanıcı kapsayıcı uygulamasını çalıştırdığında oluşur.

Uygulama başlatıldığında, genellikle denetimin bir örneğinin oluşturulması gerekir. Kapsayıcı bunu bir `CreateInstanceLic`çağrısı yaparak, gömülü lisans anahtarını bir parametre olarak geçirerek gerçekleştirir. Daha sonra, gömülü lisans anahtarı ve denetimin kendi lisans anahtarı kopyası arasında bir dize karşılaştırması yapılır. Eşleşme başarılı olursa, denetimin bir örneği oluşturulur ve uygulama normal şekilde yürütülmeye devam eder. . Denetimin kullanıcı makinesinde lık dosyası olması gerekmez.

![Lisanslı ActiveX denetimi yürütmede doğrulandı](../mfc/media/vc374d2.gif "Lisanslı ActiveX denetimi yürütmede doğrulandı") <br/>
Yürütme sırasında lisanslı bir ActiveX denetiminin doğrulanması

Denetim lisanslama iki temel bileşenden oluşur: denetim uygulama DLL dosyasındaki belirli kod ve lisans dosyası. Kod iki (veya büyük olasılıkla üç) işlev çağrısı ve bir karakter dizesinden oluşur ve bundan sonra bir telif hakkı bildirimi içeren "lisans dizesi" olarak anılacaktır. Bu çağrılar ve lisans dizesi denetim uygulamasında bulunur (. CPP) dosyası. ActiveX Denetim Sihirbazı tarafından oluşturulan lisans dosyası, bir telif hakkı bildirimine sahip bir metin dosyasıdır. İle proje adı kullanılarak adlandırılır. Örneğin ÖRNEĞI. Lik. Tasarım zamanı kullanımı gerekiyorsa, lisanslı bir denetim ile birlikte lisans dosyası gelmelidir.

##  <a name="_core_creating_a_licensed_control"></a>Lisanslı denetim oluşturma

Denetim çerçevesini oluşturmak için ActiveX Denetim Sihirbazı 'nı kullandığınızda, lisanslama desteğinin dahil edilmesi kolaydır. Denetimin bir çalışma zamanı lisansına sahip olması gerektiğini belirttiğinizde, ActiveX Denetim Sihirbazı lisansı desteklemek için denetim sınıfına kod ekler. Kod, lisans doğrulaması için bir anahtar ve lisans dosyası kullanan işlevlerden oluşur. Bu işlevler ayrıca denetim lisansını özelleştirmek için değiştirilebilir. Lisans özelleştirme hakkında daha fazla bilgi için, bu makalenin ilerleyen kısımlarında [ActiveX denetiminin lisanslamasını özelleştirme](#_core_customizing_the_licensing_of_an_activex_control) bölümüne bakın.

#### <a name="to-add-support-for-licensing-with-the-activex-control-wizard-when-you-create-your-control-project"></a>Denetim projenizi oluştururken ActiveX Denetim Sihirbazı ile lisans desteği eklemek için

1. [MFC ActiveX denetimi oluşturma](../mfc/reference/creating-an-mfc-activex-control.md)yönergelerini kullanın. ActiveX Denetim Sihirbazı 'nın **uygulama ayarları** sayfası, çalışma zamanı lisansıyla denetim oluşturma seçeneğini içerir.

ActiveX Denetim Sihirbazı artık temel lisans desteğini içeren bir ActiveX denetim çerçevesi oluşturuyor. Lisanslama kodunun ayrıntılı bir açıklaması için sonraki konuya bakın.

##  <a name="_core_licensing_support"></a>Lisanslama desteği

ActiveX denetimine lisans desteği eklemek için ActiveX Denetim Sihirbazı 'nı kullandığınızda, ActiveX Denetim Sihirbazı, lisans özelliğini bildiren ve uygulayan, denetim üstbilgisine ve uygulama dosyalarına eklenen kodu ekler. Bu kod, [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) içinde bulunan varsayılan uygulamaları geçersiz kılan bir `VerifyUserLicense` member işlevinden ve `GetLicenseKey` member işlevinden oluşur. Bu işlevler denetim lisansını alır ve doğrular.

> [!NOTE]
>  Üçüncü üye işlevi, `VerifyLicenseKey` ActiveX Denetim Sihirbazı tarafından oluşturulmaz, ancak lisans anahtarı doğrulama davranışını özelleştirmek için geçersiz kılınabilir.

Bu üye işlevleri şunlardır:

- [VerifyUserLicense](../mfc/reference/coleobjectfactory-class.md#verifyuserlicense)

   Denetimin, Denetim lisansı dosyasının varlığını denetlemek için, sistemin tasarım zamanı kullanımına izin verdiğini doğrular. Bu işlev, `IClassFactory2::GetLicInfo` ve `IClassFactory::CreateInstanceLic`işlemenin bir parçası olarak Framework tarafından çağırılır.

- [GetLicenseKey](../mfc/reference/coleobjectfactory-class.md#getlicensekey)

   Denetim DLL 'sinden benzersiz bir anahtar ister. Bu anahtar, kapsayıcı uygulamasına katıştırılır ve daha sonra denetimin bir örneğini oluşturmak için `VerifyLicenseKey`ile birlikte kullanılır. Bu işlev, `IClassFactory2::RequestLicKey`işleme parçası olarak Framework tarafından çağırılır.

- [VerifyLicenseKey](../mfc/reference/coleobjectfactory-class.md#verifylicensekey)

   Gömülü anahtarın ve denetimin benzersiz anahtarının aynı olduğunu doğrular. Bu, kapsayıcının kullanımı için bir denetimin bir örneğini oluşturmasına izin verir. Bu işlev, işleme `IClassFactory2::CreateInstanceLic` parçası olarak Framework tarafından çağrılır ve lisans anahtarının özelleştirilmiş doğrulamasını sağlamak için geçersiz kılınabilir. Varsayılan uygulama bir dize karşılaştırması gerçekleştirir. Daha fazla bilgi için, bu makalenin ilerleyen kısımlarında [ActiveX denetiminin lisanslamasını özelleştirme](#_core_customizing_the_licensing_of_an_activex_control)bölümüne bakın.

###  <a name="_core_header_file_modifications"></a>Üstbilgi dosyası değişiklikleri

ActiveX Denetim Sihirbazı aşağıdaki kodu denetim üst bilgisi dosyasına koyar. Bu örnekte, `CSampleCtrl`nesnesinin `factory` iki üye işlevi bildirilmiştir, biri denetimin varlığını doğrular. LIK dosyası ve denetimi içeren uygulamada kullanılacak lisans anahtarını alan başka bir dosya:

[!code-cpp[NVC_MFC_AxUI#39](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_1.h)]

###  <a name="_core_implementation_file_modifications"></a>Uygulama dosyası değişiklikleri

ActiveX Denetim Sihirbazı, lisans dosya adını ve lisans dizesini bildirmek üzere Denetim uygulama dosyasına aşağıdaki iki ifadeyi koyar:

[!code-cpp[NVC_MFC_AxUI#40](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_2.cpp)]

> [!NOTE]
>  `szLicString` herhangi bir şekilde değiştirirseniz, denetimdeki ilk satırı da değiştirmelisiniz. LIK dosyası veya lisanslama düzgün çalışmayacak.

ActiveX Denetim Sihirbazı, denetim sınıfı ' `VerifyUserLicense` ve `GetLicenseKey` işlevlerini tanımlamak için aşağıdaki kodu denetim uygulama dosyasına koyar:

[!code-cpp[NVC_MFC_AxUI#41](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_3.cpp)]

Son olarak, **ActiveX Denetim Sihirbazı** denetim projesini değiştirir. IDL dosyası. **Lisanslı** anahtar sözcüğü, aşağıdaki örnekte olduğu gibi, denetimin coclass bildirimine eklenir:

[!code-cpp[NVC_MFC_AxUI#42](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_4.idl)]

##  <a name="_core_customizing_the_licensing_of_an_activex_control"></a>ActiveX denetimi lisansını özelleştirme

`VerifyUserLicense`, `GetLicenseKey`ve `VerifyLicenseKey` denetim fabrikası sınıfının sanal üye işlevleri olarak bildirildiği için, denetimin lisanslama davranışını özelleştirebilirsiniz.

Örneğin, `VerifyUserLicense` veya `VerifyLicenseKey` üye işlevlerini geçersiz kılarak denetim için birkaç Lisans düzeyi sağlayabilirsiniz. Bu işlevin içinde, algılanan Lisans düzeyine göre kullanıcıya hangi özelliklerin veya yöntemlerin sunulacağına göre ayarlayabilirsiniz.

Ayrıca, denetim oluşturma işlemi başarısız olan kullanıcıya bildiren özelleştirilmiş bir yöntem sağlayan `VerifyLicenseKey` işlevine kod ekleyebilirsiniz. Örneğin, `VerifyLicenseKey` üye işlevinizde, denetimin başlatılamadığından ve neden başarısız olduğunu belirten bir ileti kutusu görüntüleyebilirsiniz.

> [!NOTE]
>  ActiveX denetimi lisans doğrulamasını özelleştirmenin başka bir yolu da, `AfxVerifyLicFile`çağırmak yerine, belirli bir kayıt defteri anahtarı için kayıt veritabanını denetmasıdır. Varsayılan uygulamanın bir örneği için, bu makalenin [uygulama dosyası değişiklikleri](#_core_implementation_file_modifications) bölümüne bakın.

Lisanslama sorunları hakkında daha fazla bilgi için bkz. [var olan bir ActiveX denetimini yükseltmekte olan](../mfc/upgrading-an-existing-activex-control.md)lisans sorunları.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md)
