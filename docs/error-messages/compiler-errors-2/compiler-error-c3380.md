---
title: Derleyici Hatası C3380 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3380
dev_langs:
- C++
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 315031946f9a89f53097e4c2371286fba213f698
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252454"
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
