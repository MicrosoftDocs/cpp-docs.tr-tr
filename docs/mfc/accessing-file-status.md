---
title: "Dosya durumuna erişme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- files [MFC], status information
- examples [MFC], file status
- files [MFC], accessing
- file status [MFC]
- status of files [MFC]
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2ed2ce199c9f29ca4648e13856b0b9c8d43b605b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="accessing-file-status"></a>Dosya Durumuna Erişme
`CFile`Ayrıca dosya durumu, dosyanın var olup olmadığını da dahil olmak üzere, oluşturma ve değiştirme tarih ve saat, mantıksal boyutu ve yol alma destekler.  
  
### <a name="to-get-file-status"></a>Dosya durumunu almak için  
  
1.  Kullanım [CFile](../mfc/reference/cfile-class.md) almak ve bir dosya hakkında bilgi ayarlamak için sınıf. Bir kullanışlı uygulama kullanmaktır `CFile` statik üye işlevi **GetStatus** bir dosya olup olmadığını belirlemek için. **GetStatus** belirtilen dosya yoksa, 0 döndürür.  
  
 Bu nedenle, sonucunu kullanabilirsiniz **GetStatus** kullanılıp kullanılmayacağını belirlemek için **CFile::modeCreate** bayrak bir dosyayı açarken aşağıdaki örnekte gösterildiği gibi:  
  
 [!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]  
  
 İlgili bilgi için bkz: [seri hale getirme](../mfc/serialization-in-mfc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosyaları](../mfc/files-in-mfc.md)

