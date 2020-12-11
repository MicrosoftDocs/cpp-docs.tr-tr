---
description: 'Hakkında daha fazla bilgi edinin: dosyaları açma'
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
ms.openlocfilehash: cad847dc74cd32f93cc8a4a13e4bbe1bd815d815
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112888"
---
# <a name="opening-files"></a>Dosyaları Açma

MFC 'de, bir dosyayı açmak için en yaygın yol iki aşamalı bir işlemdir.

#### <a name="to-open-a-file"></a>Dosya açmak için

1. Dosya nesnesini bir yol veya izin bayrakları belirtmeden oluşturun.

   Genellikle yığın çerçevesinde bir [CFile](reference/cfile-class.md) değişkeni bildirerek bir dosya nesnesi oluşturursunuz.

1. Dosya nesnesi için [Açık](reference/cfile-class.md#open) üye işlevini çağırın ve bir yol ve izin bayrakları sağlayarak.

   `Open`Dosya başarıyla açıldıysa veya belirtilen dosya açılamadığı takdirde 0 ' ın dönüş değeri sıfır dışı olacaktır. `Open`Üye işlevi prototipi şöyle yazılır:

   `virtual BOOL Open( LPCTSTR lpszFileName, UINT nOpenFlags, CFileException* pError = NULL );`

   Açık bayraklar, salt okuma gibi hangi izinlerin dosya için istediğinizi belirtir. Olası bayrak değerleri `CFile` , sınıfının içinde olduğu gibi "" ile nitelendirildikleri şekilde, sınıfında numaralandırılmış sabitler olarak tanımlanmıştır `CFile::` `CFile::modeRead` . `CFile::modeCreate`Dosyayı oluşturmak istiyorsanız bayrağını kullanın.

Aşağıdaki örnek, okuma/yazma izniyle yeni bir dosya oluşturmayı gösterir (önceki tüm dosyaları aynı yolla değiştirme):

[!code-cpp[NVC_MFCFiles#1](../atl-mfc-shared/reference/codesnippet/cpp/opening-files_1.cpp)]

> [!NOTE]
> Bu örnek bir dosya oluşturur ve açar. Sorun varsa, `Open` çağrı `CFileException` burada gösterildiği gibi son parametresinde bir nesne döndürebilir. TRACE makrosu hem dosya adını hem de hatanın nedenini belirten bir kodu yazdırır. `AfxThrowFileException`Daha ayrıntılı hata raporlama gerekiyorsa, işlevini çağırabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CFile sınıfı](reference/cfile-class.md)<br/>
[CFile:: Open](reference/cfile-class.md#open)<br/>
[Dosyalar](files-in-mfc.md)
