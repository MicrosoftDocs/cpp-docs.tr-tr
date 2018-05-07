---
title: Derleyici Uyarısı (düzey 1) C4490 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4490
dev_langs:
- C++
helpviewer_keywords:
- C4490
ms.assetid: f9b03ecf-41a1-4f4d-a74c-2c1e88234ccc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: baf6c10d50b9b6dd7a41df195dd0b1e39683c98c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4490"></a>Derleyici Uyarısı (düzey 1) C4490
'override': geçersiz kılma tanımlayıcısı; yanlış kullanımı 'function' temel ref sınıf yöntemi eşleşmiyor.  
  
 Bir geçersiz kılma tanımlayıcısı yanlış kullanıldı. Örneğin, bir arabirim işlevi geçersiz kılmaz, uyguladıktan.  
  
 Daha fazla bilgi için bkz: [geçersiz kılma tanımlayıcıları](../../windows/override-specifiers-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4490 oluşturur.  
  
```  
// C4490.cpp  
// compile with: /clr /c /W1  
  
interface struct IFace {  
   void Test();  
};  
  
ref struct Class1 : public IFace {  
   virtual void Test() override {}   // C4490  
   // try the following line instead  
   // virtual void Test() {}  
};  
```