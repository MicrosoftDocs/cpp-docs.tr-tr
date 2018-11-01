---
title: Bağlayıcı Araçları Uyarısı LNK4204
ms.date: 11/04/2016
f1_keywords:
- LNK4204
helpviewer_keywords:
- LNK4204
ms.assetid: 14adda20-0cbe-407b-90f6-9f81c93530e2
ms.openlocfilehash: 790b0fa25bbf41c38b843e1a2ea757fdc0d10b9a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475191"
---
# <a name="linker-tools-warning-lnk4204"></a>Bağlayıcı Araçları Uyarısı LNK4204

'filename', hata ayıklama başvuru modülü için bilgileri eksik; Nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor

.pdb dosyası hatalı imza içeriyor. Bağlayıcı hata ayıklama bilgileri olmadan nesneyi bağlamak devam eder. Nesne dosyası kullanarak derleyin isteyebilirsiniz [/zi](../../build/reference/z7-zi-zi-debug-information-format.md) seçeneği.

Bazı nesneler Kitaplığı'nda artık mevcut bir dosyaya başvuruda bulunuyorsa LNK4204 ortaya çıkabilir. Bu çözümün yeniden derlenmesi, örneğin oluşabilir; bir nesne dosyası silindi ve bir derleme hatası nedeniyle yeniden değil. Bu durumda, ya da ile derleme **/z7**, veya **/Fd**, nesneleri bir tek dosya başına (yani varsayılan .pdb dosyası adı değil) Kitaplığı'na başvurmak için güncelleştirilecek.  Daha fazla bilgi için [/Fd (Program veritabanı dosya adı)](../../build/reference/fd-program-database-file-name.md).  Kaynak denetim sistemi güncelleştirildiğinde her kitaplıkla .pdb kaydedildiğinden emin olun.