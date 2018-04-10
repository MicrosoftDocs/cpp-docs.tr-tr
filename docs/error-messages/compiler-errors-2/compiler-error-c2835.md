---
title: Derleyici Hatası C2835 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C2835
dev_langs:
- C++
helpviewer_keywords:
- C2835
ms.assetid: 41c70630-983f-4da2-8342-513cf48b0519
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fd4be5cb8b03b79670f83198fc6f014b2fa87078
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2835"></a>Derleyici Hatası C2835
Kullanıcı tanımlı dönüştürme 'type' biçimsel parametre almayan  
  
 Kullanıcı tanımlı tür dönüşümleri resmi parametreleri alamıyor.  
  
 Aşağıdaki örnek C2835 oluşturur:  
  
```  
// C2835.cpp  
class A {  
public:  
   char v_char;  
  
   A() {   
      v_char = 'A';   
   };  
   operator char(char a) {   // C2835  
   // try the following line instead  
   // operator char() {     
      return v_char + 1;   
   };  
};  
  
int main() {  
   A a;  
}  
```