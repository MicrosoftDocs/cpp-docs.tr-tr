---
title: "Bir form tabanlı MFC uygulaması oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.mfcforms.project
dev_langs: C++
helpviewer_keywords:
- applications [MFC], forms-based
- forms-based applications [MFC]
ms.assetid: 048d2f7d-b60d-4386-ad8e-71d49af9c05e
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1e5d43412da21edce2633c17b5a38e4b1b787495
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-forms-based-mfc-application"></a>Form Tabanlı MFC Uygulaması Oluşturma
Form, bir kullanıcının erişmek ve veri değişikliği olabilir izin denetimleri ile bir iletişim kutusudur. Kullanıcı form seçimden seçer uygulama geliştirme isteyebilirsiniz. Yaygın olarak, forms tabanlı bir uygulama tarafından tıklatın kullanıcı erişimi formları sağlar **yeni** gelen **dosya** menüsü. Hangi kullanıcılara erişim sağlamaz iletişim tabanlı bir uygulama, bir **yeni** seçeneğini **dosya** menüsünde da form tabanlı bir uygulama dikkate alınır.  
  
 Tek belge arabirimi (SDI), form tabanlı uygulama yalnızca bir örneği aynı anda çalıştırmak için belirli bir formu sağlar. Farklı form, yeni bir formdan seçerek SDI form tabanlı bir uygulamadan aynı anda çalıştırmak mümkündür **yeni** seçeneğini **dosya** menüsü.  
  
 Bir birden çok belge arabirimi (MDI), form tabanlı bir uygulama oluşturursanız, uygulamanın birden çok örneğini aynı form desteği mümkün olacaktır.  
  
 Birden çok üst düzey belge desteği ile bir uygulama oluşturursanız, Masaüstü belge için örtük üst öğedir ve belge çerçeve uygulamanın istemci alanını sınırlı değildir. Belge her biri kendi çerçevesi, menü ve görev çubuğunda simge sahip birden çok örneğini açabilirsiniz. Seçerseniz ancak belgeleri sonraki örneklerini ayrı ayrı kapatabilirsiniz `Exit` gelen seçeneği **dosya** menü uygulamanın ilk örneğinin tüm örneklerini kapatır.  
  
 SDI ve MDI birden çok üst düzey belge uygulamaları tüm form tabanlı ve belge/görünüm mimarisi olan.  
  
 Tüm iletişim tabanlı, tanımı tarafından forms tabanlı bir uygulamadır. İçin kendi ek formları oluşturma ve erişim yöntemleri yönetmelisiniz iletişim tabanlı bir uygulama belge/görünüm mimarisinin kullanmaz.  
  
 Form tabanlı uygulamalar için temel sınıfı olan [Cformview'yu](../../mfc/reference/cformview-class.md). Veritabanı desteği uygulamanız sahip sonra türetilen herhangi bir sınıf öğesini de seçebilirsiniz `CFormView`. Türetilen pencere formdur `CFormView` veya devraldığı herhangi bir sınıftan `CFormView`.  
  
 Bir taban sınıf gibi kullansanız bile [CView](../../mfc/reference/cview-class.md), form tabanlı tarafından uygulamalarınızı daha sonra yapabilirsiniz [bir MFC sınıfı ekleme](../../mfc/reference/adding-an-mfc-class.md) türetilen `CFormView` ve denetimi **DocTemplate oluştur Kaynakları** onay kutusu [MFC Sınıf Sihirbazı](../../mfc/reference/document-template-strings-mfc-add-class-wizard.md).  
  
 Sihirbazı tamamladıktan sonra projenizin açar, ve seçtiyseniz `CFormView` (veya öğesinden devralınan bir sınıf `CFormView`), temel sınıf olarak ya da iletişim tabanlı bir uygulama oluşturduysanız, Visual C++ iletişim kutusu Düzenleyicisi açılır. Bu noktada, ilk formunuzu tasarlamak hazırsınız.  
  
### <a name="to-begin-creating-a-forms-based-mfc-executable"></a>Bir form tabanlı MFC yürütülebilir oluşturmaya başlamak için  
  
1.  İçindeki yönergeleri izleyin [MFC uygulaması oluşturma](../../mfc/reference/creating-an-mfc-application.md).  
  
2.  MFC Uygulama Sihirbazı'nda [uygulama türü](../../mfc/reference/application-type-mfc-application-wizard.md) sayfasında, **belge/görünüm mimarisi desteği** onay kutusu.  
  
3.  Seçin **tek bir belge**, **birden çok belge**, veya **birden çok üst düzey belgeleri**.  
  
    > [!NOTE]
    >  Varsayılan olarak, bir SDI, MDI veya birden çok üst düzey belge arabirimi uygulamayı seçerseniz `CView` uygulamanızın görünümünde için temel sınıf olarak ayarlanmış olan [oluşturulan sınıflar](../../mfc/reference/generated-classes-mfc-application-wizard.md) Sihirbazı sayfası. Forms tabanlı bir uygulama oluşturmak için seçmelisiniz `CFormView` uygulamanın görünümü için temel sınıf olarak. Not sihirbaz form tabanlı bir uygulama için hiçbir yazdırma desteği sağlar.  
  
4.  Sihirbazın diğer sayfalarında istediğiniz diğer proje seçenekleri ayarlayın.  
  
5.  Tıklatın **son** iskelet uygulama oluşturun.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Türetilmiş görünüm sınıfları](../../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [Belge/görünüm mimarisinin alternatifleri](../../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [Uygulama Tasarımı Seçimleri](../../mfc/application-design-choices.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)   
 [Form görünümleri](../../mfc/form-views-mfc.md)   
 [Dosya Gezgini stilinde MFC uygulaması oluşturma](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)   
 [Web Tarayıcısı Stilinde MFC Uygulaması Oluşturma](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)

