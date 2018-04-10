---
title: Derleyici Hatası C3465 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- C3465
dev_langs:
- C++
helpviewer_keywords:
- C3465
ms.assetid: aeb815e5-b3fc-4525-afe2-d738e9321df1
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b7706779684158da8b1bc7187621420e52a640a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3465"></a>Derleyici Hatası C3465
türü 'type' kullanmak için 'assembly' derleme başvurusu  
  
 İstemci yeniden derleyin kadar tür iletme istemci uygulaması için çalışır. Yeniden derleyin, istemci uygulamasında kullanılan bir türü tanımını içeren her derleme için bir başvuru gerekir.  
  
 Daha fazla bilgi için bkz: [tür iletme (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, yeni konum türü içeren bütünleştirilmiş oluşturur.  
  
```  
// C3465.cpp  
// compile with: /clr /LD  
public ref class R {  
public:  
   ref class N {};  
};  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek türü tanımını içeren için kullanılan bir derlemeyi oluşturur, ancak şimdi türü için iletme sözdizimi içeriyor.  
  
```  
// C3465_b.cpp  
// compile with: /clr /LD  
#using "C3465.dll"  
[ assembly:TypeForwardedTo(R::typeid) ];  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3465 oluşturur.  
  
```  
// C3465_c.cpp  
// compile with: /clr  
// C3465 expected  
#using "C3465_b.dll"  
// Uncomment the following line to resolve.  
// #using "C3465.dll"  
  
int main() {  
   R^ r = gcnew R();  
}  
```