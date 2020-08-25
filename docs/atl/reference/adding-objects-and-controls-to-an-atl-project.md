---
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
ms.openlocfilehash: b1bf4f85ccf7a0bb2d77bfb96c512349f581f193
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832457"
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

   [Sınıf Ekle](../../ide/add-class-dialog-box.md) iletişim kutusu görünür.

1. **Kategoriler** bölmesinde seçili **ATL** klasörü ile **Şablonlar** bölmesinden eklenecek bir nesne seçin. **Aç**’a tıklayın. Seçili nesne için kod Sihirbazı görüntülenir.

   > [!NOTE]
   > Bir MFC projesine ATL nesnesi eklemek istiyorsanız, mevcut projeye ATL desteği eklemeniz gerekir. Bunu, [MFC PROJENIZE atl desteği ekleme](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)bölümündeki yönergeleri izleyerek yapabilirsiniz.

   Alternatif olarak, daha önce ATL desteği eklemeden MFC projenize ATL nesnesi eklemeye çalışırsanız, Visual Studio projenize ATL desteğinin eklenmesini isteyip istemediğinizi belirtmenizi ister. Projeye ATL desteği eklemek ve seçili ATL Sihirbazı 'nı açmak için **Evet** ' e tıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Proje Sihirbazı](../../atl/reference/atl-project-wizard.md)<br/>
[Visual Studio 'da C++ proje türleri](../../build/reference/visual-cpp-project-types.md)<br/>
[ATL COM nesnelerinin temelleri](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[ATL ve C çalışma zamanı koduyla programlama](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Varsayılan ATL Proje yapılandırması](../../atl/reference/default-atl-project-configurations.md)
