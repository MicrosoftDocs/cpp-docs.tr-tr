---
title: "Derleyici Hatası C3380 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3380
dev_langs: C++
helpviewer_keywords: C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b06f57795cea7dda7b3ba2797f7c57026a9acf60
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
