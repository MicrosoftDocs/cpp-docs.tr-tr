---
title: Derleyici Hatası C2085 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2085
dev_langs:
- C++
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0fe489dbdd0934926a056bbc7e5539f40ca1ba8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2085"></a>Derleyici Hatası C2085
'tanımlayıcısı': biçimsel parametresi listesinde değil  
  
 Tanımlayıcı işlevi tanımında ancak biçimsel parametresi listesinde bildirildi. (Yalnızca ANSI C)  
  
 Aşağıdaki örnek C2085 oluşturur:  
  
```  
// C2085.c  
void func1( void )  
int main( void ) {}   // C2085  
```  
  
 Olası çözüm:  
  
```  
// C2085b.c  
void func1( void );  
int main( void ) {}  
```  
  
 Noktalı virgül eksik `func1()` işlev tanımı gibi bir prototip şekilde göründüğünü `main` içinde tanımlanan `func1()`, hata C2085 tanımlayıcısı oluşturma `main`.