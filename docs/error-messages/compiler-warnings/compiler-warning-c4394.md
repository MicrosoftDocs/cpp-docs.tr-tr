---
title: "Derleyici Uyarısı C4394 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4394
dev_langs:
- C++
helpviewer_keywords:
- C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6ab51a4f818e8eb8a94150424124a5c96ebaf241
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4394"></a>Derleyici Uyarısı C4394
'function': appdomain başına simgesi işaretlenmemiş __declspec(dllexport) ile  
  
 Bir işlevi olarak [appdomain](../../cpp/appdomain.md) `__declspec` değiştiricisi (için yerel) MSIL ve dışarı aktarma tabloları derlenmiş ([verme](../../windows/export.md) `__declspec` değiştiricisi) yönetilen işlevleri için desteklenmez.  
  
 Ortak erişilebilirlik sağlamak için yönetilen bir işlev bildirebilirsiniz. Daha fazla bilgi için bkz: [yazın görünürlük](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) ve [üye görünürlüğü](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility).  
  
 C4394 her zaman hata olarak verilir.  Bu uyarı ile kapatabilirsiniz `#pragma warning` veya **/wd**; bkz [uyarı](../../preprocessor/warning.md) veya [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, wln, /wd, / biz, /wo, /Wv, /WX (uyarı düzeyi)](../../build/reference/compiler-option-warning-level.md)daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4394 oluşturur.  
  
```  
// C4394.cpp  
// compile with: /clr /c  
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394  
__declspec(dllexport) int g2 = 0;   // OK  
```