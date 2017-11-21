---
title: "CManualAccessor sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CManualAccessor
- ATL.CManualAccessor
- CManualAccessor
dev_langs: C++
helpviewer_keywords: CManualAccessor class
ms.assetid: a0088074-7135-465c-b228-69097a50b8cc
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f368bbb2f56497ecb16dc2cbfd2f8cf7d214e5cc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmanualaccessor-class"></a>CManualAccessor Sınıfı
Gelişmiş kullanılmak üzere tasarlanmış bir erişimci türünü temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
 [DBVIEWER](../../visual-cpp-samples.md)   
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor sınıfı](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor sınıfı](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)