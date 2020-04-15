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
ms.openlocfilehash: 6119bf922b05c30a14d8421800e3931c4a038779
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375955"
---
# <a name="opening-files"></a>Dosyaları Açma

MFC'de, dosyayı açmanın en yaygın yolu iki aşamalı bir işlemdir.

#### <a name="to-open-a-file"></a>Dosyayı açmak için

1. Bir yol veya izin bayrakları belirtmeden dosya nesnesini oluşturun.

   Genellikle yığın çerçevesi üzerinde bir [CFile](../mfc/reference/cfile-class.md) değişkeni beyan ederek bir dosya nesnesi oluşturursunuz.

1. Bir yol ve izin bayrakları sağlayarak dosya nesnesi için [Açık](../mfc/reference/cfile-class.md#open) üye işlevini çağırın.

   Belirtilen dosya `Open` açılmazsa dosya başarıyla açılırsa için iade değeri sıfırsız veya 0 olacaktır. `Open` Üye işlev aşağıdaki gibi prototiplenir:

   `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`

   Açık bayraklar, yalnızca okunur gibi dosya için istediğiniz izinleri belirtir. Olası bayrak değerleri `CFile` sınıf içinde numaralandırılmış sabitler olarak tanımlanır, bu`CFile::`nedenle " `CFile::modeRead`" ile niteliklidir . Dosyayı `CFile::modeCreate` oluşturmak istiyorsanız bayrağı kullanın.

Aşağıdaki örnek, okuma/yazma izniyle yeni bir dosyanın nasıl oluşturulduğunu gösterir (önceki herhangi bir dosyayı aynı yolla değiştirme):

[!code-cpp[NVC_MFCFiles#1](../atl-mfc-shared/reference/codesnippet/cpp/opening-files_1.cpp)]

> [!NOTE]
> Bu örnek bir dosya oluşturur ve açar. Sorun varsa, `Open` arama burada gösterildiği `CFileException` gibi, son parametresinde bir nesneyi döndürebilir. TRACE makrosu hem dosya adını hem de hata nedenini belirten bir kodu yazdırır. Daha ayrıntılı `AfxThrowFileException` hata raporlaması gerektiriyorsanız işlevi arayabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CFile Sınıfı](../mfc/reference/cfile-class.md)<br/>
[CFile::Aç](../mfc/reference/cfile-class.md#open)<br/>
[Dosyalar](../mfc/files-in-mfc.md)
