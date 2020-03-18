---
title: CL Bağlayıcı Çağırır
ms.date: 11/04/2016
helpviewer_keywords:
- compiling source code [C++], without linking
- invoking linker from the compiler
- LINK tool [C++], invoking from CL compiler
- cl.exe compiler [C++], compiling without linking
- cl.exe compiler [C++], controlling linker
ms.assetid: eae47ef7-09eb-40c9-b318-7c714cd452fc
ms.openlocfilehash: 1f9bb466ae89b8e3491b027a98b28935e7c8b523
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440185"
---
# <a name="cl-invokes-the-linker"></a>CL Bağlayıcı Çağırır

/C seçeneği kullanılmadığı takdirde CL derlendikten sonra otomatik olarak bağlayıcı çağırır. CL bağlayıcıya, derleme sırasında oluşturulan. obj dosyalarının adlarını ve komut satırında belirtilen diğer dosyaların adlarını geçirir. Bağlayıcı, bağlantı ortamı değişkeninde listelenen seçenekleri kullanır. CL komut satırındaki bağlayıcı seçeneklerini belirtmek için/link seçeneğini kullanabilirsiniz. /Link seçeneğini izleyen seçenekler bağlantı ortamı değişkeninde olanları geçersiz kılar. Aşağıdaki tablodaki seçenekler bağlamayı göstermez.

|Seçenek|Açıklama|
|------------|-----------------|
|/c|Bağlama olmadan derle|
|/E,/EP,/P|Derleme veya bağlama olmadan ön işlem|
|/Zg|İşlev prototipleri oluştur|
|/ZS|Sözdizimini denetle|

Bağlama hakkında daha fazla bilgi için bkz. [MSVC bağlayıcı seçenekleri](linker-options.md).

## <a name="example"></a>Örnek

Üç C kaynak dosyası derlediğiniz varsayın: MAIN. c, MOD1. c ve MOD2. c. Her dosya farklı bir dosyada tanımlanan bir işleve çağrı içerir:

- MAIN. c, MOD1. c içinde `func1` işlevi çağırır ve MOD2. c içindeki işlev `func2`.

- MOD1. c, standart kitaplık işlevlerini `printf_s` ve `scanf_s`çağırır.

- MOD2. c, MYGRAPH. lib adlı bir kitaplıkta tanımlanan `myline` ve `mycircle`adlı grafik işlevleri çağırır.

Bu programı derlemek için aşağıdaki komut satırıyla derleyin:

```
CL MAIN.c MOD1.C MOD2.C MYGRAPH.lib
```

CL ilk olarak C kaynak dosyalarını derler ve ana. obj, MOD1. obj ve MOD2. obj nesne dosyalarını oluşturur. Derleyici, her. obj dosyasına standart kitaplığın adını koyar. Daha ayrıntılı bilgi için bkz. [Çalışma Zamanı kitaplığını kullanma](md-mt-ld-use-run-time-library.md).

CL,. obj dosyasının adlarını MYGRAPH. lib adıyla birlikte bağlayıcıya geçirir. Bağlayıcı dış başvuruları aşağıdaki gibi çözer:

1. MAIN. obj ' de, `func1` başvurusu MOD1. obj; içindeki tanımı kullanılarak çözümlenir. `func2` başvurusu MOD2. obj içindeki tanımı kullanılarak çözümlenir.

1. MOD1. obj dosyasında, `printf_s` ve `scanf_s` başvuruları, kitaplıktaki MOD1. obj içinde adlandırılan bulduğu tanımlar kullanılarak çözümlenir.

1. MOD2. obj dosyasında, `myline` ve `mycircle` başvuruları MYGRAPH. lib içindeki tanımlar kullanılarak çözümlenir.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](compiler-command-line-syntax.md)
