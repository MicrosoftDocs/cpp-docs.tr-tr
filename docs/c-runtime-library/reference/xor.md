---
title: Xor | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- Xor
- std::xor
- std.xor
dev_langs:
- C++
helpviewer_keywords:
- xor function
ms.assetid: 0fe9554b-d87b-4487-92ed-366c6dc21df2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b899703833f2506439c58db5f9f19e64b9378d1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="xor"></a>xor
^ işleci alternatifi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#define xor ^  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Makro, ^ işlecini verir.  
  
## <a name="example"></a>Örnek  
  
```  
// iso646_xor.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iso646.h>  
  
int main( )  
{  
   using namespace std;  
   int a = 3, b = 2, result;  
  
   result= a ^ b;  
   cout << result << endl;  
  
   result= a xor_eq b;  
   cout << result << endl;  
}  
```  
  
```Output  
1  
1  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<iso646.h >