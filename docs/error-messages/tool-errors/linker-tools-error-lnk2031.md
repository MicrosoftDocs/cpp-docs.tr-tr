---
title: Bağlayıcı araçları hatası LNK2031 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2031
dev_langs:
- C++
helpviewer_keywords:
- LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d86ea6da8a73d9ba2427e9455c4fca87cd32dd2b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34703671"
---
# <a name="linker-tools-error-lnk2031"></a>Bağlayıcı Araçları Hatası LNK2031

> p/Invoke için oluşturulamadı "*function_declaration*" *decorated_name*; meta veriler eksik çağırma

## <a name="remarks"></a>Açıklamalar

Yerel bir işleve saf görüntüsüne alınmaya çalışılırken örtük çağırma kurallarını yerel ve saf derlemeler arasında farklı olduğunu unutmayın. Saf görüntüleri hakkında daha fazla bilgi için bkz: [saf ve doğrulanabilen kod (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

**/CLR: pure** derleyici seçeneği Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

## <a name="example"></a>Örnek

Bu kod örneği, çağırma olduğu örtük olarak dışarı aktarılan, yerel, işlevi içeren bir bileşen oluşturur [__cdecl](../../cpp/cdecl.md).

```cpp
// LNK2031.cpp
// compile with: /LD
extern "C" {
   __declspec(dllexport) int func() { return 3; }
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, yerel işlevi tüketir saf bir istemci oluşturur. Ancak, çağırma altında **/CLR: pure** olan [__clrcall](../../cpp/clrcall.md). Aşağıdaki örnek LNK2031 oluşturur.

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

Aşağıdaki örnek, saf görüntü yerel işlevden tüketen gösterilmektedir. Açık Not **__cdecl** arama kuralı tanımlayıcısı.

```cpp
// LNK2031_c.cpp
// compile with: /clr:pure LNK2031.lib
extern "C" int __cdecl func();

int main() {
   return func();
}
```