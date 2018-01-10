---
title: "FactoryCacheFlags numaralandırması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::FactoryCacheFlags
dev_langs: C++
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 41b31ccede1cca717418c9f489ab7de67d313319
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags Numaralandırması
Fabrika nesneleri önbelleğe alınıp alınmayacağını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum FactoryCacheFlags;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, ilke önbelleğe alma Fabrika olarak belirtilen [ModuleType](../windows/moduletype-enumeration.md) oluşturduğunuzda şablon parametresi bir [Modülü](../windows/module-class.md) nesnesi. Bu ilkeyi geçersiz kılmak için belirtmek bir `FactoryCacheFlags` değer üreteci nesnesi oluşturduğunuzda.  
  
|||  
|-|-|  
|`FactoryCacheDefault`|Önbelleğe alma İlkesi, `Module` nesnesi kullanılır.|  
|`FactoryCacheEnabled`|Fabrika bağımsız olarak, önbelleğe alınmasını etkinleştirir `ModuleType` oluşturmak için kullanılan şablon parametresi bir `Module` nesnesi.|  
|`FactoryCacheDisabled`|Fabrika bakılmaksızın önbelleğe almayı devre dışı bırakır `ModuleType` oluşturmak için kullanılan şablon parametresi bir `Module` nesnesi.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)