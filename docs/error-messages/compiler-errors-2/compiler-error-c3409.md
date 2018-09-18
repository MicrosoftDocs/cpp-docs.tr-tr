---
title: Derleyici Hatası C3409 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3409
dev_langs:
- C++
helpviewer_keywords:
- C3409
ms.assetid: e372d9fa-230c-4b28-b6d3-6ad81ccf9dbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 338a98adb45ee9fc8eb392853a5693d10a171940
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058841"
---
# <a name="compiler-error-c3409"></a>Derleyici Hatası C3409

boş öznitelik bloğuna izin verilmiyor

Köşeli ayraç derleyici tarafından yorumlanan bir [özniteliği](../../windows/cpp-attributes-reference.md) blok, ancak hiç öznitelik bulunamadı.

Köşeli ayraçlar bir lambda ifadesinin tanımının bir parçası kullandığınızda, derleyici bu hatayı oluşturabilir. Derleyici köşeli ayraç bir lambda ifadesi veya bir öznitelik blok tanımının bir parçası olup olmadığını belirleyemiyor. Bu hata oluşur. Lambda ifadeleri hakkında daha fazla bilgi için bkz. [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md).

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Köşeli ayraç öznitelik bloğuna parçası ise:

   1. Öznitelikler, bir veya daha fazla öznitelik bloğunda sağlar.

   1. Öznitelik bloğunu kaldırın.

1. Köşeli ayraç bir lambda ifadesinin parçası ise:

   1. Lambda ifadesi geçerli sözdizimi kurallarına uyduğundan emin olun.

         Lambda ifadesi söz dizimi hakkında daha fazla bilgi için bkz: [Lambda ifadesi söz dizimi](../../cpp/lambda-expression-syntax.md).

    2.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3409 oluşturur.

```
// C3409.cpp
// compile with: /c
#include <windows.h>
[]   // C3409
class a {};

// OK
[object, uuid("00000000-0000-0000-0000-000000000000")]
__interface x {};

[coclass, uuid("00000000-0000-0000-0000-000000000001")]
class b : public x {};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir lambda ifadesi kullandığından C3409 oluşturur `mutable` belirtimi, ancak parametre listesini sağlamaz. Derleyici, köşeli ayraç bir lambda ifadesi veya bir öznitelik blok tanımının bir parçası olup olmadığını belirleyemiyor.

```
// C3409b.cpp

int main()
{
   [] mutable {}();
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[attribute](../../windows/cpp-attributes-reference.md)<br/>
[Lambda İfadeleri](../../cpp/lambda-expressions-in-cpp.md)<br/>
[Lambda İfadesi Söz Dizimi](../../cpp/lambda-expression-syntax.md)