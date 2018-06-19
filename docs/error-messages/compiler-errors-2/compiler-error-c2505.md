---
title: Derleyici Hatası C2505 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2505
dev_langs:
- C++
helpviewer_keywords:
- C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fac405fc13b7696f752ea6455dcbf464318dca56
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227667"
---
# <a name="compiler-error-c2505"></a>Derleyici Hatası C2505
'simgesi': '__declspec(modifer)', yalnızca bildirimleri ya da tanımları genel nesne veya statik veri üyeleri uygulanabilir  
  
 A `__declspec` yalnızca genel kapsamda kullanılmak üzere tasarlanmış değiştiricisi bir işlevde kullanıldı.  
  
 Daha fazla bilgi için bkz: [appdomain](../../cpp/appdomain.md) ve [işlem](../../cpp/process.md).  
  
 Aşağıdaki örnek C2505 oluşturur:  
  
```  
// C2505.cpp  
// compile with: /clr  
  
// OK  
__declspec(process) int ii;  
__declspec(appdomain) int jj;  
  
int main() {  
   __declspec(process) int i;   // C2505  
   __declspec(appdomain) int j;   // C2505  
}  
```