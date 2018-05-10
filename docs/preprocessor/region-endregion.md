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
ms.openlocfilehash: 5590d2b251d86a9d20b62bfdb3d5bf929e3d92d4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="region-endregion"></a>region, endregion
**#pragma bölge** Genişlet veya daralt kullanırken kod bloğu belirtmenizi sağlar [özelliği anahat oluşturma](/visualstudio/ide/outlining) Visual Studio Kod Düzenleyicisi'nin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma region name  
#pragma endregion comment  
```  
  
#### <a name="parameters"></a>Parametreler  
 `comment`(isteğe bağlı)  
 Kod Düzenleyicisi'nde görüntüler açıklama.  
  
 *ad*(isteğe bağlı)  
 Bölge adı.  Bu adı Kod Düzenleyicisi'nde görüntülenir.  
  
## <a name="remarks"></a>Açıklamalar  
 **#pragma endregion** sonunu işaretler bir **#pragma bölge** bloğu.  
  
 A `#region` blok sonlandırıldı, ile **#pragma endregion**.  
  
## <a name="example"></a>Örnek  
  
```  
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