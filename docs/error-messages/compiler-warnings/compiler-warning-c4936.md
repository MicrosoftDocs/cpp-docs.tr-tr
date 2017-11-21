---
title: "Derleyici Uyarısı C4936 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4936
dev_langs: C++
helpviewer_keywords: C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a4342c749c5db4d66f206209a146ad7d7aef7041
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-c4936"></a>Derleyici Uyarısı C4936
Bu __declspec yalnızca/CLR veya/CLR ile derlendiğinde desteklenir: Saf  
  
 **/CLR: pure** derleyici seçeneği Visual Studio 2015'te kullanım dışıdır.  
  
 A `__declspec` değiştiricisi, ancak kullanıldı `__declspec` değiştiricisi geçerli yalnızca biri ile derlendiğinde [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) seçenekleri.  
  
 Daha fazla bilgi için bkz: [appdomain](../../cpp/appdomain.md) ve [işlem](../../cpp/process.md).  
  
 C4936 her zaman hata olarak verilir.  C4936 ile devre dışı bırakabilirsiniz [uyarı](../../preprocessor/warning.md) pragması.  
  
 Aşağıdaki örnek C4936 oluşturur:  
  
```  
// C4936.cpp  
// compile with: /c  
// #pragma warning (disable : 4936)  
__declspec(process) int i;   // C4936  
__declspec(appdomain) int j;   // C4936  
```