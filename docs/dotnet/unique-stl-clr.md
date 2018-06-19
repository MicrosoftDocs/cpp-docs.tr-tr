---
title: benzersiz (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::unique
dev_langs:
- C++
helpviewer_keywords:
- unique function [STL/CLR]
ms.assetid: 833cc314-b452-4659-bbb4-575c2bb63855
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 95e4ae3fe883f122f3a806dbcba017a0161c84b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164173"
---
# <a name="unique-stlclr"></a>benzersiz (STL/CLR)
Belirli bir aralıktaki birbirine bitişik yinelenen öğeleri kaldırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class _FwdIt> inline  
    _FwdIt unique(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt unique(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev C++ Standart Kitaplığı işlevi ile aynı şekilde davranır `unique`. Daha fazla bilgi için bkz: [benzersiz](../standard-library/algorithm-functions.md#unique).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/algoritması >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)