---
description: pragmaMicrosoft C/C++ ' da make_public yönergesi hakkında daha fazla bilgi edinin
title: make_public pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.make_public
- make_public_CPP
helpviewer_keywords:
- pragma, make_public
- make_public pragma
no-loc:
- pragma
ms.openlocfilehash: 4bc3370ac0901ff9a0656de5657f9c9f557e1dff
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713525"
---
# <a name="make_public-no-locpragma"></a>`make_public` pragma

Yerel bir türün ortak derleme erişilebilirliği olması gerektiğini belirtir.

## <a name="syntax"></a>Syntax

> **`#pragma make_public(`***tür***`)`**

### <a name="parameters"></a>Parametreler

*türüyle*\
Ortak bütünleştirilmiş kod erişilebilirliği olmasını istediğiniz türün adı.

## <a name="remarks"></a>Açıklamalar

**`make_public`** , başvuruda bulunmak istediğiniz yerel türün değiştireistemediğiniz bir üstbilgi dosyasından olması durumunda yararlıdır. Yerel türü genel derleme görünürlüğliğiyle bir türdeki ortak işlevin imzasında kullanmak istiyorsanız, yerel türün ortak derleme erişilebilirliği olması gerekir, aksi takdirde derleyici bir uyarı verebilir.

**`make_public`** genel kapsamda belirtilmesi gerekir. Bu, yalnızca kaynak kodu dosyasının sonuna kadar bildirildiği noktadan etkilidir.

Yerel tür örtük veya açık bir şekilde özel olabilir. Daha fazla bilgi için bkz. [tür görünürlüğü](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility).

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, iki yerel yapı için tanımları içeren bir üst bilgi dosyasının içeriğidir.

```cpp
// make_public_pragma.h
struct Native_Struct_1 { int i; };
struct Native_Struct_2 { int i; };
```

Aşağıdaki kod örneği üst bilgi dosyasını kullanır. Yerel yapıları, kullanarak genel olarak işaretlemediğiniz sürece, genel **`make_public`** yönetilen bir türdeki ortak işlevin imzasında yerel yapıları kullanmaya çalıştığınızda derleyicinin bir uyarı üretecektir.

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

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
