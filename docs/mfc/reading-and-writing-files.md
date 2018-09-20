---
title: Dosyaları okuma ve yazma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0fd41c085b9498d3f1ebb76378a83cce464142a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404078"
---
# <a name="reading-and-writing-files"></a>Dosyaları Okuma ve Yazma

C çalışma zamanı kitaplığı dosyası işleme işlevlerini kullandıysanız, okuma ve yazma işlemleri MFC tanıdık görünür. Bu makalede doğrudan okuma ve yazma doğrudan bir `CFile` nesne. De arabelleğe alınan dosya g/ç ile [CArchive](../mfc/reference/carchive-class.md) sınıfı.

#### <a name="to-read-from-and-write-to-the-file"></a>Okuma ve dosyaya yazmak için

1. Kullanım `Read` ve `Write` üye işlevleri dosyasına veri yazma ve okuma için.

     veya

1. `Seek` Bir üye işlevidir Ayrıca belirli bir uzaklıkta dosyası içinde taşımak için kullanılabilir.

`Read` Arabellek ve okunacak bayt sayısı için bir işaretçi alır ve gerçek okunan bayt sayısını döndürür. Gereken bayt sayısını çünkü dosya sonu okunamadı (EOF) ulaşıldı, okunan bayt sayısını döndürülür. Herhangi bir okuma hatası oluşursa bir özel durum oluşturulur. `Write` benzer `Read`, ancak yazılan bayt sayısı döndürülmez. Belirtilen tüm baytlar yazılmıyor dahil olmak üzere bir yazma hatası oluşursa bir özel durum oluşturulur. Geçerli bir varsa `CFile` nesnesi, ondan okuyun veya aşağıdaki örnekte gösterildiği gibi yazın:

[!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]

> [!NOTE]
>  Normalde giriş/çıkış işlemi içinde yürütülmesi bir **deneyin**/**catch** özel durum işleme bloğu. Daha fazla bilgi için [özel durum işleme (MFC)](../mfc/exception-handling-in-mfc.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Dosyalar](../mfc/files-in-mfc.md)

