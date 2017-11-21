---
title: "Derleyici Hatası C2753 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2753
dev_langs: C++
helpviewer_keywords: C2753
ms.assetid: 92bfeeac-524a-4a8e-9a4f-fb8269055826
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bd852023fe4e8cf9b1845ed1a4d53f937b039211
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2753"></a>Derleyici Hatası C2753
'*şablonu*': Kısmi uzmanlığı birincil şablonu için bağımsız değişken listesi eşleşemez  
  
 Şablon bağımsız değişken listesi parametre listesi eşleşirse, derleyici aynı şablonu olarak değerlendirir. Aynı şablon iki kez tanımlama izin verilmiyor.  
  
## <a name="example"></a>Örnek
 Aşağıdaki örnek C2753 oluşturur ve düzeltmek için bir yol gösterir:  
  
```cpp  
// C2753.cpp  
// compile with: cl /c C2753.cpp
template<class T>  
struct A {};  
  
template<class T>  
struct A<T> {};   // C2753  
// try the following line instead  
// struct A<int> {};  
  
template<class T, class U, class V, class W, class X>  
struct B {};  
```