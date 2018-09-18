---
title: Derleyici Hatası C2504 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2504
dev_langs:
- C++
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6fb11774f65454799761913babb428dc6a471743
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054135"
---
# <a name="compiler-error-c2504"></a>Derleyici Hatası C2504

'class': taban sınıf tanımsız

Temel sınıf bildirildi, ancak hiçbir zaman tanımlı.  Olası nedenler:

1. İçerme dosyası eksik.

1. Dış temel sınıf bildirilmemiş olan [extern](../../cpp/using-extern-to-specify-linkage.md).

Aşağıdaki örnek, C2504 oluşturur:

```
// C2504.cpp
// compile with: /c
class A;
class B : public A {};   // C2504
```

TAMAM

```
class C{};
class D : public C {};
```