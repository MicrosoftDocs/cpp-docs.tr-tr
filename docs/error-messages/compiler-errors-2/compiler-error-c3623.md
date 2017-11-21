---
title: "Derleyici Hatası C3623 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3623
dev_langs: C++
helpviewer_keywords: C3623
ms.assetid: a0341b45-062a-4f67-beb9-ba74201ed1ed
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: df590a7883266f34c749e1aaae2f7f0b8a1f0243
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3623"></a>Derleyici Hatası C3623
'değişkeni': bit alanları desteklenmiyor yönetilen veya WinRT türleri  
  
 Bit alanlarını kullanma değişkenleri yönetilen ya da WinRT sınıfı üzerinde izin verilmez.  
  
 Aşağıdaki örnek C3623 oluşturur:  
  
```  
// C3623.cpp  
// compile with: /clr  
using namespace System;  
ref class CMyClass {  
public:  
   int i : 1;   // C3623  
};  
  
int main() {  
   CMyClass^ pMyClass = gcnew CMyClass();  
   pMyClass->i = 3;  
   Console::Out->WriteLine(pMyClass->i);  
}  
```  
