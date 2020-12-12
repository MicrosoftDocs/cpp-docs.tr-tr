---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: ActiveX denetimini lisanslama'
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
ms.openlocfilehash: cf7b797ecfd7ae19af7c922443850d115b4cc2b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341600"
---
# <a name="mfc-activex-controls-licensing-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetimini Lisanslama

ActiveX denetimlerinin isteğe bağlı bir özelliği olan lisanslama desteği, denetimi kullanabilecek veya dağıtabilecek kişileri denetlemenize olanak tanır. (Lisanslama sorunları hakkında daha fazla bilgi için bkz. [var olan bir ActiveX denetimini yükseltmekte olan](upgrading-an-existing-activex-control.md)lisans sorunları.)

> [!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

Bu makalede aşağıdaki konular ele alınmaktadır:

- [ActiveX denetimi lisanslamaya genel bakış](#_core_overview_of_activex_control_licensing)

- [Lisanslı denetim oluşturma](#_core_creating_a_licensed_control)

- [Lisanslama desteği](#_core_licensing_support)

- [ActiveX denetimi lisansını özelleştirme](#_core_customizing_the_licensing_of_an_activex_control)

Lisanslama uygulayan ActiveX denetimleri, diğer kişilerin ActiveX denetimini nasıl kullanacağını belirlemede size denetim geliştiricisi olarak izin verir. Denetim satınalmacının denetimi ve ile sağlarsınız. LIK dosyası, satınalmacının denetimi dağıtabilecek, ancak olmasa da anlaşmasıyla birlikte. LIK dosyası, denetimi kullanan bir uygulamayla birlikte. Bu, söz konusu uygulamanın, denetimi sizin görüntülemeden lisanslamadan denetimi kullanan yeni uygulamalar yazmasını engeller.

## <a name="overview-of-activex-control-licensing"></a><a name="_core_overview_of_activex_control_licensing"></a> ActiveX denetimi lisanslamaya genel bakış

ActiveX denetimleri için lisans desteği sağlamak üzere [COleObjectFactory](reference/coleobjectfactory-class.md) sınıfı, arabirimindeki çeşitli işlevler için bir uygulama sağlar `IClassFactory2` : `IClassFactory2::RequestLicKey` , `IClassFactory2::GetLicInfo` ve `IClassFactory2::CreateInstanceLic` . Kapsayıcı uygulama geliştiricisi, denetimin bir örneğini oluşturmak için bir istek yaptığında, `GetLicInfo` denetimin doğrulanması için bir çağrısı yapılır. LIK dosyası var. Denetim lisanslıysa, denetimin bir örneği kapsayıcıya oluşturulup kapsayıcıya yerleştirilebilir. Geliştirici kapsayıcı uygulamasını oluşturma işlemi tamamlandıktan sonra, bu kez için başka bir işlev çağrısı `RequestLicKey` yapılır. Bu işlev, kapsayıcı uygulamasına bir lisans anahtarı (basit bir karakter dizesi) döndürür. Döndürülen anahtar daha sonra uygulamaya katıştırılır.

Aşağıdaki şekilde, bir kapsayıcı uygulamasının geliştirilmesi sırasında kullanılacak bir ActiveX denetiminin lisans doğrulaması gösterilmektedir. Daha önce belirtildiği gibi, kapsayıcı uygulama geliştiricisi doğru olmalıdır. Bir denetimin örneğini oluşturmak için geliştirme makinesine yüklenmiş bir dosya dosyası.

![Lisanslı ActiveX denetimi, geliştirme sırasında doğrulandı](../mfc/media/vc374d1.gif "Lisanslı ActiveX denetimi, geliştirme sırasında doğrulandı") <br/>
Geliştirme sırasında lisanslı bir ActiveX denetiminin doğrulanması

Aşağıdaki şekilde gösterilen sonraki işlem, Son Kullanıcı kapsayıcı uygulamasını çalıştırdığında oluşur.

Uygulama başlatıldığında, genellikle denetimin bir örneğinin oluşturulması gerekir. Kapsayıcı bunu bir çağrısı yaparak `CreateInstanceLic` , gömülü lisans anahtarını bir parametre olarak geçirerek gerçekleştirir. Daha sonra, gömülü lisans anahtarı ve denetimin kendi lisans anahtarı kopyası arasında bir dize karşılaştırması yapılır. Eşleşme başarılı olursa, denetimin bir örneği oluşturulur ve uygulama normal şekilde yürütülmeye devam eder. . Denetimin kullanıcı makinesinde lık dosyası olması gerekmez.

![Lisanslı ActiveX denetimi yürütmede doğrulandı](../mfc/media/vc374d2.gif "Lisanslı ActiveX denetimi yürütmede doğrulandı") <br/>
Yürütme sırasında lisanslı bir ActiveX denetiminin doğrulanması

Denetim lisanslama iki temel bileşenden oluşur: denetim uygulama DLL dosyasındaki belirli kod ve lisans dosyası. Kod iki (veya büyük olasılıkla üç) işlev çağrısı ve bir karakter dizesinden oluşur ve bundan sonra bir telif hakkı bildirimi içeren "lisans dizesi" olarak anılacaktır. Bu çağrılar ve lisans dizesi denetim uygulamasında bulunur (. CPP) dosyası. ActiveX Denetim Sihirbazı tarafından oluşturulan lisans dosyası, bir telif hakkı bildirimine sahip bir metin dosyasıdır. İle proje adı kullanılarak adlandırılır. Örneğin ÖRNEĞI. Lik. Tasarım zamanı kullanımı gerekiyorsa, lisanslı bir denetim ile birlikte lisans dosyası gelmelidir.

## <a name="creating-a-licensed-control"></a><a name="_core_creating_a_licensed_control"></a> Lisanslı denetim oluşturma

Denetim çerçevesini oluşturmak için ActiveX Denetim Sihirbazı 'nı kullandığınızda, lisanslama desteğinin dahil edilmesi kolaydır. Denetimin bir çalışma zamanı lisansına sahip olması gerektiğini belirttiğinizde, ActiveX Denetim Sihirbazı lisansı desteklemek için denetim sınıfına kod ekler. Kod, lisans doğrulaması için bir anahtar ve lisans dosyası kullanan işlevlerden oluşur. Bu işlevler ayrıca denetim lisansını özelleştirmek için değiştirilebilir. Lisans özelleştirme hakkında daha fazla bilgi için, bu makalenin ilerleyen kısımlarında [ActiveX denetiminin lisanslamasını özelleştirme](#_core_customizing_the_licensing_of_an_activex_control) bölümüne bakın.

#### <a name="to-add-support-for-licensing-with-the-activex-control-wizard-when-you-create-your-control-project"></a>Denetim projenizi oluştururken ActiveX Denetim Sihirbazı ile lisans desteği eklemek için

1. [MFC ActiveX denetimi oluşturma](reference/creating-an-mfc-activex-control.md)yönergelerini kullanın. ActiveX Denetim Sihirbazı 'nın **uygulama ayarları** sayfası, çalışma zamanı lisansıyla denetim oluşturma seçeneğini içerir.

ActiveX Denetim Sihirbazı artık temel lisans desteğini içeren bir ActiveX denetim çerçevesi oluşturuyor. Lisanslama kodunun ayrıntılı bir açıklaması için sonraki konuya bakın.

## <a name="licensing-support"></a><a name="_core_licensing_support"></a> Lisanslama desteği

ActiveX denetimine lisans desteği eklemek için ActiveX Denetim Sihirbazı 'nı kullandığınızda, ActiveX Denetim Sihirbazı, lisans özelliğini bildiren ve uygulayan, denetim üstbilgisine ve uygulama dosyalarına eklenen kodu ekler. Bu kod `VerifyUserLicense` `GetLicenseKey` , [COleObjectFactory](reference/coleobjectfactory-class.md) içinde bulunan varsayılan uygulamaları geçersiz kılan bir üye işlevden ve bir üye işlevden oluşur. Bu işlevler denetim lisansını alır ve doğrular.

> [!NOTE]
> Üçüncü üye işlevi, `VerifyLicenseKey` ActiveX Denetim Sihirbazı tarafından oluşturulmaz, ancak lisans anahtarı doğrulama davranışını özelleştirmek için geçersiz kılınabilir.

Bu üye işlevleri şunlardır:

- [VerifyUserLicense](reference/coleobjectfactory-class.md#verifyuserlicense)

   Denetimin, Denetim lisansı dosyasının varlığını denetlemek için, sistemin tasarım zamanı kullanımına izin verdiğini doğrular. Bu işlev, işleme ve öğesinin bir parçası olarak Framework tarafından `IClassFactory2::GetLicInfo` çağırılır `IClassFactory::CreateInstanceLic` .

- [GetLicenseKey](reference/coleobjectfactory-class.md#getlicensekey)

   Denetim DLL 'sinden benzersiz bir anahtar ister. Bu anahtar, kapsayıcı uygulamasına katıştırılır ve daha sonra, ile birlikte, `VerifyLicenseKey` denetimin bir örneğini oluşturmak için kullanılır. Bu işlev, işlemin bir parçası olarak Framework tarafından çağırılır `IClassFactory2::RequestLicKey` .

- [VerifyLicenseKey](reference/coleobjectfactory-class.md#verifylicensekey)

   Gömülü anahtarın ve denetimin benzersiz anahtarının aynı olduğunu doğrular. Bu, kapsayıcının kullanımı için bir denetimin bir örneğini oluşturmasına izin verir. Bu işlev, işlemin bir parçası olarak Framework tarafından çağrılır `IClassFactory2::CreateInstanceLic` ve lisans anahtarının özelleştirilmiş doğrulanmasını sağlamak için geçersiz kılınabilir. Varsayılan uygulama bir dize karşılaştırması gerçekleştirir. Daha fazla bilgi için, bu makalenin ilerleyen kısımlarında [ActiveX denetiminin lisanslamasını özelleştirme](#_core_customizing_the_licensing_of_an_activex_control)bölümüne bakın.

### <a name="header-file-modifications"></a><a name="_core_header_file_modifications"></a> Üstbilgi dosyası değişiklikleri

ActiveX Denetim Sihirbazı aşağıdaki kodu denetim üst bilgisi dosyasına koyar. Bu örnekte, nesnesinin iki üye işlevi olarak `CSampleCtrl` `factory` , denetimin varlığını doğrulayan bir tane bildirilmiştir. LIK dosyası ve denetimi içeren uygulamada kullanılacak lisans anahtarını alan başka bir dosya:

[!code-cpp[NVC_MFC_AxUI#39](codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_1.h)]

### <a name="implementation-file-modifications"></a><a name="_core_implementation_file_modifications"></a> Uygulama dosyası değişiklikleri

ActiveX Denetim Sihirbazı, lisans dosya adını ve lisans dizesini bildirmek üzere Denetim uygulama dosyasına aşağıdaki iki ifadeyi koyar:

[!code-cpp[NVC_MFC_AxUI#40](codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_2.cpp)]

> [!NOTE]
> `szLicString`Herhangi bir şekilde değişiklik yaparsanız, denetimdeki ilk satırı da değiştirmeniz gerekir. LIK dosyası veya lisanslama düzgün çalışmayacak.

ActiveX Denetim Sihirbazı, denetim sınıfını ve işlevleri tanımlamak için aşağıdaki kodu denetim uygulama dosyasına koyar `VerifyUserLicense` `GetLicenseKey` :

[!code-cpp[NVC_MFC_AxUI#41](codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_3.cpp)]

Son olarak, **ActiveX Denetim Sihirbazı** denetim projesini değiştirir. IDL dosyası. **Lisanslı** anahtar sözcüğü, aşağıdaki örnekte olduğu gibi, denetimin coclass bildirimine eklenir:

[!code-cpp[NVC_MFC_AxUI#42](codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_4.idl)]

## <a name="customizing-the-licensing-of-an-activex-control"></a><a name="_core_customizing_the_licensing_of_an_activex_control"></a> ActiveX denetimi lisansını özelleştirme

`VerifyUserLicense`, `GetLicenseKey` Ve, `VerifyLicenseKey` Denetim fabrikası sınıfının sanal üye işlevleri olarak bildirildiği için, denetimin lisanslama davranışını özelleştirebilirsiniz.

Örneğin, `VerifyUserLicense` veya üye işlevlerini geçersiz kılarak denetim için birkaç Lisans düzeyi sağlayabilirsiniz `VerifyLicenseKey` . Bu işlevin içinde, algılanan Lisans düzeyine göre kullanıcıya hangi özelliklerin veya yöntemlerin sunulacağına göre ayarlayabilirsiniz.

Ayrıca, `VerifyLicenseKey` denetim oluşturma işlemi başarısız olan kullanıcıya bildiren özelleştirilmiş bir yöntem sağlayan işlevine kod ekleyebilirsiniz. Örneğin, `VerifyLicenseKey` üye işlevinizde, denetimin başlatılamadığından ve neden başarısız olduğunu belirten bir ileti kutusu görüntüleyebilirsiniz.

> [!NOTE]
> ActiveX denetimi lisans doğrulamasını özelleştirmenin başka bir yolu da, çağrı yerine belirli bir kayıt defteri anahtarı için kayıt veritabanını denetmasıdır `AfxVerifyLicFile` . Varsayılan uygulamanın bir örneği için, bu makalenin [uygulama dosyası değişiklikleri](#_core_implementation_file_modifications) bölümüne bakın.

Lisanslama sorunları hakkında daha fazla bilgi için bkz. [var olan bir ActiveX denetimini yükseltmekte olan](upgrading-an-existing-activex-control.md)lisans sorunları.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)<br/>
[MFC ActiveX denetimi Sihirbazı](reference/mfc-activex-control-wizard.md)
