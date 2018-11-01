---
title: Belgeleri ve Görünümleri Temizleme
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
ms.openlocfilehash: 1357a02379a848af23a6f78dee29e5b6adc1efcc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653904"
---
# <a name="cleaning-up-documents-and-views"></a>Belgeleri ve Görünümleri Temizleme

Bir belge kapatıldığında framework önce çağırır, [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) üye işlevi. Belgenin işleminin Kurs sırasında herhangi bir yığında bellek ayırdığınızda `DeleteContents` ayırması için en iyi yerdir.

> [!NOTE]
>  Belgenin yok Edicisi belge verilerinde serbest değil. Belge nesnesi bir SDI uygulaması söz konusu olduğunda, yeniden kullanılabilir.

Bir görünümün yıkıcı yığında ayrılan belleği serbest bırakmak için geçersiz kılabilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

[Belgeleri ve Görünümleri Başlatma ve Temizleme](../mfc/initializing-and-cleaning-up-documents-and-views.md)

