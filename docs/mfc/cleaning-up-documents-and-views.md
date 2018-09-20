---
title: Belgeleri ve görünümleri temizleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f4325b0de10861fc76ee9ab816376f40ba0ba587
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437423"
---
# <a name="cleaning-up-documents-and-views"></a>Belgeleri ve Görünümleri Temizleme

Bir belge kapatıldığında framework önce çağırır, [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) üye işlevi. Belgenin işleminin Kurs sırasında herhangi bir yığında bellek ayırdığınızda `DeleteContents` ayırması için en iyi yerdir.

> [!NOTE]
>  Belgenin yok Edicisi belge verilerinde serbest değil. Belge nesnesi bir SDI uygulaması söz konusu olduğunda, yeniden kullanılabilir.

Bir görünümün yıkıcı yığında ayrılan belleği serbest bırakmak için geçersiz kılabilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

[Belgeleri ve Görünümleri Başlatma ve Temizleme](../mfc/initializing-and-cleaning-up-documents-and-views.md)

