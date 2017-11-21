---
title: "Varsayılan ad alanı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: 4712e9dc-57ba-43cc-811e-022e1dae4de8
caps.latest.revision: "6"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 9d1c04acc5754627906448db9ac4f3afd65fbe7c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="default-namespace"></a>Varsayılan ad alanı
`default` Ad alanı kapsamlarını, C + tarafından desteklenen yerleşik türleri +/ CX.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
namespace default;  
```  
  
### <a name="members"></a>Üyeler  
 Tüm yerleşik türleri aşağıdaki üyeleri devralır.  
  
|||  
|-|-|  
|[Varsayılan:: (type_name):: eşittir](../cppcx/default-type-name-equals-method.md)|Belirtilen nesnenin geçerli nesneyle eşit olup olmadığını belirler.|  
|[Varsayılan:: (type_name):: GetHashCode](../cppcx/default-type-name-gethashcode-method.md)|Bu örneğin karma kodunu döndürür.|  
|[Varsayılan:: (type_name):: GetType](../cppcx/default-type-name-gettype-method.md)|Geçerli türünü temsil eden bir dize döndürür.|  
|[Varsayılan:: (type_name):: ToString](../cppcx/default-type-name-tostring-method.md)|Geçerli türünü temsil eden bir dize döndürür.|  
  
### <a name="built-in-types"></a>Yerleşik türler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`char16`|Unicode (UTF-16) kod noktası temsil eden bir 16 bit sayısal değer.|  
|`float32`|Bir 32 bit IEEE 754 kayan noktalı sayı.|  
|`float64`|Bir 64-bit IEEE 754 kayan noktalı sayı.|  
|`int16`|Bir 16 bit işaretli tamsayıyı.|  
|`int32`|32 bit imzalı bir tamsayı.|  
|`int64`|64-bit imzalı bir tamsayı.|  
|`int8`|Bir 8 bit imzalı sayısal değer.|  
|`uint16`|Bir 16 bit işaretsiz tamsayı.|  
|`uint32`|Bir 32 bit işaretsiz tamsayı.|  
|`uint64`|Bir 64-bit işaretsiz tamsayı.|  
|`uint8`|Bir 8 bit işaretsiz sayısal değer.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** vccorlib.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ Dil Başvurusu](../cppcx/visual-c-language-reference-c-cx.md)