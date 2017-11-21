---
title: "Derleyici Hatası C2914 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2914
dev_langs: C++
helpviewer_keywords: C2914
ms.assetid: fc6a0592-f53e-4f5a-88cb-780bbed4acf2
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 67bd7d142f77012821b7e464dd73c416088bf48d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2914"></a>Derleyici Hatası C2914
'tanımlayıcısı': işlev bağımsız değişkeni belirsiz olduğu gibi tür bağımsız değişkeni türetme olamaz  
  
 Derleyici hangi işlevleri için bir genel veya şablon bağımsız değişken kullanmak için aşırı yüklü olmadığını belirleyemez.  
  
 Aşağıdaki örnek C2914 oluşturur:  
  
```  
// C2914.cpp  
// compile with: /c  
void f(int);  
void f(double);  
template<class T> void g(void (*) (T));  
void h() { g(f); }   // C2914  
// try the following line instead  
// void h() { g<int>(f); }  
```  
  
 Ayrıca C2914 genel türler kullanma ortaya çıkabilir.  Aşağıdaki örnek C2914 oluşturur:  
  
```  
// C2914b.cpp  
// compile with: /clr /c  
void f(int);  
void f(double);  
  
template<class T>   
void gf(void (*) (T));  
  
void h() { gf(f);}   // C2914  
// try the following line instead  
void h() { gf<int>(f); }  
```