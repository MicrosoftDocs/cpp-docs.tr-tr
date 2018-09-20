---
title: MFC ActiveX denetimi oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.activex.project
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b8345b99655cae3ea27b93e1742d8c07e8d80eb1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408038"
---
# <a name="creating-an-mfc-activex-control"></a>MFC ActiveX Denetimi Oluşturma

ActiveX denetimi programlar, belirli türde bir işlevi bir üst uygulamaya vermek üzere tasarlanmış modüler programlardır. Örneğin, bir iletişim kutusu veya bir Web sayfasında kullanım için bir araç kullanmak için bir düğme gibi bir denetim oluşturabilirsiniz.

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. Daha fazla bilgi için [ActiveX denetimlerini](../activex-controls.md).

MFC ActiveX denetimi oluşturmak için en kolay yolu kullanmaktır [MFC ActiveX Denetim Sihirbazı](../../mfc/reference/mfc-activex-control-wizard.md).

### <a name="to-create-an-mfc-activex-control-using-the-mfc-activex-control-wizard"></a>MFC ActiveX Denetim Sihirbazı'nı kullanarak bir MFC ActiveX denetimi oluşturmak için

1. Yardım konusundaki yönergeleri izleyerek [Visual C++ uygulama sihirbazıyla proje oluşturma](../../ide/creating-desktop-projects-by-using-application-wizards.md).

1. İçinde **yeni proje** iletişim kutusunda **MFC ActiveX denetimi** MFC ActiveX Denetim Sihirbazı'nı açmak için şablonlar bölmesindeki simgesi.

1. Tanımlayın, [uygulama ayarları](../../mfc/reference/application-settings-mfc-activex-control-wizard.md), [denetim adlarını](../../mfc/reference/control-names-mfc-activex-control-wizard.md), ve [ayarlarını denetleme](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) MFC ActiveX Denetim Sihirbazı'nı kullanarak.

    > [!NOTE]
    >  Sihirbaz tutmak için bu adımı atlayın varsayılan ayarlar.

1. Tıklayın **son** sihirbazı kapatın ve geliştirme ortamında yeni projenizi açın.

Projenizi oluşturduktan sonra oluşturulan dosyalar görüntüleyebileceğiniz **Çözüm Gezgini**. Projeniz için sihirbaz dosyaları hakkında daha fazla bilgi için proje tarafından oluşturulan ReadMe.txt dosyasına bakın. Dosya türleri hakkında daha fazla bilgi için bkz. [Visual C++ projeleri için oluşturulan dosya türleri](../../ide/file-types-created-for-visual-cpp-projects.md).

Projenizi oluşturduktan sonra kod sihirbazları eklemek için kullanabileceğiniz [işlevleri](../../ide/add-member-function-wizard.md), [değişkenleri](../../ide/add-member-variable-wizard.md), [olayları](../../ide/add-event-wizard.md), [özellikleri](../../ide/names-add-property-wizard.md), ve [yöntemleri](../../ide/add-method-wizard.md). ActiveX denetimi özelleştirme hakkında daha fazla bilgi için bkz. [MFC ActiveX denetimleri](../../mfc/mfc-activex-controls.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Özellik Sayfaları](../../ide/property-pages-visual-cpp.md)


