---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3409'
title: Derleyici hatası C3409
ms.date: 11/06/2018
f1_keywords:
- C3409
helpviewer_keywords:
- C3409
ms.assetid: e372d9fa-230c-4b28-b6d3-6ad81ccf9dbb
ms.openlocfilehash: 6d3ba602ab9f98526d2ddd6538e424b7879c7017
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316264"
---
# <a name="compiler-error-c3409"></a>Derleyici hatası C3409

> boş öznitelik bloğuna izin verilmiyor

## <a name="remarks"></a>Açıklamalar

Köşeli parantezler, derleyici tarafından [öznitelik](../../windows/attributes/attributes-alphabetical-reference.md) bloğu olarak yorumlanmıştı, ancak hiç öznitelik bulunamadı.

Bir lambda ifadesinin tanımının bir parçası olarak köşeli parantezleri kullandığınızda derleyici bu hatayı oluşturabilir. Derleyici köşeli ayracın bir lambda ifadesinin veya bir öznitelik bloğunun tanımının bir parçası olup olmadığını belirleyemediğinde bu hata oluşur. Lambda ifadeleri hakkında daha fazla bilgi için bkz. [lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md).

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Köşeli parantezler bir öznitelik bloğunun parçasıysa:

   1. Öznitelik bloğunda bir veya daha fazla öznitelik sağlayın.

   1. Öznitelik bloğunu kaldırın.

1. Köşeli parantezler bir lambda ifadesinin parçasıysa, lambda ifadesinin geçerli sözdizimi kurallarına uyduğundan emin olun.

   Lambda ifade sözdizimi hakkında daha fazla bilgi için bkz. [lambda Ifadesi sözdizimi](../../cpp/lambda-expression-syntax.md).

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C3409 oluşturur.

```cpp
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

Aşağıdaki örnek C3409 oluşturur çünkü bir lambda ifadesi **`mutable`** belirtimi kullanır, ancak bir parametre listesi sağlamıyor. Derleyici, köşeli ayracın bir lambda ifadesinin veya bir öznitelik bloğunun tanımının bir parçası olup olmadığını belirleyemiyor.

```cpp
// C3409b.cpp

int main()
{
   [] mutable {}();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[özniteliğe](../../windows/attributes/attributes-alphabetical-reference.md)<br/>
[Lambda Ifadeleri](../../cpp/lambda-expressions-in-cpp.md)<br/>
[Lambda Ifadesi söz dizimi](../../cpp/lambda-expression-syntax.md)
