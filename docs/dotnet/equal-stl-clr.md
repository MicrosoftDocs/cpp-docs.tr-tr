---
title: "eşit (STL/CLR) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::equal
dev_langs: C++
helpviewer_keywords: equal function [STL/CLR]
ms.assetid: 7f271666-2198-4e33-8e03-8b73b376c724
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e289a2a8f18dc1064e40c74e91bb68d215a4a174
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="equal-stlclr"></a>eşit (STL/CLR)
Bir ikili koşula göre belirtilen anlamda eşitlik ya da denklik için iki aralık öğesini öğeye göre karşılaştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class _InIt1, class _InIt2> inline  
    bool equal(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    bool equal(_InIt1 _First1, _InIt1 _Last1, _InIt2 _First2,  
        _Pr _Pred);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev C++ Standart Kitaplığı işlevi ile aynı şekilde davranır `equal`. Daha fazla bilgi için bkz: [eşit](../standard-library/algorithm-functions.md#equal).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/algoritması >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [algoritma (STL/CLR)](../dotnet/algorithm-stl-clr.md)