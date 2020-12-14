---
description: Daha fazla bilgi edinin:/SYMBOLS
title: /SYMBOLS
ms.date: 09/05/2018
f1_keywords:
- /symbols
helpviewer_keywords:
- symbols, dumping
- public symbols
- symbols, displaying COFF symbol table
- symbol tables
- SYMBOLS dumpbin option
- /SYMBOLS dumpbin option
- -SYMBOLS dumpbin option
ms.assetid: 34bcae90-4561-4c77-a80c-065508dec39a
ms.openlocfilehash: f0cc213a8b37f99e0cb80f6df88967e4eb5204b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230152"
---
# <a name="symbols"></a>/SYMBOLS

```
/SYMBOLS
```

Bu seçenek COFF sembol tablosunu görüntüler. Sembol tabloları tüm nesne dosyalarında bulunur. Bir COFF sembol tablosu, yalnızca/DEBUGILE bağlanmışsa bir görüntü dosyasında görünür.

Aşağıda/SYMBOLÇıKıŞıNıN açıklaması verilmiştir. /SYMBOLS çıkışının anlamı hakkında daha fazla bilgi için, Winnt. h (IMAGE_SYMBOL ve IMAGE_AUX_SYMBOL) veya COFF belgelerine bakarak bulabilirsiniz.

Aşağıdaki örnek döküm verildiğinde:

```
Dump of file main.obj
File Type: COFF OBJECT

COFF SYMBOL TABLE
000 00000000 DEBUG    notype       Filename     | .file
    main.cpp
002 000B1FDB ABS      notype       Static       | @comp.id
003 00000000 SECT1    notype       Static       | .drectve
    Section length     26, #relocs    0, #linenums    0, checksum 722C964F
005 00000000 SECT2    notype       Static       | .text
    Section length     23, #relocs    1, #linenums    0, checksum 459FF65F, selection    1 (pick no duplicates)
007 00000000 SECT2    notype ()    External     | _main
008 00000000 UNDEF    notype ()    External     | ?MyDump@@YAXXZ (void __cdecl MyDump(void))

String Table Size = 0x10 bytes

  Summary

         26 .drectve
         23 .text
```

## <a name="remarks"></a>Açıklamalar

Aşağıdaki açıklama, bir sembol numarasıyla başlayan satırlar için, kullanıcılarla ilgili bilgiler içeren sütunları açıklar:

- İlk üç basamaklı sayı, sembol Dizin/sayıdır.

- Üçüncü sütun SECT *x* içeriyorsa, sembol nesne dosyasının bu bölümünde tanımlanır. Ancak UNDEF görünmüyorsa, bu nesnede tanımlı değildir ve başka bir yerde çözülmesi gerekir.

- Beşinci sütun (statik, dış) sembolün yalnızca bu nesne içinde görünür olup olmadığını veya genel (dışarıdan görünebilir) olup olmadığını söyler. Statik bir sembol _sym, ortak bir sembol _sym bağlanamaz; Bunlar, _sym adlı işlevlerin iki farklı örneği olacaktır.

Numaralandırılmış bir satırdaki son sütun, hem düzenlenmiş hem de tasarlanılmamış sembol adıdır.

[/GL](gl-whole-program-optimization.md) derleyici seçeneği ile oluşturulan dosyalarda yalnızca [/Headers](headers.md) dumpbin seçeneği kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](dumpbin-options.md)
