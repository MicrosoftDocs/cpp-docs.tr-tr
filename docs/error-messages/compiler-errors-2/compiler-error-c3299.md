---
title: Derleyici Hatası C3299 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3299
dev_langs:
- C++
helpviewer_keywords:
- C3299
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ca5a57ca1cdfe442386872d738a01cf4235685c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117835"
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