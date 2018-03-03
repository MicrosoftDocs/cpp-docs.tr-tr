---
title: "(C++) kod sihirbazlarıyla işlevsellik ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.classes
dev_langs:
- C++
helpviewer_keywords:
- code wizards [C++]
- wizards [C++], code
- Visual C++ projects, adding functionality
- projects [C++], adding functionality
- class wizards [C++]
ms.assetid: 6afb7ef9-7056-423d-b244-91bb4236d1d7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c27aeb10a58c828b6503ce96ddaadf138c258f27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-functionality-with-code-wizards-c"></a>(C++) kod sihirbazlarıyla işlevsellik ekleme
Bir proje oluşturduğunuzda, değiştirin veya projenin işlevsellik eklemek isteyeceksiniz. Yeni üye işlevleri ve değişkenler ve ekleme Otomasyon yöntemleri ve özellikleri ekleme yeni sınıflar oluşturma gibi görevleri içerir. Kod sihirbazları bu tüm şeyler izin verecek şekilde tasarlanmıştır.  
  
> [!NOTE]
>  Şimdi ileti işleyicileri ekleyebilir ve eşleme iletileri onlara ve kullanarak MFC sanal işlevleri geçersiz kılma [Özellikler penceresini](/visualstudio/ide/reference/properties-window).  
  
## <a name="accessing-visual-c-code-wizards"></a>Visual C++ kod sihirbazları erişme  
 Visual C++ kod sihirbazları erişebileceğiniz üç konumdan vardır:  
  
-   Üzerinde **proje** menüsünde **Yeni Öğe Ekle** komutu ortaya çıkarmak verir `Add New Item` iletişim kutusunda, yeni dosyalar projenize eklemenize yardımcı olur. **Sınıfı Ekle** komutu görüntüler [sınıfı Ekle](../ide/add-class-dialog-box.md) her sınıf türleri için hangi sırayla sihirbazları Aç iletişim kutusu, projenize ekleyin. **Kaynak ekleme** komutu görüntüler [kaynak ekleme](../windows/add-resource-dialog-box.md) içinden oluşturmak veya projenize eklemek için bir kaynak seçin iletişim kutusu.  
  
     Sınıf Görünümü'nde projenize bir sınıf ya da bir arabirim vurgulayın, **proje** menüsünü de aşağıdaki komutları görüntüler:  
  
    -   **Arabirimini uygulayan** (sınıfından denetimi yalnızca)  
  
    -   **Add işlevi**  
  
    -   **Değişken Ekle**  
  
    -   **Bağlantı noktası eklemek** (yalnızca ATL sınıfı)  
  
    -   **Add yöntemi** (bir arabirimden yalnızca)  
  
    -   **Özellik ekleme** (bir arabirimden yalnızca)  
  
    -   **Olay Ekle** (sınıfından denetimi yalnızca)  
  
-   İçinde **Çözüm Gezgini**, herhangi bir klasöre sağ tıklayarak ve tıklatarak **Ekle** kısayoldan menüsü yeni veya varolan dosyaları, daha fazla klasör, öğeleri, sınıflar, kaynakları eklemenize olanak sağlar ve Web başvuruları Proje.  
  
-   Gelen [sınıfı görüntüleme penceresi](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), uygun düğümünü sağ tıklayarak ve tıklatarak **Ekle** kısayoldan menü işlevleri, değişkenleri, sınıfları, özellikleri, yöntemleri, olaylar, arabirimler, eklemenize olanak sağlar bağlantı noktaları veya başka bir kod projenize.  
  
    > [!NOTE]
    >  Visual Studio Proje için bir arabirim eklemek için bir sihirbaz sağlamaz. ATL projesinde ya da çok arabirim ekleyebileceğiniz bir [MFC projenize ATL desteği ekleme](../mfc/reference/adding-atl-support-to-your-mfc-project.md) kullanarak basit bir nesne ekleyerek [ATL Basit Nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md). Alternatif olarak, projenin .idl dosyasını açın ve yazarak arabirimi oluşturun:  
  
    ```  
    interface IMyInterface {  
    };  
  
    ```  
  
     Bkz: [arabirimi uygulama](../ide/implementing-an-interface-visual-cpp.md) ve [nesneleri ekleme ve denetimleri için ATL projesinde](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) daha fazla bilgi için.  
  
    |Erişim kodu Sihirbazı'ndan|Açıklama|  
    |-----------------------------|-----------------|  
    |Yeni Öğe Ekle|Yeni Öğe Ekle kod sihirbazları kaynak dosyalarını projenize ekleyin. Gerekirse, ek dizinler burada onları bulmak için Proje yapı altyapısı bekliyor dosyalarını içerecek şekilde oluşturulur. Kod sihirbazları Öğe Ekle simgesinden kullanılabilir şunları içerir:<br /><br /> -C++ kaynak dosyaları (.cpp, .h, .idl, .rc, .srf, .def, .rgs) ekleyin.<br />-Web geliştirme dosyaları (.html, .asp, .css, .xml) ekleyin.<br />-Yardımcı programı ve kaynak dosyaları (.bmp, .cur, .ico, .rct, .sql, .txt) ekleyin.<br /><br /> Bu kod sihirbazları genellikle herhangi bir bilgi isteme ancak geliştirme ağacına bir dosya ekleyin. Özellik penceresi dosyasında yeniden adlandırabilirsiniz.|  
    |Çözüm Gezgini|Kod sihirbazları Çözüm Gezgini'nden kullanılabilir bir öğeyi sağ tıklattığınızda burada imleç odağınız olmasına göre değişir. Varsa **Ekle** seçeneği bir öğeyi sağ tıklattığınızda görünmez sonra imlecinizi Yukarı Taşı geliştirme ağacında bir düzey ve yeniden deneyin. Kod sihirbazları her zaman ek kod geliştirme ağacında uygun yerinde bağımsız, imlecin bulunduğu yerleştirir. Kod sihirbazları Çözüm Gezgini'nden kullanılabilir şunları içerir:<br /><br /> -Add Class (açar **sınıfı Ekle** yeni kod sihirbazları içeren iletişim kutusudur).<br />-Kaynak ekleyin (yeni, içeri aktarma veya özel).<br />-Web başvuru ekleyin.|  
    |Sınıf Görünümü|Kod sihirbazları sınıfı görünümünden kullanılabilir bir öğeyi sağ tıklattığınızda burada imleç odağınız olmasına göre değişir. Varsa **Ekle** seçeneği bir öğeyi sağ tıklattığınızda görünmez sonra imlecinizi Yukarı Taşı sınıfı ağacında bir düzey ve yeniden deneyin. Kod sihirbazları her zaman ek kod geliştirme ağacında uygun yerinde bağımsız, imlecin bulunduğu yerleştirir. Kod sihirbazları sınıfı görünümünden kullanılabilir şunları içerir:<br /><br /> -   [Üye işlevi ekleme](../ide/adding-a-member-function-visual-cpp.md).<br />-   [Üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md).<br />-   [Sınıf ekleme](../ide/adding-a-class-visual-cpp.md).<br />-   [Arabirimini uygulayan](../ide/implement-interface-wizard.md) (sınıfından denetimi yalnızca)<br />-   [Bağlantı noktası eklemek](../ide/implement-connection-point-wizard.md) (yalnızca ATL sınıfı)<br />-   [Add yöntemi](../ide/add-method-wizard.md) (bir arabirimden yalnızca)<br />-   [Özellik ekleme](../ide/names-add-property-wizard.md) (bir arabirimden yalnızca)<br />-   [Olay Ekle](../ide/add-event-wizard.md) (sınıfından denetimi yalnızca)<br /><br /> Sınıf Ekle seçimi açar **sınıfı Ekle** tüm yeni sınıf Ekle kod sihirbazları için erişmenizi iletişim kutusu.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sanal işlevi geçersiz kılma](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Sınıf yapısında gezinme](../ide/navigating-the-class-structure-visual-cpp.md)   
 [Uygulama sihirbazları kullanarak masaüstü projeleri oluşturma](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Visual C++ proje türleri](../ide/visual-cpp-project-types.md)   
 [Visual C++ Projeleri için Oluşturulan Dosya Türleri](../ide/file-types-created-for-visual-cpp-projects.md)