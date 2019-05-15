---
title: Bir COM arabirimi oluşturma
ms.date: 05/14/2019
helpviewer_keywords:
- COM interfaces, creating
- methods [C++], adding to COM interfaces
- COM interfaces, editing
- properties [C++], adding to COM interfaces
ms.assetid: 1be84d3c-6886-4d1e-8493-56c4d38a96d4
ms.openlocfilehash: 09ddc113450fadb208e4f8471bc9aacf596a53f1
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65708079"
---
# <a name="create-a-com-interface"></a>Bir COM arabirimi oluşturma

Sihirbazlar ve şablonlar tanımlama COM arabirimlerine ve görüntüleme Otomasyon sınıfları ve COM nesneleri için kullanan projeleri oluşturmak için Visual Studio sağlar.

Bu sihirbazlar, aşağıdaki üç yaygın görevleri gerçekleştirmek için kullanabilirsiniz:

- [MFC projenize ATL desteği Ekle](../mfc/reference/adding-atl-support-to-your-mfc-project.md).

  Kullanarak bir MFC projesi oluşturduktan sonra bir MFC uygulaması için ATL desteği Ekle [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md) ve ardından çalıştırarak **MFC ATL desteği Ekle** kod Sihirbazı. Bu destek, eklenen bir MFC yürütülebilir veya DLL projesi için yalnızca basit COM nesneleri için geçerlidir. Bu ATL nesnesi birden fazla arabirim olabilir.

- [MFC ActiveX denetimi oluşturmak](../mfc/reference/creating-an-mfc-activex-control.md).

  Açık [MFC ActiveX Denetim Sihirbazı'nı](../mfc/reference/mfc-activex-control-wizard.md) ActiveX denetimi bir dispinterface ve sırasıyla .idl dosyasının ve denetim sınıfı içinde tanımlanan bir olay eşlemesi oluşturun.

- [ATL denetimi ekleme](../atl/reference/adding-an-atl-control.md).

  Bir birleşimini kullanmak [ATL projesi Sihirbazı](../atl/reference/atl-project-wizard.md) ve [ATL denetimi Sihirbazı](../atl/reference/atl-control-wizard.md) ATL ActiveX denetimi oluşturmak için.

  Yukarıda açıklandığı gibi MFC projesinde ATL desteği, eklediğiniz ATL denetimi de ekleyebilirsiniz. Ayrıca, seçerseniz **ATL denetimi** içinde **sınıfı Ekle** iletişim kutusu ve henüz henüz eklenen ATL desteği, MFC projenize, Visual Studio ekleme ATL desteği için soran bir iletişim kutusu görüntüler, MFC projesi.

  Bu sihirbaz, proje sınıflarda IDL kaynağı ve COM eşlemesi oluşturur.

Açık, ATL projesinde kaydederler [sınıfı Ekle](../ide/add-class-dialog-box.md) iletişim kutusu seçimi COM arabirimleri projenize eklemek için ek sihirbazlar ve şablonları sağlar. Aşağıdaki sihirbazlar, nesne için bir veya daha fazla arabirimi oluşturmak izin ver:

- [ATL COM + 1.0 bileşeni Sihirbazı](../atl/reference/atl-com-plus-1-0-component-wizard.md)
- [ATL Basit Nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md)
- [ATL active server sayfa bileşeni Sihirbazı](../atl/reference/atl-active-server-page-component-wizard.md)
- [ATL Denetim Sihirbazı](../atl/reference/atl-control-wizard.md)

Ayrıca, COM denetiminizi yeni arabirim uygulayabilir. Yalnızca nesne denetim sınıf Sınıf Görünümü'nde sağ tıklatın ve seçin [arabirim uygulama](../ide/implement-interface-wizard.md).

> [!NOTE]
> Visual Studio, bir arabirim bir projeye eklemek için sihirbaz sağlamaz. Arabirim bir ATL projesi veya çok ekleyebileceğiniz bir [MFC projenize ATL ekleme desteği](../mfc/reference/adding-atl-support-to-your-mfc-project.md) kullanarak basit bir nesne ekleyerek [ATL Basit Nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md). Alternatif olarak, projenin .idl dosyası açın ve yazarak arabirimi oluşturun:

```
interface IMyInterface {
};
```

Daha fazla bilgi için [bir arabirim](../ide/implementing-an-interface-visual-cpp.md) ve [bir ATL projesine nesne ve denetim ekleme](../atl/reference/adding-objects-and-controls-to-an-atl-project.md).

Visual C++ görüntülemek için çeşitli yollar sağlar ve [COM arabirimlerinin Düzenle](#edit-a-com-interface) projeleriniz için tanımlanmış. [Sınıf Görünümü](/visualstudio/ide/viewing-the-structure-of-code) herhangi bir arabirim veya C++ projenize bir .idl dosyasında tanımlanan dispinterface için simgeleri görüntüler.

ATL tabanlı COM nesne sınıfları için sınıf görünümü ATL sınıfı ve bunu uygulayan herhangi bir arabirimleri arasındaki ilişkiyi görüntülemek için ATL sınıfı içindeki COM eşlemesine okur.

Sınıf Görünümü ve kendi kısayol menülerini arabirimleriyle gibi çalışabilirsiniz:

- ATL nesneler için MFC tabanlı bir uygulama ekleyin.
- Yöntemler, özellikler ve olaylar ekleyin.
- Bir öğenin arabirimi kodu doğrudan öğeyi çift tıklayarak geçin.

## <a name="in-this-section"></a>Bu bölümde

- [COM arabirimini düzenleme](#edit-a-com-interface)

## <a name="edit-a-com-interface"></a>COM arabirimini düzenleme

Sınıf Görünümü kısayol menüsünden komutlarını kullanarak, yeni yöntemleri ve özellikleri COM arabirimlerinin için Visual Studio'da tanımlayabileceğiniz C++ projeleri. Araç kutusundan olayları ActiveX denetimleri için de tanımlayabilirsiniz.

ATL ve MFC tabanlı COM nesne sınıfları için sınıf uygulamasını arabirimi Düzen aynı zamanda düzenleyebilirsiniz.

> [!NOTE]
> Dışında tanımladınız arabirimleri için **sınıfı Ekle** iletişim kutusunda, Visual C++ özellikleri ve yöntemleri .idl dosyasına ekler ve bile arabirimler el ile eklendiğinde yöntemlerini uygulayan sınıflar için saplamalar ekleyin.

Aşağıdaki üç sihirbazlar, var olan arabirimler özelleştirmenize yardımcı olur. Bunlara, sınıf görünümünden erişilebilir:

|Sihirbazı|Proje türü|
|------------|------------------|
|[Özellik Ekleme Sihirbazı](../ide/names-add-property-wizard.md)|ATL destekleyen ATL veya MFC projeleri Özellik eklemek istediğiniz bir arabirime sağ tıklayın.<br /><br />Visual C++ proje türü algılar ve Özellik Ekleme Sihirbazı gerektiği gibi seçenekleri değiştirir:<br /><br />-Görüntü arabirimlerinde bulunan kullanılarak oluşturulan projeler için [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md), Özellik Ekleme Sihirbazı'nı çağrılırken, MFC'ye belirli seçenekler sunar.<br />-MFC ActiveX denetim arabirimleri için Özellik Ekleme Sihirbazı'nı stok yöntemleri ve sağladığı biçimde kullanmanız veya denetim için özelleştirme özellikleri listesini sağlar.<br />-Diğer tüm arabirimleri için ekleme özelliği sihirbazları çoğu durumlarda kullanışlı seçenekler sağlar.|
|[Yöntem Ekleme Sihirbazı](../ide/add-method-wizard.md)|ATL destekleyen ATL veya MFC projeleri Yöntem eklemek istediğiniz bir arabirime sağ tıklayın.<br /><br />Visual C++ proje türü algılar ve yöntem Ekleme Sihirbazı gerektiği gibi seçenekleri değiştirir:<br /><br />-Görüntü arabirimlerinde bulunan kullanılarak oluşturulan projeler için [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md), yöntem Ekleme Sihirbazı'nı kullanarak, MFC'ye belirli seçenekler sunar.<br />-MFC ActiveX denetim arabirimleri için yöntem Ekleme Sihirbazı'nı stok yöntemleri ve sağladığı biçimde kullanmanız veya denetim için özelleştirme özellikleri listesini sağlar.<br />-Diğer tüm arabirimler için **Ekle yöntemi** sihirbazlar çoğu durumlarda kullanışlı seçenekler sağlar.|

Ayrıca, COM denetiminizi yeni arabirim uygulayabilir. Yalnızca nesne denetim sınıf Sınıf Görünümü'nde sağ tıklatın ve seçin [arabirim uygulama](../ide/implement-interface-wizard.md).
