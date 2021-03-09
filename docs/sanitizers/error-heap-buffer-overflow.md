---
title: 'Hata: yığın arabelleği-taşma'
description: Kaynak örnekleri ve yığın değişkeni taşma hataları için canlı hata ayıklama ekran görüntüleri.
ms.date: 03/02/2021
f1_keywords:
- heap-buffer-overflow
helpviewer_keywords:
- heap-buffer-overflow error
- AddressSanitizer error heap-buffer-overflow
ms.openlocfilehash: 7eec8d0fa8c7382a5a4ecea9811298aaaba760a2
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470670"
---
# <a name="error-heap-buffer-overflow"></a>Hata: `heap-buffer-overflow`

> Adres temizleme hatası: yığın arabelleği taşması

Bu örnek, yığın tarafından ayrılan nesnenin sınırları dışında bir bellek erişimi gerçekleştiğinde oluşan hatayı gösterir.

## <a name="example---classic-heap-buffer-overflow"></a>Örnek-klasik yığın arabelleği taşması

```cpp
// example1.cpp
// heap-buffer-overflow error
#include <stdlib.h>
#include <string.h>

int main(int argc, char **argv) {

    char *x = (char*)malloc(10 * sizeof(char));
    memset(x, 0, 10);
    int res = x[argc * 10];  // Boom!

    free(x);
    return res;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>Ortaya çıkan hata

:::image type="content" source="media/heap-buffer-overflow-example-1.png" alt-text="Örnek 1 ' de yığın arabelleği taşma hatası gösteren hata ayıklayıcı ekran görüntüsü.":::

## <a name="example---improper-down-cast"></a>Örnek-uygun olmayan dönüştürme

```cpp
// example2.cpp
// heap-buffer-overflow error
class Parent {
public:
    int field;
};

class Child : public Parent {
public:
    int extra_field;
};

int main(void) {
    Parent *p = new Parent;
    Child *c = (Child*)p;  // Intentional error here!
    c->extra_field = 42;

    return 0;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example2.cpp /fsanitize=address /Zi
devenv /debugexe example2.exe
```

### <a name="resulting-error---improper-down-cast"></a>Sonuç hatası-hatalı aşağı dönüştürme

:::image type="content" source="media/heap-buffer-overflow-example-2.png" alt-text="Örnek 2 ' de yığın arabelleği taşma hatası gösteren hata ayıklayıcı ekran görüntüsü.":::

## <a name="example---strncpy-into-heap"></a>Örnek-strncpy yığına

```cpp
// example3.cpp
// heap-buffer-overflow error
#include <string.h>
#include <stdlib.h>

int main(int argc, char **argv) {

    char *hello = (char*)malloc(6);
    strcpy(hello, "hello");

    char *short_buffer = (char*)malloc(9);
    strncpy(short_buffer, hello, 10);  // Boom!

    return short_buffer[8];
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example3.cpp /fsanitize=address /Zi
devenv /debugexe example3.exe
```

### <a name="resulting-error---strncpy-into-heap"></a>Sonuç hatası-strncpy yığına

:::image type="content" source="media/heap-buffer-overflow-example-3.png" alt-text="Örnek 3 ' te yığın arabelleği taşma hatası gösteren hata ayıklayıcı ekran görüntüsü.":::

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
