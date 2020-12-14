---
description: 'Daha fazla bilgi edinin: MFC ActiveX Denetim Sihirbazı'
title: MFC ActiveX Denetim Sihirbazı
ms.date: 09/12/2018
f1_keywords:
- vc.appwiz.mfc.ctl.overview
helpviewer_keywords:
- ActiveX controls [MFC], MFC
- MFC ActiveX controls [MFC], wizards
- OLE controls [MFC], creating
- MFC ActiveX Control Wizard
- OLE controls [MFC]
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
ms.openlocfilehash: f313f2a218c06a20eddbfff33e936109e4be2cf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219271"
---
# <a name="mfc-activex-control-wizard"></a>MFC ActiveX Denetim Sihirbazı

ActiveX denetimi, belirli bir [Otomasyon sunucusu](../../mfc/automation-servers.md)türüdür; yeniden kullanılabilir bir bileşendir. ActiveX denetimini barındıran uygulama, bu denetimin [Otomasyon istemcsahiptir](../../mfc/automation-clients.md) . Amacınız böyle bir yeniden kullanılabilir bileşen oluşturmak ise, denetiminizi oluşturmak için bu sihirbazı kullanın. Daha fazla bilgi için bkz. [MFC ActiveX denetimleri](../../mfc/mfc-activex-controls.md) .

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](../activex-controls.md).

Alternatif olarak, [MFC Uygulama Sihirbazı 'nı](../../mfc/reference/mfc-application-wizard.md)kullanarak bir AUTOMATION Server MFC uygulaması da oluşturabilirsiniz.

Bu sihirbazla oluşturulmuş bir ActiveX denetimi bir kullanıcı arabirimine sahip olabilir veya görünmez olabilir. Bu seçeneği, sihirbazdaki [denetim ayarları](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) sayfasında belirtebilirsiniz. Zamanlayıcı denetimi, görünmez olmasını istediğiniz ActiveX denetimine bir örnektir.

ActiveX denetimleri karmaşık bir kullanıcı arabirimine sahip olabilir. Bazı denetimler, kapsüllenmiş formlar gibi olabilir: her bir Windows denetimi kendi sağında olan çok sayıda alan içeren tek bir denetimdir. Örneğin, MFC ActiveX denetimi olarak uygulanan bir otomatik parçalar nesnesi, kullanıcıların parça numarasını, Bölüm adını ve diğer bilgileri okuyabileceği ve düzenleyebileceği, form benzeri bir kullanıcı arabirimi sunabilir. Daha fazla bilgi için bkz. [MFC ActiveX denetimleri](../../mfc/mfc-activex-controls.md) .

ActiveX nesneleriniz için bir kapsayıcı oluşturmanız gerekiyorsa bkz. [ActiveX Denetim kapsayıcısı oluşturma](../../mfc/reference/creating-an-mfc-activex-control-container.md).

MFC başlangıç programı C++ kaynak (. cpp) dosyalarını, kaynak (. RC) dosyalarını ve bir proje (. vcxproj) dosyasını içerir. Bu başlangıç dosyalarında oluşturulan kod MFC 'yi temel alır.

Aşağıdaki örnek listede, ActiveX denetiğiniz için görevler ve geliştirme türleri gösterilmektedir:

- [ActiveX denetimini iyileştirme](../../mfc/mfc-activex-controls-optimization.md)

- [Bir ActiveX denetimine hisse senedi olayları ekleme](../../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)

- [Özel olaylar ekleme](../../mfc/mfc-activex-controls-adding-custom-events.md)

- [Stok yöntemleri ekleme](../../mfc/mfc-activex-controls-adding-stock-methods.md)

- [Özel yöntemler ekleme](../../mfc/mfc-activex-controls-adding-custom-methods.md)

- [Stok özellikleri ekleme](../../mfc/mfc-activex-controls-adding-stock-properties.md)

- [Özel özellikler ekleme](../../mfc/mfc-activex-controls-adding-custom-properties.md)

- [ActiveX denetim kapsayıcısındaki ActiveX denetimlerini programlama](../../mfc/programming-activex-controls-in-a-activex-control-container.md)

## <a name="overview"></a>Genel Bakış

Bu sihirbaz sayfası oluşturmakta olduğunuz MFC ActiveX denetimi projesi için geçerli uygulama ayarlarını açıklar. Varsayılan olarak, sihirbaz aşağıdaki gibi bir proje oluşturur:

- Varsayılan proje, hiçbir çalışma zamanı lisansı veya Yardım dosyası oluşturmaz. [Uygulama ayarları](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) sayfasında bu varsayılan ayarları değiştirebilirsiniz. Yalnızca ActiveX Denetim Sihirbazı 'nın bu sayfasında yaptığınız seçimler **genel bakış** sayfasında yansıtılır.

- Proje, projenin adına göre bir denetim sınıfı ve özellik sayfası sınıfı içerir. Projenizin ve dosya adlarının adlarını [denetim adları](../../mfc/reference/control-names-mfc-activex-control-wizard.md) sayfasında düzenleyebilirsiniz.

- Denetim, var olan bir Windows denetimini temel alır, görünür hale geldiğinde etkinleştirir, bir kullanıcı arabirimine sahiptir ve bir **hakkında** iletişim kutusu içerir. Bu varsayılan ayarları [denetim ayarları](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) sayfasında değiştirebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio projeleri-C++](../../build/creating-and-managing-visual-cpp-projects.md)<br/>
[Visual Studio 'da C++ proje türleri](../../build/reference/visual-cpp-project-types.md)<br/>
[Kavramlar](../../atl/active-template-library-atl-concepts.md)
