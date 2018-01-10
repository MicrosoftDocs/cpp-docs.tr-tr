---
title: "Denetim adları, MFC ActiveX Denetim Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.mfc.ctl.names
dev_langs: C++
helpviewer_keywords: MFC ActiveX Control Wizard, control names
ms.assetid: 9b8b81d2-36df-48ed-b58a-a771a0e269ee
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5f3444ec69ea96ee89ed7a0965f3575fc79e3b9c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="control-names-mfc-activex-control-wizard"></a>Denetim Adları, MFC ActiveX Denetim Sihirbazı
Denetim ve özellik sayfası sınıf, tür adları için ad belirtmek ve denetlemek için tanımlayıcıları yazın. Dışında **kısa ad**, diğer tüm alanlar bağımsız olarak düzenlenebilir. Metni değiştirirseniz **kısa ad**, değişiklik bu sayfasındaki diğer tüm alanların adlarını yansıtılır. Bu adlandırma davranış denetiminizi geliştirdikçe tüm adlar kolayca tanımlanabilen yapmak için tasarlanmıştır.  
  
 **Kısa ad**  
 Denetim için kısa bir ad girin. Varsayılan olarak, bu ad, sağladığınız proje adı dayanır **yeni proje** iletişim kutusu. Bu alanlar ayrı ayrı değiştirmediğiniz sürece sağladığınız ad sınıf adları, tür adları ve tür tanımlayıcıları belirler.  
  
 **Denetimin sınıf adı**  
 Varsayılan olarak, ile kısa adına denetim sınıfın adını dayanır `C` öneki olarak ve `Ctrl` soneki olarak. Örneğin, Denetim kısa adı ise `Price`, denetim sınıf adı `CPriceCtrl`.  
  
 **Denetim .h dosyası**  
 Varsayılan olarak, ile kısa adına üstbilgi dosyası adını dayanır `Ctrl` soneki olarak ve `.h` dosya uzantısı olarak. Örneğin, Denetim kısa adı ise `Price`, üstbilgi dosya adı `PriceCtrl.h`. Bu alandaki denetim sınıf adı adıyla aynı olmalıdır.  
  
 **Denetim .cpp dosyası**  
 Varsayılan olarak, ile kısa adına üstbilgi dosyası adını dayanır `Ctrl` soneki olarak ve `.cpp` dosya uzantısı olarak. Örneğin, Denetim kısa adı ise `Price`, üstbilgi dosya adı `PriceCtrl.cpp`. Bu alandaki üstbilgi adı adıyla aynı olmalıdır.  
  
 **Denetim türü adı**  
 Varsayılan olarak, Denetim türü adını ve ardından kısa ad dayanır `Control`. Örneğin, Denetim kısa adı ise `Price`, denetim sınıf türü adı `Price Control`. Bu alandaki değer değiştirirseniz, bir devralma adını gösterir emin olun.  
  
 **Denetim türü kimliği**  
 Denetim sınıfı kimlik denetimi türünü ayarlar. Bir projeye eklendiğinde denetimi bu dize kayıt defterine yazar. Kapsayıcı uygulamaları bu dize denetimi örneğini oluşturmak için kullanın.  
  
 Varsayılan olarak, Denetim türü kimliği içinde belirtilen proje adı dayanır **yeni proje** iletişim kutusu ve kısa ad. Bu ad, tür adının eşleşmesi gerekir.  
  
 Varsayılan olarak, Denetim türü kimliği aşağıdaki gibi görünür:  
  
 *ProjectName.ShortName*Ctrl.1  
  
 Bu iletişim kutusunda kısa adını değiştirirseniz, Denetim türü kimliği aşağıdaki gibi görünür:  
  
 *ProjectName.NewShortName*Ctrl.1  
  
 **PropPage sınıf adı**  
 Varsayılan olarak, ile kısa adına özellik sayfası sınıfın adını dayanır `C` öneki olarak ve `PropPage` soneki olarak. Örneğin, Denetim kısa adı ise `Price`, özellik sayfasında sınıf adı `CPricePropPage`. Bu adı ile eklenen denetim sınıf adı eşleşmelidir `PropPage`.  
  
 **PropPage .h dosyası**  
 Varsayılan olarak, özellik sayfasında üstbilgi dosyası adını kısa adına sahip olarak dayanır bir `PropPage` soneki olarak ve `.h` dosya uzantısı olarak. Örneğin, Denetim kısa adı ise `Price`, özellik sayfasında üstbilgi dosya adı `PricePropPage.h`. Bu sınıf adı adıyla aynı olmalıdır.  
  
 **PropPage .cpp dosyası**  
 Varsayılan olarak, özellik sayfasında uygulama dosyasının adı kısa adına sahip olarak dayanır bir `PropPage` soneki olarak ve `.cpp` dosya uzantısı olarak. Örneğin, Denetim kısa adı ise `Price`, özellik sayfasında üstbilgi dosya adı `PricePropPage.cpp`. Bu ad üstbilgi dosyası adı eşleşmelidir.  
  
 **PropPage türü adı**  
 Varsayılan olarak, özellik sayfasında türü adı arkasından kısa ad dayanır `Property Page`. Örneğin, Denetim kısa adı ise `Price`, özellik sayfasında tür adı `Price Property Page`. Bu alandaki değer değiştirirseniz, denetim sınıf adını gösterir emin olun.  
  
 **PropPage türü kimliği**  
 Özellik sayfası sınıfı Kimliğini ayarlar. Bir projeye uygulandığında denetimi bu dize kayıt defterinde yazar. Bir kapsayıcı uygulama denetimin özellik sayfası örneği oluşturmak için bu dizeyi kullanır.  
  
 Varsayılan olarak, özellik sayfasında türü kimliği içinde belirtilen proje adı dayanır **yeni proje** iletişim kutusu ve kısa ad. Bu ad, tür adının eşleşmesi gerekir.  
  
 Varsayılan olarak, özellik sayfasında türü kimliği aşağıdaki gibi görünür:  
  
 *ProjectName.ShortName*PropPage.1  
  
 Bu iletişim kutusunda kısa adını değiştirirseniz, özellik sayfasında türü kimliği aşağıdaki gibi görünür:  
  
 *ProjectName.NewShortName*PropPage.1  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetim Sihirbazı](../../mfc/reference/mfc-activex-control-wizard.md)   
 [Uygulama ayarları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)   
 [Denetim ayarları, MFC ActiveX Denetim Sihirbazı](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)   
 [Visual C++ Projeleri için Oluşturulan Dosya Türleri](../../ide/file-types-created-for-visual-cpp-projects.md)

