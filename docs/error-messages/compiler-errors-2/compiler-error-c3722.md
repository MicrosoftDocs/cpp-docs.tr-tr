---
title: "Derleyici Hatası C3722 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3722
dev_langs: C++
helpviewer_keywords: C3722
ms.assetid: 3cb28363-5eff-4548-bd0d-d5c615846353
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5948e0f295b9a086427c30617be055205bf8ab83
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3722"></a>Derleyici Hatası C3722
Genel olay izin verilmiyor  
  
 Derleyici yalnızca Genel sınıflar, yapılar ve işlevler sağlar.  Daha fazla bilgi için bkz: [genel türler](../../windows/generics-cpp-component-extensions.md).  
  
 Aşağıdaki örnek C3722 oluşturur:  
  
```  
// C3722.cpp  
// compile with: /clr  
generic <typename T>  
public delegate void MyEventHandler(System::Object^ sender, System::EventArgs^ e, T optional);  
  
generic <class T>  
public ref struct MyButton {  
   generic<typename U>  
   event MyEventHandler<U>^ Click;   // C3722  
};  
```