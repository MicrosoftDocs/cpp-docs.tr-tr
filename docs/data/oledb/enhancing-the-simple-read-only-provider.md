---
title: Basit salt okunur sağlayıcıyı geliştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- read-only poviders [C++]
- IRowsetLocate class
- IRowsetLocate class, adding to OLE DB template providers
- simple read-only poviders [C++]
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7c88714e4e1651839cdc5fd4b92d3c5222aa08d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100024"
---
# <a name="enhancing-the-simple-read-only-provider"></a>Basit Salt Okunur Sağlayıcıyı Geliştirme
Bu bölümde, geliştirmek gösterilmiştir [basit salt okunur sağlayıcıyı](../../data/oledb/implementing-the-simple-read-only-provider.md) önceki bölümde oluşturduğunuz. `IRowsetLocateImpl` için bir uygulama oluşturur `IRowsetLocate` arabirim ve, yer işareti desteği ekler.  
  
 Bir çalışma sağlayıcınız yoksa işlemleri işlemek veya satır getirme algoritması performansını geliştiren sağlayıcı güncelleştirme yapmak için geliştirmek isteyebilirsiniz. Varolan bir COM nesnesi arabirim ekleme çoğu sağlayıcı geliştirmeleri içerir.  
  
 Aşağıdaki konular örnekte ekleyerek satır getirme mekanizmasını geliştirir `IRowsetLocate` arabirimini `CAgentRowset`. Konular şunları nasıl yapacağınızı için:  
  
-   [IRowsetLocate devralınan RMyProviderRowset olun](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md).  
  
-   [Tüketiciye döndürülecek olan sütunları dinamik olarak belirleyen](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Basit Bir Salt Okunur Sağlayıcı Oluşturma](../../data/oledb/creating-a-simple-read-only-provider.md)