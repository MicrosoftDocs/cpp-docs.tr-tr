---
title: Kod Sihirbazlarıyla Işlevsellik ekleme (C++)
ms.date: 05/14/2019
helpviewer_keywords:
- code wizards [C++]
ms.assetid: 6afb7ef9-7056-423d-b244-91bb4236d1d7
ms.openlocfilehash: 360f206ff4dae0b49650e131ccd86ecf9a0ed87d
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907483"
---
# <a name="adding-functionality-with-code-wizards-c"></a>Kod Sihirbazlarıyla Işlevsellik ekleme (C++)

Bir proje oluşturduktan sonra, bu projenin işlevini değiştirmek veya eklemek isteyeceksiniz. Bu gibi görevler yeni sınıflar oluşturmayı, yeni üye işlevleri ve değişkenleri eklemeyi ve Otomasyon yöntemleri ve özellikleri eklemeyi içerir. Kod sihirbazları, her şeyi yapmanızı sağlayacak şekilde tasarlanmıştır.

> [!NOTE]
> Aşağıdaki nadiren kullanılan kod sihirbazları, Visual Studio 2019 ' de kaldırılır. ATL ve MFC için genel destek, bu sihirbazların kaldırılmasından etkilenmez. Bu teknolojiler için örnek kod Microsoft Docs ve VCSamples GitHub deposunda arşivlenir.

- ATL COM+ 1.0 Bileşeni Sihirbazı
- ATL Active Server Pages Bileşen Sihirbazı
- ATL OLE DB sağlayıcı Sihirbazı
- ATL Özellik Sayfası Sihirbazı
- ATL OLE DB Tüketici Sihirbazı
- MFC ODBC Tüketicisi
- ActiveX denetiminden MFC sınıfı
- Tür lib 'den MFC sınıfı.


> [!NOTE]
>  İleti işleyicileri ekleyebilir ve bunları bunlara eşleyebilirsiniz ve MFC [sınıfı Sihirbazı 'nı](../mfc/reference/mfc-class-wizard.md)kullanarak MFC sanal işlevlerini geçersiz kılabilirsiniz.

## <a name="accessing-c-code-wizards"></a>Kod C++ sihirbazlarına erişme

Kod sihirbazlarına erişebileceğiniz C++ üç konum vardır:

- **Proje** menüsünde **Yeni öğe Ekle** komutu, projenize yeni dosyalar eklemenize yardımcı olan `Add New Item` iletişim kutusunu taşımanıza olanak sağlar. **Add Class** komutu, projenize ekleyebileceğiniz her bir sınıf türü için açma sihirbazları ' nda [Sınıf Ekle](../ide/add-class-dialog-box.md) iletişim kutusunu görüntüler. MFC sınıfları için [MFC sınıf Sihirbazı](../mfc/reference/mfc-class-wizard.md)' nı kullanın. **Kaynak** Ekle komutu, projenize eklemek üzere bir kaynak oluşturabileceğiniz veya seçebileceğiniz [Kaynak Ekle](../windows/add-resource-dialog-box.md) iletişim kutusunu görüntüler.

   Sınıf Görünümü projedeki bir sınıfı veya arabirimi vurguladığınızda, **Proje** menüsü de aşağıdaki komutları görüntüler:

   - **Arabirimi Uygula** (yalnızca bir denetim sınıfından)

   - **Işlev Ekle**

   - **Değişken Ekle**

   - **Bağlantı noktası Ekle** (Yalnızca ATL sınıfı)

   - **Add yöntemi** (yalnızca bir arabirimden)

   - **Özellik Ekle** (yalnızca bir arabirimden)

   - **Olay Ekle** (yalnızca bir denetim sınıfından)

- **Çözüm Gezgini**' de, herhangi bir klasöre sağ tıklayıp kısayol menüsünden **Ekle** ' ye tıklamak, projeye yeni veya mevcut dosyalar, daha fazla klasör, öğe, sınıf, kaynak ve Web başvuruları eklemenize olanak sağlar.

- [Sınıf Görünümü penceresinden](/visualstudio/ide/viewing-the-structure-of-code), uygun düğüme sağ tıklayıp kısayol menüsünden **Ekle** ' ye tıklamak için işlevler, değişkenler, sınıflar, özellikler, Yöntemler, olaylar, arabirimler, bağlantı noktaları veya başka kodlar ekleyebilirsiniz Proje.

   > [!NOTE]
   > Visual Studio, bir projeye arabirim eklemek için bir sihirbaz sağlamaz. ATL [basit nesne Sihirbazı 'nı](../atl/reference/atl-simple-object-wizard.md)kullanarak basit bir nesne ekleyerek bir ATL projesine veya bir ATL desteği eklemek Için [MFC projenize](../mfc/reference/adding-atl-support-to-your-mfc-project.md) bir arabirim ekleyebilirsiniz. Alternatif olarak, projenin. IDL dosyasını açın ve şunu yazarak arabirimi oluşturun:

    ```IDL
    interface IMyInterface {
    };
    ```

   Daha fazla bilgi için bkz. [arabirim uygulama](../ide/implementing-an-interface-visual-cpp.md) ve [ATL projesine nesne ve denetim ekleme](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) .

   |Erişim kodu Sihirbazı|Açıklama|
   |-----------------------------|-----------------|
   |Yeni Öğe Ekle|Yeni öğe kodu ekle sihirbazları projenize kaynak dosyaları ekler. Gerekirse, proje derleme altyapısının bunları bulmayı beklediği dosyaları içerecek şekilde ek dizinler oluşturulur. Öğe Ekle simgesinde bulunan kod sihirbazları şunları içerir:<br /><br />-Kaynak C++ dosyaları (. cpp,. h,. IDL,. RC,. srf,. def,. RGS) ekleyin.<br />-Web geliştirme dosyaları ekleyin (. html,. asp,. css,. xml).<br />-Yardımcı program ve kaynak dosyaları (. bmp,. cur,. ico,. rct,. SQL,. txt) ekleyin.<br /><br />Bu kod sihirbazları genellikle sizden herhangi bir bilgi istemez, ancak geliştirme ağacınızı bir dosya eklemenize izin vermez. Dosyayı özellik penceresinde yeniden adlandırabilirsiniz.|
   |Çözüm Gezgini|Çözüm Gezgini bulunan kod sihirbazları, bir öğeye sağ tıkladığınızda imlecinizin odaklandığına bağlıdır. Bir öğeye sağ tıkladığınızda **Ekle** seçeneği görünmezse, imlecinizi geliştirme ağacında bir düzey yukarı taşıyın ve yeniden deneyin. Kod sihirbazları, imlecinizin nerede olduğuna bakılmaksızın, her zaman ek kodu geliştirme ağacında uygun yere yerleştirir. Çözüm Gezgini bulunan kod sihirbazları şunları içerir:<br /><br />-Sınıf Ekle (yeni kod sihirbazları içeren **Sınıf Ekle** iletişim kutusunu açar).<br />-Kaynak Ekle (yeni, Içeri Aktar veya özel).<br />-Web başvurusu Ekle.|
   |Sınıf Görünümü|Sınıf Görünümü bulunan kod sihirbazları, bir öğeye sağ tıkladığınızda imlecinizin odaklandığına bağlıdır. Bir öğeye sağ tıkladığınızda **Ekle** seçeneği görünmezse, imleci sınıf ağacında bir düzey yukarı taşıyın ve yeniden deneyin. Kod sihirbazları, imlecinizin nerede olduğuna bakılmaksızın, her zaman ek kodu geliştirme ağacında uygun yere yerleştirir. Sınıf Görünümü bulunan kod sihirbazları şunları içerir:<br /><br />- [Üye Işlevi ekleyin](../ide/adding-a-member-function-visual-cpp.md).<br />- [Üye değişkeni ekleyin](../ide/adding-a-member-variable-visual-cpp.md).<br />- [Sınıf ekleyin](../ide/adding-a-class-visual-cpp.md).<br />- [Arabirimi Uygula](../ide/implement-interface-wizard.md) (yalnızca bir denetim sınıfından)<br />- [Bağlantı noktası Ekle](../ide/implement-connection-point-wizard.md) (Yalnızca ATL sınıfı)<br />- [Add yöntemi](../ide/add-method-wizard.md) (yalnızca bir arabirimden)<br />- [Özellik Ekle](../ide/names-add-property-wizard.md) (yalnızca bir arabirimden)<br />- [Olay Ekle](../ide/add-event-wizard.md) (yalnızca bir denetim sınıfından)<br /><br />Sınıf Ekle seçimi, tüm yeni sınıf kodu ekleme sihirbazlarına erişmenizi sağlayan **Sınıf Ekle** iletişim kutusunu açar.|

## <a name="see-also"></a>Ayrıca bkz.

[Sanal Işlevi geçersiz kılma](../ide/overriding-a-virtual-function-visual-cpp.md)<br>
[Visual Studio C++ 'da kod tabanınız üzerinde gezinme](../ide/navigate-code-cpp.md)<br>
[C++Visual Studio 'da proje türleri](../build/reference/visual-cpp-project-types.md)<br>
[Visual Studio C++ projeleri için oluşturulan dosya türleri](../build/reference/file-types-created-for-visual-cpp-projects.md)
