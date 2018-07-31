---
title: CDynamicStringAccessorW sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicStringAccessorW
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessorW class
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fb3e12853d384f433674331342541b7e69241d4a
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340494"
---
# <a name="cdynamicstringaccessorw-class"></a>CDynamicStringAccessorW Sınıfı
Veritabanı şeması (temelindeki) hiçbir bilgiye sahip olduğunda bir veri kaynağına erişim sağlar.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
typedef CDynamicStringAccessorT<WCHAR, DBTYPE_WSTR> CDynamicStringAccessorW;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Her ikisi de sağlayıcı veri deposu olarak dize verileri, erişilen tüm verileri getirme istek ancak `CDynamicStringAccessor` Unicode dize verileri ister.  
  
 `CDynamicStringAccessorW` devralınan `GetString` ve `SetString` gelen `CDynamicStringAccessor`. Bu yöntemleri kullanırken bir `CDynamicStringAccessorW` nesnesi ***BaseType*** olduğu **WCHAR**.  
  
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