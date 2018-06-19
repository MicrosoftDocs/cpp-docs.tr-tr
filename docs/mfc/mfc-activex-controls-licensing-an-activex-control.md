---
title: 'MFC ActiveX denetimleri: ActiveX denetimini lisanslama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- COleObjectFactory
dev_langs:
- C++
helpviewer_keywords:
- COleObjectFactory class [MFC], licensing controls
- MFC ActiveX controls [MFC], licensing
- VerifyLicenseKey method [MFC]
- VerifyUserLicense method [MFC]
- GetLicenseKey method [MFC]
- licensing ActiveX controls
ms.assetid: cacd9e45-701a-4a1f-8f1f-b0b39f6ac303
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 725e6cf167ec01635a3072f09ecaa2f5055b1891
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353941"
---
# <a name="mfc-activex-controls-licensing-an-activex-control"></a>MFC ActiveX Denetimleri: ActiveX Denetimini Lisanslama
Destek lisanslama, ActiveX denetimlerinin, isteğe bağlı bir özellik sağlar. kullanabilir veya denetim dağıtmak kimin. (Lisans sorunları lisans sorunları, ek açıklama için bkz [varolan bir ActiveX denetimini güncelleştirme](../mfc/upgrading-an-existing-activex-control.md).)  
  
 Bu makalede aşağıdaki konular ele alınmıştır:  
  
-   [ActiveX denetimini lisanslama genel bakış](#_core_overview_of_activex_control_licensing)  
  
-   [Lisanslı denetimi oluşturma](#_core_creating_a_licensed_control)  
  
-   [Lisans desteği](#_core_licensing_support)  
  
-   [Bir ActiveX denetimini lisanslama özelleştirme](#_core_customizing_the_licensing_of_an_activex_control)  
  
 Lisans uygulamak ActiveX denetimleri, diğer kişilerin ActiveX denetimini nasıl kullanılacağını belirlemek için denetim geliştiricisi olarak, izin verin. Denetimle denetim satın alan sağlamak ve. LİS dosyasıyla satın alan kişinin denetim dağıtacağını ancak anlaşma. Denetimi kullanan bir uygulama ile lisans sözleşmesi dosyası. Bu, kullanıcıların, denetimden ilk lisans olmadan denetim kullanan yeni uygulamalar yazmasını uygulamasının engeller.  
  
##  <a name="_core_overview_of_activex_control_licensing"></a> ActiveX denetimini lisanslama genel bakış  
 ActiveX denetimleri için lisans desteği sağlamak için [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) SAX çeşitli işlevleri için uygulama **IClassFactory2** arabirimi: **IClassFactory2 :: RequestLicKey**, **IClassFactory2::GetLicInfo**, ve **IClassFactory2::CreateInstanceLic**. Kapsayıcı uygulama geliştiricisinin denetimi, bir çağrı örneğini oluşturmak için bir istek zaman hale getirir `GetLicInfo` doğrulamak için yapılan denetim. LİS dosya yok. Denetim lisanslanmışsa denetim örneği oluşturulur ve kapsayıcısında yerleştirilir. Geliştirici kapsayıcı uygulaması oluşturma tamamlandıktan sonra başka bir işlev çağrısı, bu sefer `RequestLicKey`, yapılır. Bu işlev, kapsayıcı uygulamaya bir lisans anahtarı (Basit karakter dizesi) döndürür. Döndürülen anahtar ardından uygulamada katıştırılır.  
  
 Aşağıdaki şekilde bir kapsayıcı uygulama geliştirme sırasında kullanılacak bir ActiveX denetimi lisans doğrulanması gösterir. Daha önce belirtildiği gibi kapsayıcı uygulama geliştiricisi uygun olması gerekir. Lisans Sözleşmesi dosyası denetimi örneğini oluşturmak için geliştirme makinede yüklü.  
  
 ![ActiveX denetimi geliştirme doğrulanır lisanslı](../mfc/media/vc374d1.gif "vc374d1")  
Lisanslı bir ActiveX denetimi doğrulama geliştirme sırasında  
  
 Son kullanıcı kapsayıcı uygulamayı çalıştırdığında aşağıdaki şekilde gösterildiği sonraki işlemi gerçekleşir.  
  
 Uygulama başlatıldığında, denetim örneği genellikle oluşturulması gerekir. Kapsayıcı bunu yapılan bir çağrı yaparak gerçekleştirir `CreateInstanceLic`, katıştırılmış lisans anahtarı parametre olarak geçirme. Dize karşılaştırması sonra katıştırılmış lisans anahtarı ve lisans anahtarı denetimin kendi kopyasını arasında yapılır. Eşleştirme başarılı olursa, denetim örneği oluşturulur ve uygulama normalde yürütmeye devam eder. Dikkat edin. LİS dosya denetim kullanıcının makinesinde mevcut olması gerekmez.  
  
 ![ActiveX denetimi yürütme sırasında doğrulandı lisanslı](../mfc/media/vc374d2.gif "vc374d2")  
Lisanslı bir ActiveX denetimi doğrulama yürütme sırasında  
  
 Denetimini lisanslama iki temel bileşenlerden oluşur: DLL denetim uygulamasında özel kod ve lisans dosyası. Kod iki (veya büyük olasılıkla üç) işlev çağrılarını ve bundan sonra "Telif hakkı uyarısı içeren bir lisans dize", başvurulan bir karakter dizesi kümesinden oluşur. Bu çağrıları ve lisans dize denetim uygulamasında bulunan (. CPP) dosyası. ActiveX Denetim Sihirbazı tarafından oluşturulan lisans dosyası, telif hakkı bildirimi ile bir metin dosyasıdır. Proje adıyla kullanarak adlı bir. LİS uzantısı, örneğin örnek. LİSANS SÖZLEŞMESİ. Tasarım zamanı kullanım gerekirse lisanslı denetim lisans dosyası tarafından eklenmelidir.  
  
##  <a name="_core_creating_a_licensed_control"></a> Lisanslı denetimi oluşturma  
 Denetim çerçevesi oluşturmak için ActiveX Denetim Sihirbazı'nı kullandığınızda, destek lisans dahil kolaydır. Denetim bir çalışma zamanı Lisansı olmalıdır belirttiğinizde, ActiveX Denetim Sihirbazı'nı kod lisans desteklemek için denetim sınıfı ekler. Lisans doğrulama için bir anahtar ve lisans dosyası kullanan işlevler kodu oluşur. Bu işlevler de denetimini lisanslama özelleştirmek için değiştirilebilir. Lisans özelleştirme hakkında daha fazla bilgi için bkz: [bir ActiveX denetimini lisanslama özelleştirme](#_core_customizing_the_licensing_of_an_activex_control) bu makalenin ilerisinde yer.  
  
#### <a name="to-add-support-for-licensing-with-the-activex-control-wizard-when-you-create-your-control-project"></a>Denetim projenizi oluşturduğunuzda ActiveX Denetim Sihirbazı'nı kullanarak lisans için destek eklemek için  
  
1.  Konusundaki yönergeleri kullanın [MFC ActiveX denetimi oluşturma](../mfc/reference/creating-an-mfc-activex-control.md). **Uygulama ayarları** ActiveX Denetim Sihirbazı sayfasında denetimi ile çalışma zamanı lisans oluşturma seçeneğini içerir.  
  
 ActiveX Denetim Sihirbazı'nı şimdi temel lisans desteği içeren bir ActiveX denetimi çerçeve oluşturur. Lisans kodu ayrıntılı bir açıklaması için sonraki konusuna bakın.  
  
##  <a name="_core_licensing_support"></a> Lisans desteği  
 Bir ActiveX denetimini lisanslama desteği eklemek için ActiveX Denetim Sihirbazı'nı kullandığınızda, ActiveX Denetim Sihirbazı'nı bildirir ve lisans yetenek uygulayan kod control üstbilgisinin ve uygulama dosyalarını eklenir ekler. Bu kod oluşan bir `VerifyUserLicense` üye işlevini ve `GetLicenseKey` bulunan varsayılan uygulamaları geçersiz üye işlevi [COleObjectFactory](../mfc/reference/coleobjectfactory-class.md) . Bu işlevler almak ve denetim lisans doğrulayın.  
  
> [!NOTE]
>  Üçüncü bir üye işlevi `VerifyLicenseKey` ActiveX Denetim Sihirbazı tarafından oluşturulmaz, ancak lisans anahtarı doğrulama davranışını özelleştirmek için geçersiz kılınabilir.  
  
 Bu üye işlevleri şunlardır:  
  
-   [VerifyUserLicense](../mfc/reference/coleobjectfactory-class.md#verifyuserlicense)  
  
     Varlığı için sistem denetimi lisans dosyasının denetleyerek denetimi tasarım zamanı kullanım izin verdiğini doğrular. Bu işlev işleme bir parçası olarak çerçevesi tarafından çağrılır **IClassFactory2::GetLicInfo** ve **IClassFactory::CreateInstanceLic**.  
  
-   [GetLicenseKey](../mfc/reference/coleobjectfactory-class.md#getlicensekey)  
  
     Benzersiz bir anahtar denetim DLL'i ister. Bu anahtar kapsayıcı uygulamasında katıştırılmış ve daha sonra ile birlikte kullanılan `VerifyLicenseKey`denetimi örneğini oluşturmak için. Bu işlev işleme bir parçası olarak çerçevesi tarafından çağrılır **IClassFactory2::RequestLicKey**.  
  
-   [VerifyLicenseKey](../mfc/reference/coleobjectfactory-class.md#verifylicensekey)  
  
     Katıştırılmış anahtar ve denetim benzersiz anahtar aynı olduğunu doğrular. Bu denetimin kullanılması için bir örneğini oluşturmak kapsayıcı sağlar. Bu işlev işleme bir parçası olarak çerçevesi tarafından çağrılır **IClassFactory2::CreateInstanceLic** ve lisans anahtarı özelleştirilmiş doğrulanmasını sağlamak için geçersiz kılınabilir. Varsayılan uygulama dize karşılaştırmasının gerçekleştirir. Daha fazla bilgi için bkz: [bir ActiveX denetimini lisanslama özelleştirme](#_core_customizing_the_licensing_of_an_activex_control), bu makalenin ilerisinde yer.  
  
###  <a name="_core_header_file_modifications"></a> Üstbilgi dosyası değişikliği  
 ActiveX Denetim Sihirbazı'nı aşağıdaki kodu denetimi üstbilgi dosyasına yerleştirir. Bu örnekte, iki üye işlevlerini `CSampleCtrl`kullanıcının nesnesi `factory` bildirildiğinde, bir denetim varlığını doğrular. LİS dosya ve diğeri de denetimi içeren bir uygulama içinde kullanılacak lisans anahtarı alır:  
  
 [!code-cpp[NVC_MFC_AxUI#39](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_1.h)]  
  
###  <a name="_core_implementation_file_modifications"></a> Uygulama dosya değişiklikleri  
 ActiveX Denetim Sihirbazı'nı aşağıdaki iki ifadeleri lisans filename ve lisans dize bildirmek için Denetim uygulama dosyasına yerleştirir:  
  
 [!code-cpp[NVC_MFC_AxUI#40](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_2.cpp)]  
  
> [!NOTE]
>  Değiştirirseniz **szLicString** herhangi bir yolla denetimi ilk satırı da değiştirmelisiniz. LİS dosya ya da lisans düzgün çalışmaz.  
  
 ActiveX Denetim Sihirbazı'nı aşağıdaki kodu control sınıfı tanımlamak için Denetim uygulama dosyasına yerleştirir `VerifyUserLicense` ve `GetLicenseKey` işlevleri:  
  
 [!code-cpp[NVC_MFC_AxUI#41](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_3.cpp)]  
  
 Son olarak, **ActiveX Denetim Sihirbazı** denetim projeyi değiştirir. IDL dosyası. **Lisanslı** anahtar sözcüğü, aşağıdaki örnekte olduğu gibi denetimi coclass bildirimi eklenir:  
  
 [!code-cpp[NVC_MFC_AxUI#42](../mfc/codesnippet/cpp/mfc-activex-controls-licensing-an-activex-control_4.idl)]  
  
##  <a name="_core_customizing_the_licensing_of_an_activex_control"></a> Bir ActiveX denetimini lisanslama özelleştirme  
 Çünkü `VerifyUserLicense`, `GetLicenseKey`, ve `VerifyLicenseKey` bildirildiğinde denetim fabrika sınıfı sanal üye işlevleri denetimin lisans davranışını özelleştirebilirsiniz.  
  
 Örneğin, denetim için geçersiz kılarak lisansı birkaç düzeyleri sağlayabilir `VerifyUserLicense` veya `VerifyLicenseKey` üye işlevleri. Bu işlev içinde hangi özelliklerinin veya yöntemlerin, algılanan lisans düzeyine göre kullanıcıya sunulan ayarlamak.  
  
 Kod ayrıca ekleyebilirsiniz `VerifyLicenseKey` oluşturma kontrol kullanıcı bildiren başarısız oldu, özelleştirilmiş bir yöntem sağlayan işlevi. Örneğin, sizin `VerifyLicenseKey` bir ileti görüntüler üye işlevi kutusuna denetim başlatılamadı belirten ve neden.  
  
> [!NOTE]
>  ActiveX denetimi lisans doğrulama özelleştirmek için başka bir çağırmak yerine, belirli kayıt defteri anahtarı için kayıt veritabanını kontrol etmek üzere yoludur `AfxVerifyLicFile`. Varsayılan uygulama örneği için bkz: [uygulama dosya değişiklikleri](#_core_implementation_file_modifications) bu makalenin.  
  
 Lisans sorunları lisans sorunları, ek açıklama için bkz [varolan bir ActiveX denetimini güncelleştirme](../mfc/upgrading-an-existing-activex-control.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md)

