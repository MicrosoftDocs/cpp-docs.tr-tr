---
title: "Derleyici Hatası C3380 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3380
dev_langs:
- C++
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f8789889ab0d9ebe93941a438c286ed718ac4721
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3380"></a>Derleyici Hatası C3380
'class': Geçersiz derleme belirleyici - yalnızca 'genel' veya 'özel' izin verilen erişim  
  
 Bir yönetilen sınıf veya yapı, uygulandığında [ortak](../../cpp/public-cpp.md) ve [özel](../../cpp/private-cpp.md) anahtar sözcükleri belirtmek sınıfı derleme meta verilerini kullanıma sunulan olup olmadığını. Yalnızca `public` veya `private` ile derlenen bir programda bir sınıfa uygulanan [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 `ref` Ve `value` ile kullanıldığında anahtar sözcükler, [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), bir sınıf yönetildiğini belirtmek (bkz [sınıflar ve yapılar](../../windows/classes-and-structs-cpp-component-extensions.md)).  
  
 Aşağıdaki örnek C3380 oluşturur:  
  
```  
// C3380_2.cpp  
// compile with: /clr  
protected ref class A {   // C3380  
// try the following line instead  
// ref class A {  
public:  
   static int i = 9;  
};  
  
int main() {  
   A^ myA = gcnew A;  
   System::Console::WriteLine(myA->i);  
}  
```  
