---
title: Derleyici Uyarısı (düzey 1) C4490
ms.date: 11/04/2016
f1_keywords:
- C4490
helpviewer_keywords:
- C4490
ms.assetid: f9b03ecf-41a1-4f4d-a74c-2c1e88234ccc
ms.openlocfilehash: bf51994c210bd751e0d29bec169dfc4366784486
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779189"
---
# <a name="compiler-warning-level-1-c4490"></a>Derleyici Uyarısı (düzey 1) C4490

'override': geçersiz kılma belirticisi; yanlış kullanımı 'function' taban başvuru sınıfı yöntemiyle eşleşmiyor

Geçersiz kılma tanımlayıcısı yanlış kullanıldı. Örneğin, bir arabirim işlevi geçersiz, uyguladıktan.

Daha fazla bilgi için [geçersiz kılma tanımlayıcıları](../../extensions/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4490 oluşturur.

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