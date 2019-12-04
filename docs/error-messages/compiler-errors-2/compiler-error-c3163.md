---
title: Derleyici hatası C3163
ms.date: 11/04/2016
f1_keywords:
- C3163
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
ms.openlocfilehash: 436fb112758dfdec9997ff7e6dd7ef8f9dcdc66e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761783"
---
# <a name="compiler-error-c3163"></a>Derleyici hatası C3163

' yapı ': öznitelikler önceki bildirimle tutarsız

Bir tanıma uygulanan öznitelikler, bir bildirime uygulanan öznitelik (ler) ile çakışıyor.

C3163 çözümlemek için bir yol, ileri bildiriminde öznitelikleri ortadan kaldırmektir. Bir iletme bildirimindeki tüm öznitelikler, tanımdaki özniteliklerden veya en çoğuna eşit olmalıdır.

C3163 hatasının olası bir nedeni, Microsoft kaynak kodu ek açıklama dili (SAL) ile ilgilidir. **/Analyze** işaretini kullanarak projenizi derlemenize kadar Sal makroları genişlemez. /Analyze olmadan düzgün bir şekilde derlenen bir program,/Analyze seçeneği ile yeniden derlemenize çalışırsanız C3163 oluşturabilir. SAL hakkında daha fazla bilgi için bkz. [sal ek açıklamaları](../../c-runtime-library/sal-annotations.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3163 oluşturur.

```cpp
// C3163.cpp
// compile with: /clr /c
using namespace System;

[CLSCompliant(true)] void f();
[CLSCompliant(false)] void f() {}   // C3163
// try the following line instead
// [CLSCompliant(true)] void f() {}
```

## <a name="see-also"></a>Ayrıca bkz.

[SAL Ek Açıklamaları](../../c-runtime-library/sal-annotations.md)
