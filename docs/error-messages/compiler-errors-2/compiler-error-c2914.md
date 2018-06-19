---
title: Derleyici Hatası C2914 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2914
dev_langs:
- C++
helpviewer_keywords:
- C2914
ms.assetid: fc6a0592-f53e-4f5a-88cb-780bbed4acf2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2eda9718af074379381cca62c481020ddf5ed204
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33243097"
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