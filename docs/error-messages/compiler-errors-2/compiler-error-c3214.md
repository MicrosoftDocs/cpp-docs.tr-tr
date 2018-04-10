---
title: Derleyici Hatası C3214 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- C3214
dev_langs:
- C++
helpviewer_keywords:
- C3214
ms.assetid: 49ee4a9a-2549-4adb-9d3a-38e154303c2e
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 77485fea44e9d18f0a08b360076a1e8d1c797c1b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3214"></a>Derleyici Hatası C3214
'type': 'param' genel 'generic_type' ın genel parametresi için geçersiz tür bağımsız değişkeni kısıtlaması 'kısıtlaması' karşılamıyor  
  
 Genel sınıfının kısıtlaması karşılamıyor genel bir sınıf için bir örnek oluşturma türü belirtildi.  
  
 Aşağıdaki örnek C3214 oluşturur:  
  
```  
// C3214.cpp  
// compile with: /clr  
interface struct A {};  
  
generic <class T>   
where T : A  
ref class C {};  
  
ref class X : public A {};  
  
int main() {  
   C<int>^ c = new C<int>;   // C3214  
   C<X ^> ^ c2 = new C<X^>;   // OK  
}  
```