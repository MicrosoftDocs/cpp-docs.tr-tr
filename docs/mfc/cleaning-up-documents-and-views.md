---
title: "Belgeleri ve görünümleri temizleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a95193d5ca3df890c9c97f458b76413e588bc59
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cleaning-up-documents-and-views"></a>Belgeleri ve Görünümleri Temizleme
Bir belgeyi kapatırken framework önce çağırır kendi [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) üye işlevi. Belgenin işlemi sürecinde yığında belleği ayırdığınızda `DeleteContents` ayırması için en iyi yerdir.  
  
> [!NOTE]
>  Belge verileri belgenin yıkıcı ayırması değil. SDI uygulamanın söz konusu olduğunda, belge nesnesi yeniden.  
  
 Bir görünümün yıkıcı ve yığında ayrılan bellek ayırması geçersiz kılabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belgeleri ve Görünümleri Başlatma ve Temizleme](../mfc/initializing-and-cleaning-up-documents-and-views.md)

