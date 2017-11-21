---
title: "Derleyici Hatası C2788 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2788
dev_langs: C++
helpviewer_keywords: C2788
ms.assetid: 8688fc5c-e652-43b4-b407-9c488c76f2db
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b3d66496da2940a08d87f968678125b5836587ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2788"></a>Derleyici Hatası C2788
'tanımlayıcısı': birden fazla GUID Bu nesneyle ilişkili  
  
 [__Uuidof](../../cpp/uuidof-operator.md) işleci bağlı bir GUID veya türünde bir nesne gibi bir kullanıcı tarafından tanımlanan kullanıcı tarafından tanımlanan bir türü alır. Bağımsız değişken birden çok GUID'yi sahip bir nesne olduğunda bu hata oluşur.  
  
 Aşağıdaki örnek C2788 oluşturur:  
  
```  
// C2788.cpp  
#include <windows.h>  
struct __declspec(uuid("00000001-0000-0000-0000-000000000000")) A {};  
struct __declspec(uuid("{00000002-0000-0000-0000-000000000000}")) B {};  
template <class T, class U> class MyClass {};  
  
typedef MyClass<A,B> MyBadClass;  
typedef MyClass<A,A> MyGoodClass;  
  
int main() {  
   __uuidof(MyBadClass);    // C2788  
   // try the following line instead  
   __uuidof(MyGoodClass);  
}  
```