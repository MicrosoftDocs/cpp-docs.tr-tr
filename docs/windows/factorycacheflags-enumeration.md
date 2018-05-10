---
title: FactoryCacheFlags numaralandırması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
dev_langs:
- C++
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5ba3d9b75ff72399e1b9a027c937c24bba4a6c37
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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