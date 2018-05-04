---
title: ATL Hizmetleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule
dev_langs:
- C++
helpviewer_keywords:
- CServiceModule class
- COM objects, ATL
- services, ATL
- ATL services
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db13b443e605168389f0a9bc767ba29a75d4234d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="atl-services"></a>ATL Hizmetleri
Bir hizmet olarak çalışır, ATL COM nesnesi oluşturmak için hizmet (EXE) ATL Proje Sihirbazı'ndaki Sunucu Seçenekleri listesinden seçmeniz yeterlidir. Sihirbaz sonra türetilmiş bir sınıf oluşturun `CAtlServiceModuleT` hizmeti uygulama.  
  
 ATL COM nesnesi bir hizmet olarak yapılandırıldığında, yalnızca yerel bir sunucu olarak kayıtlı ve Denetim Masası'ndaki Hizmetler listesinde görünmez. Bir hizmet olarak yerel bir sunucusu olarak hizmet hata ayıklamak daha kolay olmasıdır. Bir hizmet olarak yüklemek için komut istemine aşağıdaki komutu çalıştırın:  
  
 `YourEXE``.exe /Service`  
  
 Kaldırmak için şu komutu çalıştırın:  
  
 `YourEXE``.exe /UnregServer`  
  
 Bu bölümdeki ilk dört konular yürütülmesi sırasında oluşan işlemleri ele `CAtlServiceModuleT` üye işlevleri. Bu konularda işlevler genellikle çağrılır sırayla görünür. Bu konularda Anlayışınızı artırmak için bir başvuru olarak ATL Proje Sihirbazı tarafından oluşturulan kaynak kodu kullanmak için bir fikirdir. Bu ilk dört konular şunlardır:  
  

-   [CAtlServiceModuleT::Start işlevi](../atl/reference/catlservicemodulet-class.md#start)  
  
-   [CAtlServiceModuleT::ServiceMain işlevi](../atl/reference/catlservicemodulet-class.md#servicemain)  
  
-   [CAtlServiceModuleT::Run işlevi](../atl/reference/catlservicemodulet-class.md#run)  
  
-   [CAtlServiceModuleT::Handler işlevi](../atl/reference/catlservicemodulet-class.md#handler)  
  
 Son üç konuları bir hizmeti geliştirme ile ilgili kavramlar açıklanmaktadır:  
  
-   [Kayıt defteri girdileri](../atl/registry-entries.md) ATL Hizmetleri  
  
-   [DCOMCNFG](../atl/dcomcnfg.md)  
  
-   [Hata ayıklama ipuçları](../atl/debugging-tips.md) ATL Hizmetleri  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../atl/active-template-library-atl-concepts.md)

