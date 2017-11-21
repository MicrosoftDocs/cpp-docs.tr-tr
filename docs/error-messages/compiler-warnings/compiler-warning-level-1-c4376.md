---
title: "Derleyici Uyarısı (düzey 1) C4376 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4376
dev_langs: C++
helpviewer_keywords: C4376
ms.assetid: 5f202c74-9489-48fe-b36f-19cd882b1589
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b78407a29ade4c6792afbd8e15295199b7d6b2c4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4376"></a>Derleyici Uyarısı (düzey 1) C4376
erişim tanımlayıcısı ' old_specifier:' artık desteklenmiyor: Lütfen kullanın ' new_specifier:' yerine  
  
 Tür ve üye erişilebilirlik meta verilerde belirtme hakkında daha fazla bilgi için bkz [yazın görünürlük](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) ve [üye görünürlüğü](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility) içinde [nasıl yapılır: tanımlayın ve tüketmek sınıflar ve yapılar (C + +/ CLI) ](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4376 oluşturur.  
  
```  
// C4376.cpp  
// compile with: /clr /W1 /c  
public ref class G {  
public public:   // C4376  
   void m2();  
};  
  
public ref class H {  
public:   // OK  
   void m2();  
};  
```