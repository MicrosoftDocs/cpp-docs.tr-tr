---
title: Derleyici Hatası C3299
ms.date: 11/04/2016
f1_keywords:
- C3299
helpviewer_keywords:
- C3299
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
ms.openlocfilehash: 314b75a9d0ab8cde2886a7466fa0f95b5bbdd8f1
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777217"
---
# <a name="compiler-error-c3299"></a>Derleyici Hatası C3299

'member_function': kısıtlamalar belirtilemez bunlar temel yöntemden devralınır

Genel üye işlevini geçersiz kılarken, kısıtlama yan tümceleri (kısıtlamaları gelir kısıtlamaları devralınmaz yinelenen) belirtilemez.

Kısıtlama yan tümceleri geçersiz kıldıkları genel işlev üzerinde devralınır.

Daha fazla bilgi için [genel tür parametrelerindeki kısıtlamalar (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

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