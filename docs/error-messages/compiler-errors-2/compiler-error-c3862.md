---
title: "Derleyici Hatası C3862 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3862
dev_langs:
- C++
helpviewer_keywords:
- C3862
ms.assetid: ba547366-4189-4077-8c00-ab45e08a9533
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 63fa12348ee2ab58782fad02719918bfe7929ff8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3862"></a>Derleyici Hatası C3862
'function': / CLR ile yönetilmeyen işlev derlenemiyor: Saf veya/CLR: safe  
  
 **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
 Derleme ile **/CLR: pure** veya **/CLR: safe** görüntüyü yerel (yönetilmeyen) kod olmadan bir MSIL yalnızca görüntü oluşturur.  Bu nedenle, kullanamazsınız `unmanaged` pragma içinde bir **/CLR: pure** veya **/CLR: safe** derleme.  
  
 Daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ve [yönetilen, yönetilmeyen](../../preprocessor/managed-unmanaged.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3862 oluşturur:  
  
```  
// C3862.cpp  
// compile with: /clr:pure /c  
#pragma unmanaged  
void f() {}   // C3862  
```