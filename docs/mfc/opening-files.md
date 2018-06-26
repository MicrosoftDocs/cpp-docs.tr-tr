---
title: Dosyaları açma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Open member functions [MFC]
- CFile class [MFC], variable
- opening files, in MFC
- Open calls [MFC]
- Open method, CFile class [MFC]
- examples [MFC], opening files
- opening files, handling exceptions
- exception handling [MFC], when opening files
- files [MFC], opening
- file objects [MFC]
- MFC, file operations
- opening files [MFC]
- exception handling [MFC], opening files
ms.assetid: a991b8ec-b04a-4766-b47e-7485b5dd0b01
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ba12cce799d0d1ed9a02f3a4d3a268ca86d4447
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931573"
---
# <a name="opening-files"></a>Dosyaları Açma
MFC içinde bir dosyayı açmak için en yaygın yolu bir iki aşamalı işlemidir.  
  
#### <a name="to-open-a-file"></a>Bir dosyayı açmak için  
  
1.  Dosya nesne yolu veya izin bayrakları belirtmeden oluşturun.  
  
     Genellikle bir dosya nesnesi bildirerek oluşturduğunuz bir [CFile](../mfc/reference/cfile-class.md) yığın çerçevesinde değişken.  
  
2.  Çağrı [açık](../mfc/reference/cfile-class.md#open) üye işlevi için bir yol ve izni bayrakları sağladığını dosya nesnesi.  
  
     Dönüş değeri `Open` dosyası başarıyla açıldıysa sıfır olmayan veya 0 olacaktır, belirtilen dosya açılamadı. `Open` Üye işlevi şu örneklenmiş şekildedir:  
  
     `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`  
  
     Açık bayrakları hangi izinlerin gibi belirtin salt okunur dosya için istediğiniz. Olası bayrak değerleri içinde numaralandırılmış sabitler olarak tanımlanan `CFile` sınıfı ile tam şekilde "`CFile::`" olarak `CFile::modeRead`. Kullanım `CFile::modeCreate` dosyası oluşturmak istiyorsanız, bayrak.  
  
 Aşağıdaki örnekte (herhangi bir önceki dosya ile aynı yol yerine) okuma/yazma izni olan yeni bir dosya oluşturulacağını gösterir:  
  
 [!code-cpp[NVC_MFCFiles#1](../atl-mfc-shared/reference/codesnippet/cpp/opening-files_1.cpp)]  
  
> [!NOTE]
>  Bu örnek oluşturur ve bir dosyayı açar. Sorunlar, `Open` çağrısı dönebilirsiniz bir `CFileException` aşağıda gösterildiği gibi son parametresinde nesne. TRACE makrosu dosya adını ve başarısızlık nedeni gösteren bir kod yazdırır. Çağırabilirsiniz `AfxThrowFileException` daha ayrıntılı hata raporlama gerekiyorsa işlev.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CFile sınıfı](../mfc/reference/cfile-class.md)   
 [CFile::Open](../mfc/reference/cfile-class.md#open)   
 [Dosyalar](../mfc/files-in-mfc.md)

