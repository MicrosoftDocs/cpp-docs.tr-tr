---
title: "Derleyici Hatası C3132 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3132
dev_langs: C++
helpviewer_keywords: C3132
ms.assetid: d54a3d12-336a-4ed0-ad4e-43cddac33b5e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c3a0962eea743061c8f95a29c8c3d27585a70bc6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3132"></a>Derleyici Hatası C3132
'işlev parametresinin': parametre dizileri 'tek boyutlu yönetilen array' türünde resmi olarak bağımsız değişken için yalnızca uygulanabilir  
  
 [ParamArray](https://msdn.microsoft.com/en-us/library/system.paramarrayattribute.aspx) öznitelik, bir tek boyutlu dizi değildi bir parametre uygulandı.  
  
 Aşağıdaki örnek C3132 oluşturur:  
  
```  
// C3132.cpp  
// compile with: /clr /c  
using namespace System;  
void f( [ParamArray] Int32[,] );   // C3132  
void g( [ParamArray] Int32[] );   // C3132  
  
void h( [ParamArray] array<Char ^> ^ MyArray );   // OK  
  
```