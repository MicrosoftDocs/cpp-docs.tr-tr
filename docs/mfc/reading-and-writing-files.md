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
ms.openlocfilehash: e30ee5b326833b45365c422238ecfcd4f82c556d
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930917"
---
# <a name="reading-and-writing-files"></a>Dosyaları Okuma ve Yazma
C çalışma zamanı kitaplığı dosya işleme işlevlerini kullandıysanız, okuma ve yazma işlemleri MFC tanıdık görünür. Bu makalede doğrudan okuma ve yazma doğrudan bir `CFile` nesnesi. Siz ayrıca arabelleğe alınan dosya g/ç ile [CArchive](../mfc/reference/carchive-class.md) sınıfı.  
  
#### <a name="to-read-from-and-write-to-the-file"></a>Okuma ve dosyaya yazmak için  
  
1.  Kullanım `Read` ve `Write` okuyup dosyasında veri yazmak için üye işlevleri.  
  
     veya  
  
2.  `Seek` Üye işlevidir de dosyası içinde belirli bir uzaklık taşımak için kullanılabilir.  
  
 `Read` bir işaretçi bir arabellek ve okunacak bayt sayısını alır ve okuma işlemleri bayt sayısını döndürür. Gereken sayıda bayt çünkü dosya sonu okunamadı (EOF) ulaşıldığında, gerçek okunan bayt sayısını döndürülür. Herhangi bir okuma hatası oluşursa, bir özel durum oluşur. `Write` benzer `Read`, ancak yazılan bayt sayısı alınmadı. Bir yazma hatası oluşursa belirtilmezse, tüm baytlar yazma değil de dahil olmak üzere özel durum oluşur. Geçerli bir varsa `CFile` nesnesi, ondan okuyun veya aşağıdaki örnekte gösterildiği gibi yazın:  
  
 [!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]  
  
> [!NOTE]
>  Normalde girdi/çıktı işlemleri içinde yürütülmesi bir **deneyin**/**catch** özel durum işleme bloğu. Daha fazla bilgi için bkz: [özel durum işleme (MFC)](../mfc/exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosyalar](../mfc/files-in-mfc.md)

