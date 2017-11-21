---
title: "Derleyici Hatası C3699 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3699
dev_langs: C++
helpviewer_keywords: C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: caabe5d8d9e956081211ef23546f0d720ecdcbd6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3699"></a>Derleyici Hatası C3699
'işleci': Bu yöneltme 'type' türünde kullanamazsınız  
  
 İzin verilmiyor yöneltme kullanmak için bir girişimde bulunuldu `type`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3699 oluşturur.  
  
```  
// C3699.cpp  
// compile with: /clr /c  
using namespace System;  
int main() {  
   String * s;   // C3699  
   // try the following line instead  
   // String ^ s2;  
}  
```  
  
## <a name="example"></a>Örnek  
 Önemsiz bir özelliği başvuru türüne sahip olamaz. Bkz: [özelliği](../../windows/property-cpp-component-extensions.md) daha fazla bilgi için. Aşağıdaki örnek C3699 oluşturur.  
  
```  
// C3699_b.cpp  
// compile with: /clr /c  
ref struct C {  
   property System::String % x;   // C3699  
   property System::String ^ y;   // OK  
};  
```  
  
## <a name="example"></a>Örnek  
 İzleme başvurusu için bir tanıtıcı "bir işaretçi işaretçi" sözdizimi eşdeğeridir. Aşağıdaki örnek C3699 oluşturur.  
  
```  
// C3699_c.cpp  
// compile with: /clr /c  
using namespace System;  
void Test(String ^^ i);   // C3699  
void Test2(String ^% i);  
```