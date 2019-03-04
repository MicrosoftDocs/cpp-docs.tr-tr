---
title: Denetim Adları, MFC ActiveX Denetim Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.ctl.names
helpviewer_keywords:
- MFC ActiveX Control Wizard, control names
ms.assetid: 9b8b81d2-36df-48ed-b58a-a771a0e269ee
ms.openlocfilehash: a143c8b08c73676af0d37cd2b67667e8270dc2b1
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259869"
---
# <a name="control-names-mfc-activex-control-wizard"></a>Denetim Adları, MFC ActiveX Denetim Sihirbazı

Özellik sayfası sınıfının, tür adları ve denetim sınıf adlarını belirtin ve tanımlayıcıları denetiminizin yazın. Dışında **kısa ad**, diğer tüm alanlar birbirinden bağımsız olarak düzenlenebilir. Metni değiştirirseniz **kısa ad**, bu değişiklik bu sayfadaki diğer tüm alanların adlarındaki yansıtılır. Bu adlandırma davranışı denetiminiz geliştirirken tüm adlarını kolayca tanımlanabilen yapmak için tasarlanmıştır.

- **Kısa ad**

   Denetim için kısaltılmış bir ad belirtin. Varsayılan olarak, bu ad, sağlanan proje adı dayanır **yeni proje** iletişim kutusu. Bu alanları ayrı ayrı değiştirmediğiniz sürece sağladığınız adın sınıf adları, tür adları ve tür tanımlayıcıları belirler.

- **Denetim sınıfı adı**

   Varsayılan olarak, denetim sınıfı adı kısa adına, ile dayalı `C` öneki olarak ve `Ctrl` soneki olarak. Örneğin, Denetim kısa adı ise `Price`, denetim sınıfı adı `CPriceCtrl`.

- **Denetim .h dosyası**

   Varsayılan olarak, üst bilgi dosyası adını kısa adına, ile dayalı `Ctrl` soneki olarak ve `.h` dosya uzantısı. Örneğin, Denetim kısa adı ise `Price`, üst bilgi dosyası adı: `PriceCtrl.h`. Bu alan adlarında denetim sınıfı adı eşleşmelidir.

- **Denetim .cpp dosyası**

   Varsayılan olarak, üst bilgi dosyası adını kısa adına, ile dayalı `Ctrl` soneki olarak ve `.cpp` dosya uzantısı. Örneğin, Denetim kısa adı ise `Price`, üst bilgi dosyası adı: `PriceCtrl.cpp`. Bu alan adlarında, üst bilgi adı eşleşmelidir.

- **Denetim türü adı**

   Varsayılan olarak, ardından kısa adı, Denetim türü adını dayanır `Control`. Örneğin, Denetim kısa adı ise `Price`, denetim sınıf türü adı `Price Control`. Bu alandaki değer değiştirirseniz, bir devralma adından da anlaşılacağı emin olun.

- **Denetim türü kimliği**

   Denetim sınıfı kimlik denetimi türünü ayarlar. Bir projeye eklendiğinde denetim kayıt defterine bu bir dize yazar. Kapsayıcı uygulamaları denetimi örneğini oluşturmak için şu dizeyi kullanın.

   Varsayılan olarak, Denetim türü kimliği, belirtilen proje adı dayanır **yeni proje** iletişim kutusu ve kısa ad. Bu ad, tür adı eşleşmelidir.

   Varsayılan olarak, Denetim türü kimliği aşağıdaki gibi görünür:

   *ProjectName.ShortName*Ctrl.1

   Bu iletişim kutusunda kısa adını değiştirirseniz, Denetim türü kimliği şu şekilde görünür:

   *ProjectName.NewShortName*Ctrl.1

- **PropPage sınıf adı**

   Varsayılan olarak, özellik sayfası sınıfının adını kısa adına, ile dayalı `C` öneki olarak ve `PropPage` soneki olarak. Örneğin, Denetim kısa adı ise `Price`, özellik sayfası sınıfı adı `CPricePropPage`. Bu ad, protokolün denetim sınıfı adı eşleşmelidir `PropPage`.

- **PropPage .h dosyası**

   Varsayılan olarak, özellik sayfasında üst bilgi dosyası adını kısa adına, ile olarak dayalı bir `PropPage` soneki olarak ve `.h` dosya uzantısı. Örneğin, Denetim kısa adı ise `Price`, özellik sayfa üst bilgisi dosya adı `PricePropPage.h`. Bu ad, sınıf adı eşleşmelidir.

- **PropPage .cpp dosyası**

   Varsayılan olarak, özellik sayfası uygulama dosyasının adı kısa adına, ile olarak dayalı bir `PropPage` soneki olarak ve `.cpp` dosya uzantısı. Örneğin, Denetim kısa adı ise `Price`, özellik sayfa üst bilgisi dosya adı `PricePropPage.cpp`. Bu ad, üst bilgi dosyası adı eşleşmelidir.

- **PropPage tür adı**

   Varsayılan olarak, ardından kısa adı, özellik sayfa türü adı dayanır `Property Page`. Örneğin, Denetim kısa adı ise `Price`, özellik sayfa türü adı `Price Property Page`. Bu alandaki değer değiştirirseniz, denetim sınıfı adı gösterir emin olun.

- **PropPage tür kimliği**

   Özellik sayfası sınıfının bir kimlik ayarlar. Bir projeye uygulandığında denetim kayıt defterinde bu bir dize yazar. Bir kapsayıcı uygulaması denetimin özellik sayfasının bir örneğini oluşturmak için bu dizeyi kullanır.

   Varsayılan olarak, belirtilen proje adı, özellik sayfa türü kimliği dayanır **yeni proje** iletişim kutusu ve kısa ad. Bu ad, tür adı eşleşmelidir.

   Varsayılan olarak, özellik sayfa türü kimliği aşağıdaki gibi görünür:

   *ProjectName.ShortName*PropPage.1

   Bu iletişim kutusunda kısa adını değiştirirseniz, özellik sayfa türü kimliği şu şekilde görünür:

   *ProjectName.NewShortName*PropPage.1

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetim Sihirbazı](../../mfc/reference/mfc-activex-control-wizard.md)<br/>
[Uygulama Ayarları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)<br/>
[Denetim Ayarları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)<br/>
[Visual C++ Projeleri için Oluşturulan Dosya Türleri](../../ide/file-types-created-for-visual-cpp-projects.md)
