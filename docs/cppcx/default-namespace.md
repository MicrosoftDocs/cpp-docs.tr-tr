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
ms.workload: cplusplus
ms.openlocfilehash: 5a9d538e42d4173008343df186bd2579dc088fb5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
|[default::(type_name)::Equals](../cppcx/default-type-name-equals-method.md)|Belirtilen nesnenin geçerli nesneyle eşit olup olmadığını belirler.|  
|[default::(type_name)::GetHashCode](../cppcx/default-type-name-gethashcode-method.md)|Bu örneğin karma kodunu döndürür.|  
|[default::(type_name)::GetType](../cppcx/default-type-name-gettype-method.md)|Geçerli türünü temsil eden bir dize döndürür.|  
|[default::(type_name)::ToString](../cppcx/default-type-name-tostring-method.md)|Geçerli türünü temsil eden bir dize döndürür.|  
  
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