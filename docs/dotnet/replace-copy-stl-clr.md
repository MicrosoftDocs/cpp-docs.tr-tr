---
title: replace_copy (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::replace_copy
dev_langs: C++
helpviewer_keywords: replace_copy function [STL/CLR]
ms.assetid: b531b49b-b16d-4b04-8f80-74f43dd496a4
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f347e8d7f5212900878c645e0c0594935c306088
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="replacecopy-stlclr"></a>replace_copy (STL/CLR)
Bir kaynak aralığındaki her öğeyi inceler ve sonuç yeni bir hedef aralığına kopyalanırken öğe belirtilen değerle eşleşiyorsa, onu değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class _InIt, class _OutIt, class _Ty> inline  
    _OutIt replace_copy(_InIt _First, _InIt _Last, _OutIt _Dest,  
        const _Ty% _Oldval, const _Ty% _Newval);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev C++ Standart Kitaplığı işlevi ile aynı şekilde davranır `replace_copy`. Daha fazla bilgi için bkz: [replace_copy](../standard-library/algorithm-functions.md#replace_copy).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/algoritması >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [algoritma (STL/CLR)](../dotnet/algorithm-stl-clr.md)