---
title: Derleyici Hatası C2793 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2793
dev_langs:
- C++
helpviewer_keywords:
- C2793
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5b9f350a3d3845649c9423a412ed5286cb13723
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026211"
---
# <a name="compiler-error-c2793"></a>Derleyici Hatası C2793

'token': arkasında beklenmeyen belirteç '::', tanımlayıcısı veya beklenen'operator ' anahtar sözcüğü

İzleyebileceğiniz yalnızca belirteçleri `__super::` tanımlayıcı veya anahtar sözcüğü `operator`.

Aşağıdaki örnek C2793 oluşturur

```
// C2793.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super::(); // C2793
   }
};
```