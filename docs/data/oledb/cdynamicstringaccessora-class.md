---
title: CDynamicStringAccessorA sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicStringAccessorA
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e56f71a427fda2444992cc0ed2c3b6166993af1d
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39341029"
---
# <a name="cdynamicstringaccessora-class"></a>CDynamicStringAccessorA Sınıfı
Veritabanı şeması (temelindeki) hiçbir bilgiye sahip olduğunda bir veri kaynağına erişim sağlar.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Her ikisi de sağlayıcı veri deposu olarak dize verileri, erişilen tüm verileri getirme istek ancak `CDynamicStringAccessor` istekleri ANSI veri dizesi.  
  
 `CDynamicStringAccessorA` devralınan `GetString` ve `SetString` gelen `CDynamicStringAccessor`. Bu yöntemleri kullanırken bir `CDynamicStringAccessorA` nesnesi ***BaseType*** olduğu **CHAR**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Üst bilgi**: atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor sınıfı](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor sınıfı](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor sınıfı](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor Sınıfı](../../data/oledb/cdynamicstringaccessor-class.md)