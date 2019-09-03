---
title: make_public pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.make_public
- make_public_CPP
helpviewer_keywords:
- pragmas, make_public
- make_public pragma
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
ms.openlocfilehash: d12fab685e0088993cb43073c3603bda12edd2f3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218825"
---
# <a name="make_public-pragma"></a>make_public pragması

Yerel bir türün ortak derleme erişilebilirliği olması gerektiğini belirtir.

## <a name="syntax"></a>Sözdizimi

> **#pragma make_public (** *tür* **)**

### <a name="parameters"></a>Parametreler

*türüyle*\
Ortak bütünleştirilmiş kod erişilebilirliği olmasını istediğiniz türün adı.

## <a name="remarks"></a>Açıklamalar

**make_public** , başvuruda bulunmak istediğiniz yerel türün değiştireistemediğiniz bir üstbilgi dosyasından ne zaman olacağı için yararlıdır. Yerel türü genel derleme görünürlüğliğiyle bir türdeki ortak işlevin imzasında kullanmak istiyorsanız, yerel türün ortak derleme erişilebilirliği olması gerekir, aksi takdirde derleyici bir uyarı verebilir.

**make_public** genel kapsamda belirtilmelidir. Bu, yalnızca kaynak kodu dosyasının sonuna kadar bildirildiği noktadan etkilidir.

Yerel tür örtük veya açık bir şekilde özel olabilir. Daha fazla bilgi için bkz. [tür görünürlüğü](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility).

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, iki yerel yapı için tanımları içeren bir üst bilgi dosyasının içeriğidir.

```cpp
// make_public_pragma.h
struct Native_Struct_1 { int i; };
struct Native_Struct_2 { int i; };
```

Aşağıdaki kod örneği üst bilgi dosyasını kullanır. Yerel yapıları **make_public**kullanarak genel olarak işaretlemediğiniz sürece, derleyicinin ortak yönetilen bir türdeki ortak işlevin imzasında yerel yapılar kullanmayı denediğinizde bir uyarı üretecektir.

```cpp
// make_public_pragma.cpp
// compile with: /c /clr /W1
#pragma warning (default : 4692)
#include "make_public_pragma.h"
#pragma make_public(Native_Struct_1)

public ref struct A {
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692
};
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
