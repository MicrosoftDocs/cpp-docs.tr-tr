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
ms.openlocfilehash: bb4efeb716255ae67a01fca7cf04a54816e227d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Microsoft::WRL Namespace](../windows/microsoft-wrl-namespace.md)