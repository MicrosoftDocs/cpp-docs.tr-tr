---
description: Gecikmeli yük için dll 'Ler belirtme hakkında daha fazla bilgi edinin
title: Yük gecikmesi için dll 'Leri belirtin
ms.date: 01/19/2021
helpviewer_keywords:
- DELAYLOAD linker option
- delayed loading of DLLs
- delayed loading of DLLs, specifying
- /DELAYLOAD linker option
ms.openlocfilehash: de8c2e3cb9605cbc6dbc215a0449348c12295c17
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667497"
---
# <a name="specify-dlls-to-delay-load"></a>Yük gecikmesi için dll 'Leri belirtin

Hangi dll 'Lerin yük, bağlayıcı seçeneğini kullanarak geciktirimesini belirtebilirsiniz [`/delayload:dllname`](delayload-delay-load-import.md) . Kendi yardımcı işlevinizin sürümünü kullanmayı planlamıyorsanız, programınızı *`delayimp.lib`* (masaüstü uygulamaları için) veya *`dloadhelper.lib`* (UWP uygulamaları için) ile bağlamanız gerekir.

Bir DLL yükleme gecikmesi için basit bir örnek aşağıda verilmiştir:

```cpp
// cl t.cpp user32.lib delayimp.lib  /link /DELAYLOAD:user32.dll
#include <windows.h>
// uncomment these lines to remove .libs from command line
// #pragma comment(lib, "delayimp")
// #pragma comment(lib, "user32")

int main() {
   // user32.dll will load at this point
   MessageBox(NULL, "Hello", "Hello", MB_OK);
}
```

Projenin hata ayıklama sürümünü oluşturun. Hata ayıklayıcıyı kullanarak kodda adım adım ilerleyin ve *`user32.dll`* yalnızca çağrısını yaptığınızda yüklendiğini görürsünüz `MessageBox` .

## <a name="see-also"></a>Ayrıca bkz.

[Gecikmeli yüklenen DLL'ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)
