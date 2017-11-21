---
title: "Derleyici Hatası C2942 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2942
dev_langs: C++
helpviewer_keywords: C2942
ms.assetid: 13abf744-8fa1-450d-886d-e5717c04956e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2685762bc57b4ff0c2d056dff4c246d2286503eb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2942"></a>Derleyici Hatası C2942
'class': türü sınıfı kimliği bir resmi bir işlev bağımsız değişkeni yeniden tanımlandı  
  
 Genel veya Şablon sınıfı biçimsel bağımsız değişken olarak kullanamazsınız. Genel oluşturucu veya Şablon sınıfı için bağımsız değişken geçiremezsiniz.  
  
 Aşağıdaki örnek C2942 oluşturur:  
  
```  
  
// C2942.cpp  
// compile with: /c  
template<class T>  
struct TC {};   
void f(int TC<int>) {}   // C2942  
  
// OK  
struct TC2 {};  
void f(TC2 i) {}  
```  
  
 Ayrıca C2942 genel türler kullanma ortaya çıkabilir:  
  
```  
// C2942b.cpp  
// compile with: /clr /c  
generic<class T>  
ref struct GC {};  
void f(int GC<int>) {}   // C2942  
ref struct GC2 { };  
void f(int GC2) {}  
```