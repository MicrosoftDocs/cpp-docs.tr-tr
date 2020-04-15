---
title: Kod Sihirbazlarıyla İşlevsellik Ekleme (C++)
ms.date: 05/14/2019
helpviewer_keywords:
- code wizards [C++]
ms.assetid: 6afb7ef9-7056-423d-b244-91bb4236d1d7
ms.openlocfilehash: ab0bf802221bcf3f93469f27f29f86c95877a407
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365340"
---
# <a name="adding-functionality-with-code-wizards-c"></a>Kod Sihirbazlarıyla İşlevsellik Ekleme (C++)

Bir proje oluşturduktan sonra, bu projenin işlevselliğini değiştirmek veya eklemek isteyeceksiniz. Bu tür görevler arasında yeni sınıflar oluşturma, yeni üye işlevler ve değişkenler ekleme ve Otomasyon yöntemleri ve özellikleri ekleme yer alır. Kod sihirbazları tüm bunları yapmanıza izin vermek için tasarlanmıştır.

> [!NOTE]
> Visual Studio 2019'da nadiren kullanılan kod sihirbazları kaldırılır. ATL ve MFC için genel destek bu sihirbazların kaldırılmasından etkilenmez. Bu teknolojilerin örnek kodu Microsoft Docs'ta ve VCSamples GitHub deposunda arşivlendi.

- ATL COM+ 1.0 Bileşeni Sihirbazı
- ATL Etkin Sunucu Sayfaları Bileşen Sihirbazı
- ATL OLE DB Sağlayıcısı Sihirbazı
- ATL Özellik Sayfası Sihirbazı
- ATL OLE DB Tüketicisi Sihirbazı
- MFC ODBC Tüketici
- ActiveX kontrolünden MFC sınıfı
- Tip Lib'den MFC sınıfı.

> [!NOTE]
> İleti işleyicileri ve eşmesajları ekleyebilirsiniz ve [MFC Sınıf Sihirbazı](../mfc/reference/mfc-class-wizard.md)kullanarak MFC sanal işlevleri geçersiz kılar.

## <a name="accessing-c-code-wizards"></a>C++ Kod Sihirbazlarına Erişim

C++ kod sihirbazlarına erişebileceğiniz üç konum vardır:

- **Proje** menüsünde **Yeni Öğe Ekle** komutu, projenize yeni dosyalar eklemenize yardımcı olan `Add New Item` iletişim kutusunu açmanızı sağlar. **Sınıf Ekle** komutu, projenize ekleyebileceğiniz sınıf türlerinin her biri için sihirbazları açan [Sınıf Ekle](../ide/add-class-dialog-box.md) iletişim kutusunu görüntüler. MFC sınıfları için [MFC Sınıf Sihirbazı'nı](../mfc/reference/mfc-class-wizard.md)kullanın. **Kaynak Ekle** komutu, projenize ekleyecek bir kaynak oluşturabileceğiniz veya seçebileceğiniz [Kaynak Ekle](../windows/add-resource-dialog-box.md) iletişim kutusunu görüntüler.

   Projenizde sınıf görünümünde bir sınıfı veya arabirimi vurgularsanız, **Proje** menüsü de aşağıdaki komutları görüntüler:

  - **Arabirimi Uygula** (yalnızca bir denetim sınıfından)

  - **Fonksiyon Ekle**

  - **Değişken Ekle**

  - **Bağlantı Noktası Ekle** (Yalnızca ATL sınıfı)

  - **Yöntem Ekle** (yalnızca bir arabirimden)

  - **Özellik Ekle** (yalnızca bir arabirimden)

  - **Olay Ekle** (yalnızca bir denetim sınıfından)

- **Çözüm Gezgini'nde,** herhangi bir klasörü sağ tıklatmak ve kısayol menüsünden **Ekle'yi** tıklatmak, projeye yeni veya varolan dosyalar, daha fazla klasör, öğe, sınıf, kaynak ve Web referansları eklemenize olanak tanır.

- Sınıf [Görünümü penceresinden,](/visualstudio/ide/viewing-the-structure-of-code)uygun düğüme sağ tıklayarak kısayol menüsünden **Ekle'yi** tıklatarak projenize işlevler, değişkenler, sınıflar, özellikler, yöntemler, etkinlikler, arabirimler, bağlantı noktaları veya başka bir kod eklemenize olanak tanır.

   > [!NOTE]
   > Visual Studio, projeye arabirim eklemek için sihirbaz sağlamaz. ATL projesine veya [MFC Projenize ATL Desteği eklemeye,](../mfc/reference/adding-atl-support-to-your-mfc-project.md) [ATL Basit Nesne Sihirbazı'nı](../atl/reference/atl-simple-object-wizard.md)kullanarak basit bir nesne ekleyerek arabirim ekleyebilirsiniz. Alternatif olarak, projenin .idl dosyasını açın ve aşağıdakileri yazarak arabirimi oluşturun:

    ```IDL
    interface IMyInterface {
    };
    ```

   Bkz. Daha fazla bilgi için [Arabirim Uygulama](../ide/implementing-an-interface-visual-cpp.md) ve [ATL Projesine Nesne ve Denetim Ekleme.](../atl/reference/adding-objects-and-controls-to-an-atl-project.md)

   |Erişim kodu sihirbazı|Açıklama|
   |-----------------------------|-----------------|
   |Yeni Öğe Ekle|Yeni Öğe Ekle kod sihirbazları projenize kaynak dosyaları ekler. Gerekirse, proje oluşturma altyapısının bulmayı beklediği dosyaları içerecek şekilde ek dizinler oluşturulur. Öğe Ekle simgesinden kullanılabilen kod sihirbazları şunlardır:<br /><br />- C++ kaynak dosyalarını ekleyin (.cpp, .h, .idl, .rc, .srf, .def, .rgs).<br />- Web geliştirme dosyaları ekleyin (.html, .asp, .css, .xml).<br />- Yardımcı program ve kaynak dosyaları ekleyin (.bmp, .cur, .ico, .rct, .sql, .txt).<br /><br />Bu kod sihirbazları genellikle sizden herhangi bir bilgi istemez, ancak geliştirme ağacınıza bir dosya ekler. Özellik penceresinde dosyayı yeniden adlandırabilirsiniz.|
   |Çözüm Gezgini|Çözüm Gezgini'nden kullanılabilen kod sihirbazları, bir öğeyi sağ tıklattığınızda imleç odağınızın nerede olduğuna bağlıdır. Bir öğeyi sağ tıklattığınızda **Ekle** seçeneği görünmüyorsa, imlecinizi geliştirme ağacında bir düzeye taşıyın ve yeniden deneyin. Kod sihirbazları imleciniz nerede olursa olsun, ek kodu her zaman geliştirme ağacında uygun yere yerleşir. Solution Explorer'dan edinilebilen kod sihirbazları şunlardır:<br /><br />- Sınıf Ekle (Yeni kod sihirbazlarını içeren **Sınıf Ekle** iletişim kutusunu açar).<br />- Kaynak Ekleyin (Yeni, İçe Aktarma veya Özel).<br />- Web Başvurusu ekleyin.|
   |Sınıf Görünümü|Sınıf Görünümü'nde kullanılabilen kod sihirbazları, bir öğeyi sağ tıklattığınızda imleç odağınızın nerede olduğuna bağlıdır. Bir öğeyi sağ tıklattığınızda **Ekle** seçeneği görünmüyorsa, imlecinizi sınıf ağacında bir düzeye taşıyın ve yeniden deneyin. Kod sihirbazları imleciniz nerede olursa olsun, ek kodu her zaman geliştirme ağacında uygun yere yerleşir. Sınıf Görünümü'nden kullanılabilen kod sihirbazları şunlardır:<br /><br />- [Üye Fonksiyonu Ekle](../ide/adding-a-member-function-visual-cpp.md).<br />- [Üye Değişkeni Ekle](../ide/adding-a-member-variable-visual-cpp.md).<br />- [Sınıf Ekle](../ide/adding-a-class-visual-cpp.md).<br />- [Arabirimi Uygula](../ide/implement-interface-wizard.md) (yalnızca bir denetim sınıfından)<br />- [Bağlantı Noktası Ekle](../ide/implement-connection-point-wizard.md) (Yalnızca ATL sınıfı)<br />- [Yöntem Ekle](../ide/add-method-wizard.md) (yalnızca bir arabirimden)<br />- [Özellik Ekle](../ide/names-add-property-wizard.md) (yalnızca bir arabirimden)<br />- [Olay Ekle](../ide/add-event-wizard.md) (yalnızca bir denetim sınıfından)<br /><br />Sınıf Ekle seçkisi, tüm yeni Sınıf Ekle kod sihirbazlarına erişmenizi sağlayan **Sınıf Ekle** iletişim kutusunu açar.|

## <a name="see-also"></a>Ayrıca bkz.

[Sanal İşlev Geçersiz Kılma](../ide/overriding-a-virtual-function-visual-cpp.md)<br>
[Visual Studio'da C++ kod tabanınızda gezinme](../ide/navigate-code-cpp.md)<br>
[Visual Studio'da C++ proje türleri](../build/reference/visual-cpp-project-types.md)<br>
[Visual Studio C++ projeleri için Oluşturulan Dosya Türleri](../build/reference/file-types-created-for-visual-cpp-projects.md)
