---
title: MFC ActiveX Denetim Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.ctl.overview
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [MFC], MFC
- MFC ActiveX controls [MFC], wizards
- OLE controls [MFC], creating
- MFC ActiveX Control Wizard
- OLE controls [MFC]
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ccf2da630c72962ee3e74badc250de5cce5f14e2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407159"
---
# <a name="mfc-activex-control-wizard"></a>MFC ActiveX Denetim Sihirbazı

Bir ActiveX denetimini belirli bir türüdür [Otomasyon sunucusu](../../mfc/automation-servers.md); yeniden kullanılabilir bir bileşendir. ActiveX denetimi barındırma uygulaması [otomasyon istemci](../../mfc/automation-clients.md) denetimin. Amacınız, yeniden kullanılabilir bir bileşen oluşturmak için ise, bu Sihirbazı, bir denetim oluşturmak için kullanın. Bkz: [MFC ActiveX denetimleri](../../mfc/mfc-activex-controls.md) daha fazla bilgi için.

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerini modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](../activex-controls.md).

Alternatif olarak, bir Otomasyon sunucusu MFC uygulaması kullanarak oluşturabileceğiniz [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md).

Görünmez olabilir veya bu Sihirbazı ile oluşturulan ActiveX denetimi bir kullanıcı arabirimi olabilir. Bu seçeneği belirtebilirsiniz [denetim ayarları](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) sihirbaz sayfasında. Bir zamanlayıcı denetimi görünmez olmasını istediğiniz bir ActiveX denetimini örneğidir.

ActiveX denetimleri, bir karmaşık kullanıcı arabirimi olabilir. Bazı denetimler kapsüllenmiş formlar gibi olabilir: birçok içeren tek bir denetim alanları, her bir Windows Denetim kendi. Örneğin, MFC ActiveX denetimi uygulanan bir otomatik bölümleri nesnesinin bir form gibi kullanıcı arabirimi üzerinden kullanıcılar okuyabilir ve parça numarasını parçası adı ve diğer bilgileri Düzenle sunabilir. Bkz: [MFC ActiveX denetimleri](../../mfc/mfc-activex-controls.md) daha fazla bilgi için.

ActiveX nesneleriniz için bir kapsayıcı oluşturmak için ihtiyacınız varsa bkz [bir ActiveX denetimi kapsayıcısı oluşturma](../../mfc/reference/creating-an-mfc-activex-control-container.md).

MFC başlangıç paketi programının C++ kaynak (.cpp) dosyaları, kaynak (.rc) dosyaları ve proje (.vcxproj) dosyasını içerir. Bu Başlatıcı dosyalarında oluşturulan kodu MFC'ye dayalı.

Aşağıdaki örnek listesi, görevleri ve ActiveX denetiminizin geliştirmeleri türlerini gösterir:

- [ActiveX denetimi en iyi duruma getirme](../../mfc/mfc-activex-controls-optimization.md)

- [Bir ActiveX denetimine stok olaylar ekleme](../../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)

- [Özel olaylar ekleme](../../mfc/mfc-activex-controls-adding-custom-events.md)

- [Stok yöntemler ekleme](../../mfc/mfc-activex-controls-adding-stock-methods.md)

- [Özel yöntemler ekleme](../../mfc/mfc-activex-controls-adding-custom-methods.md)

- [Stok Özellikler ekleme](../../mfc/mfc-activex-controls-adding-stock-properties.md)

- [Özel Özellikler ekleme](../../mfc/mfc-activex-controls-adding-custom-properties.md)

- [Bir ActiveX denetim kapsayıcısındaki ActiveX denetimlerini programlama](../../mfc/programming-activex-controls-in-a-activex-control-container.md)

## <a name="overview"></a>Genel Bakış

Bu sihirbaz sayfası oluşturduğunuz MFC ActiveX denetimi projesi için geçerli uygulama ayarlarını açıklar. Varsayılan olarak, Sihirbazı gibi bir proje oluşturur:

- Varsayılan proje çalışma zamanı lisans ya da Yardım dosyaları oluşturur. Bu varsayılan ayarları değiştirebilirsiniz [uygulama ayarları](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) sayfası. ActiveX Denetim Sihirbazı'nı bu sayfada yaptığınız seçimleri yansıtılır **genel bakış** sayfası.

- Denetim sınıfı ve proje adını temel alarak bir özellik sayfası sınıfının proje içerir. Proje ve dosya adları adlarını düzenleyebileceğiniz [denetim adları](../../mfc/reference/control-names-mfc-activex-control-wizard.md) sayfası.

- Denetimi mevcut hiçbir Windows denetimine bağlı, görünür hale gelir, bir kullanıcı arabirimine sahiptir ve içerir etkinleştirir bir **hakkında** iletişim kutusu. Bu varsayılan ayarları değiştirebilirsiniz [denetim ayarları](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) sayfası.

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ proje oluşturma ve yönetme](../../ide/creating-and-managing-visual-cpp-projects.md)<br/>
[Visual C++ Proje Türleri](../../ide/visual-cpp-project-types.md)<br/>
[Kavramları](../../atl/active-template-library-atl-concepts.md)

