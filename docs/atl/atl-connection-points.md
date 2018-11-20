---
title: ATL Bağlantı Noktaları
ms.date: 11/04/2016
helpviewer_keywords:
- connections, connection points
- ATL, connection points
- connection points [C++], about connection points
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
ms.openlocfilehash: 520537f5d562450dc4ea2a5e5a0c68af513da509
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175062"
---
# <a name="atl-connection-points"></a>ATL Bağlantı Noktaları

Bir bağlanılabilirlik giden arabirimleri destekleyen bir nesnedir. Bir istemci ile iletişim kurmak nesne giden bir arabirim sağlar. Giden her arayüz için bir bağlantı noktası bağlanılabilirlik nesne kullanıma sunar. Her giden bir arabirim bir havuz olarak adlandırılan bir nesne üzerinde bir istemci tarafından uygulanır.

![Bağlantı noktaları](../atl/media/vc2zw31.gif "bağlantı noktaları")

Her bağlantı noktası destekleyen [IConnectionPoint](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpoint) arabirimi. Bağlanılabilirlik nesne, bağlantı noktaları aracılığıyla istemcisine sunar [IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer) arabirimi.

## <a name="in-this-section"></a>Bu Bölümde

[ATL Bağlantı Noktası Sınıfları](../atl/atl-connection-point-classes.md)<br/>
Bağlantı noktaları destekleyen ATL sınıfları kısaca açıklanmaktadır.

[Bir Nesneye Bağlantı Noktaları Ekleme](../atl/adding-connection-points-to-an-object.md)<br/>
Bir nesneye bağlantı noktaları eklemek için kullanılan adımları açıklanmaktadır.

[ATL Bağlantı Noktası Örneği](../atl/atl-connection-point-example.md)<br/>
Bir bağlantı noktası bildirme bir örnek sağlar.

## <a name="related-sections"></a>İlgili Bölümler

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Active Template Library kullanarak programlama hakkında kavramsal konulara bağlantılar sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[Kavramları](../atl/active-template-library-atl-concepts.md)

