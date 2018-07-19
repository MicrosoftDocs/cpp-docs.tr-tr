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
ms.openlocfilehash: 015b07e5870aa6269dc76af8610d42fb469a6d33
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848356"
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL ve Ücretsiz İş Parçacıklı Sıralayıcı
ATL Basit Nesne Sihirbazı'nın öznitelikler sayfasını ücretsiz iş parçacıklı sıralayıcı (FTM) toplamak kendi sınıfınızı izin veren bir seçenek sunar.  
  
 Sihirbaz ücretsiz iş parçacıklı Sıralayıcı bir örneğini oluşturmak için kod oluşturur `FinalConstruct` ve bu örnekte sürüm `FinalRelease`. COM_INTERFACE_ENTRY_AGGREGATE makrosu COM eşlemesine emin olmak için otomatik olarak eklenen `QueryInterface` için istekleri [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707) ücretsiz iş parçacıklı sıralayıcı tarafından işlenir.  
  
 Ücretsiz iş parçacıklı Sıralayıcı doğrudan erişim arabirimlerine nesneniz üzerinde herhangi bir iş parçacığı aynı işlemde, çapraz-grup aramaları hızlandırma izin verir. Bu seçenek her iki iş parçacığı modeli kullandığınız sınıflar için tasarlanmıştır.  
  
 Bu seçenek kullanıldığında, sınıf verilerini iş parçacığı güvenliği için sorumluluğunu üstlenmelidir. Ayrıca, ücretsiz iş parçacıklı Sıralayıcı toplama ve diğer nesnelerden elde edilen arabirim işaretçilerini kullanması gereken nesneleri, arabirimler doğru sıralanmış emin olmak için ek adımlar atmanız gerekir. Genellikle bu arabirim işaretçilerini genel arabirim tablosu (GIT) depolama ve işaretçiyi GİT'ten her kullanılışında alma içerir. ATL sağlar sınıfını [Ccomgıtptr](../atl/reference/ccomgitptr-class.md) git'te arabirim işaretçilerini kullanmanıza yardımcı olacak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../atl/active-template-library-atl-concepts.md)   
 [CoCreateFreeThreadedMarshaler](http://msdn.microsoft.com/library/windows/desktop/ms694500)   
 [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707)   
 [Genel arabirim tablosu kullanma zamanı](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [İşlem sunucusu iş parçacığı oluşturma sorunları](http://msdn.microsoft.com/library/windows/desktop/ms687205)

