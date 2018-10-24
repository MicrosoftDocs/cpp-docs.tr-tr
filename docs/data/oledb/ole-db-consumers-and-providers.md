---
title: OLE DB Tüketicileri ve sağlayıcıları | Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
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
ms.openlocfilehash: 3a6290c923b5aa4b54a71bda5f0617d1b3acc8db
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2018
ms.locfileid: "49989872"
---
# <a name="ole-db-consumers-and-providers"></a>OLE DB Tüketicileri ve Sağlayıcıları

OLE DB Mimari Tüketicileri ve sağlayıcıları modelini kullanır. Bir tüketici veri istekleri yapar. Bir sağlayıcı verileri tablo biçiminde yerleştirip tüketiciye döndürmeden bu isteklere yanıt verir. Tüketici yapabilen herhangi bir çağrı sağlayıcısında uygulanmalıdır.  
  
Teknik olarak tanımlanan bir tüketici OLE DB arabirimleri aracılığıyla verilere erişen tüm sistem veya uygulama (OLE DB bileşeni gerekmez) kodudur. Arabirimler sağlayıcı uygulanır. Bu nedenle bir OLE DB veri erişimi kapsülleyen ve diğer nesneleri (diğer bir deyişle, tüketiciler) üzerinden kullanıma sunacaksınız arabirimleri uygulayan herhangi bir yazılım bileşeni sağlayıcısıdır.  
  
Roller için bir tüketici OLE DB arabirimleri üzerinde yöntemleri çağırır; bir OLE DB sağlayıcısı gerekli OLE DB arabirimlerini uygular.  
  
OLE DB, çünkü bu rollerin her zaman, özellikle bir n katmanlı durumda anlamsız koşulları istemci ve sunucu önler. Bir tüketici bir bileşen başka bir bileşene hizmet katmanı olabileceğinden, bir istemci çağırmak için bileşen kafa karıştırıcı olacaktır. Ayrıca, bir sağlayıcı bazen daha bir sunucu veritabanı sürücüsünden gibi davranır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Programlama](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB Programlamaya Genel Bakış](../../data/oledb/ole-db-programming-overview.md)