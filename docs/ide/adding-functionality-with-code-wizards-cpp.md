---
title: (C++) kod sihirbazlarıyla işlevsellik ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ebda52eaa4deab6ddf8535da9b4c5a94a2cbc77b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679411"
---
# <a name="adding-functionality-with-code-wizards-c"></a>(C++) kod sihirbazlarıyla işlevsellik ekleme
Proje oluşturulduktan sonra değiştirin veya projenin işlevsellik eklemek isteyebilirsiniz. Yeni üye işlevleri ve değişkenler ve ekleme Otomasyon yöntemleri ve özellikleri ekleme yeni sınıflar oluşturma gibi görevleri içerir. Kod sihirbazları, tüm bu işlemler yapmanıza olanak sağlamak için tasarlanmıştır.  
  
> [!NOTE]
>  Şimdi ileti işleyicileri ekleyebilir ve harita iletileri için ve MFC kullanarak sanal işlevleri geçersiz kılma [Özellikler penceresi](/visualstudio/ide/reference/properties-window).  
  
## <a name="accessing-visual-c-code-wizards"></a>Visual C++ kod sihirbazları erişme  
 Visual C++ kod sihirbazları erişebileceğiniz üç konum vardır:  
  
-   Üzerinde **proje** menüsünde **Yeni Öğe Ekle** komutu ortaya çıkarmak verir `Add New Item` iletişim kutusunda, yeni dosyalar projenize eklemenize yardımcı olur. **Sınıfı Ekle** komutunu görüntüler [sınıfı Ekle](../ide/add-class-dialog-box.md) her sınıf türleri için hangi sırayla sihirbazları Aç iletişim kutusu, projenize ekleyebilirsiniz. **Kaynak Ekle** komutunu görüntüler [kaynak Ekle](../windows/add-resource-dialog-box.md) iletişim kutusunda, içinden oluşturun veya projenize eklemek için bir kaynak seçin.  
  
     Sınıf Görünümü'nde, projenizdeki bir sınıf veya arabirim vurgulayın, **proje** menüsünü de aşağıdaki komutları görüntüler:  
  
    -   **Arabirimini uygulayan** (bir sınıftan denetimi yalnızca)  
  
    -   **İşlev Ekle**  
  
    -   **Değişken Ekle**  
  
    -   **Bağlantı Noktası Ekle** (sadece ATL sınıfı)  
  
    -   **Add yöntemi** (bir arabirimden yalnızca)  
  
    -   **Özellik Ekle** (bir arabirimden yalnızca)  
  
    -   **Olay ekleme** (bir sınıftan denetimi yalnızca)  
  
-   İçinde **Çözüm Gezgini**, herhangi bir klasörü sağ tıklatın ve tıklayarak **Ekle** kısayoldan menü, yeni veya mevcut dosyaları, daha fazla klasör, öğeleri, sınıflar, kaynaklar eklemenize olanak sağlar ve Web başvuruları Proje.  
  
-   Gelen [Sınıf Görünümü penceresi](/visualstudio/ide/viewing-the-structure-of-code)ve uygun düğümü sağ tıklayarak **Ekle** kısayol menüsünde, İşlevler, değişkenler, sınıfları, özellikleri, yöntemleri, olaylar, arabirimler, eklemenize olanak sağlar bağlantı noktaları veya başka bir kod projenize.  
  
    > [!NOTE]
    >  Visual Studio, bir arabirim bir projeye eklemek için sihirbaz sağlamaz. Arabirim bir ATL projesi veya çok ekleyebileceğiniz bir [MFC projenize ATL desteği ekleme](../mfc/reference/adding-atl-support-to-your-mfc-project.md) kullanarak basit bir nesne ekleyerek [ATL Basit Nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md). Alternatif olarak, projenin .idl dosyası açın ve yazarak arabirimi oluşturun:  
  
    ```  
    interface IMyInterface {  
    };  
  
    ```  
  
     Bkz: [arabirimi uygulama](../ide/implementing-an-interface-visual-cpp.md) ve [nesneler ekleme ve denetimleri için ATL projesinde](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) daha fazla bilgi için.  
  
    |Erişim kod Sihirbazı'ndan|Açıklama|  
    |-----------------------------|-----------------|  
    |Yeni Öğe Ekle|Yeni Öğe Ekle kod sihirbazları, kaynak dosyaları projenize ekleyin. Gerekirse, ek dizinleri yeri bulmak için proje oluşturma altyapısı bekliyor olan dosyaları içermesini oluşturulur. Kod sihirbazları Öğe Ekle simgesini kullanılabilir şunlardır:<br /><br /> -C++ kaynak dosyaları (.cpp, .h, .idl, .rc, .srf, .def, .rgs) ekleyin.<br />-Web geliştirme dosyaları (.html, .asp, .css, .xml) ekleyin.<br />-Yardımcı program ve kaynak dosyaları (.bmp, .cur, .ico, .rct, .sql, .txt) ekleyin.<br /><br /> Bu kod sihirbazları, genellikle herhangi bir bilgi sorma ancak geliştirme ağacınızı bir dosya ekleyin. Özellik penceresine dosyasında yeniden adlandırabilirsiniz.|  
    |Çözüm Gezgini|Çözüm Gezgini'nden kod sihirbazları, bir öğeyi sağ tıklattığınızda Burada, imleç odağı olmasına göre değişir. Varsa **Ekle** seçeneği, bir öğeyi sağ tıklattığınızda görünmez ardından imleci Yukarı Taşı geliştirme ağacında bir düzey ve yeniden deneyin. Kod sihirbazları her zaman ek kod geliştirme ağacında uygun bir yerden olursa olsun, imlecin bulunduğu yerleştirmeniz gerekir. Çözüm Gezgini'nden kod sihirbazları içerir:<br /><br /> -Sınıf ekleme (açılır **sınıfı Ekle** yeni kod sihirbazları içeren iletişim kutusu).<br />-Kaynak ekleme (yeni, içeri aktarma veya özel).<br />-Web referansı ekleyin.|  
    |Sınıf Görünümü|Sınıf Görünümü'ndeki kullanılabilir kod sihirbazları, bir öğeyi sağ tıklattığınızda nerede imleç odağınızı olmasına göre değişir. Varsa **Ekle** seçeneği, bir öğeyi sağ tıklattığınızda görünmez ardından imleci Yukarı Taşı sınıfı ağacında bir düzey ve yeniden deneyin. Kod sihirbazları her zaman ek kod geliştirme ağacında uygun bir yerden olursa olsun, imlecin bulunduğu yerleştirmeniz gerekir. Kod sihirbazları, sınıf görünümünden kullanılabilir şunlardır:<br /><br /> -   [Üye işlevi Ekle](../ide/adding-a-member-function-visual-cpp.md).<br />-   [Üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md).<br />-   [Sınıf ekleme](../ide/adding-a-class-visual-cpp.md).<br />-   [Arabirimini uygulayan](../ide/implement-interface-wizard.md) (bir sınıftan denetimi yalnızca)<br />-   [Bağlantı Noktası Ekle](../ide/implement-connection-point-wizard.md) (sadece ATL sınıfı)<br />-   [Add yöntemi](../ide/add-method-wizard.md) (bir arabirimden yalnızca)<br />-   [Özellik Ekle](../ide/names-add-property-wizard.md) (bir arabirimden yalnızca)<br />-   [Olay ekleme](../ide/add-event-wizard.md) (bir sınıftan denetimi yalnızca)<br /><br /> Sınıf Ekle'seçimini açılır **sınıfı Ekle** iletişim kutusunda, tüm yeni sınıf Ekle kod sihirbazları için erişmenizi sağlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir sanal işlevi geçersiz kılma](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Sınıf yapısında gezinme](../ide/navigating-the-class-structure-visual-cpp.md)   
 [Uygulama sihirbazları kullanarak masaüstü projeleri oluşturma](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Visual C++ proje türleri](../ide/visual-cpp-project-types.md)   
 [Visual C++ Projeleri için Oluşturulan Dosya Türleri](../ide/file-types-created-for-visual-cpp-projects.md)