---
title: Derleyici Hatası C2780 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2780
dev_langs:
- C++
helpviewer_keywords:
- C2780
ms.assetid: 423793d8-a3b2-4f35-85f8-ae1d043e2b69
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fba3d16284e8f56dd3583cb73d4b8fec56222a38
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2780"></a>Derleyici Hatası C2780
'bildirimi': N bağımsız değişken - M sağlanan bekler  
  
 İşlev şablonu çok az veya çok fazla sayıda bağımsız değişken yok.  
  
 Aşağıdaki örnek C2780 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2780.cpp  
template<typename T>  
void f(T, T){}  
  
int main() {  
   f(1);  // C2780  
   // try the following line instead  
   // f(1,2);  
}  
```