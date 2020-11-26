---
title: Kod Sihirbazlarıyla İşlevsellik Ekleme (C++)
ms.date: 05/14/2019
helpviewer_keywords:
- code wizards [C++]
ms.assetid: 6afb7ef9-7056-423d-b244-91bb4236d1d7
ms.openlocfilehash: 651eac8c630636455dd1ffa04fdd02b71fa3cf62
ms.sourcegitcommit: 6284bca6549e7b4f199d4560c30df6c1278bd4a0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96188919"
---
# <a name="adding-functionality-with-code-wizards-c"></a>Kod Sihirbazlarıyla İşlevsellik Ekleme (C++)

Bir proje oluşturduktan sonra, bu projenin işlevini değiştirmek veya eklemek isteyeceksiniz. Bu gibi görevler yeni sınıflar oluşturmayı, yeni üye işlevleri ve değişkenleri eklemeyi ve Otomasyon yöntemleri ve özellikleri eklemeyi içerir. Kod sihirbazları, her şeyi yapmanızı sağlayacak şekilde tasarlanmıştır.

> [!NOTE]
> Aşağıdaki nadiren kullanılan kod sihirbazları, Visual Studio 2019 ' de kaldırılır. ATL ve MFC için genel destek, bu sihirbazların kaldırılmasından etkilenmez. Bu teknolojilerin örnek kodu Microsoft Docs'ta ve VCSamples GitHub deposunda arşivlendi.

- ATL COM+ 1.0 Bileşeni Sihirbazı
- ATL Active Server Pages Bileşen Sihirbazı
- ATL OLE DB Sağlayıcısı Sihirbazı
- ATL Özellik Sayfası Sihirbazı
- ATL OLE DB Tüketicisi Sihirbazı
- MFC ODBC Tüketicisi
- ActiveX denetiminden MFC sınıfı
- Tür lib 'den MFC sınıfı.

> [!NOTE]
> İleti işleyicileri ekleyebilir ve bunları bunlara eşleyebilirsiniz ve MFC [sınıfı Sihirbazı 'nı](../mfc/reference/mfc-class-wizard.md)kullanarak MFC sanal işlevlerini geçersiz kılabilirsiniz.

## <a name="accessing-c-code-wizards"></a>C++ kod sihirbazlarına erişme

C++ kod sihirbazlarına erişebileceğiniz üç konum vardır:

- **Proje** menüsünde **Yeni öğe Ekle** komutu, `Add New Item` projenize yeni dosyalar eklemenize yardımcı olan iletişim kutusunu taşımanıza olanak sağlar. **Add Class** komutu, projenize ekleyebileceğiniz her bir sınıf türü için açma sihirbazları ' nda [Sınıf Ekle](./adding-a-class-visual-cpp.md#add-class-dialog-box) iletişim kutusunu görüntüler. MFC sınıfları için [MFC sınıf Sihirbazı](../mfc/reference/mfc-class-wizard.md)' nı kullanın. **Kaynak** Ekle komutu, projenize eklemek üzere bir kaynak oluşturabileceğiniz veya seçebileceğiniz [Kaynak Ekle](../windows/how-to-create-a-resource-script-file.md) iletişim kutusunu görüntüler.

   Sınıf Görünümü projedeki bir sınıfı veya arabirimi vurguladığınızda, **Proje** menüsü de aşağıdaki komutları görüntüler:

  - **Arabirim Uygula** (yalnızca bir denetim sınıfından)

  - **Işlev Ekle**

  - **Değişken Ekle**

  - **Bağlantı noktası Ekle** (yalnızca atl sınıfı)

  - **Add yöntemi** (yalnızca bir arabirimden)

  - **Özellik Ekle** (yalnızca bir arabirimden)

  - **Olay Ekle** (yalnızca bir denetim sınıfından)

- **Çözüm Gezgini**' de, herhangi bir klasöre sağ tıklayıp kısayol menüsünden **Ekle** ' ye tıklamak, projeye yeni veya mevcut dosyalar, daha fazla klasör, öğe, sınıf, kaynak ve Web başvuruları eklemenize olanak sağlar.

- [Sınıf Görünümü penceresinden](/visualstudio/ide/viewing-the-structure-of-code), uygun düğüme sağ tıklayıp kısayol menüsünden **Ekle** ' ye tıklamak, projenize işlevler, değişkenler, sınıflar, özellikler, Yöntemler, olaylar, arabirimler, bağlantı noktaları veya başka kodlar eklemenize olanak sağlar.

   > [!NOTE]
   > Visual Studio, bir projeye arabirim eklemek için bir sihirbaz sağlamaz. ATL [basit nesne Sihirbazı 'nı](../atl/reference/atl-simple-object-wizard.md)kullanarak basit bir nesne ekleyerek bir ATL projesine veya bir ATL desteği eklemek Için [MFC projenize](../mfc/reference/adding-atl-support-to-your-mfc-project.md) bir arabirim ekleyebilirsiniz. Alternatif olarak, projenin. IDL dosyasını açın ve şunu yazarak arabirimi oluşturun:

    ```IDL
    interface IMyInterface {
    };
    ```

   Daha fazla bilgi için bkz. [arabirim uygulama](../ide/implementing-an-interface-visual-cpp.md) ve [ATL projesine nesne ve denetim ekleme](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) .

   |Erişim kodu Sihirbazı|Açıklama|
   |-----------------------------|-----------------|
   |Yeni Öğe Ekle|Yeni öğe kodu ekle sihirbazları projenize kaynak dosyaları ekler. Gerekirse, proje derleme altyapısının bunları bulmayı beklediği dosyaları içerecek şekilde ek dizinler oluşturulur. Öğe Ekle simgesinde bulunan kod sihirbazları şunları içerir:<br /><br />-C++ kaynak dosyaları (. cpp,. h,. IDL,. RC,. srf,. def,. RGS) ekleyin.<br />-Web geliştirme dosyaları ekleyin (. html,. asp,. css,. xml).<br />-Yardımcı program ve kaynak dosyaları (. bmp,. cur,. ico,. rct,. SQL,. txt) ekleyin.<br /><br />Bu kod sihirbazları genellikle sizden herhangi bir bilgi istemez, ancak geliştirme ağacınızı bir dosya eklemenize izin vermez. Dosyayı özellik penceresinde yeniden adlandırabilirsiniz.|
   |Çözüm Gezgini|Çözüm Gezgini bulunan kod sihirbazları, bir öğeye sağ tıkladığınızda imlecinizin odaklandığına bağlıdır. Bir öğeye sağ tıkladığınızda **Ekle** seçeneği görünmezse, imlecinizi geliştirme ağacında bir düzey yukarı taşıyın ve yeniden deneyin. Kod sihirbazları, imlecinizin nerede olduğuna bakılmaksızın, her zaman ek kodu geliştirme ağacında uygun yere yerleştirir. Çözüm Gezgini bulunan kod sihirbazları şunları içerir:<br /><br />-Sınıf Ekle (yeni kod sihirbazları içeren **Sınıf Ekle** iletişim kutusunu açar).<br />-Kaynak Ekle (yeni, Içeri Aktar veya özel).<br />-Web başvurusu Ekle.|
   |Sınıf Görünümü|Sınıf Görünümü bulunan kod sihirbazları, bir öğeye sağ tıkladığınızda imlecinizin odaklandığına bağlıdır. Bir öğeye sağ tıkladığınızda **Ekle** seçeneği görünmezse, imleci sınıf ağacında bir düzey yukarı taşıyın ve yeniden deneyin. Kod sihirbazları, imlecinizin nerede olduğuna bakılmaksızın, her zaman ek kodu geliştirme ağacında uygun yere yerleştirir. Sınıf Görünümü bulunan kod sihirbazları şunları içerir:<br /><br />- [Üye Işlevi ekleyin](../ide/adding-a-member-function-visual-cpp.md).<br />- [Üye değişkeni ekleyin](../ide/adding-a-member-variable-visual-cpp.md).<br />- [Sınıf ekleyin](../ide/adding-a-class-visual-cpp.md).<br />- [Arabirim Uygula](./implementing-an-interface-visual-cpp.md#implement-interface-wizard) (yalnızca bir denetim sınıfından)<br />- [Bağlantı noktası Ekle](./implementing-a-connection-point-visual-cpp.md#implement-connection-point-wizard) (yalnızca atl sınıfı)<br />- [Add yöntemi](./adding-a-method-visual-cpp.md#add-method-wizard) (yalnızca bir arabirimden)<br />- [Özellik Ekle](./adding-a-property-visual-cpp.md#names-add-property-wizard) (yalnızca bir arabirimden)<br />- [Olay Ekle](./adding-an-event-visual-cpp.md#add-event-wizard) (yalnızca bir denetim sınıfından)<br /><br />Sınıf Ekle seçimi, tüm yeni sınıf kodu ekleme sihirbazlarına erişmenizi sağlayan **Sınıf Ekle** iletişim kutusunu açar.|

## <a name="see-also"></a>Ayrıca bkz.

[Sanal Işlevi geçersiz kılma](../ide/overriding-a-virtual-function-visual-cpp.md)<br>
[Visual Studio 'da C++ kod tabanınız üzerinde gezinme](../ide/navigate-code-cpp.md)<br>
[Visual Studio 'da C++ proje türleri](../build/reference/visual-cpp-project-types.md)<br>
[Visual Studio C++ projeleri için oluşturulan dosya türleri](../build/reference/file-types-created-for-visual-cpp-projects.md)
