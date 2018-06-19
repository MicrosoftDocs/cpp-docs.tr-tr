---
title: Derleyici Hatası C2784 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2784
dev_langs:
- C++
helpviewer_keywords:
- C2784
ms.assetid: 3d761fe2-881c-48bd-afae-e2e714e20473
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: beca5e3db426828eeec884cfc8e5e6048006fcd5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233324"
---
# <a name="compiler-error-c2784"></a>Derleyici Hatası C2784
'bildirimi': 'type' için şablon bağımsız değişken 'türünden' modülüne yapılan değil  
  
 Derleyici bir şablon bağımsız değişkenden sağlanan işlev bağımsız değişkenleri belirleyemiyor.  
  
 Aşağıdaki örnek C2784 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2784.cpp  
template<class T> class X {};  
template<class T> void f(X<T>) {}  
  
int main() {  
   X<int> x;  
   f(1);   // C2784  
  
   // To fix it, try the following line instead  
   f(x);  
}  
```