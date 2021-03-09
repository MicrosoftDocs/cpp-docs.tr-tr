---
title: 'Hata: yığın arabelleği-taşma'
description: Yığın arabelleği taşma hataları için kaynak örnekleri ve canlı hata ayıklama ekran görüntüleri.
ms.date: 03/02/2021
f1_keywords:
- stack-buffer-overflow
helpviewer_keywords:
- stack-buffer-overflow error
- AddressSanitizer error stack-buffer-overflow
ms.openlocfilehash: 52b4dcf2caad04703b9fa407f0546e94528849c4
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470750"
---
# <a name="error-stack-buffer-overflow"></a>Hata: `stack-buffer-overflow`

> Adres temizleme hatası: yığın arabelleği taşması

Yığın arabelleği taşması, C veya C++ ' da birçok yol ortaya çıkabilir. Basit bir yeniden derleyerek yakalayabilmeniz için bu hata kategorisi için birkaç örnek sağlıyoruz.

## <a name="example---stack-buffer-overflow"></a>Örnek-yığın arabelleği taşması

```cpp
// example1.cpp
// stack-buffer-overflow error
#include <string.h>

int main(int argc, char **argv) {
    char x[10];
    memset(x, 0, 10);
    int res = x[argc * 10];  // Boom! Classic stack buffer overflow

    return res;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>Ortaya çıkan hata

:::image type="content" source="media/stack-buffer-overflow-example-1.png" alt-text="1 örnek 1 ' de yığın arabelleği taşma hatası gösteren hata ayıklayıcı ekran görüntüsü.":::

## <a name="example---stack-buffer-math"></a>Örnek-yığın arabelleği matematik

```cpp
// example2.cpp
// stack-buffer-overflow error
#include <string.h>
#include <stdio.h>
#include <stdlib.h>
#include <assert.h>

int main(int argc, char **argv) {
    assert(argc >= 2);
    int idx = atoi(argv[1]);
    char AAA[10], BBB[10], CCC[10];
    memset(AAA, 0, sizeof(AAA));
    memset(BBB, 0, sizeof(BBB));
    memset(CCC, 0, sizeof(CCC));
    int res = 0;
    char *p = AAA + idx;
    printf("AAA: %p\ny: %p\nz: %p\np: %p\n", AAA, BBB, CCC, p);

    return *(short*)(p) + BBB[argc % 2] + CCC[argc % 2];  // Boom! ... when argument is 9
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example2.cpp /fsanitize=address /Zi
devenv /debugexe example2.exe 9
```

### <a name="resulting-error---stack-buffer-math"></a>Sonuç hatası-yığın arabelleği matematik

:::image type="content" source="media/stack-buffer-overflow-example-2.png" alt-text="Yığın arabelleği gösteren hata ayıklayıcı ekran görüntüsü örnek 2 ' de.":::

## <a name="example---improper-down-cast-on-stack"></a>Örnek-yığında uygun olmayan dönüştürme

```cpp
// example3.cpp
// stack-buffer-overflow error
class Parent {
public:
    int field;
};

class Child : public Parent {
public:
    int extra_field;
};

int main(void) {

    Parent p;
    Child *c = (Child*)&p;  // Boom !
    c->extra_field = 42;

    return 0;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example3.cpp /fsanitize=address /Zi
devenv /debugexe example3.exe
```

### <a name="resulting-error---improper-down-cast-on-stack"></a>Sonuç hatası-yığında hatalı aşağı dönüştürme

:::image type="content" source="media/stack-buffer-overflow-example-3.png" alt-text="3. örnekte yığın arabelleği taşma hatası gösteren hata ayıklayıcı ekran görüntüsü.":::

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
