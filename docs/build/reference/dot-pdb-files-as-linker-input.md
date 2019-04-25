---
title: Bağlayıcı Girişi olarak .Pdb Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- .pdb files, as linker input
- PDB files, as linker input
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
ms.openlocfilehash: 365f2955f5bc9e8082221a070af454c820c665f1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273293"
---
# <a name="pdb-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Pdb Dosyaları

Nesne (.obj) dosyaları / zi seçeneği kullanılarak derlenmiş bir program veritabanı (PDB) adını içerir. Bağlayıcı için nesnenin PDB dosya adı belirtmeyin; BAĞLANTIYI katıştırılmış adı PDB gerekirse bulmak için kullanır. Bu Kitaplığı'nda yer alan hata ayıklanabilir nesneleri için de geçerlidir; hata ayıklanabilir kitaplığı için PDB bağlayıcı kitaplık ile birlikte kullanılabilir olması gerekir.

BAĞLANTI bir PDB .exe veya .dll dosyası için hata ayıklama bilgileri tutmak için de kullanır. BAĞLANTI PDB güncelleştirdiğinden program oluşturur, programın PDB hem bir çıktı dosyası ve bir giriş dosyası ' dir.

## <a name="see-also"></a>Ayrıca bkz.

[LINK Giriş Dosyaları](link-input-files.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
