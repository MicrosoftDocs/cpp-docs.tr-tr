---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3299'
title: Derleyici hatası C3299
ms.date: 11/04/2016
f1_keywords:
- C3299
helpviewer_keywords:
- C3299
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
ms.openlocfilehash: ab86a675eb13b975943130802ae98679dbc1cbb3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337405"
---
# <a name="compiler-error-c3299"></a>Derleyici hatası C3299

' member_function ': kısıtlamalar belirtilemiyor, taban yönteminden devralınırlar

Genel bir üye işlevini geçersiz kıldığınızda, kısıtlama yan tümcelerini belirtemezsiniz (kısıtlamaları tekrarlarken kısıtlamaların devralınmaz).

Geçersiz kılmanın genel işlevindeki kısıtlama yan tümceleri devralınacaktır.

Daha fazla bilgi için bkz. [genel tür parametrelerindeki kısıtlamalar (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3299 oluşturur.

```cpp
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
