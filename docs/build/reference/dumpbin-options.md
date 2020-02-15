---
title: DUMPBIN seçenekleri
description: Microsoft DUMPBIN yardımcı program komut satırı seçeneklerine yönelik başvuru kılavuzu.
ms.date: 02/09/2020
f1_keywords:
- dumpbin
helpviewer_keywords:
- DUMPBIN program, options
ms.assetid: 563b696e-7599-4480-94b9-014776289ec8
ms.openlocfilehash: 98a4fd221d66b93f945667deadaba3180f8d3e66
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257734"
---
# <a name="dumpbin-options"></a>DUMPBIN seçenekleri

Bir seçenek, bir tire (`-`) veya eğik çizgi (`/`) ve ardından seçeneğin adı olan bir *seçenek belirticisinden*oluşur. Seçenek adları kısaltılabilir. Bazı seçenekler, iki nokta üst üste (`:`) sonra belirtilen bağımsız değişkenler alır. Seçenek belirtimi içinde boşluk veya sekmeye izin verilmez. Komut satırındaki seçenek belirtimlerini ayırmak için bir veya daha fazla boşluk ya da sekme kullanın. Seçenek adları ve bunların anahtar sözcüğü veya dosya adı bağımsız değişkenleri büyük/küçük harfe duyarlı değildir. Çoğu seçenek tüm ikili dosyalar için geçerlidir, ancak bazıları yalnızca belirli dosya türleri için geçerlidir. Varsayılan olarak, DUMPBIN standart çıktıya bilgi gönderir. Çıktıyı bir dosyaya göndermek için [/Out](out-dumpbin.md) seçeneğini kullanın.

## <a name="options-list"></a>Seçenekler listesi

DUMPBIN aşağıdaki seçeneklere sahiptir:

- [/ALL](all.md)

- [/ARCHIVEMEMBERS](archivemembers.md)

- [/CLRHEADER](clrheader.md)

- [/DEPENDENTS](dependents.md)

- [/DIRECTIVES](directives.md)

- [/DISASM\[: {BYTES\|NOBYTES}\]](disasm.md)

- [/errorreport: {None | KOMUT ISTEMI | KUYRUK | Gönder}](errorreport-dumpbin-exe.md) (kullanım dışı)

- [/EXPORTS](dash-exports.md)

- [/FPO](fpo.md)

- [/HEADERS](headers.md)

- [/IMPORTS\[: filename\]](imports-dumpbin.md)

- [/LINENUMBERS](linenumbers.md)

- [/LINKERMEMBER\[: {1 | 2}\]](linkermember.md)

- [/LOADCONFIG](loadconfig.md)

- [/NOPDB](nopdb.md)

- [/OUT: filename](out-dumpbin.md)

- [/PDATA](pdata.md)

- [/PDBPATH\[: VERBOSE\]](pdbpath.md)

- [/RANGEE: vaMin\[, vaMax\]](range.md)

- [/RAWDATA\[: {NONE\|1\|2\|4\|8}\[, #\]\]](rawdata.md)

- [/RELOCATIONS](relocations.md)

- [/SECTION: ad](section-dumpbin.md)

- [/SUMMARY](summary.md)

- [/SYMBOLS](symbols.md)

- [/TLS](tls.md)

Komut satırında DUMPBIN tarafından desteklenen seçenekleri listelemek için **/?** kullanın seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[Ek MSVC derleme araçları](c-cpp-build-tools.md)\
[Dumpbin komut satırı](dumpbin-command-line.md)\
[DUMPBIN başvurusu](dumpbin-reference.md)
