---
title: accumulate (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::accumulate
dev_langs:
- C++
helpviewer_keywords:
- accumulate function [STL/CLR]
ms.assetid: b80e1ef1-1858-4c1d-817b-c42ad1f17a2f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d9fefc3e7e7a2838891488996518b405972ba0f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="accumulate-stlclr"></a>biriktir (STL/CLR)
Tüm öğelerin toplamı, art arda kısmi toplamlarını bilgi işlem tarafından bazı başlangıç değeri de dahil olmak üzere belirli bir aralık içinde hesaplar veya benzer şekilde toplam dışında belirtilen bir ikili işlem kullanılarak elde edilen art arda kısmi sonuçlar sonucunu hesaplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class _InIt, class _Ty> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val);  
template<class _InIt, class _Ty, class _Fn2> inline  
    _Ty accumulate(_InIt _First, _InIt _Last, _Ty _Val, _Fn2 _Func);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev C++ Standart Kitaplığı sayısal işlevi ile aynı şekilde davranır `accumulate`. Daha fazla bilgi için bkz: [accumulate](../standard-library/numeric-functions.md#accumulate).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/sayısal >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [numeric (STL/CLR)](../dotnet/numeric-stl-clr.md)