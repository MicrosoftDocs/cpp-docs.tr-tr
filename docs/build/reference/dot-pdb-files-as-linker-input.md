---
title: ". Bağlayıcı girişi olarak pdb dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- .pdb files, as linker input
- PDB files, as linker input
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c5acdc01a58cf0d501be5947cddf710d1b7c6d18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="pdb-files-as-linker-input"></a>Bağlayıcı Girişi olarak .Pdb Dosyaları
(.Obj) dosyaları / zi seçeneğini kullanarak derlenmiş program veritabanı (PDB) adını içeren nesne. Bağlayıcı için nesnenin PDB dosya adı belirtmeyin; BAĞLANTI katıştırılmış adı gerekirse PDB bulmak için kullanır. Bu kitaplıkta bulunan debuggable nesneler için de geçerlidir; PDB debuggable kitaplık için kitaplık birlikte bağlayıcı için kullanılabilir olmalıdır.  
  
 BAĞLANTI bir PDB .exe veya .dll dosyası için hata ayıklama bilgilerini tutmak için de kullanır. Program yeniden oluşturur, bağlantı PDB güncelleştirdiğinden programın PDB bir çıktı dosyası ve bir giriş dosyası ' dir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINK giriş dosyaları](../../build/reference/link-input-files.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)