---
title: Derleyici Hatası C3299
ms.date: 11/04/2016
f1_keywords:
- C3299
helpviewer_keywords:
- C3299
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
ms.openlocfilehash: 4ad48ea0bc09e098a41cb9aa969a08e9ead48f73
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484849"
---
# <a name="compiler-error-c3299"></a>Derleyici Hatası C3299

'member_function': kısıtlamalar belirtilemez bunlar temel yöntemden devralınır

Genel üye işlevini geçersiz kılarken, kısıtlama yan tümceleri (kısıtlamaları gelir kısıtlamaları devralınmaz yinelenen) belirtilemez.

Kısıtlama yan tümceleri geçersiz kıldıkları genel işlev üzerinde devralınır.

Daha fazla bilgi için [genel tür parametrelerindeki kısıtlamalar (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3299 oluşturur.

```
// C3299.cpp
// compile with: /clr /c
public ref struct R {
   generic<class T>
   where T : R
   virtual void f();
};

public ref struct S : R {
   generic<class T>
   where T : R   // C3299
   virtual void f() override;
};
```