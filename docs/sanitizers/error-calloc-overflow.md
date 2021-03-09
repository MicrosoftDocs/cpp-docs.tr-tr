---
title: 'Hata: calloc-overflow'
description: Kaynak örnekleri ve calloc overflow hataları için canlı hata ayıklama ekran görüntüleri.
ms.date: 03/02/2021
f1_keywords:
- calloc-overflow
helpviewer_keywords:
- calloc-overflow error
- AddressSanitizer error calloc-overflow
ms.openlocfilehash: 63af733061d255924f0b0fbd5f54e4d77359c436
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470674"
---
# <a name="error-calloc-overflow"></a>Hata: `calloc-overflow`

> Adres temizleme hatası: calloc-overflow

CRT işlevi, [`calloc`](../c-runtime-library/reference/calloc.md) bir dizide 0 olarak başlatılan öğeleri içeren bir dizi oluşturur. Bağımsız değişkenler, dönüş değeri olarak NULL bir işaretçiye yol gösteren bir iç hata oluşturabilir.

## <a name="example"></a>Örnek

```cpp
// example1.cpp
// calloc-overflow error
#include <stdio.h>
#include <stdlib.h>

int number = -1;
int element_size = 1000;

int main() {

    void *p = calloc(number, element_size);      // Boom!

    printf("calloc returned: %zu\n", (size_t)p);

    return 0;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>Ortaya çıkan hata

:::image type="content" source="media/calloc-overflow-example-1.png" alt-text="Örnek 1 ' de calloc-overflow hatası görüntüleyen hata ayıklayıcının ekran görüntüsü.":::

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
