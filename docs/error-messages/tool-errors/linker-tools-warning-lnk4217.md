---
title: Bağlayıcı Araçları Uyarısı LNK4217
ms.date: 07/23/2019
f1_keywords:
- LNK4217
helpviewer_keywords:
- LNK4217
ms.assetid: 280dc03e-5933-4e8d-bb8c-891fbe788738
ms.openlocfilehash: 1ce410312493b353bb68ea7264fce9cd6a394e0d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183117"
---
# <a name="linker-tools-warning-lnk4217"></a>Bağlayıcı Araçları Uyarısı LNK4217

> '*filename_1. obj*' içinde tanımlanan '*symbol*' sembolü, '*Function*' işlevindeki '*filename_2. obj*' tarafından içeri aktarıldı

sembol aynı görüntüde bir nesne dosyasında tanımlı olsa da, sembol için [__declspec (dllimport)](../../cpp/dllexport-dllimport.md) belirtildi. Bu uyarıyı çözmek için `__declspec(dllimport)` değiştiricisini kaldırın.

## <a name="remarks"></a>Açıklamalar

*sembol* , görüntüde tanımlanan simge adıdır. *işlevi* , sembolünü içeri aktaran işlevdir.

Bu uyarı [/clr](../../build/reference/clr-common-language-runtime-compilation.md) seçeneğini kullanarak derlerken görünmez.

LNK4217, iki modülü birlikte bağlamayı denerseniz, bunun yerine ilk modülün içeri aktarma kitaplığıyla ikinci modülü derlemeniz gerekir.

```cpp
// main.cpp
__declspec(dllimport) void func();

int main()
{
    func();
    return 0;
}

```

ardından,

```cpp
// tt.cpp
// compile with: /c
void func() {}
```

Burada gösterildiği gibi bu iki modülün derlenmesi denenmeye LNK4217 neden olur:

```cmd
cl.exe /c main.cpp tt.cpp
link.exe main.obj tt.obj
```

Hatayı onarmak için, iki dosyayı derledikten sonra, bir. lib dosyası oluşturmak için TT. obj ' ye Pass. exe ' ye geçirin ve ardından burada gösterildiği gibi Main. obj ile TT. lib ' i bağlayın:

```cmd
cl.exe /c main.cpp tt.cpp
lib.exe tt.obj /export:func /def
link.exe main.obj tt.lib
```

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı araçları uyarısı LNK4049](linker-tools-warning-lnk4049.md) \
[Bağlayıcı araçları uyarısı LNK4286](linker-tools-warning-lnk4286.md) \
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)
