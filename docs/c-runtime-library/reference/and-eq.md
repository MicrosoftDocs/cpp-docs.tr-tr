---
title: and_eq | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
- and_eq
- std.and_eq
- std::and_eq
dev_langs: C++
helpviewer_keywords: and_eq macro
ms.assetid: 11091772-e359-4c2b-95c6-00841ac04354
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 119747054f2996f021db7deab604613f3dc0b184
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="andeq"></a>and_eq
Alternatif & = işleci.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#define and_eq &=  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Makro & = işleci verir.  
  
## <a name="example"></a>Örnek  
  
```  
// iso646_and_eq.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iso646.h>  
  
int main( )  
{  
   using namespace std;  
   int a = 3, b = 2, result;  
  
   result= a &= b;  
   cout << result << endl;  
  
   result= a and_eq b;  
   cout << result << endl;  
}  
```  
  
```Output  
2  
2  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<iso646.h >