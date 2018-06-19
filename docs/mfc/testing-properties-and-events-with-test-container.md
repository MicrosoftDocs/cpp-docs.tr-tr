---
title: Test kapsayıcısı ile özellikleri ve olayları test etme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- testing, test containers
- tstcon32.exe
- debugging ActiveX controls
- test container
- ActiveX Control Test Container
- ActiveX controls [MFC], testing
- properties [MFC], testing
ms.assetid: 626867cf-fe53-4c30-8973-55bb93ef3917
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fbf2b7c26b7fc44a526381f4fb3e4dee5c94ba8d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381042"
---
# <a name="testing-properties-and-events-with-test-container"></a>Test Kapsayıcısı ile Özellikleri ve Olayları Test Etme
Visual C++'da, gönderilen Test kapsayıcısı, test ve ActiveX denetimlerinde hata ayıklama için bir ActiveX denetimi kapsayıcısı uygulamasıdır. Test kapsayıcısı özelliklerini değiştirme yöntemlerini çağırma ve olaylarını tetikleme denetimin işlevselliğini sınamak denetim Geliştirici sağlar. Test kapsayıcısı veri bağlama bildirimleri günlüklerini görüntüleyebilir ve ayrıca bir ActiveX denetiminin Kalıcılık işlevselliğini test etme için olanakları sağlar: akış veya substorage özelliklerini kaydetmek, bunları yeniden ve saklı akış verilerini inceleyin. Bu bölümde, Test kapsayıcısı temel özelliklerini kullanmayı açıklar. Ek bilgi için seçin **yardımcı** Test kapsayıcısı çalıştırılırken menüsü.  
  
### <a name="to-access-the-activex-control-test-container"></a>ActiveX denetimi Test kapsayıcısı erişmek için  
  
1.  Yapı [TSTCON örnek: ActiveX denetimi Test kapsayıcısı](../visual-cpp-samples.md).  
  
### <a name="to-test-your-activex-control"></a>ActiveX denetimi test etmek için  
  
1.  Üzerinde **Düzenle** Test kapsayıcısı menüsünü **yeni denetimi Ekle**.  
  
2.  İçinde **ekler denetimi** kutusuna istenen denetimi seçin ve tıklatın **Tamam**. Denetimi denetim kapsayıcısında görünür.  
  
    > [!NOTE]
    >  Denetim içinde listelenmemişse **Denetimi Ekle** iletişim kutusunda, kendisiyle kaydettirdiğiniz emin olun **denetimleri Kaydet** komutunu **dosya** Test menüsü Kapsayıcı.  
  
 Bu noktada denetiminizin özellikleri veya olayları test edebilirsiniz.  
  
#### <a name="to-test-properties"></a>Özelliklerini sınamak için  
  
1.  Üzerinde **denetim** menüsünde tıklatın **çağırma yöntemleri**.  
  
2.  İçinde **yöntem adı** aşağı açılan listesinde, test etmek istediğiniz özelliği PropPut yöntemi seçin.  
  
3.  Değiştirme **parametre değeri** veya **parametre türü** ve tıklayın **değeri ayarlanmış** düğmesi.  
  
4.  Tıklatın **Invoke** yeni değer nesneye uygulamak için.  
  
     Özelliği artık yeni bir değer içerir.  
  
#### <a name="to-test-events-and-specify-the-destination-of-event-information"></a>Olayları sınamak ve olay bilgilerini hedef belirtmek için.  
  
1.  Üzerinde **seçenekleri** menüsünde tıklatın **günlüğü**.  
  
2.  Olay bilgilerini hedefi belirtin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)   
 [Nasıl yapılır: bir ActiveX denetimi hata ayıklama](/visualstudio/debugger/how-to-debug-an-activex-control)

