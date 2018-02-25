---
title: "CDynamicStringAccessorA sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicStringAccessorA
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b7dfd677d0a0090946cfa7d6a19ac36e1da57a0f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicstringaccessora-class"></a>CDynamicStringAccessorA Sınıfı
Veritabanı şeması (temel yapısı) olanağıyla varsa, bir veri kaynağına erişim sağlar.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Her ikisi de sağlayıcı dize verileri, veri deposundan erişilen tüm veriler getirilemedi isteği ancak `CDynamicStringAccessor` istekleri ANSI dize verileri.  
  
 `CDynamicStringAccessorA` devralınan **GetString** ve `SetString` gelen `CDynamicStringAccessor`. Bu yöntemleri kullandığınızda, bir `CDynamicStringAccessorA` nesnesi ***BaseType*** olan **CHAR**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi**: atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor sınıfı](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor sınıfı](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor sınıfı](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor Sınıfı](../../data/oledb/cdynamicstringaccessor-class.md)