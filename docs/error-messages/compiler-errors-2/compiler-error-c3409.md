---
title: Derleyici Hatası C3409
ms.date: 11/06/2018
f1_keywords:
- C3409
helpviewer_keywords:
- C3409
ms.assetid: e372d9fa-230c-4b28-b6d3-6ad81ccf9dbb
ms.openlocfilehash: b6ceb6f2e8700a5459dbd01db443ef90de314b5e
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330092"
---
# <a name="compiler-error-c3409"></a>Derleyici Hatası C3409

> boş öznitelik bloğuna izin verilmiyor

## <a name="remarks"></a>Açıklamalar

Köşeli ayraç derleyici tarafından yorumlanan bir [özniteliği](../../windows/cpp-attributes-reference.md) blok, ancak hiç öznitelik bulunamadı.

Köşeli ayraçlar bir lambda ifadesinin tanımının bir parçası kullandığınızda, derleyici bu hatayı oluşturabilir. Derleyici köşeli ayraç bir lambda ifadesi veya bir öznitelik blok tanımının bir parçası olup olmadığını belirleyemiyor. Bu hata oluşur. Lambda ifadeleri hakkında daha fazla bilgi için bkz. [Lambda ifadeleri](../../cpp/lambda-expressions-in-cpp.md).

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Köşeli ayraç öznitelik bloğuna parçası ise:

   1. Öznitelikler, bir veya daha fazla öznitelik bloğunda sağlar.

   1. Öznitelik bloğunu kaldırın.

1. Köşeli ayraç bir lambda ifadesinin parçası ise lambda ifadesi geçerli sözdizimi kurallarına uyduğundan emin olun.

   Lambda ifadesi söz dizimi hakkında daha fazla bilgi için bkz: [Lambda ifadesi söz dizimi](../../cpp/lambda-expression-syntax.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3409 oluşturur.

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

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir lambda ifadesi kullandığından C3409 oluşturur `mutable` belirtimi, ancak parametre listesini sağlamaz. Derleyici, köşeli ayraç bir lambda ifadesi veya bir öznitelik blok tanımının bir parçası olup olmadığını belirleyemiyor.

```cpp
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