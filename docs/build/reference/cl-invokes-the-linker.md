---
title: CL bağlayıcı çağırır | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- compiling source code [C++], without linking
- invoking linker from the compiler
- LINK tool [C++], invoking from CL compiler
- cl.exe compiler [C++], compiling without linking
- cl.exe compiler [C++], controlling linker
ms.assetid: eae47ef7-09eb-40c9-b318-7c714cd452fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed6c968b86192ae79c0c921f8b3fababc596c9a2
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713836"
---
# <a name="cl-invokes-the-linker"></a>CL Bağlayıcı Çağırır

CL bağlayıcı /c seçeneği kullanılmadığı sürece derledikten sonra otomatik olarak çağırır. CL komut satırında belirtilen dosyaların adlarını ve derleme sırasında oluşturulan .obj dosyaları adlarını bağlayıcıya iletir. Bağlayıcı bağlantı ortam değişkeninde listelenen seçenekler kullanır. CL komut satırında bağlayıcı seçenekleri belirtmek için/Link seçeneği kullanabilirsiniz. / Link seçeneği izleyen seçenekleri bağlantı ortam değişkeninde geçersiz kılar. Seçenekler aşağıdaki tabloda, bağlama gösterme.

|Seçenek|Açıklama|
|------------|-----------------|
|/c|Bağlantılandırmadan derleme|
|/ E, /EP, /P|Derleme veya bağlama önceden işlenir|
|/ZG|İşlev prototipleri üret|
|/ZS|Sözdizimini denetle|

Bağlama hakkında daha fazla bilgi için [bağlayıcı seçenekleri](../../build/reference/linker-options.md).

## <a name="example"></a>Örnek

Üç C kaynak dosyaları derleme varsayar: MAIN.c MOD1.c ve MOD2.c. Her dosya, farklı bir dosyada tanımlanan bir işlev çağrısı içerir:

- MAIN.c işlevi çağırır `func1` MOD1.c ve işlev `func2` MOD2.c içinde.

- MOD1.c standart kitaplık işlevleri çağırır `printf_s` ve `scanf_s`.

- MOD2.c adlı grafik işlevlerini çağıran `myline` ve `mycircle`, MYGRAPH.lib adlı bir kitaplığında tanımlanır.

Bu program oluşturmak için aşağıdaki komut satırında derleyin:

```
CL MAIN.c MOD1.C MOD2.C MYGRAPH.lib
```

CL ilk C kaynak dosyaları derler ve MAIN.obj MOD1.obj ve MOD2.obj nesne dosyaları oluşturur. Derleyici standart kitaplık adını her .obj dosyasına yerleştirir. Daha fazla ayrıntı için [çalışma zamanı kitaplığını kullan](../../build/reference/md-mt-ld-use-run-time-library.md).

CL MYGRAPH.lib, adı ile birlikte .obj dosyaları adlarını bağlayıcıya iletir. Bağlayıcının dış başvuruları gibi çözer:

1. MAIN.obj, başvuru olarak `func1` tanımı içinde MOD1.obj; kullanarak çözümlenen başvuru `func2` tanımı içinde MOD2.obj kullanılarak çözümlenir.

1. MOD1.obj, başvuruları içinde `printf_s` ve `scanf_s` tanımları içinde MOD1.obj adlı bağlayıcı bulur kitaplığı kullanılarak çözümlenir.

1. MOD2.obj, başvuruları içinde `myline` ve `mycircle` tanımları içinde MYGRAPH.lib kullanılarak çözümlenir.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)