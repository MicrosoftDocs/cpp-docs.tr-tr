---
title: Derleyici Hatası C2563 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C2563
dev_langs:
- C++
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dfd46b56de9bcdec0d742c488b96b76066478246
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2563"></a>Derleyici Hatası C2563
biçimsel parametresi listesi birleşiminde  
  
 Bir işlev (veya bir işlev işaretçisi) biçimsel parametresi listesi başka bir işlevi (veya bir üye işlev işaretçisi) içeriğiyle eşleşmiyor. Sonuç olarak, işlevleri veya işaretçiler atama yapılamıyor.  
  
 Aşağıdaki örnek C2563 oluşturur:  
  
```  
// C2563.cpp  
void func( int );  
void func( int, int );  
int main() {  
   void *fp();  
   fp = func;   // C2563  
}  
```