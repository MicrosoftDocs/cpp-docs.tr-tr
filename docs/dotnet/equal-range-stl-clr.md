---
title: equal_range (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::equal_range
dev_langs:
- C++
helpviewer_keywords:
- equal_range function [STL/CLR]
ms.assetid: 1b2e76c3-6b52-486d-9785-2639b54277fd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9001d4b39b1b20e2caa7b5d81ac3b06d42042071
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105874"
---
# <a name="equalrange-stlclr"></a>equal_range (STL/CLR)
Sıralanmış aralıktaki konumların çiftini bulur, birinci belirtilen bir öğenin konumundan küçük veya ona eşittir ve ikinci öğenin konumundan büyüktür, burada dizideki konumlar oluşturmak için kullanılan denkliğin veya sıralamanın anlamı bir ikili koşula göre belirtilebilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class _FwdIt, class _Ty> inline  
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val);  
template<class _FwdIt, class _Ty, class _Pr> inline  
    _PAIR_TYPE(_FwdIt) equal_range(_FwdIt _First, _FwdIt _Last,  
        const _Ty% _Val, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlev C++ Standart Kitaplığı işlevi ile aynı şekilde davranır `equal_range`. Daha fazla bilgi için bkz: [equal_range](../standard-library/algorithm-functions.md#equal_range).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/algoritması >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)