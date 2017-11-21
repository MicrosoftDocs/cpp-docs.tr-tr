---
title: bitor | Microsoft Docs
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
- bitor
- std.bitor
- std::bitor
dev_langs: C++
helpviewer_keywords: bitor function
ms.assetid: 3c0a3711-9c74-41f2-b400-2f7797da30d1
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7f840179a2087138ce46c1ec2c9ba16acd20bc70
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="bitor"></a>bitor
Alternatif &#124; işleç.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
#define bitor |  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Makro işleci &#124;verir;.  
  
## <a name="example"></a>Örnek  
  
```  
// iso646_bitor.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iso646.h>  
  
int main( )  
{  
   using namespace std;  
   int a = 1, b = 2, result;  
  
   result = a | b;  
   cout << result << endl;  
  
   result= a bitor b;  
   cout << result << endl;  
}  
```  
  
```Output  
3  
3  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<iso646.h >