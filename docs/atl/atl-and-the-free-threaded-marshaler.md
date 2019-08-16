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
ms.openlocfilehash: 94e4961c69e9441d160d72d9b72afcee3677e25f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491906"
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL ve Ücretsiz İş Parçacıklı Sıralayıcı

ATL basit nesne Sihirbazı 'nın öznitelikler sayfası, sınıfınızın boş iş parçacıklı Sıralayıcı 'yı (FTM) toplamasını sağlayan bir seçenek sunar.

Sihirbaz, içindeki `FinalConstruct` serbest iş parçacıklı Sıralayıcı 'nın bir örneğini oluşturmak için kod üretir ve bu `FinalRelease`örneği serbest bırakın. COM_INTERFACE_ENTRY_AGGREGATE makrosu, `QueryInterface` [imarshal](/windows/win32/api/objidlbase/nn-objidlbase-imarshal) isteklerinin ücretsiz iş parçacıklı Sıralayıcı tarafından işlenmesini sağlamak için otomatik olarak com haritasına eklenir.

Ücretsiz iş parçacıklı Sıralayıcı, aynı işlemdeki herhangi bir iş parçacığından nesneniz üzerindeki arabirimlere doğrudan erişim sağlar ve gruplar arası çağrıları hızlandırın. Bu seçenek, her Iki iş parçacığı modelini kullanan sınıflar için tasarlanmıştır.

Bu seçenek kullanıldığında, sınıfların iş parçacığı güvenliği için bir sorumluluğu olmalıdır. Ayrıca, serbest iş parçacıklı sıralayıcıyı toplayan ve diğer nesnelerden elde edilen arabirim işaretçilerinin kullanılması gereken nesneler, arabirimlerin doğru bir şekilde sıralanmasını sağlamak için ek adımlar almalıdır. Genellikle bu, arabirim işaretçilerinin genel arabirim tablosunda (GIT) depolanmasını ve her kullanıldığında GIT 'ten işaretçiyi almanızı içerir. ATL, GIT 'te depolanan arabirim işaretçilerini kullanmanıza yardımcı olmak için [CComGITPtr](../atl/reference/ccomgitptr-class.md) sınıfını sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Tiren](../atl/active-template-library-atl-concepts.md)<br/>
[CoCreateFreeThreadedMarshaler](/windows/win32/api/combaseapi/nf-combaseapi-cocreatefreethreadedmarshaler)<br/>
[IMarshal](/windows/win32/api/objidlbase/nn-objidlbase-imarshal)<br/>
[Genel arabirim tablosunun ne zaman kullanılacağı](/windows/win32/com/when-to-use-the-global-interface-table)<br/>
[Işlem içi sunucu Iş parçacığı sorunları](/windows/win32/com/in-process-server-threading-issues)
