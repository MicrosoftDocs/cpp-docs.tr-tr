---
title: ATL Hizmetleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CServiceModule
dev_langs: C++
helpviewer_keywords:
- CServiceModule class
- COM objects, ATL
- services, ATL
- ATL services
ms.assetid: 8c09d1a8-7548-4d2c-947c-9d795a81659b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d13eebbe96ba57c82e3bf1c360b0cb471a6bd975
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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

