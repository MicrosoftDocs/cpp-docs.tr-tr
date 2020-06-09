---
title: Belgeleri ve Görünümleri Temizleme
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
ms.openlocfilehash: 8cb6e9337b69daf78286f57898c9badf513c7921
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626520"
---
# <a name="cleaning-up-documents-and-views"></a>Belgeleri ve Görünümleri Temizleme

Bir belge kapatılırken, Framework ilk olarak [DeleteContents](reference/cdocument-class.md#deletecontents) üye işlevini çağırır. Belgenin işleminin kursu sırasında yığında herhangi bir bellek ayırdıysanız, `DeleteContents` serbest bırakmak için en iyi yer vardır.

> [!NOTE]
> Belgenin yıkıcısında belge verilerini serbest bırakma kullanmamalısınız. SDI uygulaması söz konusu olduğunda, belge nesnesi yeniden kullanılıyor olabilir.

Yığında ayrılan belleği serbest bırakmak için bir görünümün yıkıcısında geçersiz kılabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Belgeleri ve görünümleri başlatma ve Temizleme](initializing-and-cleaning-up-documents-and-views.md)
