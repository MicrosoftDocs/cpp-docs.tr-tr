---
title: 'Hata: dinamik yığın arabelleği-taşma'
description: Allowca hataları için kaynak örnekleri ve canlı hata ayıklama ekran görüntüleri.
ms.date: 03/02/2021
f1_keywords:
- dynamic-stack-buffer-overflow
helpviewer_keywords:
- dynamic-stack-buffer-overflow error
- AddressSanitizer error dynamic-stack-buffer-overflow
ms.openlocfilehash: 4ccf8c9bbab7eb14cac80f0f1d3f9478fc035f8b
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470769"
---
# <a name="error-dynamic-stack-buffer-overflow"></a>Hata: `dynamic-stack-buffer-overflow`

> Adres temizleme hatası: dinamik yığın arabelleği-taşma

Bu örnek, yığın tarafından ayrılan nesnenin sınırları dışında arabellek erişiminin sonucu olan hatayı gösterir.

## <a name="example---alloca-overflow-right"></a>Örnek `alloca` taşma (sağ)

```cpp
// example1.cpp
// dynamic-stack-buffer-overflow error
#include <malloc.h>

__declspec(noinline)
void foo(int index, int len) {

    volatile char *str = (volatile char *)_alloca(len);

    //    reinterpret_cast<long>(str) & 31L;

    str[index] = '1'; // Boom !
}

int main(int argc, char **argv) {

    foo(33, 10);
    return 0;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>Ortaya çıkan hata

:::image type="content" source="media/dynamic-stack-buffer-overflow-example-1.png" alt-text="Örnek 1 ' de dinamik yığın arabelleği-taşma hatası görüntüleyen hata ayıklayıcının ekran görüntüsü.":::

## <a name="example---alloca-overflow-left"></a>Örnek `alloca` taşma (sol)

```cpp
// example2.cpp
// dynamic-stack-buffer-overflow error
#include <malloc.h>

__declspec(noinline)
void foo(int index, int len) {

    volatile char *str = (volatile char *)_alloca(len);

    str[index] = '1';  // Boom!
}

int main(int argc, char **argv) {
    foo(-1, 10);
    return 0;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example2.cpp /fsanitize=address /Zi
devenv /debugexe example2.exe
```

### <a name="resulting-error---alloca-overflow-left"></a>Ortaya çıkan hata- `alloca` taşma (sol)

:::image type="content" source="media/dynamic-stack-buffer-overflow-example-2.png" alt-text="Örnek 2 ' de dinamik yığın arabelleği-taşma hatası görüntüleyen hata ayıklayıcının ekran görüntüsü.":::

## <a name="example---several-calls-to-alloca"></a>Örnek-birkaç öğesine çağrı `alloca`

```cpp
// example3.cpp
// dynamic-stack-buffer-overflow error
#include <stdio.h>
#include <stdlib.h>
#include <malloc.h>

#define SIZE 7
extern void nothing();
int x=13,*aa,*bb,y=0;
int fail = 0;
int tmp;

int main()
{
    int* cc;
    int i;
    int k = 17;
    __try {
        tmp = k;
        aa = (int*)_alloca(SIZE * sizeof(int));
        if (((int)aa) & 0x3)
            fail = 1;
        for (i = 0; i < SIZE; i++) {
            aa[i] = x + 1 + i;
        }
        bb = (int*)_alloca(x * sizeof(int));
        if (((int)bb) & 0x3)
            fail = 1;

        for (i = 0; i < x; i++) {
            bb[i] = 7;
            bb[i] = bb[i] + i;
        }
        {
            int s = 112728283;
            int ar[8];
            for (i = 0; i < 8; i++)
                ar[i] = s * 17 * i;
        }

        cc = (int*)_alloca(x);
        if (((int)cc) & 0x3)
            fail = 1;

        cc[0] = 0;
        cc[1] = 1;
        cc[2] = 2;
        cc[3] = 3;             // <--- Boom!
        for (i = 0; i < x; i++)
            if (bb[i] != (7 + i))
                fail = 1;
        if (tmp != k)
            fail = 1;
        if (fail) {
            printf("fail\n");
            exit(7);
        }
        printf("%d\n", (*cc) / y);
        printf("fail\n");
        exit(7);
    }
    __except (1)
    {
        for (i = 0; i < SIZE; i++)
            if (aa[i] != (x + i + 1))
                fail = 1;
        if (fail) {
            printf("fail\n");
            exit(7);
        }
        printf("pass\n");
        exit(0);
    }
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example3.cpp /fsanitize=address /Zi
devenv /debugexe example3.exe
```

### <a name="resulting-error---several-calls-to-alloca"></a>Sonuç hatası-alloca 'ya birkaç çağrı

:::image type="content" source="media/dynamic-stack-buffer-overflow-example-3.png" alt-text="Örnek 3 ' te dinamik yığın arabelleği-taşma hatası görüntüleyen hata ayıklayıcının ekran görüntüsü.":::

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
