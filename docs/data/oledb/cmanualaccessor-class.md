---
title: "CManualAccessor sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CManualAccessor
- ATL.CManualAccessor
- CManualAccessor
dev_langs:
- C++
helpviewer_keywords:
- CManualAccessor class
ms.assetid: a0088074-7135-465c-b228-69097a50b8cc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ecb9f31c862f62ddc2422f201aa824a959e961a0
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="cmanualaccessor-class"></a>CManualAccessor Sınıfı
Gelişmiş kullanılmak üzere tasarlanmış bir erişimci türünü temsil eder.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CManualAccessor : public CAccessorBase  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md)|Çıkış sütunlarında bir BIND girdisi ekler.|  
|[AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md)|Parametre giriş parametre erişimcisi ekler.|  
|[CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md)|Bağ yapıları sütunu için bellek ayırır ve sütun veri üyelerine başlatır.|  
|[CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md)|Bağ yapıları parametresi için bellek ayırır ve parametre veri üyeleri başlatır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanarak `CManualAccessor`, parametresini belirtin ve çalışma zamanı işlev çağrıları sütun bağlama çıktı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DBViewer](../../visual-cpp-samples.md)   
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor sınıfı](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor sınıfı](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor Sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)