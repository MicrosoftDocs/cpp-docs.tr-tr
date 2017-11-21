---
title: make_heap (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::make_heap
dev_langs: C++
helpviewer_keywords: make_heap function [STL/CLR]
ms.assetid: bc1bed28-7a26-4540-901d-5584cd117ea1
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 970cbe054aed2f5809e5acc05bad480e8f634349
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="makeheap-stlclr"></a>make_heap (STL/CLR)
Belirtilen bir aralıktaki öğeleri ilk öğenin en büyük olduğu ve onun için bir ikili koşula sahip bir sıralama ölçütünün belirtilebildiği bir yığına dönüştürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class _RanIt> inline  
    void make_heap(_RanIt _First, _RanIt _Last);  
template<class _RanIt, class _Pr> inline  
    void make_heap(_RanIt _First, _RanIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev C++ Standart Kitaplığı işlevi ile aynı şekilde davranır `make_heap`. Daha fazla bilgi için bkz: [make_heap](../standard-library/algorithm-functions.md#make_heap).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/algoritması >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [algoritma (STL/CLR)](../dotnet/algorithm-stl-clr.md)