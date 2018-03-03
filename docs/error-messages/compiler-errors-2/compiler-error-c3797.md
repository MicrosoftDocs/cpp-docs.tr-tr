---
title: "Derleyici Hatası C3797 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3797
dev_langs:
- C++
helpviewer_keywords:
- C3797
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5157e8b63bf15c2d972235e38f692e2ba356a629
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3797"></a>Derleyici Hatası C3797
'override': olay bildirimi geçersiz kılma tanımlayıcısı (yerleştirilmelidir olay Ekle/Kaldır/artırma yöntemlerde yerine) sahip olamaz  
  
 Önemsiz olay (açıkça tanımlanmış erişimci yöntemleri olmadan bir olay) başka bir önemsiz olay ile geçersiz kılamaz. Geçersiz kılma olay erişimci işlevlerle davranışını tanımlamanız gerekir.  
  
 Daha fazla bilgi için bkz: [olay](../../windows/event-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3797 oluşturur.  
  
```  
// C3797.cpp  
// compile with: /clr /c  
delegate void MyDel();  
  
ref class Class1 {  
public:  
   virtual event MyDel ^ E;  
};  
  
ref class Class2 : public Class1 {  
public:  
   virtual event MyDel ^ E override;   // C3797  
};  
  
// OK  
ref class Class3 : public Class1 {  
public:  
   virtual event MyDel ^ E {  
      void add(MyDel ^ d) override {}  
      void remove(MyDel ^ d) override {}  
   }  
};  
```