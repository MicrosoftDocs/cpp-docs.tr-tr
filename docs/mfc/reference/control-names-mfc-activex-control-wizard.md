---
title: Denetim Adları, MFC ActiveX Denetim Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.ctl.names
helpviewer_keywords:
- MFC ActiveX Control Wizard, control names
ms.assetid: 9b8b81d2-36df-48ed-b58a-a771a0e269ee
ms.openlocfilehash: eff7b537e7fe5c19d10cce8766557a3d1ff49342
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077512"
---
# <a name="control-names-mfc-activex-control-wizard"></a>Denetim Adları, MFC ActiveX Denetim Sihirbazı

Denetiminiz için denetim sınıfı ve özellik sayfası sınıfı, tür adları ve tür tanımlayıcıları için adlar belirtin. **Kısa ad**hariç olmak üzere, diğer tüm alanlar bağımsız olarak düzenlenebilir. **Kısa ad**için metni değiştirirseniz, değişiklik bu sayfadaki diğer tüm alanların adlarına yansıtılır. Bu adlandırma davranışı, denetiminizi geliştirirken tüm adların sizin için kolayca tanımlanabilir olmasını sağlayacak şekilde tasarlanmıştır.

- **Kısa ad**

   Denetim için kısaltılmış bir ad sağlayın. Bu ad, varsayılan olarak, **Yeni proje** iletişim kutusunda verdiğiniz proje adına göre belirlenir. Sağladığınız ad, bu alanları ayrı ayrı değiştirmediğiniz müddetçe sınıf adlarını, tür adlarını ve tür tanımlayıcılarını belirler.

- **Denetim sınıfı adı**

   Varsayılan olarak, denetim sınıfının adı, ön ek olarak `C` ve sonek olarak `Ctrl`, kısa adı temel alır. Örneğin, denetiminizin kısa adı `Price`ise, denetim sınıfı adı `CPriceCtrl`.

- **Control. h dosyası**

   Varsayılan olarak, üst bilgi dosyasının adı, sonek olarak `Ctrl` ve dosya uzantısı olarak `.h`, kısa adı temel alır. Örneğin, denetiminizin kısa adı `Price`ise, üst bilgi dosya adı `PriceCtrl.h`. Bu alandaki ad, denetim sınıfı adıyla eşleşmelidir.

- **Denetim. cpp dosyası**

   Varsayılan olarak, üst bilgi dosyasının adı, sonek olarak `Ctrl` ve dosya uzantısı olarak `.cpp`, kısa adı temel alır. Örneğin, denetiminizin kısa adı `Price`ise, üst bilgi dosya adı `PriceCtrl.cpp`. Bu alandaki ad üstbilgi adıyla eşleşmelidir.

- **Denetim türü adı**

   Varsayılan olarak, denetim türünün adı, kısa adı temel alır ve ardından `Control`. Örneğin, denetiminizin kısa adı `Price`ise, denetim sınıfı tür adı `Price Control`. Bu alandaki değeri değiştirirseniz, adın bir devralmayı belirttiğinizden emin olun.

- **Denetim türü KIMLIĞI**

   Denetim sınıfının denetim türü KIMLIĞINI ayarlar. Denetim, bir projeye eklendiğinde bu dizeyi kayıt defterine yazar. Kapsayıcı uygulamalar bu dizeyi, denetimin bir örneğini oluşturmak için kullanır.

   Varsayılan olarak, denetim türü KIMLIĞI, **Yeni proje** iletişim kutusunda ve kısa ad ' da belirttiğiniz proje adına göre belirlenir. Bu ad, tür adıyla eşleşmelidir.

   Varsayılan olarak, denetim türü KIMLIĞI aşağıdaki gibi görünür:

   *ProjectName. ShortName* CTRL. 1

   Bu iletişim kutusunda kısa adı değiştirirseniz, denetim türü KIMLIĞI aşağıdaki gibi görünür:

   *ProjectName. NewShortName* CTRL. 1

- **PropPage sınıf adı**

   Varsayılan olarak, özellik sayfası sınıfının adı, ön ek olarak `C` ve sonek olarak `PropPage`, kısa adı temel alır. Örneğin, denetiminizin kısa adı `Price`ise, özellik sayfası sınıf adı `CPricePropPage`. Bu ad, `PropPage`eklenerek denetim sınıfı adıyla eşleşmelidir.

- **PropPage. h dosyası**

   Varsayılan olarak, özellik sayfası üstbilgi dosyasının adı, sonek olarak `PropPage` ve dosya uzantısı olarak `.h` olmak üzere kısa adı temel alır. Örneğin, denetiminizin kısa adı `Price`ise, özellik sayfası üstbilgi dosyası adı `PricePropPage.h`. Bu ad, sınıf adıyla eşleşmelidir.

- **PropPage. cpp dosyası**

   Varsayılan olarak, özellik sayfası uygulama dosyasının adı, sonek olarak `PropPage` ve dosya uzantısı olarak `.cpp` olmak üzere kısa adı temel alır. Örneğin, denetiminizin kısa adı `Price`ise, özellik sayfası üstbilgi dosyası adı `PricePropPage.cpp`. Bu ad, üstbilgi dosyası adıyla eşleşmelidir.

- **PropPage tür adı**

   Varsayılan olarak, özellik sayfası tür adı kısa adı temel alır ve ardından `Property Page`. Örneğin, denetiminizin kısa adı `Price`ise, özellik sayfası tür adı `Price Property Page`. Bu alandaki değeri değiştirirseniz, adın denetim sınıfını gösterdiği olduğundan emin olun.

- **PropPage tür KIMLIĞI**

   Özellik sayfası sınıfının KIMLIĞINI ayarlar. Denetim, bir projeye uygulandığında bu dizeyi kayıt defterine yazar. Bir kapsayıcı uygulaması bu dizeyi, denetimin özellik sayfasının bir örneğini oluşturmak için kullanır.

   Varsayılan olarak, özellik sayfası türü KIMLIĞI, **Yeni proje** iletişim kutusunda belirttiğiniz proje adına ve kısa ada göre belirlenir. Bu ad, tür adıyla eşleşmelidir.

   Varsayılan olarak, özellik sayfası tür KIMLIĞI aşağıdaki gibi görünür:

   *ProjectName. ShortName* PropPage. 1

   Bu iletişim kutusunda kısa adı değiştirirseniz, özellik sayfası türü KIMLIĞI aşağıdaki gibi görünür:

   *ProjectName. NewShortName* PropPage. 1

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetim Sihirbazı](../../mfc/reference/mfc-activex-control-wizard.md)<br/>
[Uygulama Ayarları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)<br/>
[Denetim Ayarları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)<br/>
[Visual Studio C++ projeleri için oluşturulan dosya türleri](../../build/reference/file-types-created-for-visual-cpp-projects.md)
