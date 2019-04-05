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
ms.openlocfilehash: f5940ca65e42787c3156a9537cb3f3f6694339c0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031319"
---
# <a name="ole-db-consumers-and-providers"></a>OLE DB Tüketicileri ve Sağlayıcıları

OLE DB Mimari Tüketicileri ve sağlayıcıları modelini kullanır. Bir tüketici veri istekleri yapar. Bir sağlayıcı verileri tablo biçiminde yerleştirip tüketiciye döndürmeden bu isteklere yanıt verir. Tüketici yapabilen herhangi bir çağrı sağlayıcısında uygulanmalıdır.

Teknik olarak tanımlanan bir tüketici OLE DB arabirimleri aracılığıyla verilere erişen tüm sistem veya uygulama (OLE DB bileşeni gerekmez) kodudur. Arabirimler sağlayıcı uygulanır. Bu nedenle bir OLE DB veri erişimi kapsülleyen ve diğer nesneleri (diğer bir deyişle, tüketiciler) üzerinden kullanıma sunacaksınız arabirimleri uygulayan herhangi bir yazılım bileşeni sağlayıcısıdır.

Roller için bir tüketici OLE DB arabirimleri üzerinde yöntemleri çağırır; bir OLE DB sağlayıcısı gerekli OLE DB arabirimlerini uygular.

OLE DB, çünkü bu rollerin her zaman, özellikle bir n katmanlı durumda anlamsız koşulları istemci ve sunucu önler. Bir tüketici bir bileşen başka bir bileşene hizmet katmanı olabileceğinden, bir istemci çağırmak için bileşen kafa karıştırıcı olacaktır. Ayrıca, bir sağlayıcı bazen daha bir sunucu veritabanı sürücüsünden gibi davranır.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Programlama](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB Programlamaya Genel Bakış](../../data/oledb/ole-db-programming-overview.md)