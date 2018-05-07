---
title: Derleyici Uyarısı (düzey 1) C4794 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4794
dev_langs:
- C++
helpviewer_keywords:
- C4794
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88ffa1200e7c760f028549335f0df5a9ea8ba3d5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4794"></a>Derleyici Uyarısı (düzey 1) C4794
iş parçacığı yerel depolama değişken '' bölüm adından' değiştirilen '.tls$ ' değişkeni' parçası  
  
 Kullanılan [#pragma data_seg](../../preprocessor/data-seg.md) başlangıç değil .tls$ ile bir bölümdeki bir tls değişken yerleştirilecek.  
  
 .Tls$*x* bölüm nesne dosyasında var olduğu [__declspec(thread)](../../cpp/thread.md) değişkenleri tanımlanır. EXE ya da DLL .tls bölümünde bu bölümlerden neden olur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4794 oluşturur:  
  
```  
// C4794.cpp  
// compile with: /W1 /c  
#pragma data_seg(".someseg")  
__declspec(thread) int i;   // C4794  
  
// OK  
#pragma data_seg(".tls$9")  
__declspec(thread) int j;  
```