---
title: 'Hata: yığın-ara bellek-yetersiz'
description: Yığın arabellek yetersizliği hataları için kaynak örnekleri ve canlı hata ayıklama ekran görüntüleri.
ms.date: 03/02/2021
f1_keywords:
- stack-buffer-underflow
helpviewer_keywords:
- stack-buffer-underflow error
- AddressSanitizer error stack-buffer-underflow
ms.openlocfilehash: 78705933378d7880057d9b7fd13a933f73129fcb
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470650"
---
# <a name="error-stack-buffer-underflow"></a>Hata: `stack-buffer-underflow`

> Adres temizleme hatası: yığın arabelleği yetersiz

Bu hata iletileri bir yığın değişkeninin başlangıcından önce bir yere bellek erişimi gösterir.

## <a name="example---local-array-underflow"></a>Örnek-yerel dizi yetersiz

```cpp
// example1.cpp
// stack-buffer-underflow error
#include <stdio.h>

int main() {

    int subscript = -1;
    char buffer[42];
    buffer[subscript] = 42; // Boom!
   
    return 0;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>Ortaya çıkan hata

:::image type="content" source="media/stack-buffer-underflow-example-1.png" alt-text="Örnek 1 ' de yığın arabellek yetersiz hatası gösteren hata ayıklayıcı ekran görüntüsü.":::

## <a name="example---stack-underflow-on-thread"></a>Örnek-iş parçacığında yığın yetersiz kalması

```cpp
// example2.cpp
// stack-buffer-underflow error
#include <windows.h>

DWORD WINAPI thread_proc(void *) {
    int subscript = -1;
    volatile char stack_buffer[42];
    stack_buffer[subscript] = 42;

    return 0;
}

int main() {
    HANDLE thr = CreateThread(NULL, 0, thread_proc, NULL, 0, NULL);

    if (thr == 0) return 0;

    WaitForSingleObject(thr, INFINITE);

    return 0;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example2.cpp /fsanitize=address /Zi
devenv /debugexe example2.exe
```

### <a name="resulting-error----stack-underflow-on-thread"></a>Ortaya çıkan hata-iş parçacığında yığın yetersiz kalması

:::image type="content" source="media/stack-buffer-underflow-example-2.png" alt-text="Örnek 2 ' de yığın arabellek yetersiz hatası gösteren hata ayıklayıcı ekran görüntüsü.":::

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
