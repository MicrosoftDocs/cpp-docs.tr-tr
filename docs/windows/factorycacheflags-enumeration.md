---
title: FactoryCacheFlags sabit listesi | Microsoft Docs
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
ms.openlocfilehash: cc4bd998368fb325878a81ee4954a2ceec9432fe
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570109"
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags Numaralandırması
Fabrika nesneleri önbelleğe alınıp alınmayacağını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum FactoryCacheFlags;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, önbelleğe alma İlkesi Fabrika olarak belirtilen [ModuleType](../windows/moduletype-enumeration.md) oluşturduğunuzda şablon parametresi bir [Modülü](../windows/module-class.md) nesne. Bu ilkeyi geçersiz kılmak için belirtin bir **FactoryCacheFlags** değeri bir Fabrika nesnesine oluşturduğunuzda.  
  
|||  
|-|-|  
|`FactoryCacheDefault`|Önbelleğe alma İlkesi, `Module` nesnesi kullanılır.|  
|`FactoryCacheEnabled`|Fabrika bağımsız olarak, önbelleğe alınmasını etkinleştirir `ModuleType` oluşturmak için kullanılan şablon parametresi bir `Module` nesne.|  
|`FactoryCacheDisabled`|Fabrika bağımsız olarak, önbelleğe alma devre dışı bırakır `ModuleType` oluşturmak için kullanılan şablon parametresi bir `Module` nesne.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)