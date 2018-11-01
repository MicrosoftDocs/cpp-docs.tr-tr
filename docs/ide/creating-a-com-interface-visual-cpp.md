---
title: COM Arabirimi Oluşturma (Visual C++)
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.com.creating.interfaces
helpviewer_keywords:
- COM interfaces, creating
ms.assetid: 1be84d3c-6886-4d1e-8493-56c4d38a96d4
ms.openlocfilehash: 53379a7937bd96b50de61652f67bd0dcb34a6730
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569747"
---
# <a name="creating-a-com-interface-visual-c"></a>COM Arabirimi Oluşturma (Visual C++)

Visual C++ sihirbazları ve şablonlarını tanımlama COM arabirimlerine ve görüntüleme Otomasyon sınıfları ve COM nesneleri için kullanan projeleri oluşturmak için sağlar.

Bu sihirbazlar, aşağıdaki üç yaygın görevleri gerçekleştirmek için kullanabilirsiniz:

- [MFC Projenize ATL Desteği Ekleme](../mfc/reference/adding-atl-support-to-your-mfc-project.md)

   Kullanarak bir MFC projesi oluşturduktan sonra bir MFC uygulaması için ATL desteği Ekle [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md) ve ardından çalıştırarak **MFC ATL desteği Ekle** kod Sihirbazı. Bu destek, eklenen bir MFC yürütülebilir veya DLL projesi için yalnızca basit COM nesneleri için geçerlidir. Bu ATL nesneleri birden çok arabirimlere sahip olabilir.

- [MFC ActiveX Denetimi Oluşturma](../mfc/reference/creating-an-mfc-activex-control.md)

   Açık [MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md) ActiveX denetimi bir dispinterface ve sırasıyla .idl dosyasının ve denetim sınıfı içinde tanımlanan bir olay eşlemesi oluşturun.

- [ATL Denetimi Ekleme](../atl/reference/adding-an-atl-control.md)

   Bir birleşimini kullanmak [ATL projesi Sihirbazı](../atl/reference/atl-project-wizard.md) ve [ATL denetimi Sihirbazı](../atl/reference/atl-control-wizard.md) ATL ActiveX denetimi oluşturmak için.

   Yukarıda açıklandığı gibi MFC projesinde ATL desteği, eklediğiniz ATL denetimi de ekleyebilirsiniz. Ayrıca, seçerseniz **ATL denetimi** içinde **sınıfı Ekle** iletişim kutusu ve henüz eklenmedi ATL desteği, MFC projenize, Visual Studio ATL desteği ekleme onaylama bir iletişim kutusu görüntüler, MFC projesi.

   Bu sihirbaz, proje sınıflarda IDL kaynağı ve COM eşlemesi oluşturur.

Bir ATL projesi açın, sonra [sınıfı Ekle](../ide/add-class-dialog-box.md) iletişim kutusu seçimi COM arabirimleri projenize eklemek için ek sihirbazlar ve şablonları sağlar. Aşağıdaki sihirbazlar, nesne için bir veya daha fazla arabirimi oluşturmak izin ver:

- [ATL COM+ 1.0 Bileşeni Sihirbazı](../atl/reference/atl-com-plus-1-0-component-wizard.md)

- [ATL Basit Nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md)

- [ATL Active Server Page Bileşeni Sihirbazı](../atl/reference/atl-active-server-page-component-wizard.md)

- [ATL Denetimi Sihirbazı](../atl/reference/atl-control-wizard.md)

Ayrıca, nesnenin denetim sınıf Sınıf Görünümü'nde sağ tıklatıp COM denetiminizi yeni arabirim uygulayabilir [arabirimi uygulayan](../ide/implement-interface-wizard.md).

> [!NOTE]
>  Visual Studio, bir arabirim bir projeye eklemek için sihirbaz sağlamaz. Arabirim bir ATL projesi veya çok ekleyebileceğiniz bir [MFC projenize ATL desteği ekleme](../mfc/reference/adding-atl-support-to-your-mfc-project.md) kullanarak basit bir nesne ekleyerek [ATL Basit Nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md). Alternatif olarak, projenin .idl dosyası açın ve yazarak arabirimi oluşturun:

```
interface IMyInterface {
};

```

Bkz: [arabirimi uygulama](../ide/implementing-an-interface-visual-cpp.md) ve [nesneler ekleme ve denetimleri için ATL projesinde](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) daha fazla bilgi için.

Visual C++ görüntülemek için çeşitli yollar sağlar ve [COM arabirimlerinin Düzenle](../ide/editing-a-com-interface.md) projeleriniz için tanımlanmış. [Sınıf Görünümü](/visualstudio/ide/viewing-the-structure-of-code) herhangi bir arabirim veya C++ projenize bir .idl dosyasında tanımlanan dispinterface için simgeleri görüntüler.

ATL tabanlı COM nesne sınıfları için sınıf görünümü ATL sınıfı ve bunu uygulayan herhangi bir arabirimleri arasındaki ilişkiyi görüntülemek için ATL sınıfı içindeki COM eşlemesine okur.

Sınıf Görünümü ve kendi kısayol menülerini arabirimleriyle gibi çalışabilirsiniz:

- ATL nesneler için MFC tabanlı bir uygulama ekleyin.

- Yöntemler, özellikler ve olaylar ekleyin.

- Bir öğenin arabirimi kodu doğrudan öğeyi çift tıklayarak geçin.

## <a name="see-also"></a>Ayrıca Bkz.

[Uygulama Sihirbazları Kullanarak Masaüstü Projeleri Oluşturma](../ide/creating-desktop-projects-by-using-application-wizards.md)<br>
[Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)