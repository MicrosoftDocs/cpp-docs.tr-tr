---
description: 'Hakkında daha fazla bilgi edinin: Test kapsayıcısı ile özellikleri ve olayları test etme'
title: Test Kapsayıcısı ile Özellikleri ve Olayları Test Etme
ms.date: 11/04/2016
helpviewer_keywords:
- testing, test containers
- tstcon32.exe
- debugging ActiveX controls
- test container
- ActiveX Control Test Container
- ActiveX controls [MFC], testing
- properties [MFC], testing
ms.assetid: 626867cf-fe53-4c30-8973-55bb93ef3917
ms.openlocfilehash: 61cccbda723fb1cfac0ca3fc696639849bde9dd1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216229"
---
# <a name="testing-properties-and-events-with-test-container"></a>Test Kapsayıcısı ile Özellikleri ve Olayları Test Etme

Visual C++ ' de gönderilen test kapsayıcı uygulaması, ActiveX denetimlerinin sınanması ve hata ayıklaması için bir ActiveX denetim kapsayıcısıdır. Test kapsayıcısı denetim geliştiricinin özelliklerini değiştirerek, yöntemlerini çağırarak ve olaylarını harekete geçirerek denetimin işlevselliğini test etmesine olanak tanır. Test kapsayıcısı, veri bağlama bildirimlerinin günlüklerini görüntüleyebilir ve ayrıca ActiveX denetiminin Kalıcılık işlevlerini test etmek için tesisler sağlar: özellikleri bir akışa veya alt depolamaya kaydedebilir, yeniden yükleyebilir ve depolanan akış verilerini inceleyebilirsiniz. Bu bölümde, test kapsayıcısının temel özelliklerinin nasıl kullanılacağı açıklanmaktadır. Daha fazla bilgi için, test kapsayıcısını çalıştırırken **Yardım** menüsünü seçin.

### <a name="to-access-the-activex-control-test-container"></a>ActiveX denetimi test kapsayıcısına erişmek için

1. [Tstcon örneği: ActiveX denetimi test kapsayıcısını](../overview/visual-cpp-samples.md)oluşturun.

### <a name="to-test-your-activex-control"></a>ActiveX denetiminizi test etmek için

1. Test kapsayıcısının **düzenleme** menüsünde **Yeni Denetim Ekle**' ye tıklayın.

1. **Ekle denetim** kutusunda istenen denetimi seçin ve **Tamam**' ı tıklatın. Denetim, denetim kapsayıcısında görüntülenir.

    > [!NOTE]
    >  Denetiminiz **Denetim Ekle** iletişim kutusunda listelenmiyorsa, test kapsayıcısının **Dosya** menüsünden **denetimleri kaydet** komutuyla kaydettiğinizden emin olun.

Bu noktada, denetiminizin özelliklerini veya olaylarını test edebilirsiniz.

#### <a name="to-test-properties"></a>Özellikleri test etmek için

1. **Denetim** menüsünde **yöntemleri çağır**' a tıklayın.

1. **Yöntem adı** açılır listesinde, sınamak istediğiniz özellik Için PropPut yöntemini seçin.

1. **Parametre değerini** veya **parametre türünü** değiştirin ve **değer ayarla** düğmesine tıklayın.

1. Nesneye yeni değeri uygulamak için **çağır** ' a tıklayın.

   Özelliği artık yeni değeri içerir.

#### <a name="to-test-events-and-specify-the-destination-of-event-information"></a>Olayları test etmek ve olay bilgilerinin hedefini belirtmek için.

1. **Seçenekler** menüsünde **günlüğe** Kaydet ' e tıklayın.

1. Olay bilgilerinin hedefini belirtin.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)<br/>
[Nasıl yapılır: ActiveX denetiminde hata ayıklama](/visualstudio/debugger/how-to-debug-an-activex-control)
