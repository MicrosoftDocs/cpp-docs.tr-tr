---
title: bölge, endregion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
dev_langs:
- C++
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e6ec22be873dcec06f224913eb905a2779e4efd
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42465360"
---
# <a name="region-endregion"></a>region, endregion
`#pragma region` Genişlet veya daralt kullanarak bir kod bloğunu belirtmenizi sağlar [anahat oluşturma özelliği](/visualstudio/ide/outlining) Visual Studio Kod Düzenleyicisi'nin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma region name  
#pragma endregion comment  
```  
  
### <a name="parameters"></a>Parametreler  
*Yorum* (isteğe bağlı)  
Kod Düzenleyicisi'nde görüntüleyen bir açıklama.  
  
*Ad* (isteğe bağlı)  
Bölge adı.  Bu ad, Kod Düzenleyicisi'nde görüntülenir.  
  
## <a name="remarks"></a>Açıklamalar  
 
`#pragma endregion` sonunu işaretleyen bir `#pragma region` blok.  
  
A `#region` blok sonlandırıldı, ile `#pragma endregion`.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// pragma_directives_region.cpp  
#pragma region Region_1  
void Test() {}  
void Test2() {}  
void Test3() {}  
#pragma endregion Region_1  
  
int main() {}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)