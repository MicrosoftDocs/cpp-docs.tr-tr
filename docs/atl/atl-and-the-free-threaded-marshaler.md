---
description: 'Daha fazla bilgi edinin: ATL ve ücretsiz Iş parçacıklı Sıralayıcı'
title: ATL ve Ücretsiz İş Parçacıklı Sıralayıcı
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, free threaded marshaler
- free threaded marshaler
- threading [C++], marshaler in ATL
- threading [ATL], free threaded marshaler
- FTM in ATL
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
ms.openlocfilehash: 01fb54386b5f48c8e49cc805e047c0faf8b0c39b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166076"
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL ve Ücretsiz İş Parçacıklı Sıralayıcı

ATL basit nesne Sihirbazı 'nın öznitelikler sayfası, sınıfınızın boş iş parçacıklı Sıralayıcı 'yı (FTM) toplamasını sağlayan bir seçenek sunar.

Sihirbaz, içindeki serbest iş parçacıklı Sıralayıcı 'nın bir örneğini oluşturmak için kod üretir `FinalConstruct` ve bu örneği serbest bırakın `FinalRelease` . `QueryInterface` [IMarshal](/windows/win32/api/objidlbase/nn-objidlbase-imarshal) isteklerinin ücretsiz iş parçacıklı Sıralayıcı tarafından işlenmesini sağlamak için bir COM_INTERFACE_ENTRY_AGGREGATE MAKROSU otomatik olarak com eşlemesine eklenir.

Ücretsiz iş parçacıklı Sıralayıcı, aynı işlemdeki herhangi bir iş parçacığından nesneniz üzerindeki arabirimlere doğrudan erişim sağlar ve gruplar arası çağrıları hızlandırın. Bu seçenek, her Iki iş parçacığı modelini kullanan sınıflar için tasarlanmıştır.

Bu seçenek kullanıldığında, sınıfların iş parçacığı güvenliği için bir sorumluluğu olmalıdır. Ayrıca, serbest iş parçacıklı sıralayıcıyı toplayan ve diğer nesnelerden elde edilen arabirim işaretçilerinin kullanılması gereken nesneler, arabirimlerin doğru bir şekilde sıralanmasını sağlamak için ek adımlar almalıdır. Genellikle bu, arabirim işaretçilerinin genel arabirim tablosunda (GIT) depolanmasını ve her kullanıldığında GIT 'ten işaretçiyi almanızı içerir. ATL, GIT 'te depolanan arabirim işaretçilerini kullanmanıza yardımcı olmak için [CComGITPtr](../atl/reference/ccomgitptr-class.md) sınıfını sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../atl/active-template-library-atl-concepts.md)<br/>
[CoCreateFreeThreadedMarshaler](/windows/win32/api/combaseapi/nf-combaseapi-cocreatefreethreadedmarshaler)<br/>
[IMarshal](/windows/win32/api/objidlbase/nn-objidlbase-imarshal)<br/>
[Genel arabirim tablosunun ne zaman kullanılacağı](/windows/win32/com/when-to-use-the-global-interface-table)<br/>
[Işlem içi sunucu Iş parçacığı sorunları](/windows/win32/com/in-process-server-threading-issues)
