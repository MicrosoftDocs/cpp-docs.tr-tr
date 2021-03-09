---
title: 'Hata: strncat-param-örtüşme'
description: Strcat parametresi örtüşme hataları için kaynak örnekleri ve canlı hata ayıklama ekran görüntüleri.
ms.date: 03/02/2021
f1_keywords:
- strncat-param-overlap
helpviewer_keywords:
- strncat-param-overlap error
- AddressSanitizer error strcat-param-overlap
ms.openlocfilehash: 9ae5b6f602d61f26e1c5d3d9eded35d3f587c53e
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470642"
---
# <a name="error-strncat-param-overlap"></a>Hata: `strncat-param-overlap`

> Adres temizleme hatası: strncat-param-örtüşme

Belleği çakışan arabellekte taşınan kod, tanılama hatalarına neden olabilir.

## <a name="example"></a>Örnek

Bu örnek, Addresstemizleyerek örtüşen parametrelerin CRT işlevlerine neden olan hataları nasıl yakalayaabileceğini gösterir.

( [LLVM-Project/Compiler-RT/test/asan/TestCases/strncat-Overlap. cpp](https://github.com/llvm/llvm-project/blob/62ec4ac90738a5f2d209ed28c822223e58aaaeb7/compiler-rt/test/asan/TestCases/strncat-overlap.cpp)tabanlı)

```cpp
// example1.cpp
// strncat-param-overlap error
#include <string.h>

void bad_function() {
    char buffer[] = "hello\0XXX";
    strncat(buffer, buffer + 1, 3); // BOOM
    return;
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

:::image type="content" source="media/strcat-param-overlap-example-1.png" alt-text="Strncat-param-örnek 1 ' de çakışma hatası görüntüleyen hata ayıklayıcı ekran görüntüsü.":::

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
