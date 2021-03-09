---
title: 'Hata: ayırma-ayırma uyumsuzluğu'
description: Kaynak örnekleri ve ayırma uyuşmazlığı hataları için canlı hata ayıklama ekran görüntüleri.
ms.date: 03/02/2021
f1_keywords:
- alloc-dealloc-mismatch
helpviewer_keywords:
- alloc-dealloc-mismatch error
- AddressSanitizer error alloc-dealloc-mismatch
ms.openlocfilehash: 150809d28631d5d194363e3cb5525163bf7a5e88
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470778"
---
# <a name="error-alloc-dealloc-mismatch"></a>Hata: `alloc-dealloc-mismatch`

> Adres temizleme hatası: ayırma ve ayırmayı kaldırma API 'Leri arasında uyuşmazlık

`alloc` / `dealloc` Addresstemizleyerek eşleşmeyen işlev Windows için varsayılan olarak kapalıdır. Etkinleştirmek için `set ASAN_OPTIONS=alloc_dealloc_mismatch=1` programı çalıştırmadan önce ' yi çalıştırın. Bu ortam değişkeni,, ve üzerindeki hataları raporlamak için çalışma zamanında denetlenir `malloc` / `delete` `new` / `free` `new` / `delete[]` .

## <a name="example"></a>Örnek

```cpp
// example1.cpp
// alloc-dealloc-mismatch error
#include <stdio.h>
#include <stdlib.h>

int main(int argc, char* argv[]) {

    if (argc != 2) return -1;

    switch (atoi(argv[1])) {

    case 1:
        delete[](new int[10]);
        break;
    case 2:
        delete (new int[10]);      // Boom!
        break;
    default:
        printf("arguments: 1: no error 2: runtime error\n");
        return -1;
    }

    return 0;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example1.cpp /fsanitize=address /Zi
set ASAN_OPTIONS=alloc_dealloc_mismatch=1
devenv /debugexe example1.exe 2
```

### <a name="resulting-error"></a>Ortaya çıkan hata

:::image type="content" source="media/alloc-dealloc-mismatch-example-1.png" alt-text="Örnek 1 ' de ayırma kaldırma hatası gösteren hata ayıklayıcı ekran görüntüsü.":::

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
