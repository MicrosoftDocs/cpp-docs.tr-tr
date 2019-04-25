---
title: Bağlayıcı Araçları Hatası LNK2028
ms.date: 11/04/2016
f1_keywords:
- LNK2028
helpviewer_keywords:
- LNK2028
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
ms.openlocfilehash: ed2dc1a95d4dd7c447b360da21b5046e20f79083
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298990"
---
# <a name="linker-tools-error-lnk2028"></a>Bağlayıcı Araçları Hatası LNK2028

"*exported_function*" (*decorated_name*) işlevinde başvurulan "*function_containing_function_call*" (*decorated_name*)

## <a name="remarks"></a>Açıklamalar

Yerel bir işlevin saf bir görüntüye alınmaya çalışılırken örtük çağırma kuralları yerel ve saf derlemeler farkı olduğunu unutmayın.

**/CLR: pure** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

## <a name="example"></a>Örnek

Bu kod örneği, çağırma kuralı olduğunu örtük olarak dışarı aktarılan, yerel, işlevi içeren bir bileşen oluşturur [__cdecl](../../cpp/cdecl.md).

```cpp
// LNK2028.cpp
// compile with: /LD
__declspec(dllexport) int func() {
   return 3;
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, yerel işlev tüketen saf bir istemci oluşturur. Ancak, çağırma kuralı altında **/CLR: pure** olduğu [__clrcall](../../cpp/clrcall.md). Aşağıdaki örnek, LNK2028 oluşturur.

```cpp
// LNK2028_b.cpp
// compile with: /clr:pure lnk2028.lib
// LNK2028 expected
int func();

int main() {
   return func();
}
```