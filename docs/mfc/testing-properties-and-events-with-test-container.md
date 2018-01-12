---
title: "Test kapsayıcısı ile özellikleri ve olayları test etme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- testing, test containers
- tstcon32.exe
- debugging ActiveX controls
- test container
- ActiveX Control Test Container
- ActiveX controls [MFC], testing
- properties [MFC], testing
ms.assetid: 626867cf-fe53-4c30-8973-55bb93ef3917
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 381f4e421b63b2ba48fe649a30e5bf7648b50d27
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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

