---
title: Derleyici Hatası C3908 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3908
dev_langs:
- C++
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7591b8ab5f8495b6af866e23e7a169b0f9cd29a6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047323"
---
# <a name="compiler-error-c3908"></a>Derleyici Hatası C3908

'yapısı' daha az kısıtlayıcı erişim düzeyi

Bir özellik erişimci yöntemini (get veya set) özelliği üzerinde belirtilen erişim'den daha az kısıtlayıcı erişim sahip olamaz.  Olay erişimci metotları için benzer şekilde.

Daha fazla bilgi için [özelliği](../../windows/property-cpp-component-extensions.md) ve [olay](../../windows/event-cpp-component-extensions.md).

Aşağıdaki örnek, C3908 oluşturur:

```
// C3908.cpp
// compile with: /clr
ref class X {
protected:
   property int i {
   public:   // C3908 property i is protected
      int get();
   private:
      void set(int);   // OK more restrictive
   };
};
```