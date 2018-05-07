---
title: partial_sum (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::partial_sum
dev_langs:
- C++
helpviewer_keywords:
- partial_sum function [STL/CLR]
ms.assetid: 845badae-8519-4ac8-9ea7-2b921bac7c51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0c8141e93d7c8101c9bbfaea08c317748cd44f87
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="partialsum-stlclr"></a>partial_sum (STL/CLR)
SUM'ları ilk öğe ile bir giriş aralığında bir dizi hesaplar `i`th öğesi ve her tür toplamda sonucunu depolar `i`th öğesi bir hedef aralığının veya genel bir yordam sonucunu hesaplar burada toplam işlem Belirtilen başka bir ikili işlem tarafından değiştirilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last, _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt partial_sum(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev C++ Standart Kitaplığı sayısal işlevi ile aynı şekilde davranır `partial_sum`. Daha fazla bilgi için bkz: [partial_sum](../standard-library/numeric-functions.md#partial_sum).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/sayısal >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [numeric (STL/CLR)](../dotnet/numeric-stl-clr.md)