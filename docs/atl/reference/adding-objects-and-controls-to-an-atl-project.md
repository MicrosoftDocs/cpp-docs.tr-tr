---
title: Bir ATL projesine nesne ve denetim ekleme
ms.date: 11/04/2016
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
ms.openlocfilehash: 94478f01655ff68b6b8067771eb3fdab42d1af01
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62249092"
---
# <a name="adding-objects-and-controls-to-an-atl-project"></a>Bir ATL projesine nesne ve denetim ekleme

ATL kodu sihirbazlardan birini, ATL veya MFC tabanlı projelerinize bir nesne veya bir denetim eklemek için kullanabilirsiniz. Her bir COM nesnesi veya denetim için eklemenize, sihirbaz, .cpp ve .h dosyaları yanı sıra, kayıt defteri betik tabanlı desteği için bir .rgs dosyası oluşturur. Aşağıdaki ATL kod sihirbazları, Visual Studio'da kullanılabilir:

||||
|-|-|-|
|[ATL Basit Nesne](../../atl/reference/atl-simple-object-wizard.md)|[ATL iletişim kutusu](../../atl/reference/atl-dialog-wizard.md)|[ATL denetimi](../../atl/reference/atl-control-wizard.md)|
|[ATL özellik sayfası](../../atl/reference/atl-property-page-wizard.md)|[ATL Active Server Page bileşeni](../../atl/reference/atl-active-server-page-component-wizard.md)|[ATL OLE DB Tüketicisi](../../atl/reference/atl-ole-db-consumer-wizard.md)|
|[MFC'ye ATL desteği Ekle](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)|[ATL COM+ 1.0 Bileşeni Sihirbazı](../../atl/reference/atl-com-plus-1-0-component-wizard.md)|[ATL OLE DB sağlayıcısı](../../atl/reference/atl-ole-db-provider-wizard.md)|

> [!NOTE]
> Projenize ATL nesnesi eklemeden önce Ayrıntılar ve gereksinimler için Yardım konusuna nesnesinde gözden geçirmelisiniz.

## <a name="to-add-an-object-or-a-control-using-the-atl-control-wizard"></a>Bir nesne veya ATL Denetim Sihirbazı'nı kullanarak bir denetim eklemek için

1. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklatıp **Ekle** kısayol menüsünden. Tıklayın **sınıfı Ekle**.

   [Sınıfı Ekle](../../ide/add-class-dialog-box.md) iletişim kutusu görüntülenir.

1. İle **ATL** seçili klasör **kategorileri** bölmesinde öğesinden eklenecek nesne bir seçin **şablonları** bölmesi. Tıklayın **açık**. Seçili nesne için kod Sihirbazı görünür.

   > [!NOTE]
   > MFC projesinde ATL nesnesi eklemek istiyorsanız, varolan bir projeye ATL desteği eklemeniz gerekir. Bu yönergeleri izleyerek yapabilirsiniz [MFC projenize ATL desteği ekleme](../../mfc/reference/adding-atl-support-to-your-mfc-project.md).

   Alternatif olarak, ATL desteği eklemeden önce MFC projenize ATL nesnesi eklemek çalışırsanız, Visual Studio projenize eklenen ATL desteğinin isteyip istemediğinizi belirtmenizi ister. Tıklayın **Evet** projeye ATL desteği Ekle ve seçili ATL Sihirbazı'nı açın.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Projesi Sihirbazı](../../atl/reference/atl-project-wizard.md)<br/>
[Visual C++ Proje Türleri](../../build/reference/visual-cpp-project-types.md)<br/>
[ATL COM Nesnelerinin Temelleri](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[ATL ve C Çalışma Zamanı Koduyla Programlama](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[Varsayılan ATL Projesi Yapılandırmaları](../../atl/reference/default-atl-project-configurations.md)
