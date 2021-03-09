---
title: 'Hata: genel arabellek taşması'
description: Kaynak örnekleri ve genel değişken taşma hataları için canlı hata ayıklama ekran görüntüleri.
ms.date: 03/02/2021
f1_keywords:
- global-buffer-overflow
helpviewer_keywords:
- global-buffer-overflow error
- AddressSanitizer error global-buffer-overflow
ms.openlocfilehash: cdc637318c523d43684f938df51030ec803a754b
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470762"
---
# <a name="error-global-buffer-overflow"></a>Hata: `global-buffer-overflow`

> Adres temizleme hatası: genel arabellek taşması

Derleyici, veya bölümlerindeki herhangi bir değişken için meta veriler oluşturur `.data` `.bss` . Bu değişkenlerin genel veya dosya statik dil kapsamı vardır. Başlamadan önce bellekte ayrılırlar `main()` . C 'deki genel değişkenler C++ ' dan çok farklı şekilde değerlendirilir. Bu fark, C bağlamak için karmaşık kurallar nedeniyle oluşur.

C 'de, genel bir değişken birkaç kaynak dosyasında bildirilebilirler ve her tanım farklı türlere sahip olabilir. Derleyici tüm olası tanımları aynı anda göremez, ancak bağlayıcı olabilir. C için bağlayıcı varsayılan olarak en büyük boyutlu değişkeni tüm farklı bildirimlerin arasından seçmeye yöneliktir.

C++ ' da, derleyici tarafından bir Global değer ayrılır. Yalnızca bir tanım olabilir, bu nedenle her tanımın boyutu derleme zamanında bilinirdi.

## <a name="example---globals-in-c-with-multiple-type-definitions"></a>Örnek-birden çok tür tanımına sahip ' C ' içinde Globals

```cpp
// file: a.c
int x;
```

```cpp
// file: b.c
char* x;
```

```cpp
// file: c.c
float* x[3];
```

```cpp
// file: example1-main.c
// global-buffer-overflow error

// AddressSanitizer reports a buffer overflow at the first line
// in function main() in all cases, REGARDLESS of the order in 
// which the object files: a.obj, b.obj, and c.obj are linked.
  
double x[5];
 
int main() { 
    int rc = (int) x[5];  // Boom!
    return rc; 
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl a.c b.c c.c example1-main.c /fsanitize=address /Zi
devenv /debugexe example1-main.exe
```

### <a name="resulting-error"></a>Ortaya çıkan hata

:::image type="content" source="media/global-overflow-example-1.png" alt-text="Örnek 1 ' de genel arabellek taşması hatası görüntüleyen hata ayıklayıcının ekran görüntüsü.":::

## <a name="example---simple-function-level-static"></a>Örnek-basit işlev düzeyi statik

```cpp
// example2.cpp
// global-buffer-overflow error
#include <string.h>

int 
main(int argc, char **argv) {

    static char XXX[10];
    static char YYY[10];
    static char ZZZ[10];

    memset(XXX, 0, 10); memset(YYY, 0, 10); memset(ZZZ, 0, 10);

    int res = YYY[argc * 10];  // Boom!

    res += XXX[argc] + ZZZ[argc];
    return res;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example2.cpp /fsanitize=address /Zi
devenv /debugexe example2.exe
```

### <a name="resulting-error---simple-function-level-static"></a>Sonuç hatası-basit işlev düzeyi statik

:::image type="content" source="media/global-overflow-example-2.png" alt-text="Örnek 2 ' de genel arabellek taşması hatasını görüntüleyen hata ayıklayıcı ekran görüntüsü.":::

## <a name="example---all-global-scopes-in-c"></a>Örnek-C++ ' ta tüm Genel kapsamlar

```cpp
// example3.cpp
// global-buffer-overflow error

// Run 4 different ways with the choice of one of these options:
//
// -g : Global
// -c : File static
// -f : Function static
// -l : String literal

#include <string.h>

struct C {
    static int array[10];
};

// normal global
int global[10];

// class static
int C::array[10];

int main(int argc, char **argv) {

    int one = argc - 1;

    switch (argv[1][1]) {
    case 'g': return global[one * 11];     //Boom! simple global
    case 'c': return C::array[one * 11];   //Boom! class static
    case 'f':
        static int array[10];
        memset(array, 0, 10);
        return array[one * 11];            //Boom! function static
    case 'l':
        // literal global ptr created by compiler
        const char *str = "0123456789";
        return str[one * 11];              //Boom! .rdata string literal allocated by compiler
    }
    return 0;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example3.cpp /fsanitize=address /Zi
devenv /debugexe example3.exe -l
```

### <a name="resulting-error---all-global-scopes-in-c"></a>Sonuç hatası-C++ ' ta tüm Genel kapsamlar

:::image type="content" source="media/global-overflow-example-3.png" alt-text="Örnek 3 ' te genel arabellek taşması hatası görüntüleyen hata ayıklayıcının ekran görüntüsü.":::

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
