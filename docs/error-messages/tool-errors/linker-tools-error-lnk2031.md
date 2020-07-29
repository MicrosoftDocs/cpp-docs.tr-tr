---
title: Bağlayıcı Araçları Hatası LNK2031
ms.date: 11/04/2016
f1_keywords:
- LNK2031
helpviewer_keywords:
- LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
ms.openlocfilehash: 326886f8de8b59cce9df46eb7b0325b7cc9eb9f2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225208"
---
# <a name="linker-tools-error-lnk2031"></a>Bağlayıcı Araçları Hatası LNK2031

> "*function_declaration*" için p/ınvoke oluşturulamıyor *decorated_name*; meta verilerde çağırma kuralı eksik

## <a name="remarks"></a>Açıklamalar

Yerel bir işlevi saf bir görüntüye aktarmaya çalışırken, örtük çağırma kurallarının yerel ve saf derlemeler arasında farklı olduğunu unutmayın. Saf görüntüler hakkında daha fazla bilgi için bkz. [saf ve Doğrulanabilen kod (C++/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

**/Clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

## <a name="example"></a>Örnek

Bu kod örneği,, çağıran kuralı örtük olarak [__cdecl](../../cpp/cdecl.md), dışarıya aktarılmış, yerel, işlevi olan bir bileşen oluşturur.

```cpp
// LNK2031.cpp
// compile with: /LD
extern "C" {
   __declspec(dllexport) int func() { return 3; }
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, yerel işlevi tüketen bir saf istemci oluşturur. Ancak, **/clr: Pure** altındaki çağırma kuralı [__clrcall](../../cpp/clrcall.md). Aşağıdaki örnek LNK2031 oluşturur.

```cpp
// LNK2031_b.cpp
// compile with: /clr:pure LNK2031.lib
// LNK2031 expected
extern "C" int func();

int main() {
   return func();
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir saf görüntüden yerel işlevin nasıl kullanıldığını gösterir. Açık **`__cdecl`** çağırma kuralı belirticisini aklınızda edin.

```cpp
// LNK2031_c.cpp
// compile with: /clr:pure LNK2031.lib
extern "C" int __cdecl func();

int main() {
   return func();
}
```
