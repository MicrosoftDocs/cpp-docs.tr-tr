---
title: count_if (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- cliext::count_if
dev_langs:
- C++
helpviewer_keywords:
- count_if function [STL/CLR]
ms.assetid: a8aa149d-20b8-4b3f-917b-1ec66f178a5d
caps.latest.revision: 4
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 80436e1920b53af284c8029766fc27320c9c1472
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="countif-stlclr"></a>count_if (STL/CLR)
Değerleri belirtilen bir koşulla eşleşen bir aralıktaki öğelerin sayısını döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class _InIt, class _Pr> inline  
    typename iterator_traits<_InIt>::difference_type  
        count_if(_InIt _First, _InIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev C++ Standart Kitaplığı işlevi ile aynı şekilde davranır `count_if`. Daha fazla bilgi için bkz: [count_if](../standard-library/algorithm-functions.md#count_if).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/algoritması >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)