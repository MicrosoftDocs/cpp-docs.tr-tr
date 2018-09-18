---
title: Derleyici Hatası C2599 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2599
dev_langs:
- C++
helpviewer_keywords:
- C2599
ms.assetid: 88515f36-7589-47e2-862e-0de8b18d6668
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 515e380ea87b8ea648a00644ce8bca6428903f18
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044489"
---
# <a name="compiler-error-c2599"></a>Derleyici Hatası C2599

'enum': sabit listesi türü ileri dönük bildirimi izin verilmez

Derleyici artık, yönetilen bir numaralandırmanın İleri dönük bildirimi de destekler.

Bir numaralandırma türünün İleri dönük bildirimi altında verilmez [/Za](../../build/reference/za-ze-disable-language-extensions.md).

Aşağıdaki örnek, C2599 oluşturur:

```
// C2599.cpp
// compile with: /clr /c
enum class Status;   // C2599

enum class Status2 { stop2, hold2, go2};

ref struct MyStruct {
   // Delete the following line to resolve.
   Status m_status;

   Status2 m_status2;   // OK
};

enum class Status { stop, hold, go };
```