---
title: ATL Bağlantı Noktaları
ms.date: 11/04/2016
helpviewer_keywords:
- connections, connection points
- ATL, connection points
- connection points [C++], about connection points
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
ms.openlocfilehash: 4d94396ef8839516d9bfee15a2611cce66baa6bd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252313"
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

## <a name="see-also"></a>Ayrıca bkz.

[Kavramları](../atl/active-template-library-atl-concepts.md)
