---
title: Derleyici Uyarısı (Düzey 3) C4638 | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4638
dev_langs:
- C++
helpviewer_keywords:
- C4638
ms.assetid: 2c07923a-e103-4e40-bd11-fdfed428a5ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29febc17f041fee27064fc085896c892eecd5c56
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43198238"
---
# <a name="compiler-warning-level-3-c4638"></a>Derleyici Uyarısı (Düzey 3) C4638

> XML belgesi yorum hedef: Bilinmeyen sembole başvuru '*sembol*'

## <a name="remarks"></a>Açıklamalar

Derleyici bir sembol çözümleyemedi (*sembol*). Simgenin derlemede geçerli olmalıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4638 oluşturur:

```cpp
// C4638.cpp
// compile with: /clr /doc /LD /W3
using namespace System;

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary> Text </summary>
   /// <see cref="aSymbolThatAppearsNowhereInMyProject"/>
   // Try the following line instead:
   // /// <see cref="System::Console::WriteLine"/>
   void MyMethod() {}
};   // C4638
```