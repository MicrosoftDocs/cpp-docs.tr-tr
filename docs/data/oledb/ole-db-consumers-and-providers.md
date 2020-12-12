---
description: 'Hakkında daha fazla bilgi edinin: OLE DB tüketicileri ve sağlayıcılar'
title: OLE DB Tüketicileri ve Sağlayıcıları
ms.date: 10/22/2018
helpviewer_keywords:
- OLE DB providers, OLE DB data architecture
- OLE DB providers
- OLE DB consumers, OLE DB data architecture
- OLE DB consumers
- OLE DB, data model
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
ms.openlocfilehash: dedcbe7837cf7fad5bc9db8832e34edd3859a02b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317148"
---
# <a name="ole-db-consumers-and-providers"></a>OLE DB Tüketicileri ve Sağlayıcıları

OLE DB mimarisi, tüketicilerinin ve sağlayıcıların modelini kullanır. Bir tüketici veri istekleri yapar. Sağlayıcı, verileri tablolu bir biçimde yerleştirip tüketiciye döndürerek bu isteklere yanıt verir. Tüketicinin yapabilmesinin gereken her türlü çağrı, sağlayıcıya uygulanmalıdır.

Teknik olarak tanımlanan tüketici, OLE DB arabirimler aracılığıyla verilere erişen sistem veya uygulama kodlarıdır (bir OLE DB bileşeni değildir). Arabirimler bir sağlayıcıya uygulanır. Böylece sağlayıcı, verilere erişimi kapsüllemek ve diğer nesnelere (diğer bir deyişle, müşteriler) sunmak için OLE DB arabirimlerini uygulayan herhangi bir yazılım bileşenidir.

Roller için bir tüketici OLE DB arabirimlerde Yöntemler çağırır; OLE DB sağlayıcı gerekli OLE DB arabirimlerini uygular.

OLE DB, özellikle n katmanlı bir durumda, bu roller her zaman anlamlı hale gelmediğinden, koşulları istemci ve sunucu olarak engeller. Tüketici başka bir bileşene hizmet eden katmanda bir bileşen olabileceği için, bir istemci bileşeni bunu çağırmak için kafa karıştırıcı olur. Ayrıca, bir sağlayıcı bazen bir sunucudan daha fazla veritabanı sürücüsü gibi davranır.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Programlama](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB Programlamaya Genel Bakış](../../data/oledb/ole-db-programming-overview.md)
