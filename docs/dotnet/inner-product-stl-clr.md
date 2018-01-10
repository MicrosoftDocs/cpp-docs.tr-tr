---
title: inner_product (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::inner_product
dev_langs: C++
helpviewer_keywords: inner_product function [STL/CLR]
ms.assetid: 97d7a507-7494-4216-aedf-0546ed0edb3f
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5d61de34fcb029000ac27efcf74bd1321d1b7e32
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="innerproduct-stlclr"></a>inner_product (STL/CLR)
İki aralıklarının element-wise ürün toplamını hesaplar ve belirtilen ilk değerine ekler veya sum ve ürün ikili işlemleri tarafından belirtilen diğer ikili işlemlerin burada değiştirilir genelleştirilmiş bir yordamın sonuç hesaplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class _InIt1, class _InIt2, class _Ty> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val);  
template<class _InIt1, class _InIt2, class _Ty, class _Fn21,  
       class _Fn22> inline  
    _Ty inner_product(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Ty _Val, _Fn21 _Func1, _Fn22 _Func2);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev C++ Standart Kitaplığı sayısal işlevi ile aynı şekilde davranır `inner_product`. Daha fazla bilgi için bkz: [inner_product](../standard-library/numeric-functions.md#inner_product).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/sayısal >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [numeric (STL/CLR)](../dotnet/numeric-stl-clr.md)