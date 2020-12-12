---
description: 'Hakkında daha fazla bilgi edinin: ATL projesine nesne ve denetim ekleme'
title: ATL Projesine Nesne ve Denetim Ekleme
ms.date: 05/09/2019
f1_keywords:
- vc.appwiz.ATL.controls
helpviewer_keywords:
- ATL projects, adding objects
- wizards [C++], ATL projects
- ATL projects, adding controls
- controls [ATL], adding to projects
- objects [C++], adding to ATL projects
- ATL Control Wizard
ms.assetid: c0adcbd0-07fe-4c55-a8fd-8c2c65ecdaad
ms.openlocfilehash: 979e15a6fe27599e68841e82ef03a457d66d3bf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165595"
---
# <a name="adding-objects-and-controls-to-an-atl-project"></a>ATL Projesine Nesne ve Denetim Ekleme

> [!NOTE]
> ATL COM+ 1,0 Bileşen Sihirbazı, ATL OLE DB Tüketici Sihirbazı ve ATL Active Server Page bileşeni Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz.

ATL veya MFC tabanlı projelerinize bir nesne veya denetim eklemek için ATL kod sihirbazlarından birini kullanabilirsiniz. Eklediğiniz her bir COM nesnesi veya denetimi için, sihirbaz. cpp ve. h dosyalarını ve betik tabanlı kayıt defteri desteği için bir. rgs dosyası oluşturur. Aşağıdaki ATL kod sihirbazları, Visual Studio 'da kullanılabilir:

- [ATL basit nesnesi](../../atl/reference/atl-simple-object-wizard.md)
- [ATL Iletişim kutusu](../../atl/reference/atl-dialog-wizard.md)
- [ATL denetimi](../../atl/reference/atl-control-wizard.md)
- [ATL Özellik sayfası](../../atl/reference/atl-property-page-wizard.md)
- [ATL Active Server sayfa bileşeni](../../atl/reference/atl-active-server-page-component-wizard.md)
- [ATL OLE DB tüketicisi](../../atl/reference/atl-ole-db-consumer-wizard.md)
- [MFC 'ye ATL desteği ekleme](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)
- [ATL COM+ 1.0 Bileşeni Sihirbazı](../../atl/reference/atl-com-plus-1-0-component-wizard.md)
- [ATL OLE DB sağlayıcısı](../../atl/reference/atl-ole-db-provider-wizard.md)

> [!NOTE]
> Projenize ATL nesnesi eklemeden önce ilgili yardım konularında nesnenin ayrıntılarını ve gereksinimlerini gözden geçirmeniz gerekir.

## <a name="to-add-an-object-or-a-control-using-the-atl-control-wizard"></a>ATL Denetim Sihirbazı 'Nı kullanarak bir nesne veya denetim eklemek için

1. **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve kısayol menüsünden **Ekle** ' ye tıklayın. **Sınıf Ekle**' ye tıklayın.

   [Sınıf Ekle](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) iletişim kutusu görünür.

1. **Kategoriler** bölmesinde seçili **ATL** klasörü ile **Şablonlar** bölmesinden eklenecek bir nesne seçin. **Aç**'a tıklayın. Seçili nesne için kod Sihirbazı görüntülenir.

   > [!NOTE]
   > Bir MFC projesine ATL nesnesi eklemek istiyorsanız, mevcut projeye ATL desteği eklemeniz gerekir. Bunu, [MFC PROJENIZE atl desteği ekleme](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)bölümündeki yönergeleri izleyerek yapabilirsiniz.

   Alternatif olarak, daha önce ATL desteği eklemeden MFC projenize ATL nesnesi eklemeye çalışırsanız, Visual Studio projenize ATL desteğinin eklenmesini isteyip istemediğinizi belirtmenizi ister. Projeye ATL desteği eklemek ve seçili ATL Sihirbazı 'nı açmak için **Evet** ' e tıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Proje Sihirbazı](../../atl/reference/atl-project-wizard.md)<br/>
[Visual Studio 'da C++ proje türleri](../../build/reference/visual-cpp-project-types.md)<br/>
[ATL COM nesnelerinin temelleri](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[ATL ve C Run-Time kodla programlama](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Varsayılan ATL Proje yapılandırması](../../atl/reference/default-atl-project-configurations.md)
