---
title: 'Hata: memckopyala-param-örtüşme'
description: Kaynak örnekleri ve memcler parametresi örtüşme hataları için canlı hata ayıklama ekran görüntüleri.
ms.date: 03/02/2021
f1_keywords:
- memcpy-param-overlap
helpviewer_keywords:
- memcpy-param-overlap error
- AddressSanitizer error memcpy-param-overlap
ms.openlocfilehash: 1df0310ab2abb326cf895a72afbdffa7c239d9da
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470761"
---
# <a name="error-memcpy-param-overlap"></a>Hata: `memcpy-param-overlap`

> Adres temizleme hatası: memckopyala-param-örtüşme

CRT işlevi [`memcpy`](../c-runtime-library/reference/memcpy-wmemcpy.md) Çakışan belleği **desteklemiyor** . CRT, çakışan belleği desteklemeye yönelik bir alternatif sağlar `memcpy` : [`memmove`](../c-runtime-library/reference/memmove-wmemmove.md) .

Yaygın olarak karşılaşılan bir hata, `memmove` anlam ile eşdeğer olarak değerlendirilir `memcpy` .

## <a name="example"></a>Örnek

```cpp
// example1.cpp
// memcpy-param-overlap error
#include <string.h>

__declspec(noinline) void bad_function() {
    char buffer[] = "hello";

    memcpy(buffer, buffer + 1, 5); // BOOM!
}

int main(int argc, char **argv) {
    bad_function();
    return 0;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>Ortaya çıkan hata

:::image type="content" source="media/memcpy-param-overlap-example-1.png" alt-text="Örnek 1 ' de memckopyala-param-çakışma hatası görüntülüyor hata ayıklayıcı ekran görüntüsü.":::

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
