---
description: 'Daha fazla bilgi edinin: COM arabirimi oluşturma'
title: COM arabirimi oluşturma
ms.date: 05/14/2019
helpviewer_keywords:
- COM interfaces, creating
- methods [C++], adding to COM interfaces
- COM interfaces, editing
- properties [C++], adding to COM interfaces
ms.assetid: 1be84d3c-6886-4d1e-8493-56c4d38a96d4
ms.openlocfilehash: 81274b2d6a966dc4f8b16649f1fb9d33b595de62
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240721"
---
# <a name="create-a-com-interface"></a>COM arabirimi oluşturma

Visual Studio, com nesneleri ve otomasyon sınıflarınız için COM tanımlama arabirimlerini ve görüntüleme arabirimlerini kullanan projeler oluşturmaya yönelik sihirbazlar ve şablonlar sağlar.

Bu sihirbazları kullanarak aşağıdaki üç ortak görevi gerçekleştirebilirsiniz:

- [MFC PROJENIZE atl desteği ekleyin](../mfc/reference/adding-atl-support-to-your-mfc-project.md).

  MFC [Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md) 'nı kullanarak bir MFC projesi oluşturduktan sonra MFC uygulamasına atl desteği ekleyin ve ardından **MFC koduna atl desteği ekle** Sihirbazı 'nı çalıştırın. Bu destek yalnızca MFC yürütülebilir dosyası veya DLL projesine eklenen basit COM nesneleri için geçerlidir. Bu ATL nesneleri birden fazla arabirime sahip olabilir.

- [MFC ActiveX denetimi oluşturma](../mfc/reference/creating-an-mfc-activex-control.md).

  Bir dispınterface ile ActiveX denetimi oluşturmak için [MFC ActiveX denetimi Sihirbazı 'nı](../mfc/reference/mfc-activex-control-wizard.md) açın ve. IDL dosyasında ve denetim sınıfında tanımlanmış bir olay eşlemesi oluşturun.

- [ATL denetimi ekleyin](../atl/reference/adding-an-atl-control.md).

  ATL ActiveX denetimi oluşturmak için [atl Proje Sihirbazı](../atl/reference/atl-project-wizard.md) 'Nın ve [atl Denetim Sihirbazı](../atl/reference/atl-control-wizard.md) 'nın bir birleşimini kullanın.

  Aşağıda açıklandığı gibi, ATL desteği eklediğiniz bir MFC projesine ATL denetimi de ekleyebilirsiniz. Ayrıca, **Sınıf Ekle** Iletişim kutusunda **ATL denetimi** ' nı seçer ve henüz MFC projenize ATL desteği EKLEMEDIYSENIZ, VISUAL Studio MFC projenize ATL desteğinin eklenmesini doğrulayan bir iletişim kutusu görüntüler.

  Bu sihirbaz, proje sınıflarında IDL kaynağı ve bir COM haritası oluşturur.

Bir ATL projesi açık olduktan sonra, [Sınıf Ekle](./adding-a-class-visual-cpp.md#add-class-dialog-box) iletişim kutusu projenize com arabirimleri eklemek için ek sihirbazlar ve şablonlar seçeneği sunar. Aşağıdaki sihirbazlar nesne için bir veya daha fazla arabirim kurmanıza olanak tanır:

- [ATL COM+ 1,0 Bileşen Sihirbazı](../atl/reference/atl-com-plus-1-0-component-wizard.md)
- [ATL basit nesne Sihirbazı](../atl/reference/atl-simple-object-wizard.md)
- [ATL Active Server Page bileşeni Sihirbazı](../atl/reference/atl-active-server-page-component-wizard.md)
- [ATL Denetim Sihirbazı](../atl/reference/atl-control-wizard.md)

Ayrıca, COM denetibir denetime yeni arabirimler uygulayabilirsiniz. Sınıf Görünümü nesnenin denetim sınıfına sağ tıklayıp [arabirim Uygula](./implementing-an-interface-visual-cpp.md#implement-interface-wizard)' yı seçmeniz yeterlidir.

> [!NOTE]
> Visual Studio, bir projeye arabirim eklemek için bir sihirbaz sağlamaz. ATL [basit nesne Sihirbazı 'nı](../atl/reference/atl-simple-object-wizard.md)kullanarak basit bir nesne ekleyerek bir ATL projesine veya bir ATL öğesine [atl desteği ekleyebilirsiniz](../mfc/reference/adding-atl-support-to-your-mfc-project.md) . Alternatif olarak, projenin. IDL dosyasını açın ve şunu yazarak arabirimi oluşturun:

```
interface IMyInterface {
};
```

Daha fazla bilgi için bkz. [bir arabirim uygulama](../ide/implementing-an-interface-visual-cpp.md) ve [ATL projesine nesne ve denetim ekleme](../atl/reference/adding-objects-and-controls-to-an-atl-project.md).

Visual C++, projeleriniz için tanımlanan [COM arabirimlerini](#edit-a-com-interface) görüntülemek ve düzenlemek için çeşitli yollar sağlar. [Sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code) C++ projenizdeki. IDL dosyasında tanımlanan tüm arabirim veya dispınterface için simgeler görüntüler.

ATL tabanlı COM nesne sınıfları için, Sınıf Görünümü ATL sınıfı ve uyguladığı arabirimler arasındaki ilişkiyi göstermek için ATL sınıfındaki COM eşlemesini okur.

Sınıf Görünümü ve kısayol menülerinde, arabirimlerle aşağıdaki gibi çalışabilirsiniz:

- MFC tabanlı bir uygulamaya ATL nesneleri ekleyin.
- Yöntemler, Özellikler ve olaylar ekleyin.
- Öğeye çift tıklayarak doğrudan bir öğenin arabirim koduna atlayın.

## <a name="in-this-section"></a>Bu bölümde

- [COM arabirimini düzenleme](#edit-a-com-interface)

## <a name="edit-a-com-interface"></a>COM arabirimini düzenleme

Sınıf Görünümü kısayol menüsündeki komutları kullanarak, Visual Studio C++ projelerinizde COM arabirimleri için yeni yöntemler ve özellikler tanımlayabilirsiniz. Araç kutusundan ActiveX denetimleri için de olayları tanımlayabilirsiniz.

ATL ve MFC tabanlı COM nesne sınıfları için, arabirimi düzenlediğiniz sırada sınıf uygulamasını düzenleyebilirsiniz.

> [!NOTE]
> **Sınıf Ekle** iletişim kutusunun dışında tanımladığınız arabirimler için Visual C++, yöntemleri veya özellikleri. IDL dosyasına ekler ve arabirimler el ile eklendiğinde bile yöntemleri uygulayan sınıflara saplamalar ekler.

Aşağıdaki üç sihirbaz mevcut arabirimleri özelleştirmenize yardımcı olur. Sınıf Görünümü kullanılabilir:

|Ekleme|Proje türü|
|------------|------------------|
|[Özellik Ekleme Sihirbazı](./adding-a-property-visual-cpp.md#names-add-property-wizard)|ATL destekleyen ATL veya MFC projeleri. Özelliği eklemek istediğiniz arabirime sağ tıklayın.<br /><br />Visual C++ proje türünü algılar ve gerektiğinde Özellik Ekleme Sihirbazı 'ndaki seçenekleri değiştirir:<br /><br />- [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md)kullanılarak oluşturulan projelerde Dispınterfaces Için Özellik Ekleme Sihirbazı ' nı çağırmak MFC 'ye özgü seçenekler sağlar.<br />-MFC ActiveX denetim arabirimleri için Özellik Ekleme Sihirbazı, denetimi için sağlanan veya özelleştirdiğiniz stok yöntemlerinin ve özelliklerinin bir listesini sağlar.<br />-Diğer tüm arabirimler için Özellik Ekle sihirbazları çoğu durumda yararlı seçenekler sağlar.|
|[Yöntem Ekleme Sihirbazı](./adding-a-method-visual-cpp.md#add-method-wizard)|ATL destekleyen ATL veya MFC projeleri. Yöntemi eklemek istediğiniz arabirime sağ tıklayın.<br /><br />Visual C++, proje türünü algılar ve yöntemi ekleme Sihirbazı 'ndaki seçenekleri gerektiği şekilde değiştirir:<br /><br />- [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md)kullanılarak oluşturulan projelerde dispınterfaces Için, yöntem ekleme Sihirbazı ' nı kullanarak MFC 'ye özgü seçenekler sağlar.<br />-MFC ActiveX denetim arabirimleri için yöntem ekleme Sihirbazı, denetimi için sağlanan veya özelleştirdiğiniz stok yöntemlerinin ve özelliklerinin bir listesini sağlar.<br />-Diğer tüm arabirimler için **yöntem ekleme** sihirbazları çoğu durumda yararlı seçenekler sağlar.|

Ayrıca, COM denetibir denetime yeni arabirimler uygulayabilirsiniz. Sınıf Görünümü nesnenin denetim sınıfına sağ tıklayıp [arabirim Uygula](./implementing-an-interface-visual-cpp.md#implement-interface-wizard)' yı seçmeniz yeterlidir.
