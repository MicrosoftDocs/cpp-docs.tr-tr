---
title: 'Hata: Çift boş'
description: İkili ücretsiz hatalara yönelik kaynak örnekleri ve canlı hata ayıklama ekran görüntüleri.
ms.date: 03/02/2021
f1_keywords:
- double-free
helpviewer_keywords:
- double-free error
- AddressSanitizer error double-free
ms.openlocfilehash: 6fb508e581a8c19474311d0406622e6353208433
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470774"
---
# <a name="error-double-free"></a>Hata: `double-free`

> Adres temizleme hatası: serbest bırakılan belleğin ayırmayı kaldırma

C 'de, yanlışlıkla hatalı çağrı yapabilirsiniz `free` . C++ ' da birden `delete` çok kez çağrı yapabilirsiniz. Bu örneklerde, ve ile ilgili hataları gösteririz `delete` `free` `HeapCreate` .

## <a name="example-c---double-operator-delete"></a>Örnek C++-Double `operator delete`

```cpp
// example1.cpp
// double-free error
int main() {

    int *x = new int[42];
    delete [] x;

    // ... some complex body of code

    delete [] x;
    return 0;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error---double-operator-delete"></a>Sonuç hatası-Double `operator delete`

:::image type="content" source="media/double-free-example-1.png" alt-text="Örnek 1 ' de çift boş hata görüntüleyen hata ayıklayıcının ekran görüntüsü.":::

## <a name="example-c---double-free"></a>Örnek ' C '-Double `free`

```cpp
// example2.cpp
// double-free error
#include <stdlib.h>
#include <string.h>

int main(int argc, char** argv) {

    char* x = (char*)malloc(10 * sizeof(char));
    memset(x, 0, 10);
    int res = x[argc];
    free(x);

    // ... some complex body of code

    free(x + argc - 1);  // Boom!
    return res;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example2.cpp /fsanitize=address /Zi
devenv /debugexe example2.exe
```

### <a name="resulting-error---double-free"></a>Sonuç hatası-Double `free`

:::image type="content" source="media/double-free-example-2.png" alt-text="Örnek 2 ' de çift boş hata görüntüleyen hata ayıklayıcının ekran görüntüsü.":::

## <a name="example---windows-heapcreate-double-heapfree"></a>Örnek-Windows `HeapCreate` Double `HeapFree`

```cpp
// example3.cpp
// double-free error
#include <Windows.h>
#include <stdio.h>

int main() {
    void* newHeap = HeapCreate(0, 0, 0);
    void* newAlloc = HeapAlloc(newHeap, 0, 100);

    HeapFree(newHeap, 0, newAlloc);
    HeapFree(newHeap, 0, newAlloc);
    printf("failure\n");
    return 1;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example3.cpp /fsanitize=address /Zi
devenv /debugexe example3.exe
```

### <a name="resulting-error---windows-heapcreate-double-heapfree"></a>Ortaya çıkan hata-Windows `HeapCreate` Double `HeapFree`

:::image type="content" source="media/double-free-example-3.png" alt-text="Örnek 3 ' te çift boş hata görüntüleyen hata ayıklayıcının ekran görüntüsü.":::

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
