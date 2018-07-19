---
title: Derleyici Uyarısı (düzey 4) C4690 | Microsoft Docs
ms.custom: ''
ms.date: 07/03/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4690
dev_langs:
- C++
helpviewer_keywords:
- C4690
ms.assetid: 080a0ea1-458b-477b-a37a-4a34c94709ff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04fb68bdab762f0f541849fad1568caff836b623
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853328"
---
# <a name="compiler-warning-level-4-c4690"></a>Derleyici Uyarısı (düzey 4) C4690

> \[ emitidl (pop)]: atma sayısından fazla

## <a name="remarks"></a>Açıklamalar

[Emitidl](../../windows/emitidl.md) özniteliği POP gönderildi daha fazla bir kez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4690 oluşturur. Bu sorunu gidermek için tam olarak dilediğiniz kadar bu öznitelik POP emin olmak için gönderilir.

```cpp
// C4690.cpp
// compile with: /c /W4
[emitidl(pop)];   // C4690
class x {};
```
