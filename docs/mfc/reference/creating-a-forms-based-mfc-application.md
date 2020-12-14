---
description: 'Daha fazla bilgi edinin: Forms-Based MFC uygulaması oluşturma'
title: Form Tabanlı MFC Uygulaması Oluşturma
ms.date: 09/09/2019
f1_keywords:
- vc.appwiz.mfcforms.project
helpviewer_keywords:
- applications [MFC], forms-based
- forms-based applications [MFC]
ms.assetid: 048d2f7d-b60d-4386-ad8e-71d49af9c05e
ms.openlocfilehash: 2023f4f2c074ef1d0e3adf936cd4c31bd334b795
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343244"
---
# <a name="creating-a-forms-based-mfc-application"></a>Form Tabanlı MFC Uygulaması Oluşturma

Form, bir kullanıcının erişimine ve muhtemelen verileri değiştirmesine izin veren denetimleri içeren bir iletişim kutusudur. Kullanıcının bir form seçiminden seçtiği bir uygulama geliştirmek isteyebilirsiniz. Genellikle, form tabanlı bir uygulama, kullanıcının **Dosya** menüsünde **Yeni** ' ye tıklayarak formlara erişmesini sağlar. Kullanıcılara **Dosya** menüsündeki **Yeni** bir seçeneğe erişim izni veren iletişim kutusu tabanlı bir uygulama, form tabanlı bir uygulama olarak da değerlendirilir.

Tek belge arabirimi (SDI), form tabanlı uygulama belirli bir formun tek seferde yalnızca bir örneğinin çalışmasına izin verir. **Dosya** menüsündeki **Yeni** seçenekten yeni bir form seçerek bir SDI form tabanlı uygulamadan aynı anda farklı formlar çalıştırmak mümkündür.

Birden çok belge arabirimi (MDI), form tabanlı uygulama oluşturursanız, uygulama aynı formun birden çok örneğini destekleyebilir.

Birden çok üst düzey belge desteğine sahip bir uygulama oluşturursanız, Masaüstü, belgenin örtülü üst öğesidir ve belgenin çerçevesi uygulamanın istemci alanıyla sınırlı değildir. Belgenin birden çok örneğini, her biri kendi çerçevesini, menüsünü ve görev çubuğu simgesini kullanarak açabilirsiniz. Belgelerin sonraki örneklerini tek tek kapatabilirsiniz, ancak ilk Örneğin **Dosya** menüsünden **Çıkış** seçeneğini belirlerseniz, uygulama tüm örnekleri kapatır.

SDI, MDI ve birden çok üst düzey belge uygulaması, tüm form tabanlıdır ve belge/görünüm mimarisini kullanır.

Tüm iletişim tabanlı uygulamalar, tanım temelinde Forms tabanlıdır. İletişim temelli bir uygulama belge/görünüm mimarisini kullanmaz, bu nedenle kendi ek formlarınız için oluşturma ve erişim yöntemlerini yönetmeniz gerekir.

Form tabanlı uygulamalar için temel sınıf [CFormView](cformview-class.md)' dir. Uygulamanızda veritabanı desteği varsa, ' den türetilen tüm sınıfları da seçebilirsiniz `CFormView` . Form, öğesinden devralan herhangi bir sınıftan veya ondan türetilmiş herhangi bir penceredir `CFormView` `CFormView` .

[CView](cview-class.md)gibi bir temel sınıf kullansanız bile, daha sonra uygulamalarınızdan TÜRETILMIŞ [bir MFC sınıfı ekleyerek](adding-an-mfc-class.md) uygulamalarınızı Forms tabanlı hale getirebilirsiniz `CFormView` .

Sihirbazla tamamladıktan sonra projeniz açılır ve `CFormView` temel sınıfınız olarak (veya öğesinden devralan bir sınıf `CFormView` ) seçtiyseniz veya iletişim kutusu tabanlı bir uygulama oluşturduysanız, iletişim kutusu düzenleyicisini açar Visual C++. Bu noktada, ilk formunuzu tasarlamaya hazırlanın.

### <a name="to-begin-creating-a-forms-based-mfc-executable"></a>Form tabanlı MFC çalıştırılabilir dosyası oluşturmaya başlamak için

1. Form tabanlı MFC uygulaması için [MFC uygulaması oluşturma](creating-an-mfc-application.md) yönergelerini izleyin.

1. MFC Uygulama Sihirbazı [uygulama türü](application-type-mfc-application-wizard.md) sayfasında **belge/görünüm mimari desteği** onay kutusunu seçin.

1. **Tek belge**, **birden çok belge** veya **birden çok üst düzey belge** seçin.

    > [!NOTE]
    >  Bir SDI, MDI veya birden çok üst düzey belge arabirimi uygulaması seçerseniz, varsayılan olarak, `CView` sihirbazın [oluşturulan sınıflar](generated-classes-mfc-application-wizard.md) sayfasında uygulamanızın görünümü için temel sınıf olarak ayarlanır. Form tabanlı bir uygulama oluşturmak için, `CFormView` uygulamanın görünümü için temel sınıf olarak öğesini seçmeniz gerekir. Sihirbazın form tabanlı bir uygulama için yazdırma desteği sunmadığını unutmayın.

1. Sihirbazın diğer sayfalarında istediğiniz diğer proje seçeneklerini ayarlayın.

1. İskelet uygulamasını oluşturmak için **son** ' a tıklayın.

Daha fazla bilgi için bkz:

- [Türetilmiş Görünüm sınıfları](../derived-view-classes-available-in-mfc.md)

- [Belge/görünüm mimarisi alternatifleri](../alternatives-to-the-document-view-architecture.md)

- [Uygulama tasarımı seçimleri](../application-design-choices.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC Uygulama Sihirbazı](mfc-application-wizard.md)<br/>
[Form görünümleri](../form-views-mfc.md)<br/>
[MFC uygulaması Explorer-Style dosya oluşturma](creating-a-file-explorer-style-mfc-application.md)<br/>
[Web Browser-Style MFC uygulaması oluşturma](creating-a-web-browser-style-mfc-application.md)
