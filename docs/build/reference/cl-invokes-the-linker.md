---
description: 'Daha fazla bilgi edinin: CL, bağlayıcıyı çağırır'
title: CL Bağlayıcı Çağırır
ms.date: 11/04/2016
helpviewer_keywords:
- compiling source code [C++], without linking
- invoking linker from the compiler
- LINK tool [C++], invoking from CL compiler
- cl.exe compiler [C++], compiling without linking
- cl.exe compiler [C++], controlling linker
ms.assetid: eae47ef7-09eb-40c9-b318-7c714cd452fc
ms.openlocfilehash: ddd693cdba625756b8085d2f8cb3870d8cdc6add
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179167"
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

- MAIN. c, işlevi `func1` MOD1. c içinde ve `func2` MOD2. c içindeki işlevi çağırır.

- MOD1. c, standart kitaplık işlevlerini `printf_s` ve ' i çağırır `scanf_s` .

- MOD2. c `myline` `mycircle` , MYGRAPH. lib adlı bir kitaplıkta tanımlanan ve adlı grafik işlevleri çağırır.

Bu programı derlemek için aşağıdaki komut satırıyla derleyin:

```
CL MAIN.c MOD1.C MOD2.C MYGRAPH.lib
```

CL ilk olarak C kaynak dosyalarını derler ve ana. obj, MOD1. obj ve MOD2. obj nesne dosyalarını oluşturur. Derleyici, her. obj dosyasına standart kitaplığın adını koyar. Daha ayrıntılı bilgi için bkz. [Run-Time Kitaplığı kullanma](md-mt-ld-use-run-time-library.md).

CL,. obj dosyasının adlarını MYGRAPH. lib adıyla birlikte bağlayıcıya geçirir. Bağlayıcı dış başvuruları aşağıdaki gibi çözer:

1. MAIN. obj ' de, başvurusu `func1` MOD1. obj içindeki tanımı kullanılarak çözümlenir; başvurusu `func2` MOD2. obj içindeki tanımı kullanılarak çözümlenir.

1. MOD1. obj içinde öğesine başvuruları, `printf_s` `scanf_s` kitaplıktaki MOD1. obj içinde adlandırılmış olarak bulduğu tanımlar kullanılarak çözümlenir.

1. MOD2. obj dosyasında, ve ile başvuruları `myline` `mycircle` MYGRAPH. lib içindeki tanımlar kullanılarak çözümlenir.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](compiler-command-line-syntax.md)
