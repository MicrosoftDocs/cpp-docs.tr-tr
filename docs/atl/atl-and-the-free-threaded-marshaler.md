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
ms.openlocfilehash: 60d8d81e772a6da66254d6e777c0cafa4fc8a296
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069280"
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL ve Ücretsiz İş Parçacıklı Sıralayıcı

ATL Basit Nesne Sihirbazı'nın öznitelikler sayfasını ücretsiz iş parçacıklı sıralayıcı (FTM) toplamak kendi sınıfınızı izin veren bir seçenek sunar.

Sihirbaz ücretsiz iş parçacıklı Sıralayıcı bir örneğini oluşturmak için kod oluşturur `FinalConstruct` ve bu örnekte sürüm `FinalRelease`. COM_INTERFACE_ENTRY_AGGREGATE makrosu COM eşlemesine emin olmak için otomatik olarak eklenen `QueryInterface` için istekleri [IMarshal](/windows/desktop/api/objidlbase/nn-objidlbase-imarshal) ücretsiz iş parçacıklı sıralayıcı tarafından işlenir.

Ücretsiz iş parçacıklı Sıralayıcı doğrudan erişim arabirimlerine nesneniz üzerinde herhangi bir iş parçacığı aynı işlemde, çapraz-grup aramaları hızlandırma izin verir. Bu seçenek her iki iş parçacığı modeli kullandığınız sınıflar için tasarlanmıştır.

Bu seçenek kullanıldığında, sınıf verilerini iş parçacığı güvenliği için sorumluluğunu üstlenmelidir. Ayrıca, ücretsiz iş parçacıklı Sıralayıcı toplama ve diğer nesnelerden elde edilen arabirim işaretçilerini kullanması gereken nesneleri, arabirimler doğru sıralanmış emin olmak için ek adımlar atmanız gerekir. Genellikle bu arabirim işaretçilerini genel arabirim tablosu (GIT) depolama ve işaretçiyi GİT'ten her kullanılışında alma içerir. ATL sağlar sınıfını [Ccomgıtptr](../atl/reference/ccomgitptr-class.md) git'te arabirim işaretçilerini kullanmanıza yardımcı olacak.

## <a name="see-also"></a>Ayrıca Bkz.

[Kavramları](../atl/active-template-library-atl-concepts.md)<br/>
[CoCreateFreeThreadedMarshaler](/windows/desktop/api/combaseapi/nf-combaseapi-cocreatefreethreadedmarshaler)<br/>
[IMarshal](/windows/desktop/api/objidlbase/nn-objidlbase-imarshal)<br/>
[Genel arabirim tablosu kullanma zamanı](/windows/desktop/com/when-to-use-the-global-interface-table)<br/>
[İşlem sunucusu iş parçacığı oluşturma sorunları](/windows/desktop/com/in-process-server-threading-issues)

