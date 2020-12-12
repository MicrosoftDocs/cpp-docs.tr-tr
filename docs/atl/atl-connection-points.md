---
description: 'Daha fazla bilgi edinin: ATL bağlantı noktaları'
title: ATL Bağlantı Noktaları
ms.date: 11/04/2016
helpviewer_keywords:
- connections, connection points
- ATL, connection points
- connection points [C++], about connection points
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
ms.openlocfilehash: 60b9018185bea2af26407ee9d7a203148c8dc477
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165829"
---
# <a name="atl-connection-points"></a>ATL Bağlantı Noktaları

Bağlanılabilir bir nesne, giden arabirimleri destekleyen bir nesnedir. Giden arabirim, nesnenin bir istemciyle iletişim kurmasına izin verir. Her giden arabirim için, bağlanılabilir nesne bir bağlantı noktası gösterir. Her giden arabirim, havuz adlı bir nesne üzerinde bir istemci tarafından uygulanır.

![Bağlantı noktaları](../atl/media/vc2zw31.gif "Bağlantı noktaları")

Her bağlantı noktası [IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint) arabirimini destekler. Bağlanılabilir nesne, [IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer) arabirimi aracılığıyla istemciye bağlantı noktalarını kullanıma sunar.

## <a name="in-this-section"></a>Bu Bölümde

[ATL bağlantı noktası sınıfları](../atl/atl-connection-point-classes.md)<br/>
Bağlantı noktalarını destekleyen ATL sınıflarını kısaca açıklar.

[Bir nesneye bağlantı noktaları ekleme](../atl/adding-connection-points-to-an-object.md)<br/>
Bir nesneye bağlantı noktaları eklemek için kullanılan adımları özetler.

[ATL bağlantı noktası örneği](../atl/atl-connection-point-example.md)<br/>
Bir bağlantı noktası bildirme örneği sağlar.

## <a name="related-sections"></a>İlgili Bölümler

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Etkin Şablon kitaplığı 'nı kullanarak programla programlama hakkında kavramsal konuların bağlantılarını sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Kavramlar](../atl/active-template-library-atl-concepts.md)
