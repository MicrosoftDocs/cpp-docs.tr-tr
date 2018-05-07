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
ms.openlocfilehash: 2dfe54c13db6f44bc70289380ae5f50d99c3722b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cleaning-up-documents-and-views"></a>Belgeleri ve Görünümleri Temizleme
Bir belgeyi kapatırken framework önce çağırır kendi [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) üye işlevi. Belgenin işlemi sürecinde yığında belleği ayırdığınızda `DeleteContents` ayırması için en iyi yerdir.  
  
> [!NOTE]
>  Belge verileri belgenin yıkıcı ayırması değil. SDI uygulamanın söz konusu olduğunda, belge nesnesi yeniden.  
  
 Bir görünümün yıkıcı ve yığında ayrılan bellek ayırması geçersiz kılabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belgeleri ve Görünümleri Başlatma ve Temizleme](../mfc/initializing-and-cleaning-up-documents-and-views.md)

