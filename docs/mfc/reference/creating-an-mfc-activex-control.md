---
title: MFC ActiveX Denetimi Oluşturma
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.activex.project
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
ms.openlocfilehash: 19e9ca6f985423bb01a8dea38988c5dcf7285683
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91505976"
---
# <a name="creating-an-mfc-activex-control"></a>MFC ActiveX Denetimi Oluşturma

ActiveX denetim programları, bir üst uygulamaya belirli bir tür işlevsellik sağlamak için tasarlanan modüler programlardır. Örneğin, bir iletişim kutusunda kullanım için düğme veya bir Web sayfasında kullanmak için araç çubuğu gibi bir denetim oluşturabilirsiniz.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. Daha fazla bilgi için bkz. [ActiveX denetimleri](../activex-controls.md).

MFC ActiveX denetimi oluşturmanın en kolay yolu [MFC ActiveX Denetim Sihirbazı](../../mfc/reference/mfc-activex-control-wizard.md)'nı kullanmaktır.

### <a name="to-create-an-mfc-activex-control-using-the-mfc-activex-control-wizard"></a>MFC ActiveX denetimi Sihirbazı 'Nı kullanarak bir MFC ActiveX denetimi oluşturmak için

1. [BIR MFC uygulaması oluşturma](creating-an-mfc-application.md) yardım konusundaki yönergeleri izleyin, ancak kullanılabilir şablonlar listesinden **MFC ActiveX denetimi** ' ni seçin.

1. MFC ActiveX Denetim Sihirbazı 'nı kullanarak [uygulama ayarlarınızı](../../mfc/reference/application-settings-mfc-activex-control-wizard.md), [Denetim adlarınızı](../../mfc/reference/control-names-mfc-activex-control-wizard.md)ve [denetim ayarlarını](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) tanımlayın.

    > [!NOTE]
    >  Sihirbazın varsayılan ayarlarını korumak için bu adımı atlayın.

1. Sihirbazı kapatmak için **son** ' a tıklayın ve yeni projenizi geliştirme ortamında açın.

Projenizi oluşturduktan sonra, **Çözüm Gezgini**' de oluşturulan dosyaları görüntüleyebilirsiniz. Sihirbazın projeniz için oluşturduğu dosyalar hakkında daha fazla bilgi için, bkz. proje tarafından oluşturulan dosya ReadMe.txt. Dosya türleri hakkında daha fazla bilgi için bkz. [Visual Studio C++ projeleri Için oluşturulan dosya türleri](../../build/reference/file-types-created-for-visual-cpp-projects.md).

Projenizi oluşturduktan sonra, [işlevler](../../ide/adding-a-member-function-visual-cpp.md#add-member-function-wizard), [değişkenler](../../ide/adding-a-member-variable-visual-cpp.md#add-member-variable-wizard), [Olaylar](../../ide/adding-an-event-visual-cpp.md#add-event-wizard), [Özellikler](../../ide/adding-a-property-visual-cpp.md#names-add-property-wizard)ve [Yöntemler](../../ide/adding-a-method-visual-cpp.md#add-method-wizard)eklemek için kod sihirbazları ' nı kullanabilirsiniz. ActiveX denetiminizi özelleştirme hakkında daha fazla bilgi için bkz. [MFC ActiveX denetimleri](../../mfc/mfc-activex-controls.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Özellik Sayfaları](../../build/reference/property-pages-visual-cpp.md)
