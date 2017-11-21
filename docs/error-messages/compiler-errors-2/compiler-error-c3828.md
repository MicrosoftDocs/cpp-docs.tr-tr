---
title: "Derleyici Hatası C3828 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3828
dev_langs: C++
helpviewer_keywords: C3828
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1b2dfaa6e0c414c80122bcb4291bb021bc1f3c74
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3828"></a>Derleyici Hatası C3828
'nesne türü': yerleştirme değişkenler örneklerini oluşturmaya yönetilen sırada izin verilmiyor veya WinRTclasses  
  
 Bir yönetilen türü veya Windows çalışma zamanı türü bir nesne oluştururken yerleştirme formun işlecinin kullanamazsınız [yeni başvuru, gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md) veya [yeni](../../cpp/new-operator-cpp.md).  
  
 Aşağıdaki örnek C3828 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C3828a.cpp  
// compile with: /clr  
ref struct M {  
};  
  
ref struct N {  
   static array<char>^ bytes = gcnew array<char>(256);  
};  
  
int main() {  
   M ^m1 = new (&N::bytes) M();   // C3828  
   // The following line fixes the error.  
   // M ^m1 = gcnew M();  
}  
```