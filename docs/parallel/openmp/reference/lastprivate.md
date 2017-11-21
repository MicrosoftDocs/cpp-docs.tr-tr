---
title: lastprivate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: lastprivate
dev_langs: C++
helpviewer_keywords: lastprivate OpenMP clause
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9429a54a21d58be7f2dd1667478ae653da5a8c35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="lastprivate"></a>lastprivate
Değişkeni kapsayan bağlamın sürümünü son yineleme (döngü için yapı) ya da son Kısım (#pragma bölümleri) hangi iş parçacığı yürütür özel sürümü için eşit olarak ayarlanır belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
lastprivate(var)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada,  
  
 `var`  
 Hangi iş parçacığı özel sürümüne eşit olarak ayarlanır değişkeni son yineleme (döngü için yapı) ya da son Kısım (#pragma bölümleri) yürütür.  
  
## <a name="remarks"></a>Açıklamalar  
 `lastprivate`Aşağıdaki yönergeleri için geçerlidir:  
  
-   [için](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [bölümler](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Daha fazla bilgi için bkz: [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [zamanlama](../../../parallel/openmp/reference/schedule.md) kullanma örneği için `lastprivate` yan tümcesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yan tümceleri](../../../parallel/openmp/reference/openmp-clauses.md)