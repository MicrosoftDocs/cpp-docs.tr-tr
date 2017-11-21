---
title: "Derleyici Hatası C3821 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3821
dev_langs: C++
helpviewer_keywords: C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 47e0a2ed3c824ed1598f7e998d4966b95cc9233b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3821"></a>Derleyici Hatası C3821
'function': yönetilen tür veya işlev yönetilmeyen bir işlevi olarak kullanılamaz  
  
 Satır içi derlemeyle işlevler veya [setjmp](../../c-runtime-library/reference/setjmp.md) değer türleri veya yönetilen sınıflar içeremez. Bu hatayı düzeltmek için satır içi derleme kaldırın ve `setjmp` yönetilen nesnelerini veya kaldırın.  
  
 Otomatik depolama vararg işlevinde kullanmayı denerseniz C3821 da oluşabilir.  Daha fazla bilgi için bkz: [değişken bağımsız değişken listeleri (...) (C + +/ CLI) ](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md) ve [başvuru türleri için C++ yığın anlamları](../../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3821 oluşturur.  
  
```  
// C3821a.cpp  
// compile with: /clr /c  
public ref struct R {};  
void test1(...) {  
   R r;   // C3821  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3821 oluşturur.  
  
```  
// C3821b.cpp  
// compile with: /clr  
// processor: /x86  
ref class A {  
   public:  
   int i;  
};  
  
int main() {  
   // cannot use managed classes in this function  
   A ^a;     
  
   __asm {  
      nop  
   }  
} // C3821  
```  
