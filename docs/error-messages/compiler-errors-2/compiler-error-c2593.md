---
title: Derleyici Hatası C2593 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2593
dev_langs:
- C++
helpviewer_keywords:
- C2593
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e419416266e0e3c4ebff8190b3b26b1c43c9ba0f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2593"></a>Derleyici Hatası C2593
' işleci ' belirsiz tanımlayıcısıdır  
  
 Birden fazla olası işleci aşırı yüklenmiş bir işleç için tanımlanır.  
  
 Bir veya daha fazla gerçek parametrelere açık atama kullanırsanız, bu hata düzeltilebilir.  
  
 Aşağıdaki örnek C2593 oluşturur:  
  
```  
// C2593.cpp  
struct A {};  
struct B : A {};  
struct X {};  
struct D : B, X {};  
void operator+( X, X );  
void operator+( A, B );  
D d;  
  
int main() {  
   d +  d;         // C2593, D has an A, B, and X   
   (X)d + (X)d;    // OK, uses operator+( X, X )  
}  
```  
  
 Kayan nokta değişkeni kullanarak bir seri hale getirme tarafından bu hatanın nedeni olabilir bir `CArchive` nesnesi. Derleyici tanımlayan `<<` belirsiz olarak işleci. Yalnızca ilkel C++ türleri `CArchive` seri hale getirebilir sabit boyutlu türleridir `BYTE`, `WORD`, `DWORD`, ve `LONG`. Tüm tamsayı türleri bu türden biri için seri hale getirme için dönüştürmeniz gerekir. Kayan nokta türleri gerekir arşivlenmiş kullanarak `CArchive::Write()` üye işlevi.  
  
 Aşağıdaki örnek bir kayan nokta değişken arşivlemek nasıl gösterir (`f`) arşivi `ar`:  
  
```  
ar.Write(&f, sizeof( float ));  
```