---
title: "Basit salt okunur sağlayıcıyı geliştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- read-only poviders [C++]
- IRowsetLocate class
- IRowsetLocate class, adding to OLE DB template providers
- simple read-only poviders [C++]
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 30b87ecae6f479c912c937fb2ce23e1f9dc98da3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="enhancing-the-simple-read-only-provider"></a>Basit Salt Okunur Sağlayıcıyı Geliştirme
Bu bölümde, geliştirmek gösterilmiştir [basit salt okunur sağlayıcıyı](../../data/oledb/implementing-the-simple-read-only-provider.md) önceki bölümde oluşturduğunuz. `IRowsetLocateImpl`için bir uygulama oluşturur `IRowsetLocate` arabirim ve, yer işareti desteği ekler.  
  
 Bir çalışma sağlayıcınız yoksa işlemleri işlemek veya satır getirme algoritması performansını geliştiren sağlayıcı güncelleştirme yapmak için geliştirmek isteyebilirsiniz. Varolan bir COM nesnesi arabirim ekleme çoğu sağlayıcı geliştirmeleri içerir.  
  
 Aşağıdaki konular örnekte ekleyerek satır getirme mekanizmasını geliştirir `IRowsetLocate` arabirimini `CAgentRowset`. Konular şunları nasıl yapacağınızı için:  
  
-   [IRowsetLocate devralınan RMyProviderRowset olun](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md).  
  
-   [Tüketiciye döndürülecek olan sütunları dinamik olarak belirleyen](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Basit salt okunur sağlayıcı oluşturma](../../data/oledb/creating-a-simple-read-only-provider.md)