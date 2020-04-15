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
ms.openlocfilehash: 6c4b2b21bbfa19fb73997f8475cfa9a4047dc0ca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371795"
---
# <a name="reading-and-writing-files"></a>Dosyaları Okuma ve Yazma

C çalışma zamanı kitaplığı dosya işleme işlevlerini kullandıysanız, MFC okuma ve yazma işlemleri tanıdık görünür. Bu makalede, doğrudan bir `CFile` nesneye okuma ve yazma açıklanır. [CArchive](../mfc/reference/carchive-class.md) sınıfıyla arabelleğe alan dosya G/Ç'yi de yapabilirsiniz.

#### <a name="to-read-from-and-write-to-the-file"></a>Dosyadan okumak ve dosyaya yazmak için

1. Dosyadaki `Read` `Write` verileri okumak ve yazmak için ve üye işlevleri kullanın.

     -veya-

1. `Seek` Üye işlev, dosya içinde belirli bir ofset taşımak için de kullanılabilir.

`Read`bir arabelleğe işaretçi alır ve okunacak bayt sayısını alır ve okunan baytların gerçek sayısını döndürür. Dosya sonu (EOF) ulaşıldığı için gerekli bayt sayısı okunamazsa, okunan bayt sayısı döndürülür. Herhangi bir okuma hatası oluşursa, bir özel durum atılır. `Write`' ye `Read`benzer, ancak yazılan bayt sayısı döndürülmez. Belirtilen tüm baytların yazılmadığını da içeren bir yazma hatası oluşursa, bir özel durum atılır. Geçerli `CFile` bir nesneniz varsa, aşağıdaki örnekte gösterildiği gibi ondan okuyabilir veya yazabilirsiniz:

[!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]

> [!NOTE]
> Normalde bir **deneme**/**catch** özel durum işleme bloğu içinde giriş/çıkış işlemleri yürütmek gerekir. Daha fazla bilgi için [bkz.](../mfc/exception-handling-in-mfc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Dosyalar](../mfc/files-in-mfc.md)
