---
title: Bağlayıcı Araçları Hatası LNK2031
ms.date: 11/04/2016
f1_keywords:
- LNK2031
helpviewer_keywords:
- LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
ms.openlocfilehash: 003b9a58bfb08130f034530f59e2de27efa2ae8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298925"
---
# <a name="linker-tools-error-lnk2031"></a>Bağlayıcı Araçları Hatası LNK2031

> için p/invoke üretilemiyor "*function_declaration*" *decorated_name*; çağırma kuralı meta veriler eksik

## <a name="remarks"></a>Açıklamalar

Yerel bir işlevin saf bir görüntüye alınmaya çalışılırken örtük çağırma kuralları yerel ve saf derlemeler farkı olduğunu unutmayın. Saf görüntüleri hakkında daha fazla bilgi için bkz. [saf ve doğrulanabilen kod (C++/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

**/CLR: pure** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

## <a name="example"></a>Örnek

Bu kod örneği, çağırma kuralı olduğunu örtük olarak dışarı aktarılan, yerel, işlevi içeren bir bileşen oluşturur [__cdecl](../../cpp/cdecl.md).

```cpp
// LNK2031.cpp
// compile with: /LD
extern "C" {
   __declspec(dllexport) int func() { return 3; }
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, yerel işlev tüketen saf bir istemci oluşturur. Ancak, çağırma kuralı altında **/CLR: pure** olduğu [__clrcall](../../cpp/clrcall.md). Aşağıdaki örnek, LNK2031 oluşturur.

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

Aşağıdaki örnek, yerel işlev saf bir görüntüden kullanma işlemi gösterilmektedir. Açıkça Not **__cdecl** çağırma kuralı tanımlayıcısı.

```cpp
// LNK2031_c.cpp
// compile with: /clr:pure LNK2031.lib
extern "C" int __cdecl func();

int main() {
   return func();
}
```