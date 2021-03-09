---
title: 'Hata: Stack-RETURN-RETURN-RETURN'
description: Kaynak örnekleri ve yığın kullanımı için hata ayıklama ekran görüntüleri Return hatalarından sonra.
ms.date: 03/02/2021
f1_keywords:
- stack-use-after-return
helpviewer_keywords:
- stack-use-after-return error
- AddressSanitizer error stack-use-after-return
ms.openlocfilehash: 37d950b0c3b4da880524c0c5825d86d6feec9654
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470745"
---
# <a name="error-stack-use-after-return"></a>Hata: `stack-use-after-return`

> Adres temizleme hatası: döndürmeden sonra yığın belleği kullanımı

Bu denetim, ek bir derleyici seçeneği tarafından etkinleştirilen [`/fsanitize-address-use-after-return`](../build/reference/fsanitize.md) ve ortam değişkenini ayarlayarak kod oluşturmayı gerektirir `ASAN_OPTIONS=detect_stack_use_after_return=1` .

Bu denetim, uygulamanızı önemli ölçüde yavaşlatabilir. Döndürmeden sonra kullanımı destekleyen algoritmanın [Clang özetini](https://github.com/google/sanitizers/wiki/AddressSanitizerUseAfterReturn) ve daha büyük performans maliyetlerini göz önünde bulundurun.

> [!IMPORTANT]
> Ek derleyici seçeneğini kullanarak bir nesne dosyası oluşturursanız **`/fsanitize-address-use-after-return`** , derleyici tarafından oluşturulan kod, yığın çerçevesinin nasıl ayrılacağını gösteren bir çalışma zamanı kararı sağlar. Ortam değişkeni `ASAN_OPTIONS` olarak ayarlanmamışsa `detect_stack_use_after_return` , kod hala kendi tarafından kullanmaktan daha yavaştır [`/fsanitize=address`](../build/reference/fsanitize.md) . Kullanarak bir çerçevenin parçaları için alan ayıran bazı yığın çerçevelerinden hala ek yük olduğundan bu daha yavaştır `alloca()` . Bu nesne dosyalarını, RETURN-RETURN-RETURN hatalarını işlemeyi bitirdiğinizde silmek en iyisidir.

## <a name="example---simple-c"></a>Örnek-basit C

```cpp
// example1.cpp
// stack-use-after-return error
char* x;

void foo() {
    char stack_buffer[42];
    x = &stack_buffer[13];
}

int main() {

    foo();
    *x = 42; // Boom!

    return 0;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example1.cpp /fsanitize=address /fsanitize-address-use-after-return /Zi
set ASAN_OPTIONS=detect_stack_use_after_return=1
devenv /debugexe example1.exe
```

### <a name="resulting-error---simple-c"></a>Ortaya çıkan hata-basit C

:::image type="content" source="media/stack-use-after-return-example-1.png" alt-text="Yığın kullanan hata ayıklayıcı ekran görüntüsü örnek 1 ' de-RETURN-RETURN-RETURN hatası.":::

## <a name="example---c-and-templates"></a>Örnek-C++ ve şablonlar

```cpp
// example2.cpp
// stack-use-after-return error
#include <stdlib.h>

enum ReadOrWrite { Read = 0, Write = 1 };

struct S32 {
    char x[32];
};

template<class T>
T* LeakStack() {
    T t[100];
    static volatile T* x;
    x = &t[0];
    return (T*)x;
}

template<class T>
void StackUseAfterReturn(int Idx, ReadOrWrite w) {
    static T sink;
    T* t = LeakStack<T>();
    if (w)
        t[100 + Idx] = T();
    else
        sink = t[100 + Idx];
}

int main(int argc, char* argv[]) {

    if (argc != 2) return 1;
    int kind = atoi(argv[1]);

    switch (kind) {
    case 1: StackUseAfterReturn<char>(0, Read); break;
    case 2: StackUseAfterReturn<S32>(0, Write); break;
    }
    return 0;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example2.cpp /fsanitize=address /fsanitize-address-use-after-return /Zi
set ASAN_OPTIONS=detect_stack_use_after_return=1
devenv /debugexe example2.exe 1
```

### <a name="resulting-error---c-and-templates"></a>Ortaya çıkan hata-C++ ve şablonlar

:::image type="content" source="media/stack-use-after-return-example-2.png" alt-text="Yığın-RETURN-RETURN-RETURN hatası gösteren hata ayıklayıcı ekran görüntüsü örnek 2.":::

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
