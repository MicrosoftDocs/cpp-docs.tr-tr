---
title: max_element (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::max_element
dev_langs: C++
helpviewer_keywords: max_element function [STL/CLR]
ms.assetid: c6274bae-1216-4285-b395-254280253dae
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: aebe6addd047130918ce16718122ff42cebb0cd0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="maxelement-stlclr"></a>max_element (STL/CLR)
Belirtilen bir aralıktaki en büyük öğenin geçtiği ilk yeri bulur, burada sıralama ölçütü bir ikili koşula göre belirtilebilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class _FwdIt> inline  
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev C++ Standart Kitaplığı işlevi ile aynı şekilde davranır `max_element`. Daha fazla bilgi için bkz: [max_element](../standard-library/algorithm-functions.md#max_element).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/algoritması >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)