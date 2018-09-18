---
title: OLE DB Tüketicileri ve sağlayıcıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, OLE DB data architecture
- OLE DB providers
- OLE DB consumers, OLE DB data architecture
- OLE DB consumers
- OLE DB, data model
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b37a06ec89f0e2e21c4332a480e58c605f0d161f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110724"
---
# <a name="ole-db-consumers-and-providers"></a>OLE DB Tüketicileri ve Sağlayıcıları

OLE DB Mimari Tüketicileri ve sağlayıcıları modelini kullanır. Bir tüketici veri istekleri yapar. Bir sağlayıcı verileri tablo biçiminde yerleştirip tüketiciye döndürmeden bu isteklere yanıt verir. Tüketici yapabilen herhangi bir çağrı sağlayıcısında uygulanmalıdır.  
  
Teknik olarak tanımlanan bir tüketici OLE DB arabirimleri aracılığıyla verilere erişen tüm sistem veya uygulama (OLE DB bileşeni gerekmez) kodudur. Arabirimler sağlayıcı uygulanır. Bu nedenle, bir veri erişimi kapsülleyen ve diğer nesneleri (diğer bir deyişle, tüketiciler) göstermek için OLE DB arabirimlerini uygulayan herhangi bir yazılım bileşeni sağlayıcısıdır.  
  
Rolleri açısından bir tüketici OLE DB arabirimleri üzerinde yöntemleri çağırır; bir OLE DB sağlayıcısı gerekli OLE DB arabirimlerini uygular.  
  
OLE DB, bu rolleri her zaman, özellikle bir n katmanlı durumda mantıklı değildir çünkü koşulları istemci ve sunucu önler. Bir tüketici bir bileşen başka bir bileşene hizmet katmanı olabileceğinden, bir istemci çağırmak için bileşen kafa karıştırıcı olacaktır. Ayrıca, bir sağlayıcı bazen daha bir sunucu veritabanı sürücüsünden gibi davranır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Programlama](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB Programlamaya Genel Bakış](../../data/oledb/ole-db-programming-overview.md)