---
title: "bölge, endregion | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
dev_langs: C++
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad2eb3d094447ae3ae35b0dbe9dc0fef2fe06710
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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