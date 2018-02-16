---
title: Otomasyon | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Automation servers, about Automation servers
- clients, Automation
- programmatic control [MFC]
- properties [MFC], Automation
- MFC, COM support
- OLE Automation
- Automation
- servers [MFC], Automation
- Automation clients
- sample applications [MFC], Automation
- methods [MFC]
- passing parameters, Automation
- Automation method [MFC]
- Automation, passing parameters
- Automation property [MFC]
- MFC COM, Automation
- methods [MFC], Automation
ms.assetid: 329117f0-c1aa-4680-a901-bfb71277dfba
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b0204ab105b48350ea7fe934c28c5d5f95bea71f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="automation"></a>Otomatikleştirme
Otomasyon (önceki adıyla OLE Otomasyon bilinir), bir uygulama için başka bir uygulamaya uygulanan nesneleri değiştirmek için ya da bunlar işlenebilir nesnelerini ortaya çıkarmak için mümkün kılar.  
  
 Bir [Otomasyon sunucusu](../mfc/automation-servers.md) adlı diğer uygulamalara COM arabirimleri aracılığıyla kendi işlevselliği kullanıma sunan bir uygulamasıdır (COM sunucusu türü) [Otomasyon istemcileri](../mfc/automation-clients.md). Etkilenme Otomasyon istemcileri doğrudan nesnelere erişme ve sağladıkları hizmetlerini kullanarak belirli işlevleri otomatikleştirmenizi sağlar.  
  
 Otomasyon sunucuları ve istemcileri her zaman türetilmiş COM arabirimleri kullanırlar `IDispatch` almak ve veri türleri Automation türleri olarak adlandırılan belirli bir dizi döndürür. Yöntemleri ve diğer uygulamalardan erişebildiği özellikleri sağlayan bir Otomasyon arabirimi kullanıma sunan herhangi bir nesne otomatik hale getirebilirsiniz. Otomasyon OLE ve COM nesneleri için kullanılabilir. Otomatik nesne yerel veya uzak (başka bir makine bir ağ üzerinden erişilebilir); olabilir Bu nedenle Otomasyon iki kategorisi vardır:  
  
-   Otomasyon (yerel).  
  
-   Uzak Otomasyon (üzerinde dağıtılmış COM'u ya da DCOM kullanarak bir ağ).  
  
 Uygulamaları işlevselliği başka uygulamalar için yararlı sağladığınızda nesneleri gösterme faydalıdır. Örneğin, bir ActiveX denetimini Otomasyon sunucusu türüdür; ActiveX denetimi barındırma uygulama bu denetimin Otomasyon istemcidir.  
  
 Başka bir örnek olarak, sözcük işlemci yazım denetimi işlevselliğini diğer programları doğurabilir. Nesneleri riskini diğer uygulamaları hazır işlevselliğini kullanarak kendi uygulamalarında iyileştirmek satıcılar sağlar. Bu şekilde, Otomasyon bazı yeniden kullanılırlığı ve uygulamaların kendileri düzeyinde kapsülleme gibi nesne odaklı programlama ilkeler uygulanır.  
  
 Kullanıcılar ve çözüm sağlayıcıları için Otomasyon sağladığı desteği daha önemlidir. Uygulama işlevselliği ortak, iyi tanımlanmış bir arabirim aracılığıyla göstererek Otomasyon, geniş kapsamlı çözümleri bir tek genel programlama dili, Microsoft Visual Basic gibi de yerine oluşturmak mümkün kılar uygulamaya özgü makrosu diller.  
  
 Microsoft Excel ve Microsoft Visual C++ gibi birçok ticari uygulamaları, işlevlerinin çoğunu otomatikleştirmenizi sağlar. Örneğin, Visual C++'da otomatikleştirmek için VBScript makrolar oluşturur, düzenleme ya da görevleri hata ayıklama kodu yönlerini yazabilirsiniz.  
  
##  <a name="_core_passing_parameters_in_automation"></a> Otomasyon parametreleri geçirme  
 Otomasyon yöntemleri oluşturma bir zorluk otomasyon sunucuları ve istemciler arasında veri iletmek için bir Tekdüzen "safe" mekanizmaya yardımcı olur. Otomasyon kullanan **değişken** veri iletmek için türü. **Değişken** etiketli UNION türüdür. (Bu, anonim bir C++ birleşimi) değer için bir veri üyesi ve birleşim içinde depolanan bilgi türünü belirten bir veri üyesi vardır. **Değişken** türü bir dizi standart veri türlerini destekler: 2 ve 4 bayt tamsayı, 4 - ve 8-bayt kayan nokta sayıları, dizeleri ve Boole değerleri. Ayrıca, desteklediği `HRESULT` (OLE hata kodları) **para birimi** (sabit noktalı sayısal bir tür), ve **tarih** (mutlak tarih ve saat) türleri, işaretçileri yanı sıra **IUnknown**  ve `IDispatch` arabirimleri.  
  
 **Değişken** türü kapsüllenmiş [COleVariant](../mfc/reference/colevariant-class.md) sınıfı. Destekleyici **para birimi** ve **tarih** sınıfları kapsüllenmiş içinde [COleCurrency](../mfc/reference/colecurrency-class.md) ve [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) sınıfları.  
  
## <a name="automation-samples"></a>Otomasyon örnekleri  
  
-   [AUTOCLIK](../visual-cpp-samples.md) Otomasyon teknikleri öğrenmek için bu örneği kullanmak ve uzak Otomasyon öğrenme için bir temel olarak.  
  
-   [ACDUAL](../visual-cpp-samples.md) çift arabirimler Otomasyon sunucusu uygulamaya ekler.  
  
-   [CALCDRIV](../visual-cpp-samples.md) MFCCALC yürüten Automation istemci uygulaması.  
  
-   [InProc](../visual-cpp-samples.md) bir işlem içi Otomasyon sunucu uygulaması gösterir.  
  
-   [IPDRIVE](../visual-cpp-samples.md) InProc yürüten Automation istemci uygulaması.  
  
-   [MFCCALC](../visual-cpp-samples.md) bir otomasyon istemci uygulamasının gösterir.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Otomasyon İstemcileri](../mfc/automation-clients.md)  
  
-   [Otomasyon Sunucuları](../mfc/automation-servers.md)  
  
-   [OLE](../mfc/ole-in-mfc.md)  
  
-   [Etkin teknoloji](../mfc/mfc-com.md)  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz  
  
-   [Bir otomasyon sınıfı ekleme](../mfc/automation-servers.md)  
  
-   [Tür kitaplıklarını kullanma](../mfc/automation-clients-using-type-libraries.md)  
   
-   [Erişim otomasyon sunucuları](../mfc/automation-servers.md)  
  
-   [Otomasyon istemcileri C++ ile yazma](../mfc/automation-clients.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC COM](../mfc/mfc-com.md)
