---
description: 'Hakkında daha fazla bilgi edinin: denetim adları, MFC ActiveX denetimi Sihirbazı'
title: Denetim Adları, MFC ActiveX Denetim Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.ctl.names
helpviewer_keywords:
- MFC ActiveX Control Wizard, control names
ms.assetid: 9b8b81d2-36df-48ed-b58a-a771a0e269ee
ms.openlocfilehash: 26d329465c13c3988a3e9d4d7ccd06294f3b2be3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345244"
---
# <a name="control-names-mfc-activex-control-wizard"></a>Denetim Adları, MFC ActiveX Denetim Sihirbazı

Denetiminiz için denetim sınıfı ve özellik sayfası sınıfı, tür adları ve tür tanımlayıcıları için adlar belirtin. **Kısa ad** hariç olmak üzere, diğer tüm alanlar bağımsız olarak düzenlenebilir. **Kısa ad** için metni değiştirirseniz, değişiklik bu sayfadaki diğer tüm alanların adlarına yansıtılır. Bu adlandırma davranışı, denetiminizi geliştirirken tüm adların sizin için kolayca tanımlanabilir olmasını sağlayacak şekilde tasarlanmıştır.

- **Kısa ad**

   Denetim için kısaltılmış bir ad sağlayın. Bu ad, varsayılan olarak, **Yeni proje** iletişim kutusunda verdiğiniz proje adına göre belirlenir. Sağladığınız ad, bu alanları ayrı ayrı değiştirmediğiniz müddetçe sınıf adlarını, tür adlarını ve tür tanımlayıcılarını belirler.

- **Denetim sınıfı adı**

   Varsayılan olarak, denetim sınıfının adı, önek ve sonek olarak, kısa adı temel alır `C` `Ctrl` . Örneğin, denetiminizin kısa adı ise `Price` , denetim sınıfı adı olur `CPriceCtrl` .

- **Control. h dosyası**

   Varsayılan olarak, üst bilgi dosyasının adı, `Ctrl` sonek ve dosya uzantısı gibi kısa adı temel alır `.h` . Örneğin, denetiminizin kısa adı ise `Price` , üst bilgi dosya adı olur `PriceCtrl.h` . Bu alandaki ad, denetim sınıfı adıyla eşleşmelidir.

- **Denetim. cpp dosyası**

   Varsayılan olarak, üst bilgi dosyasının adı, `Ctrl` sonek ve dosya uzantısı gibi kısa adı temel alır `.cpp` . Örneğin, denetiminizin kısa adı ise `Price` , üst bilgi dosya adı olur `PriceCtrl.cpp` . Bu alandaki ad üstbilgi adıyla eşleşmelidir.

- **Denetim türü adı**

   Varsayılan olarak, denetim türünün adı, kısa adı temel alır ve öğesinden sonra `Control` . Örneğin, denetiminizin kısa adı ise, `Price` Denetim sınıfı tür adı olur `Price Control` . Bu alandaki değeri değiştirirseniz, adın bir devralmayı belirttiğinizden emin olun.

- **Denetim türü KIMLIĞI**

   Denetim sınıfının denetim türü KIMLIĞINI ayarlar. Denetim, bir projeye eklendiğinde bu dizeyi kayıt defterine yazar. Kapsayıcı uygulamalar bu dizeyi, denetimin bir örneğini oluşturmak için kullanır.

   Varsayılan olarak, denetim türü KIMLIĞI, **Yeni proje** iletişim kutusunda ve kısa ad ' da belirttiğiniz proje adına göre belirlenir. Bu ad, tür adıyla eşleşmelidir.

   Varsayılan olarak, denetim türü KIMLIĞI aşağıdaki gibi görünür:

   *ProjectName. ShortName* CTRL. 1

   Bu iletişim kutusunda kısa adı değiştirirseniz, denetim türü KIMLIĞI aşağıdaki gibi görünür:

   *ProjectName. NewShortName* CTRL. 1

- **PropPage sınıf adı**

   Varsayılan olarak, özellik sayfası sınıfının adı, önek ve sonek olarak, kısa adı temel alır `C` `PropPage` . Örneğin, denetiminizin kısa adı ise, `Price` özellik sayfası sınıf adı olur `CPricePropPage` . Bu ad, ile eklenmiş olan denetim sınıfı adıyla eşleşmelidir `PropPage` .

- **PropPage. h dosyası**

   Varsayılan olarak, özellik sayfası üstbilgi dosyasının adı, `PropPage` sonek olarak ve dosya uzantısı olarak, kısa adı temel alır `.h` . Örneğin, denetiminizin kısa adı ise `Price` , özellik sayfası üstbilgi dosyası adı olur `PricePropPage.h` . Bu ad, sınıf adıyla eşleşmelidir.

- **PropPage. cpp dosyası**

   Varsayılan olarak, özellik sayfası uygulama dosyasının adı, `PropPage` sonek olarak ve dosya uzantısı olarak, kısa adı temel alır `.cpp` . Örneğin, denetiminizin kısa adı ise `Price` , özellik sayfası üstbilgi dosyası adı olur `PricePropPage.cpp` . Bu ad, üstbilgi dosyası adıyla eşleşmelidir.

- **PropPage tür adı**

   Varsayılan olarak, özellik sayfası türü adı, kısa adı temel alır ve öğesinden sonra `Property Page` . Örneğin, denetiminizin kısa adı ise, `Price` özellik sayfası tür adı olur `Price Property Page` . Bu alandaki değeri değiştirirseniz, adın denetim sınıfını gösterdiği olduğundan emin olun.

- **PropPage tür KIMLIĞI**

   Özellik sayfası sınıfının KIMLIĞINI ayarlar. Denetim, bir projeye uygulandığında bu dizeyi kayıt defterine yazar. Bir kapsayıcı uygulaması bu dizeyi, denetimin özellik sayfasının bir örneğini oluşturmak için kullanır.

   Varsayılan olarak, özellik sayfası türü KIMLIĞI, **Yeni proje** iletişim kutusunda belirttiğiniz proje adına ve kısa ada göre belirlenir. Bu ad, tür adıyla eşleşmelidir.

   Varsayılan olarak, özellik sayfası tür KIMLIĞI aşağıdaki gibi görünür:

   *ProjectName. ShortName* PropPage. 1

   Bu iletişim kutusunda kısa adı değiştirirseniz, özellik sayfası türü KIMLIĞI aşağıdaki gibi görünür:

   *ProjectName. NewShortName* PropPage. 1

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimi Sihirbazı](../../mfc/reference/mfc-activex-control-wizard.md)<br/>
[Uygulama ayarları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)<br/>
[Denetim ayarları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)<br/>
[Visual Studio C++ projeleri için oluşturulan dosya türleri](../../build/reference/file-types-created-for-visual-cpp-projects.md)
