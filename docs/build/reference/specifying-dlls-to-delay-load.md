---
description: "Daha fazla bilgi edinin: Gecikmeli yük için dll 'Ler belirtme"
title: Gecikme Yükü DLL'lerini Belirtme
ms.date: 11/04/2016
helpviewer_keywords:
- DELAYLOAD linker option
- delayed loading of DLLs
- delayed loading of DLLs, specifying
- /DELAYLOAD linker option
ms.assetid: 94cbecfe-7a42-40d1-a618-9f2786bac0d8
ms.openlocfilehash: ece96ea6f818c7e0bc6b6e032ce523e96a9f4ecb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224551"
---
# <a name="specifying-dlls-to-delay-load"></a>Gecikme Yükü DLL'lerini Belirtme

[/Delayload](delayload-delay-load-import.md): bağlayıcı seçeneğiyle hangi dll 'lerin yük geciktirip gerektiğini belirtebilirsiniz `dllname` . Kendi yardımcı işlevinizin sürümünü kullanmayı planlamıyorsanız, programınızı delayimp. lib (masaüstü uygulamaları için) veya dloadhelper. lib (Mağaza uygulamaları için) ile bağlamanız gerekir.

Aşağıda DLL yükleme gecikmesi için basit bir örnek verilmiştir:

```
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

Projenin hata ayıklama sürümünü oluşturun. Hata ayıklayıcıyı kullanarak kodda adım adım ilerleyin ve user32.dll yalnızca çağrısı yaptığınızda yükleneceğini fark edersiniz `MessageBox` .

## <a name="see-also"></a>Ayrıca bkz.

[Delay-Loaded dll 'Ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)
