---
title: Dosya Durumuna Erişme
ms.date: 11/04/2016
helpviewer_keywords:
- files [MFC], status information
- examples [MFC], file status
- files [MFC], accessing
- file status [MFC]
- status of files [MFC]
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
ms.openlocfilehash: 26c263b2d7e4e0243444925cb9416cb337dcd79d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298899"
---
# <a name="accessing-file-status"></a>Dosya Durumuna Erişme

`CFile` Ayrıca dosya durumunu, dosyanın var olup olmadığını da dahil olmak üzere, oluşturma ve değiştirme tarih ve saat, mantıksal boyutu ve yolu alma destekler.

### <a name="to-get-file-status"></a>Dosya durumunu almak için

1. Kullanım [CFile](../mfc/reference/cfile-class.md) almak ve bir dosya hakkında bilgi ayarlamak için sınıf. Faydalı bir uygulama kullanmaktır `CFile` statik üye işlevini **GetStatus** bir dosyanın var olup olmadığını belirlemek için. **GetStatus** belirtilen dosya yoksa, 0 döndürür.

Bu nedenle, sonucunu kullanabilirsiniz **GetStatus** kullanılıp kullanılmayacağını belirleme **CFile::modeCreate** bayrak bir dosyayı açtığınızda aşağıdaki örnekte gösterildiği gibi:

[!code-cpp[NVC_MFCFiles#3](../atl-mfc-shared/reference/codesnippet/cpp/accessing-file-status_1.cpp)]

İlgili bilgiler için bkz. [serileştirme](../mfc/serialization-in-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dosyalar](../mfc/files-in-mfc.md)
