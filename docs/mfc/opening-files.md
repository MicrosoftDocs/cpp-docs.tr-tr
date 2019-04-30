---
title: Dosyaları Açma
ms.date: 11/04/2016
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
ms.openlocfilehash: dab7a680d9b33a6e334da99a045b709fe00f215c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394487"
---
# <a name="opening-files"></a>Dosyaları Açma

MFC içinde bir dosyayı açmak için en yaygın iki aşamalı işlemi yoludur.

#### <a name="to-open-a-file"></a>Bir dosyayı açmak için

1. Dosya nesnesini bir yol veya izni bayrakları belirtmeden oluşturun.

   Genellikle bir dosya nesnesine bildirerek oluşturduğunuz bir [CFile](../mfc/reference/cfile-class.md) yığın çerçevesinde değişken.

1. Çağrı [açık](../mfc/reference/cfile-class.md#open) yolu ve izni bayrakları sağlama dosya nesnesinin üye işlevi.

   Dönüş değeri `Open` dosyası başarıyla açıldı olursa sıfır dışı veya 0 ise belirtilen dosya açılamadı. `Open` Üye işlevi şu prototipli şekildedir:

   `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`

   Hangi izinleri gibi açık bayrakları belirtin salt okunur dosyada kullanmak istediğiniz. Olası bayrak değerleri içinde listelenmiş sabitlerde olarak tanımlanan `CFile` sınıfı ile tam olduğundan "`CFile::`" olarak `CFile::modeRead`. Kullanım `CFile::modeCreate` dosyası oluşturmak istiyorsanız bayrak.

Aşağıdaki örnek, (önceki herhangi bir dosya aynı yol ile değiştirerek) okuma/yazma iznine sahip yeni bir dosya oluşturma işlemi gösterilmektedir:

[!code-cpp[NVC_MFCFiles#1](../atl-mfc-shared/reference/codesnippet/cpp/opening-files_1.cpp)]

> [!NOTE]
>  Bu örnek, oluşturur ve bir dosya açar. Sorunları varsa `Open` çağrı döndürebilir bir `CFileException` burada gösterildiği gibi son parametre nesne. TRACE makrosu hem dosya adını ve hatanın nedenini gösteren bir kod yazdırır. Çağırabilirsiniz `AfxThrowFileException` daha ayrıntılı hata raporlama gerekiyorsa işlev.

## <a name="see-also"></a>Ayrıca bkz.

[CFile Sınıfı](../mfc/reference/cfile-class.md)<br/>
[CFile::Open](../mfc/reference/cfile-class.md#open)<br/>
[Dosyalar](../mfc/files-in-mfc.md)
