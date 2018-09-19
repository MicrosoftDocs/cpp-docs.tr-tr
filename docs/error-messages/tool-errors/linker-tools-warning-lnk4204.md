---
title: Bağlayıcı araçları uyarısı LNK4204 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4204
dev_langs:
- C++
helpviewer_keywords:
- LNK4204
ms.assetid: 14adda20-0cbe-407b-90f6-9f81c93530e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee6164f20bbf91a8cb0b88d8a1333107f239d3f2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136243"
---
# <a name="linker-tools-warning-lnk4204"></a>Bağlayıcı Araçları Uyarısı LNK4204

'filename', hata ayıklama başvuru modülü için bilgileri eksik; Nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor

.pdb dosyası hatalı imza içeriyor. Bağlayıcı hata ayıklama bilgileri olmadan nesneyi bağlamak devam eder. Nesne dosyası kullanarak derleyin isteyebilirsiniz [/zi](../../build/reference/z7-zi-zi-debug-information-format.md) seçeneği.

Bazı nesneler Kitaplığı'nda artık mevcut bir dosyaya başvuruda bulunuyorsa LNK4204 ortaya çıkabilir. Bu çözümün yeniden derlenmesi, örneğin oluşabilir; bir nesne dosyası silindi ve bir derleme hatası nedeniyle yeniden değil. Bu durumda, ya da ile derleme **/z7**, veya **/Fd**, nesneleri bir tek dosya başına (yani varsayılan .pdb dosyası adı değil) Kitaplığı'na başvurmak için güncelleştirilecek.  Daha fazla bilgi için [/Fd (Program veritabanı dosya adı)](../../build/reference/fd-program-database-file-name.md).  Kaynak denetim sistemi güncelleştirildiğinde her kitaplıkla .pdb kaydedildiğinden emin olun.