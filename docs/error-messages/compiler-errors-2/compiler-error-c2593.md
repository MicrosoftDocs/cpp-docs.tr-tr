---
title: "Derleyici Hatası C2593 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2593
dev_langs: C++
helpviewer_keywords: C2593
ms.assetid: 4a0fe9bb-2163-447d-91f6-1890ed8250f6
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cb0b752259503f7e14cd78298e487f5304e13a0d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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