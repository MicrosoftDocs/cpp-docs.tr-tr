---
title: Belgeleri ve Görünümleri Temizleme
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
ms.openlocfilehash: 940c768823d26950d9710fb1d1a52e6a1955fead
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57258820"
---
# <a name="cleaning-up-documents-and-views"></a>Belgeleri ve Görünümleri Temizleme

Bir belge kapatıldığında framework önce çağırır, [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) üye işlevi. Belgenin işleminin Kurs sırasında herhangi bir yığında bellek ayırdığınızda `DeleteContents` ayırması için en iyi yerdir.

> [!NOTE]
>  Belgenin yok Edicisi belge verilerinde serbest değil. Belge nesnesi bir SDI uygulaması söz konusu olduğunda, yeniden kullanılabilir.

Bir görünümün yıkıcı yığında ayrılan belleği serbest bırakmak için geçersiz kılabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Belgeleri ve Görünümleri Başlatma ve Temizleme](../mfc/initializing-and-cleaning-up-documents-and-views.md)
