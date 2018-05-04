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
ms.openlocfilehash: f6707be955b5c4a332d1162f53b1cb854391a2ce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="pdb-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Pdb Dosyaları
(.Obj) dosyaları / zi seçeneğini kullanarak derlenmiş program veritabanı (PDB) adını içeren nesne. Bağlayıcı için nesnenin PDB dosya adı belirtmeyin; BAĞLANTI katıştırılmış adı gerekirse PDB bulmak için kullanır. Bu kitaplıkta bulunan debuggable nesneler için de geçerlidir; PDB debuggable kitaplık için kitaplık birlikte bağlayıcı için kullanılabilir olmalıdır.  
  
 BAĞLANTI bir PDB .exe veya .dll dosyası için hata ayıklama bilgilerini tutmak için de kullanır. Program yeniden oluşturur, bağlantı PDB güncelleştirdiğinden programın PDB bir çıktı dosyası ve bir giriş dosyası ' dir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINK giriş dosyaları](../../build/reference/link-input-files.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)