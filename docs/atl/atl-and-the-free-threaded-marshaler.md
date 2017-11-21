---
title: "ATL ve ücretsiz iş parçacıklı Sıralayıcı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ATL, free threaded marshaler
- free threaded marshaler
- threading [C++], marshaler in ATL
- threading [ATL], free threaded marshaler
- FTM in ATL
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ed5660be9a5559d5f51d0cdb0ec2e5bc185bd0b4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL ve Ücretsiz İş Parçacıklı Sıralayıcı
ATL Basit Nesne sihirbazın öznitelikleri sayfasında sınıfınızı ücretsiz iş parçacıklı sıralayıcı (FTM) toplamak izin veren bir seçenek sağlar.  
  
 Sihirbaz ücretsiz iş parçacıklı Sıralayıcı örneğini oluşturmak için kod oluşturur `FinalConstruct` ve bu örneğinde yayın `FinalRelease`. A `COM_INTERFACE_ENTRY_AGGREGATE` makrosu emin olmak için COM eşlemesi otomatik olarak eklenen `QueryInterface` için istekleri [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707) ücretsiz iş parçacıklı sıralayıcı tarafından işlenir.  
  
 Ücretsiz iş parçacıklı Sıralayıcı doğrudan erişim nesnenizin arabirimlere aynı işlemde herhangi bir iş parçacığı arası grup aramaları hızlandırma izin verir. Bu seçenek her iki iş parçacığı modelini kullanan sınıflar için tasarlanmıştır.  
  
 Bu seçenek kullanıldığında sınıfları verilerini iş parçacığı güvenliği sorumluluğunu almanız gerekir. Ayrıca, ücretsiz iş parçacıklı Sıralayıcı toplamak ve diğer nesneleri elde arabirim işaretçileri kullanmak gereken nesneleri arabirimler doğru şekilde sıralanmış emin olmak için ek adımlar atmanız gerekir. Genellikle bu arabirim işaretçileri genel arabirim tablosu (GIT) depolamak ve işaretçiyi GIT her kullanılışında alma içerir. ATL sağlar sınıfı [CComGITPtr](../atl/reference/ccomgitptr-class.md) GIT içinde depolanan arabirim işaretçileri kullanmanıza yardımcı olacak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../atl/active-template-library-atl-concepts.md)   
 [CoCreateFreeThreadedMarshaler](http://msdn.microsoft.com/library/windows/desktop/ms694500)   
 [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707)   
 [Genel arabirim tablosu kullanma zamanı](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [İşlemdeki sunucu iş parçacığı oluşturma sorunları](http://msdn.microsoft.com/library/windows/desktop/ms687205)

