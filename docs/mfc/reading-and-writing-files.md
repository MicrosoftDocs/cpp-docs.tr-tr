---
title: Dosyaları Okuma ve Yazma
ms.date: 11/04/2016
helpviewer_keywords:
- CFile class [MFC], objects
- examples [MFC], reading files
- files [MFC], writing to
- examples [MFC], writing to files
- files [MFC], reading
- MFC, file operations
- CFile class [MFC], reading and writing CFile objects
- reading files
- writing to files [MFC]
ms.assetid: cac0c826-ba56-495f-99b3-ce6336f65763
ms.openlocfilehash: f68fd5c48bce214329437cc13fc39da0c3ca7d2b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228589"
---
# <a name="reading-and-writing-files"></a>Dosyaları Okuma ve Yazma

C çalışma zamanı kitaplığı dosya işleme işlevlerini kullandıysanız, MFC okuma ve yazma işlemleri tanıdık gelecektir. Bu makalede doğrudan bir nesneye doğrudan okuma ve doğrudan yazma açıklanmaktadır `CFile` . Ayrıca, [CArchive](../mfc/reference/carchive-class.md) sınıfı ile arabelleğe alınmış dosya g/ç 'yi de yapabilirsiniz.

#### <a name="to-read-from-and-write-to-the-file"></a>Dosyadan okumak ve dosyaya yazmak için

1. `Read` `Write` Dosyadaki verileri okumak ve yazmak için ve üye işlevlerini kullanın.

     -veya-

1. `Seek`Üye işlevi, dosyanın içindeki belirli bir uzaklığa geçmek için de kullanılabilir.

`Read`arabelleğin bir işaretçisini ve okunan bayt sayısını ve okunan gerçek bayt sayısını döndürür. Dosya sonu (EOF) değerine ulaşıldığından, gereken sayıda bayt okunamadı, okunan bayt sayısı değeri döndürülür. Herhangi bir okuma hatası oluşursa, bir özel durum oluşturulur. `Write`Şuna benzerdir `Read` , ancak yazılan bayt sayısı döndürülmez. Belirtilen baytları yazmadan bir yazma hatası oluşursa, bir özel durum oluşturulur. Geçerli bir `CFile` nesneniz varsa, bunu okuyabilir veya aşağıdaki örnekte gösterildiği gibi yazabilirsiniz:

[!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]

> [!NOTE]
> Genellikle bir **`try`** / **`catch`** özel durum işleme bloğunda giriş/çıkış işlemleri gerçekleştirmeniz gerekir. Daha fazla bilgi için bkz. [özel durum işleme (MFC)](../mfc/exception-handling-in-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosyalarý](../mfc/files-in-mfc.md)
