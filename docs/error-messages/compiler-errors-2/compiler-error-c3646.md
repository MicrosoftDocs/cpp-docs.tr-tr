---
title: Derleyici Hatası C3646 | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3646
dev_langs:
- C++
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c038520c1a35fa5264e1e98b074687efb336d028
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "35658617"
---
# <a name="compiler-error-c3646"></a>Derleyici Hatası C3646

> 'belirticisi': Bilinmeyen geçersiz kılma belirticisi

## <a name="remarks"></a>Açıklamalar

Derleyici, burada, bir geçersiz kılma tanımlayıcısı bekleniyordu, ancak belirteç derleyici tarafından tanınmadı konumda bir belirteci bulundu.

Örneğin, tanınmayan *belirticisi* olduğu **_NOEXCEPT**, anahtar sözcüğüyle değiştirin **noexcept**.

Daha fazla bilgi için [geçersiz kılma tanımlayıcıları](../../windows/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3646 oluşturur ve bunu düzeltmek için bir yol gösterir:

```cpp
// C3646.cpp
// compile with: /clr /c
ref class C {
   void f() unknown;   // C3646
   // try the following line instead
   // virtual void f() abstract;
};
```