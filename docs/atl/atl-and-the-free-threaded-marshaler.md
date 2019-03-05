---
title: ATL ve Ücretsiz İş Parçacıklı Sıralayıcı
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, free threaded marshaler
- free threaded marshaler
- threading [C++], marshaler in ATL
- threading [ATL], free threaded marshaler
- FTM in ATL
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
ms.openlocfilehash: ddea5a74dbd40d097398d04c0b2bc274df5ec972
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57300004"
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL ve Ücretsiz İş Parçacıklı Sıralayıcı

ATL Basit Nesne Sihirbazı'nın öznitelikler sayfasını ücretsiz iş parçacıklı sıralayıcı (FTM) toplamak kendi sınıfınızı izin veren bir seçenek sunar.

Sihirbaz ücretsiz iş parçacıklı Sıralayıcı bir örneğini oluşturmak için kod oluşturur `FinalConstruct` ve bu örnekte sürüm `FinalRelease`. COM_INTERFACE_ENTRY_AGGREGATE makrosu COM eşlemesine emin olmak için otomatik olarak eklenen `QueryInterface` için istekleri [IMarshal](/windows/desktop/api/objidlbase/nn-objidlbase-imarshal) ücretsiz iş parçacıklı sıralayıcı tarafından işlenir.

Ücretsiz iş parçacıklı Sıralayıcı doğrudan erişim arabirimlerine nesneniz üzerinde herhangi bir iş parçacığı aynı işlemde, çapraz-grup aramaları hızlandırma izin verir. Bu seçenek her iki iş parçacığı modeli kullandığınız sınıflar için tasarlanmıştır.

Bu seçenek kullanıldığında, sınıf verilerini iş parçacığı güvenliği için sorumluluğunu üstlenmelidir. Ayrıca, ücretsiz iş parçacıklı Sıralayıcı toplama ve diğer nesnelerden elde edilen arabirim işaretçilerini kullanması gereken nesneleri, arabirimler doğru sıralanmış emin olmak için ek adımlar atmanız gerekir. Genellikle bu arabirim işaretçilerini genel arabirim tablosu (GIT) depolama ve işaretçiyi GİT'ten her kullanılışında alma içerir. ATL sağlar sınıfını [Ccomgıtptr](../atl/reference/ccomgitptr-class.md) git'te arabirim işaretçilerini kullanmanıza yardımcı olacak.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramları](../atl/active-template-library-atl-concepts.md)<br/>
[CoCreateFreeThreadedMarshaler](/windows/desktop/api/combaseapi/nf-combaseapi-cocreatefreethreadedmarshaler)<br/>
[IMarshal](/windows/desktop/api/objidlbase/nn-objidlbase-imarshal)<br/>
[Genel arabirim tablosu kullanma zamanı](/windows/desktop/com/when-to-use-the-global-interface-table)<br/>
[İşlem sunucusu iş parçacığı oluşturma sorunları](/windows/desktop/com/in-process-server-threading-issues)
