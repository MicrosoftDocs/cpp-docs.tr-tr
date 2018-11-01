---
title: Bağlayıcı Girişi olarak .Pdb Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- .pdb files, as linker input
- PDB files, as linker input
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
ms.openlocfilehash: 23974a9e20f8259c3a38af15664d328ded7ff7d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628906"
---
# <a name="pdb-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Pdb Dosyaları

Nesne (.obj) dosyaları / zi seçeneği kullanılarak derlenmiş bir program veritabanı (PDB) adını içerir. Bağlayıcı için nesnenin PDB dosya adı belirtmeyin; BAĞLANTIYI katıştırılmış adı PDB gerekirse bulmak için kullanır. Bu Kitaplığı'nda yer alan hata ayıklanabilir nesneleri için de geçerlidir; hata ayıklanabilir kitaplığı için PDB bağlayıcı kitaplık ile birlikte kullanılabilir olması gerekir.

BAĞLANTI bir PDB .exe veya .dll dosyası için hata ayıklama bilgileri tutmak için de kullanır. BAĞLANTI PDB güncelleştirdiğinden program oluşturur, programın PDB hem bir çıktı dosyası ve bir giriş dosyası ' dir.

## <a name="see-also"></a>Ayrıca Bkz.

[LINK Giriş Dosyaları](../../build/reference/link-input-files.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)