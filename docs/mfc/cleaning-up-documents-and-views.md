---
title: Belgeleri ve Görünümleri Temizleme
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
ms.openlocfilehash: 06ff60a2cf6245f64e80d899c13a8444558fcf0b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374615"
---
# <a name="cleaning-up-documents-and-views"></a>Belgeleri ve Görünümleri Temizleme

Bir belge kapanDığında, çerçeve ilk olarak [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) üye işlevini çağırır. Belgenin çalışması sırasında yığına herhangi bir bellek ayırdıysanız, `DeleteContents` belgenin yerini tespit etmek için en iyi yerdir.

> [!NOTE]
> Belgeyi yok eden belge verilerini ele almamalısınız. Bir SDI uygulaması söz konusu olduğunda, belge nesnesi yeniden kullanılabilir.

Yığına ayırdığınız herhangi bir belleği bulmak için bir görünümün yıkıcısını geçersiz kılabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Belge ve Görünümleri Başlatma ve Temizleme](../mfc/initializing-and-cleaning-up-documents-and-views.md)
