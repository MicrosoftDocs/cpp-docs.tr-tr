---
title: Derleyici hatası C3163
ms.date: 11/04/2016
f1_keywords:
- C3163
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
ms.openlocfilehash: 29f810ab1ab1608ab9c0492c9f88b8edfe042168
ms.sourcegitcommit: 6e55aeb538b1c39af754f82d6f7738a18f5aa031
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/29/2020
ms.locfileid: "87390032"
---
# <a name="compiler-error-c3163"></a>Derleyici hatası C3163

> '*Yapı*': öznitelikler önceki bildirimle tutarsız

Bir tanıma uygulanan öznitelikler, bir bildirime uygulanan öznitelik (ler) ile çakışıyor.

C3163 çözümlemek için bir yol, ileri bildiriminde öznitelikleri ortadan kaldırmektir. Bir iletme bildirimindeki tüm öznitelikler, tanımdaki özniteliklerden veya en çoğuna eşit olmalıdır.

C3163 hatasının olası bir nedeni, Microsoft kaynak kodu ek açıklama dili (SAL) ile ilgilidir. , Bayrağını kullanarak projenizi derlemediğiniz takdirde SAL makroları genişlemez **`/analyze`** . Seçeneği olmadan düzgün bir şekilde derlenen bir program **`/analyze`** , bunu seçeneğiyle yeniden derlemenize çalışırsanız C3163 oluşturabilir **`/analyze`** . SAL hakkında daha fazla bilgi için bkz. [sal ek açıklamaları](../../c-runtime-library/sal-annotations.md).

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

[SAL ek açıklamaları](../../c-runtime-library/sal-annotations.md)
