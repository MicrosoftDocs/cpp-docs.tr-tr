---
title: ATL bağlantı noktaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- connections, connection points
- ATL, connection points
- connection points [C++], about connection points
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec0e902f2b01e33ac460c6210d51c5e0637c3282
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202926"
---
# <a name="atl-connection-points"></a>ATL Bağlantı Noktaları
Bir bağlanılabilirlik giden arabirimleri destekleyen bir nesnedir. Bir istemci ile iletişim kurmak nesne giden bir arabirim sağlar. Giden her arayüz için bir bağlantı noktası bağlanılabilirlik nesne kullanıma sunar. Her giden bir arabirim bir havuz olarak adlandırılan bir nesne üzerinde bir istemci tarafından uygulanır.  
  
 ![Bağlantı noktaları](../atl/media/vc2zw31.gif "vc2zw31")  
  
 Her bağlantı noktası destekleyen [IConnectionPoint](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint) arabirimi. Bağlanılabilirlik nesne, bağlantı noktaları aracılığıyla istemcisine sunar [IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer) arabirimi.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [ATL Bağlantı Noktası Sınıfları](../atl/atl-connection-point-classes.md)  
 Bağlantı noktaları destekleyen ATL sınıfları kısaca açıklanmaktadır.  
  
 [Bir Nesneye Bağlantı Noktaları Ekleme](../atl/adding-connection-points-to-an-object.md)  
 Bir nesneye bağlantı noktaları eklemek için kullanılan adımları açıklanmaktadır.  
  
 [ATL Bağlantı Noktası Örneği](../atl/atl-connection-point-example.md)  
 Bir bağlantı noktası bildirme bir örnek sağlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Active Template Library kullanarak programlama hakkında kavramsal konulara bağlantılar sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../atl/active-template-library-atl-concepts.md)

