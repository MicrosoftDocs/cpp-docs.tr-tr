---
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
ms.openlocfilehash: 2b1d023488e8d547217dafffd224ab9fc05bd876
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267907"
---
# <a name="testing-properties-and-events-with-test-container"></a>Test Kapsayıcısı ile Özellikleri ve Olayları Test Etme

Visual C++'da sevk Test kapsayıcısı, test ve hata ayıklama ActiveX denetimleri için bir ActiveX denetimi kapsayıcısı uygulamasıdır. Test kapsayıcısı özelliklerini değiştirme yöntemlerini çağırma ve kendi olayları tetikleme denetiminin işlevselliğini test etmek denetim geliştiricinin sağlar. Test kapsayıcısı veri bağlama bildirimleri günlüklerini görüntüleyebilir ve ayrıca bir ActiveX denetiminin Kalıcılık işlevselliğini test etme için olanakları sağlar: akış veya substorage özelliklerini kaydetmek, bunları yeniden ve saklı akış verilerini inceleyin. Bu bölümde, Test kapsayıcı'nın temel özelliklerinin nasıl kullanılacağını açıklar. Ek bilgi için seçin **yardımcı** Test kapsayıcısı çalışırken menüsü.

### <a name="to-access-the-activex-control-test-container"></a>ActiveX denetimi Test kapsayıcısı erişmek için

1. Derleme [TSTCON örnek: ActiveX denetimi Test kapsayıcısı](../visual-cpp-samples.md).

### <a name="to-test-your-activex-control"></a>ActiveX denetimi test etmek için

1. Üzerinde **Düzenle** Test kapsayıcısının menüsünü **yeni denetimi Ekle**.

1. İçinde **ekler denetimi** kutusunda, istediğiniz denetimi seçin ve tıklayın **Tamam**. Denetim denetim kapsayıcısında görünür.

    > [!NOTE]
    >  Denetiminiz olarak listelenmemişse **ekler denetimi** iletişim kutusunda, kendisiyle kaydettiğiniz emin olun **denetimleri Kaydet** komutunu **dosya** Test menüsü Kapsayıcı.

Bu noktada, denetimin özellikleri veya etkinlikleri test edebilirsiniz.

#### <a name="to-test-properties"></a>Özelliklerini test etmek için

1. Üzerinde **denetimi** menüsünde tıklatın **çağırma yöntemleri**.

1. İçinde **yöntem adı** aşağı açılan listesinde, test etmek istediğiniz bir özellik için PropPut yöntemi seçin.

1. Değiştirme **parametre değeri** veya **parametre türü** tıklayın **değer kümesi** düğmesi.

1. Tıklayın **Invoke** nesnesine yeni bir değer uygulamak için.

   Özelliği artık yeni bir değer içerir.

#### <a name="to-test-events-and-specify-the-destination-of-event-information"></a>İçin test olayları ve olay bilgilerini hedefini belirtin.

1. Üzerinde **seçenekleri** menüsünde tıklatın **günlüğü**.

1. Olay bilgilerini hedefini belirtin.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)<br/>
[Nasıl yapılır: ActiveX Denetiminde Hata Ayıklama](/visualstudio/debugger/how-to-debug-an-activex-control)
