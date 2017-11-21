---
title: copy_backward (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::copy_backward
dev_langs: C++
helpviewer_keywords: copy_backward function [STL/CLR]
ms.assetid: 649db3fd-5a79-44b6-bea9-ecbcbeba1f32
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9d9138ef071acd984826add535bba57f86b00864
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="copybackward-stlclr"></a>copy_backward (STL/CLR)
Bir kaynak aralığındaki öğe değerlerini bir hedef aralığına atayarak, öğelerin kaynak sırası boyunca yineler ve bunları yeni konumlarına geri yönde atar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class _BidIt1, class _BidIt2> inline  
    _BidIt2 copy_backward(_BidIt1 _First, _BidIt1 _Last,  
        _BidIt2 _Dest);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev C++ Standart Kitaplığı işlevi ile aynı şekilde davranır `copy_backward`. Daha fazla bilgi için bkz: [copy_backward](../standard-library/algorithm-functions.md#copy_backward).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/algoritması >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [algoritma (STL/CLR)](../dotnet/algorithm-stl-clr.md)