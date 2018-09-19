---
title: Derleyici Uyarısı (düzey 4) C4289 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4289
dev_langs:
- C++
helpviewer_keywords:
- C4289
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 35cb22c767c0ea64a1536bd4d02ad8653bb94250
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102846"
---
# <a name="compiler-warning-level-4-c4289"></a>Derleyici Uyarısı (düzey 4) C4289

standart olmayan uzantı kullanıldı : 'var': for döngüsünde bildirimi yapılan döngü denetim değişkeni for döngüsü kapsamının dışında kullanılıyor

İle derlerken [/Ze](../../build/reference/za-ze-disable-language-extensions.md) ve **/Zc:forScope-**, içinde bildirilen bir değişken bir [için](../../cpp/for-statement-cpp.md) döngü sonra kullanıldı **için**-döngü kapsamı.

Bkz: [/ZC: forscope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) standart davranışını belirtme hakkında daha fazla bilgi için **için** ile döngü **/Ze**.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

Aşağıdaki örnek, C4289 oluşturur:

```
// C4289.cpp
// compile with: /W4 /Zc:forScope-
#pragma warning(default:4289)
int main() {
   for (int i = 0 ; ; )   // C4289
      break;
   i++;
}
```