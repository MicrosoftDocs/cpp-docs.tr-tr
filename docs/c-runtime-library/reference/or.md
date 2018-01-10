---
title: veya | Microsoft Docs
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
- std::or
- std.or
- Or
dev_langs: C++
helpviewer_keywords: or function
ms.assetid: 6523b3ac-0a18-44ec-9e9a-b9bab8525ead
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6746cb23ef48fb0ac8bf3c5c87770c9df7522dbb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="or"></a>veya
Alternatif &#124; &#124; işleç.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#define or ||  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Makro işleci &#124; &#124;verir;.  
  
## <a name="example"></a>Örnek  
  
```  
// iso646_or.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iso646.h>  
  
int main( )  
{  
   using namespace std;  
   bool a = true, b = false, result;  
  
   boolalpha(cout);  
  
   result= a || b;  
   cout << result << endl;  
  
   result= a or b;  
   cout << result << endl;  
}  
```  
  
```Output  
true  
true  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<iso646.h >