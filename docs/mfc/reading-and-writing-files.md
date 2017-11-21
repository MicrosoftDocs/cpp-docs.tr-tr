---
title: "Dosyaları okuma ve yazma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6ea8f37c09c852acb0309ee7361589b6006a44d2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="reading-and-writing-files"></a>Dosyaları Okuma ve Yazma
C çalışma zamanı kitaplığı dosya işleme işlevlerini kullandıysanız, okuma ve yazma işlemleri MFC tanıdık görünür. Bu makalede doğrudan okuma ve yazma doğrudan bir `CFile` nesnesi. Siz ayrıca arabelleğe alınan dosya g/ç ile [CArchive](../mfc/reference/carchive-class.md) sınıfı.  
  
#### <a name="to-read-from-and-write-to-the-file"></a>Okuma ve dosyaya yazmak için  
  
1.  Kullanım **okuma** ve **yazma** okuyup dosyasında veri yazmak için üye işlevleri.  
  
     veya  
  
2.  `Seek` Üye işlevidir de dosyası içinde belirli bir uzaklık taşımak için kullanılabilir.  
  
 **Okuma** bir işaretçi bir arabellek ve okunacak bayt sayısını alır ve okuma işlemleri bayt sayısını döndürür. Gereken sayıda bayt çünkü dosya sonu okunamadı (EOF) ulaşıldığında, gerçek okunan bayt sayısını döndürülür. Herhangi bir okuma hatası oluşursa, bir özel durum oluşur. **Yazma** benzer **okuma**, ancak yazılan bayt sayısı alınmadı. Bir yazma hatası oluşursa belirtilmezse, tüm baytlar yazma değil de dahil olmak üzere özel durum oluşur. Geçerli bir varsa `CFile` nesnesi, ondan okuyun veya aşağıdaki örnekte gösterildiği gibi yazın:  
  
 [!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]  
  
> [!NOTE]
>  Normalde girdi/çıktı işlemleri içinde yürütülmesi bir **deneyin**/**catch** özel durum işleme bloğu. Daha fazla bilgi için bkz: [özel durum işleme (MFC)](../mfc/exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosyaları](../mfc/files-in-mfc.md)

