---
title: "OLE DB Tüketicileri ve sağlayıcıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB providers, OLE DB data architecture
- OLE DB providers
- OLE DB consumers, OLE DB data architecture
- OLE DB consumers
- OLE DB, data model
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cd09e1566a6f53244d420387870a03b0b34f8fb6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ole-db-consumers-and-providers"></a>OLE DB Tüketicileri ve Sağlayıcıları
OLE DB Mimari Tüketicileri ve sağlayıcıları modelini kullanır. Bir tüketici veri isteğinde bulunur. Bir sağlayıcı tablo biçiminde veri yerleştirip tüketiciye dönmeden bu isteklere yanıt verir. Tüketici yapabilen herhangi bir çağrısına sağlayıcısında uygulanmalıdır.  
  
 Teknik olarak tanımlanan bir tüketici OLE DB arabirimleri aracılığıyla verilere erişen tüm sistem veya uygulama (OLE DB bileşen gerekmez) kodudur. Arabirimler sağlayıcı uygulanır. Bu nedenle, bir veri erişimi kapsüllemek ve başka nesnelere (tüketiciler) kullanıma sunmak için OLE DB arabirimlerini uygulayan herhangi bir yazılım bileşeni sağlayıcıdır.  
  
 Roller açısından bir tüketici OLE DB arabirimlerinde yöntemlerini çağıran; OLE DB sağlayıcısı gerekli OLE DB arabirimlerini uygular.  
  
 Bu rolleri her zaman, özellikle bir n katmanlı durumda anlamlı değil çünkü OLE DB koşulları istemci ve sunucu önler. Bir tüketici başka bir bileşene hizmet katmanında bir bileşeni olabilir çünkü bir istemci çağırmak için bileşen kafa karıştırıcı olacaktır. Ayrıca, bir sağlayıcı bazen daha sunucu veritabanı sürücüsünden gibi davranır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB programlama](../../data/oledb/ole-db-programming.md)   
 [OLE DB programlamaya genel bakış](../../data/oledb/ole-db-programming-overview.md)