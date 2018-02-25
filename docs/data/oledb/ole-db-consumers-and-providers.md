---
title: "OLE DB Tüketicileri ve sağlayıcıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ec0a8764ef8f5e906ad399d76a5a004c313f500b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ole-db-consumers-and-providers"></a>OLE DB Tüketicileri ve Sağlayıcıları
OLE DB Mimari Tüketicileri ve sağlayıcıları modelini kullanır. Bir tüketici veri isteğinde bulunur. Bir sağlayıcı tablo biçiminde veri yerleştirip tüketiciye dönmeden bu isteklere yanıt verir. Tüketici yapabilen herhangi bir çağrısına sağlayıcısında uygulanmalıdır.  
  
 Teknik olarak tanımlanan bir tüketici OLE DB arabirimleri aracılığıyla verilere erişen tüm sistem veya uygulama (OLE DB bileşen gerekmez) kodudur. Arabirimler sağlayıcı uygulanır. Bu nedenle, bir veri erişimi kapsüllemek ve başka nesnelere (tüketiciler) kullanıma sunmak için OLE DB arabirimlerini uygulayan herhangi bir yazılım bileşeni sağlayıcıdır.  
  
 Roller açısından bir tüketici OLE DB arabirimlerinde yöntemlerini çağıran; OLE DB sağlayıcısı gerekli OLE DB arabirimlerini uygular.  
  
 Bu rolleri her zaman, özellikle bir n katmanlı durumda anlamlı değil çünkü OLE DB koşulları istemci ve sunucu önler. Bir tüketici başka bir bileşene hizmet katmanında bir bileşeni olabilir çünkü bir istemci çağırmak için bileşen kafa karıştırıcı olacaktır. Ayrıca, bir sağlayıcı bazen daha sunucu veritabanı sürücüsünden gibi davranır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB programlama](../../data/oledb/ole-db-programming.md)   
 [OLE DB Programlamaya Genel Bakış](../../data/oledb/ole-db-programming-overview.md)