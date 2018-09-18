---
title: Derleyici Uyarısı (düzey 1) C4364 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4364
dev_langs:
- C++
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e37c7f37e1b51296bd5c3ae2cbdb85a93326f027
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087259"
---
# <a name="compiler-warning-level-1-c4364"></a>Derleyici Uyarısı (düzey 1) C4364

\#daha önce görülme location(line_number) as_friend özniteliği;'dosya ' derlemesi için kullanma as_friend uygulanmadı

A `#using` yönergesi için belirtilen meta veri dosyası, yinelenen ancak `as_friend` niteleyicisi olmayan içinde ilk oluşum kullanıldı; derleyici ikinci yoksayacak `as_friend`.

Daha fazla bilgi için [arkadaş derlemeler (C++)](../../dotnet/friend-assemblies-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir bileşen oluşturur.

```
// C4364.cpp
// compile with: /clr /LD
ref class A {};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4364 oluşturur.

```
// C4364_b.cpp
// compile with: /clr /W1 /c
#using " C4364.dll"
#using " C4364.dll" as_friend   // C4364
```