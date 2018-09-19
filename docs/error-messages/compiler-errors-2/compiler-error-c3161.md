---
title: Derleyici Hatası C3161 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3161
dev_langs:
- C++
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11396ccad33489b41d18759ba4d2f00b445e94a3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136081"
---
# <a name="compiler-error-c3161"></a>Derleyici Hatası C3161

'interface': iç içe sınıf, yapı, birleşim veya bir arabirim içindeki arabirim; geçersiz Arabirim içinde sınıf, yapı veya birleşim geçersizdir

Bir [__interface](../../cpp/interface.md) yalnızca genel kapsamda veya ad alanı içinde yer alabilir. Bir sınıf, yapı veya birleşim arabirim içinde yer alamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3161 oluşturur.

```
// C3161.cpp
// compile with: /c
__interface X {
   __interface Y {};   // C3161 A nested interface
};
```