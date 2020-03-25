---
title: Bağlayıcı Araçları Uyarısı LNK4204
ms.date: 11/04/2016
f1_keywords:
- LNK4204
helpviewer_keywords:
- LNK4204
ms.assetid: 14adda20-0cbe-407b-90f6-9f81c93530e2
ms.openlocfilehash: 98c53c9b998e9bd544c1cc72bd2b0c3fd2b0a418
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193868"
---
# <a name="linker-tools-warning-lnk4204"></a>Bağlayıcı Araçları Uyarısı LNK4204

' filename ' öğesine başvuran modül için hata ayıklama bilgileri eksik; nesne, hata ayıklama bilgileri yokmuş gibi bağlanıyor

. Pdb dosyasının imzası hatalı. Bağlayıcı, hata ayıklama bilgileri olmadan nesneyi bağlantılandırmasına devam edecektir. [/Zı](../../build/reference/z7-zi-zi-debug-information-format.md) seçeneğini kullanarak nesne dosyasını yeniden derlemek isteyebilirsiniz.

Kitaplıktaki nesnelerden bazıları artık mevcut olmayan bir dosyaya LNK4204, bu durum oluşabilir. Çözüm yeniden oluşturulurken bu durum oluşabilir; Örneğin, bir derleme hatası nedeniyle bir nesne dosyası silinebilir ve yeniden oluşturulamaz. Bu durumda, nesneleri kitaplık başına tek bir dosyaya (varsayılan. pdb dosya adı değil) başvuracak şekilde güncelleştirmek için **/Z7**ya da **/FD**ile derleyin.  Daha fazla bilgi için bkz. [/FD (program veritabanı dosya adı)](../../build/reference/fd-program-database-file-name.md).  Kaynak denetim sisteminde her güncelleştirildiği sırada. pdb 'nin kitaplıkla birlikte kaydedildiğinden emin olun.
