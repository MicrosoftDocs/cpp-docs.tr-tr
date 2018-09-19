---
title: Derleyici Hatası C3394 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3394
dev_langs:
- C++
helpviewer_keywords:
- C3394
ms.assetid: 4e025d79-27ba-43c8-b0d9-839ecef98126
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d7a7f66d437158504b3ca4c8dccaf3c35d2c1ae4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096424"
---
# <a name="compiler-error-c3394"></a>Derleyici Hatası C3394

kısıtlama yan tümcesinde sözdizimi hatası: 'identifier' beklenen bir tür bulunamadı

Kısıtlama ill oluşturulmuş.  Daha fazla bilgi için [genel tür parametrelerindeki kısıtlamalar (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3394 oluşturur:

```
// C3394.cpp
// compile with: /clr /c
ref class MyClass {};
ref class R {
   generic<typename T>
   where T : static   // C3394
   // try the following line instead
   // where T : MyClass
   void f() {}
};
```