---
description: 'Hakkında daha fazla bilgi edinin: dosyaları okuma ve yazma'
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
ms.openlocfilehash: 169135f57eaecb52605eca88b7f19e333551f1ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248625"
---
# <a name="reading-and-writing-files"></a>Dosyaları Okuma ve Yazma

C çalışma zamanı kitaplığı dosya işleme işlevlerini kullandıysanız, MFC okuma ve yazma işlemleri tanıdık gelecektir. Bu makalede doğrudan bir nesneye doğrudan okuma ve doğrudan yazma açıklanmaktadır `CFile` . Ayrıca, [CArchive](../mfc/reference/carchive-class.md) sınıfı ile arabelleğe alınmış dosya g/ç 'yi de yapabilirsiniz.

#### <a name="to-read-from-and-write-to-the-file"></a>Dosyadan okumak ve dosyaya yazmak için

1. `Read` `Write` Dosyadaki verileri okumak ve yazmak için ve üye işlevlerini kullanın.

     -veya-

1. `Seek`Üye işlevi, dosyanın içindeki belirli bir uzaklığa geçmek için de kullanılabilir.

`Read` arabelleğin bir işaretçisini ve okunan bayt sayısını ve okunan gerçek bayt sayısını döndürür. Dosya sonu (EOF) değerine ulaşıldığından, gereken sayıda bayt okunamadı, okunan bayt sayısı değeri döndürülür. Herhangi bir okuma hatası oluşursa, bir özel durum oluşturulur. `Write` Şuna benzerdir `Read` , ancak yazılan bayt sayısı döndürülmez. Belirtilen baytları yazmadan bir yazma hatası oluşursa, bir özel durum oluşturulur. Geçerli bir `CFile` nesneniz varsa, bunu okuyabilir veya aşağıdaki örnekte gösterildiği gibi yazabilirsiniz:

[!code-cpp[NVC_MFCFiles#2](../atl-mfc-shared/reference/codesnippet/cpp/reading-and-writing-files_1.cpp)]

> [!NOTE]
> Genellikle bir **`try`** / **`catch`** özel durum işleme bloğunda giriş/çıkış işlemleri gerçekleştirmeniz gerekir. Daha fazla bilgi için bkz. [özel durum işleme (MFC)](../mfc/exception-handling-in-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosyalar](../mfc/files-in-mfc.md)
