---
title: . Bağlayıcı girişi olarak pdb dosyaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- .pdb files, as linker input
- PDB files, as linker input
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6b728903d2a270efc6b3eb736e45540651dae8c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706192"
---
# <a name="pdb-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Pdb Dosyaları

Nesne (.obj) dosyaları / zi seçeneği kullanılarak derlenmiş bir program veritabanı (PDB) adını içerir. Bağlayıcı için nesnenin PDB dosya adı belirtmeyin; BAĞLANTIYI katıştırılmış adı PDB gerekirse bulmak için kullanır. Bu Kitaplığı'nda yer alan hata ayıklanabilir nesneleri için de geçerlidir; hata ayıklanabilir kitaplığı için PDB bağlayıcı kitaplık ile birlikte kullanılabilir olması gerekir.

BAĞLANTI bir PDB .exe veya .dll dosyası için hata ayıklama bilgileri tutmak için de kullanır. BAĞLANTI PDB güncelleştirdiğinden program oluşturur, programın PDB hem bir çıktı dosyası ve bir giriş dosyası ' dir.

## <a name="see-also"></a>Ayrıca Bkz.

[LINK Giriş Dosyaları](../../build/reference/link-input-files.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)