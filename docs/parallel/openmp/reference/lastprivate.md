---
title: lastprivate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- lastprivate
dev_langs:
- C++
helpviewer_keywords:
- lastprivate OpenMP clause
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c87dfc47f7f2554e75567a1de4ea9cb2e06eaa00
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028200"
---
# <a name="lastprivate"></a>lastprivate
Değişkeni kapsayan bir bağlamın sürümü hangi iş parçacığının son yineleme (for-döngüsü yapısı) ya da son bölümdeki (#pragma bölümleri) yürüten özel sürümüne eşit ayarlandığını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
lastprivate(var)  
```  
  
### <a name="parameters"></a>Parametreler
  
*var*<br/>
Hangi iş parçacığının özel bir sürümünü ayarlanır değişkeni son yineleme (for-döngüsü yapısı) ya da son bölümdeki (#pragma bölümleri) yürütür.  
  
## <a name="remarks"></a>Açıklamalar  
 `lastprivate` Aşağıdaki yönergeleri için geçerlidir:  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Bölümleri](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Daha fazla bilgi için [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [zamanlama](../../../parallel/openmp/reference/schedule.md) kullanma örneği için `lastprivate` yan tümcesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan Tümceler](../../../parallel/openmp/reference/openmp-clauses.md)