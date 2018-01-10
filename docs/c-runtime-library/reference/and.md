---
title: ve | Microsoft Docs
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
- And
- std.and
- std::and
dev_langs: C++
helpviewer_keywords: and macro
ms.assetid: 2644ab57-8e1b-48f0-9021-cafe3e26bdc4
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1d28d0258584eab48aeaa77eaa78fe7640cb3300
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="and"></a>and
Alternatif & & işleci.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#define and &&  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Makro işleci verir & &.  
  
## <a name="example"></a>Örnek  
  
```  
// iso646_and.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iso646.h>  
  
int main( )  
{  
   using namespace std;  
   bool a = true, b = false, result;  
  
   boolalpha(cout);  
  
   result= a && b;  
   cout << result << endl;  
  
   result= a and b;  
   cout << result << endl;  
}  
```  
  
```Output  
false  
false  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<iso646.h >