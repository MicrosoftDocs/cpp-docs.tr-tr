---
title: (C++) kod sihirbazlarıyla işlevsellik ekleme
ms.date: 05/14/2019
helpviewer_keywords:
- code wizards [C++]
ms.assetid: 6afb7ef9-7056-423d-b244-91bb4236d1d7
ms.openlocfilehash: efced3be3a0bcc7efe16aef1061c4cd9ec1ed21c
ms.sourcegitcommit: 65ed563a8a1d4d90f872a2a6edcb086f84ec9f77
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66741633"
---
# <a name="adding-functionality-with-code-wizards-c"></a>(C++) kod sihirbazlarıyla işlevsellik ekleme

Proje oluşturulduktan sonra değiştirin veya projenin işlevsellik eklemek isteyebilirsiniz. Yeni üye işlevleri ve değişkenler ve ekleme Otomasyon yöntemleri ve özellikleri ekleme yeni sınıflar oluşturma gibi görevleri içerir. Kod sihirbazları, tüm bu işlemler yapmanıza olanak sağlamak için tasarlanmıştır.

> [!NOTE]
> Aşağıdaki nadiren kullanılan kod sihirbazları Visual Studio 2019 kaldırılır. ATL ve MFC genel desteği, bu sihirbazlar kaldırılmasını tarafından etkilenmez. Bu teknolojiler için örnek kod Microsoft Docs ve VCSamples GitHub deposunu arşivlenir.

- ATL COM+ 1.0 Bileşeni Sihirbazı
- ATL Active Server Pages bileşeni Sihirbazı
- ATL OLE DB sağlayıcısı Sihirbazı
- ATL Özellik Sayfası Sihirbazı
- ATL OLE DB Tüketicisi Sihirbazı
- MFC ODBC Tüketicisi
- ActiveX denetiminden MFC sınıfı
- Tür kitaplığı kitaplığından MFC sınıfı.


> [!NOTE]
>  Şimdi ileti işleyicileri ekleyebilir ve harita iletileri için ve MFC kullanarak sanal işlevleri geçersiz kılma [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

## <a name="accessing-c-code-wizards"></a>Erişim C++ kod sihirbazları

Erişebileceğiniz üç konum vardır C++ kod sihirbazları:

- Üzerinde **proje** menüsünde **Yeni Öğe Ekle** komutu ortaya çıkarmak verir `Add New Item` iletişim kutusunda, yeni dosyalar projenize eklemenize yardımcı olur. **Sınıfı Ekle** komutunu görüntüler [sınıfı Ekle](../ide/add-class-dialog-box.md) her sınıf türleri için hangi sırayla sihirbazları Aç iletişim kutusu, projenize ekleyebilirsiniz. **Kaynak Ekle** komutunu görüntüler [kaynak Ekle](../windows/add-resource-dialog-box.md) iletişim kutusunda, içinden oluşturun veya projenize eklemek için bir kaynak seçin.

   Sınıf Görünümü'nde, projenizdeki bir sınıf veya arabirim vurgulayın, **proje** menüsünü de aşağıdaki komutları görüntüler:

   - **Arabirimini uygulayan** (bir sınıftan denetimi yalnızca)

   - **İşlev Ekle**

   - **Değişken Ekle**

   - **Bağlantı Noktası Ekle** (sadece ATL sınıfı)

   - **Add yöntemi** (bir arabirimden yalnızca)

   - **Özellik Ekle** (bir arabirimden yalnızca)

   - **Olay ekleme** (bir sınıftan denetimi yalnızca)

- İçinde **Çözüm Gezgini**, herhangi bir klasörü sağ tıklatın ve tıklayarak **Ekle** kısayoldan menü, yeni veya mevcut dosyaları, daha fazla klasör, öğeleri, sınıflar, kaynaklar eklemenize olanak sağlar ve Web başvuruları Proje.

- Gelen [Sınıf Görünümü penceresi](/visualstudio/ide/viewing-the-structure-of-code)ve uygun düğümü sağ tıklayarak **Ekle** kısayol menüsünde, İşlevler, değişkenler, sınıfları, özellikleri, yöntemleri, olaylar, arabirimler, eklemenize olanak sağlar bağlantı noktaları veya başka bir kod projenize.

   > [!NOTE]
   > Visual Studio, bir arabirim bir projeye eklemek için sihirbaz sağlamaz. Arabirim bir ATL projesi veya çok ekleyebileceğiniz bir [MFC projenize ATL desteği ekleme](../mfc/reference/adding-atl-support-to-your-mfc-project.md) kullanarak basit bir nesne ekleyerek [ATL Basit Nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md). Alternatif olarak, projenin .idl dosyası açın ve yazarak arabirimi oluşturun:

    ```IDL
    interface IMyInterface {
    };
    ```

   Bkz: [arabirimi uygulama](../ide/implementing-an-interface-visual-cpp.md) ve [nesneler ekleme ve denetimleri için ATL projesinde](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) daha fazla bilgi için.

   |Erişim kod Sihirbazı'ndan|Açıklama|
   |-----------------------------|-----------------|
   |Yeni Öğe Ekle|Yeni Öğe Ekle kod sihirbazları, kaynak dosyaları projenize ekleyin. Gerekirse, ek dizinleri yeri bulmak için proje oluşturma altyapısı bekliyor olan dosyaları içermesini oluşturulur. Kod sihirbazları Öğe Ekle simgesini kullanılabilir şunlardır:<br /><br />-C++ kaynak dosyaları (.cpp, .h, .idl, .rc, .srf, .def, .rgs) ekleyin.<br />-Web geliştirme dosyaları (.html, .asp, .css, .xml) ekleyin.<br />-Yardımcı program ve kaynak dosyaları (.bmp, .cur, .ico, .rct, .sql, .txt) ekleyin.<br /><br />Bu kod sihirbazları, genellikle herhangi bir bilgi sorma ancak geliştirme ağacınızı bir dosya ekleyin. Özellik penceresine dosyasında yeniden adlandırabilirsiniz.|
   |Çözüm Gezgini|Çözüm Gezgini'nden kod sihirbazları, bir öğeyi sağ tıklattığınızda Burada, imleç odağı olmasına göre değişir. Varsa **Ekle** seçeneği, bir öğeyi sağ tıklattığınızda görünmez ardından imleci Yukarı Taşı geliştirme ağacında bir düzey ve yeniden deneyin. Kod sihirbazları her zaman ek kod geliştirme ağacında uygun bir yerden olursa olsun, imlecin bulunduğu yerleştirmeniz gerekir. Çözüm Gezgini'nden kod sihirbazları içerir:<br /><br />-Sınıf ekleme (açılır **sınıfı Ekle** yeni kod sihirbazları içeren iletişim kutusu).<br />-Kaynak ekleme (yeni, içeri aktarma veya özel).<br />-Web referansı ekleyin.|
   |Sınıf Görünümü|Sınıf Görünümü'ndeki kullanılabilir kod sihirbazları, bir öğeyi sağ tıklattığınızda nerede imleç odağınızı olmasına göre değişir. Varsa **Ekle** seçeneği, bir öğeyi sağ tıklattığınızda görünmez ardından imleci Yukarı Taşı sınıfı ağacında bir düzey ve yeniden deneyin. Kod sihirbazları her zaman ek kod geliştirme ağacında uygun bir yerden olursa olsun, imlecin bulunduğu yerleştirmeniz gerekir. Kod sihirbazları, sınıf görünümünden kullanılabilir şunlardır:<br /><br />- [Üye işlevi Ekle](../ide/adding-a-member-function-visual-cpp.md).<br />- [Üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md).<br />- [Sınıf ekleme](../ide/adding-a-class-visual-cpp.md).<br />- [Arabirimini uygulayan](../ide/implement-interface-wizard.md) (bir sınıftan denetimi yalnızca)<br />- [Bağlantı Noktası Ekle](../ide/implement-connection-point-wizard.md) (sadece ATL sınıfı)<br />- [Add yöntemi](../ide/add-method-wizard.md) (bir arabirimden yalnızca)<br />- [Özellik Ekle](../ide/names-add-property-wizard.md) (bir arabirimden yalnızca)<br />- [Olay ekleme](../ide/add-event-wizard.md) (bir sınıftan denetimi yalnızca)<br /><br />Sınıf Ekle'seçimini açılır **sınıfı Ekle** iletişim kutusunda, tüm yeni sınıf Ekle kod sihirbazları için erişmenizi sağlar.|

## <a name="see-also"></a>Ayrıca bkz.

[Bir sanal işlevi geçersiz kılma](../ide/overriding-a-virtual-function-visual-cpp.md)<br>
[Git, C++ Visual Studio'da temel kod](../ide/navigate-code-cpp.md)<br>
[C++Visual Studio Proje türleri](../build/reference/visual-cpp-project-types.md)<br>
[Oluşturulan türleri için Visual Studio dosya C++ projeleri](../build/reference/file-types-created-for-visual-cpp-projects.md)
