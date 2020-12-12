---
description: Hakkında daha fazla bilgi edinin:. Bağlayıcı girişi olarak pdb dosyaları
title: Bağlayıcı Girişi olarak .Pdb Dosyaları
ms.date: 11/04/2016
helpviewer_keywords:
- .pdb files, as linker input
- PDB files, as linker input
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
ms.openlocfilehash: 713d42e7e95b5d1e7e3b1f9be21203b75569cdbe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201163"
---
# <a name="pdb-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Pdb Dosyaları

/ZI seçeneği kullanılarak derlenen nesne (. obj) dosyaları, bir program veritabanı (PDB) adını içerir. Nesnenin PDB dosya adını bağlayıcıya belirtmeyin; BAĞLANTı, gerekirse PDB 'yi bulmak için gömülü adı kullanır. Bu ayrıca bir kitaplıkta bulunan hata ayıklanabilir nesneleri için de geçerlidir; hata ayıklanabilir kitaplığı için PDB, kitaplıkla birlikte bağlayıcı için kullanılabilir olmalıdır.

BAĞLANTı,. exe dosyası veya. dll dosyası için hata ayıklama bilgilerini tutmak için PDB de kullanır. Bir çıkış dosyası ve bir giriş dosyası, bağlantı, programı yeniden oluştururken PDB güncelleştirdiğinden, programın PDB 'si bir çıktı dosyası ve bir giriş dosyasıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Giriş dosyalarını bağlama](link-input-files.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
