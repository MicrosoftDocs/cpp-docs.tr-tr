---
title: remove_copy (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::remove_copy
dev_langs: C++
helpviewer_keywords: remove_copy function [STL/CLR]
ms.assetid: 602fd8e3-26f7-491f-bf2c-cddf269f9807
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9d4b7a400e089ec8fb4be21e39f31b5562c5df24
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="removecopy-stlclr"></a>remove_copy (STL/CLR)
Öğeleri, belirtilen değerin kopyalanmayan öğeleri hariç, kalan öğelerin sırasını bozmadan ve yeni hedef aralığın sonuna döndürerek bir kaynak aralıktan bir hedef aralığa kopyalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class _InIt, class _OutIt, class _Ty> inline  
    _OutIt remove_copy(_InIt _First, _InIt _Last,  
        _OutIt _Dest, const _Ty% _Val);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev C++ Standart Kitaplığı işlevi ile aynı şekilde davranır `remove_copy`. Daha fazla bilgi için bkz: [remove_copy](../standard-library/algorithm-functions.md#remove_copy).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/algoritması >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)