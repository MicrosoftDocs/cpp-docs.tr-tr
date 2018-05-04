---
title: ATL ve ücretsiz iş parçacıklı Sıralayıcı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, free threaded marshaler
- free threaded marshaler
- threading [C++], marshaler in ATL
- threading [ATL], free threaded marshaler
- FTM in ATL
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1716985adf65b714a418f20d3873f45c32d368b4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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

