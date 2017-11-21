---
title: "Derleyici Hatası C2780 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2780
dev_langs: C++
helpviewer_keywords: C2780
ms.assetid: 423793d8-a3b2-4f35-85f8-ae1d043e2b69
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 96ca469a10c96ad16027ec696af0b43e8ac4e2c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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