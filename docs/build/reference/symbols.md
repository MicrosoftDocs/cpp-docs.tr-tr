---
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
ms.openlocfilehash: a47b7da9f0b01353ef15e8b5c070c19e7c521c37
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317711"
---
# <a name="symbols"></a>/SYMBOLS

```
/SYMBOLS
```

Bu seçenek COFF sembol tablosu görüntüler. Tüm nesne dosyalarında sembol tablolarını mevcut. COFF sembol tablosu ile/Debug yalnızca bağlı bir görüntü dosyasına görüntülenir.

/SYMBOLS çıktısı bir açıklaması verilmiştir. Winnt.h (IMAGE_SYMBOL ve IMAGE_AUX_SYMBOL) veya COFF belgelere bakarak /SYMBOLS çıkış anlamı hakkında daha fazla bilgi bulunabilir.

Aşağıdaki örnek dökümü verilir:

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

Bir sembol sayı ile başlayan satırlar için aşağıdaki açıklama, kullanıcılarla ilgili bilgilere sahip sütunların açıklanmaktadır:

- İlk üç basamaklı sayı simge dizin/numarasıdır.

- Üçüncü sütunda bölü içeriyorsa*x*, sembolü nesne dosyasının bu bölümünde tanımlanır. Ancak UNDEF görünürse, o nesnenin tanımlı değil ve başka bir yerde çözümlenmesi gerekir.

- Beşinci sütun (statik, dış) sembolü yalnızca bu nesne içinde görünür olup veya genel bildirir (görünür harici olarak). _Sym, statik bir simge için bir ortak sembol _sym bağlı mıydı; Bu işlevlerin _sym adlı iki farklı örnekleri olacaktır.

Numaralı satırdaki son sütun sembol adı, her ikisi de düzenlenmiş ve tamamlanmamış.

Yalnızca [OPTIONAL](headers.md) DUMPBIN seçeneği ile üretilen dosyalar kullanıma [/GL](gl-whole-program-optimization.md) derleyici seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[DUMPBIN Seçenekleri](dumpbin-options.md)
