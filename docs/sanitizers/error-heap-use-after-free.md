---
title: 'Hata: yığın-sonra-boş kullan'
description: Boş hatalardan sonra yığın kullanımı için kaynak örnekleri ve canlı hata ayıklama ekran görüntüleri.
ms.date: 03/02/2021
f1_keywords:
- heap-use-after-free
helpviewer_keywords:
- heap-use-after-free error
- AddressSanitizer error heap-use-after-free
ms.openlocfilehash: 86e64537d40a86b1867e9ba16781f10b6ea9b417
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470666"
---
# <a name="error-heap-use-after-free"></a>Hata: `heap-use-after-free`

> Adres temizleme hatası: serbest bırakılmış bellek kullanımı

Yığın içindeki depolamanın `malloc` , `realloc` (C) ve `new` (C++) ile birlikte, kullanımı hariç olmak üzere ayrılabileceği üç örnek gösterilmektedir `volatile` .

## <a name="example---malloc"></a>Örnek - `malloc`

```cpp
// example1.cpp
// heap-use-after-free error
#include <stdlib.h>

int main() {
  char *x = (char*)malloc(10 * sizeof(char));
  free(x);

  // ...

  return x[5];   // Boom!
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example1.cpp /fsanitize=address /Zi
devenv /debugexe example1.exe
```

### <a name="resulting-error"></a>Ortaya çıkan hata

:::image type="content" source="media/heap-use-after-free-example-1.png" alt-text="Yığın-kullanım-sonrası hatası gösteren hata ayıklayıcı ekran görüntüsü örnek 1.":::

## <a name="example---operator-new"></a>Örnek - `operator new`

```cpp
// example2.cpp
// heap-use-after-free error
#include <windows.h>

int main() {
  char *buffer = new char[42];
  delete [] buffer;

  // ...

  buffer[0] = 42;  // Boom!
  return 0;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example2.cpp /fsanitize=address /Zi
devenv /debugexe example2.exe
```

### <a name="resulting-error---operator-new"></a>Sonuç hatası-işleç yeni

:::image type="content" source="media/heap-use-after-free-example-2.png" alt-text="Yığın-kullanım-sonrası hatası gösteren hata ayıklayıcı ekran görüntüsü örnek 2.":::

## <a name="example---realloc"></a>Örnek - `realloc`

```cpp
// example3.cpp
// heap-use-after-free error
#include <malloc.h>

int main() {
  char *buffer = (char*)realloc(0, 42);
  free(buffer);

  // ...

  buffer[0] = 42;  // Boom!
  return 0;
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example3.cpp /fsanitize=address /Zi
devenv /debugexe example3.exe
```

### <a name="resulting-error---realloc"></a>Sonuç hatası-realloc

:::image type="content" source="media/heap-use-after-free-example-3.png" alt-text="Yığın-kullanım-sonrası hatası gösteren hata ayıklayıcı ekran görüntüsü örnek 3.":::

## <a name="example---volatile"></a>Örnek-geçici

```cpp
// example4.cpp
// heap-use-after-free error
#include <stdlib.h>

int main() {

  volatile char *x = (char*)malloc(sizeof(char));
  free((void*)x);

      //...

  *x = 42;        // Boom!
}
```

Bu örneği derlemek ve test etmek için, bu komutları bir Visual Studio 2019 sürüm 16,9 veya sonraki bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts)çalıştırın:

```cmd
cl example4.cpp /fsanitize=address /Zi
devenv /debugexe example4.exe
```

### <a name="resulting-error---volatile"></a>Sonuç hatası-geçici

:::image type="content" source="media/heap-use-after-free-example-4.png" alt-text="Örnek 4 ' te hata görüntüleyen hata ayıklayıcı ekran görüntüsü.":::

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
