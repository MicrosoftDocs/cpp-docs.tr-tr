---
title: OLE DB Tüketicileri ve Sağlayıcıları
ms.date: 10/22/2018
helpviewer_keywords:
- OLE DB providers, OLE DB data architecture
- OLE DB providers
- OLE DB consumers, OLE DB data architecture
- OLE DB consumers
- OLE DB, data model
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
ms.openlocfilehash: d57ded9d084971c3562fc7f22e6a1a12a4e3368d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210087"
---
# <a name="ole-db-consumers-and-providers"></a>OLE DB Tüketicileri ve Sağlayıcıları

OLE DB mimarisi, tüketicilerinin ve sağlayıcıların modelini kullanır. Bir tüketici veri istekleri yapar. Sağlayıcı, verileri tablolu bir biçimde yerleştirip tüketiciye döndürerek bu isteklere yanıt verir. Tüketicinin yapabilmesinin gereken her türlü çağrı, sağlayıcıya uygulanmalıdır.

Teknik olarak tanımlanan tüketici, OLE DB arabirimler aracılığıyla verilere erişen sistem veya uygulama kodlarıdır (bir OLE DB bileşeni değildir). Arabirimler bir sağlayıcıya uygulanır. Böylece sağlayıcı, verilere erişimi kapsüllemek ve diğer nesnelere (diğer bir deyişle, müşteriler) sunmak için OLE DB arabirimlerini uygulayan herhangi bir yazılım bileşenidir.

Roller için bir tüketici OLE DB arabirimlerde Yöntemler çağırır; OLE DB sağlayıcı gerekli OLE DB arabirimlerini uygular.

OLE DB, özellikle n katmanlı bir durumda, bu roller her zaman anlamlı hale gelmediğinden, koşulları istemci ve sunucu olarak engeller. Tüketici başka bir bileşene hizmet eden katmanda bir bileşen olabileceği için, bir istemci bileşeni bunu çağırmak için kafa karıştırıcı olur. Ayrıca, bir sağlayıcı bazen bir sunucudan daha fazla veritabanı sürücüsü gibi davranır.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Programlama](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB Programlamaya Genel Bakış](../../data/oledb/ole-db-programming-overview.md)
