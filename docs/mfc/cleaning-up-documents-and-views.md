---
title: "Belgeleri ve görünümleri temizleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f9bb1cbcb58e2693b33693b390a09d3826c77cfd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cleaning-up-documents-and-views"></a>Belgeleri ve Görünümleri Temizleme
Bir belgeyi kapatırken framework önce çağırır kendi [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) üye işlevi. Belgenin işlemi sürecinde yığında belleği ayırdığınızda `DeleteContents` ayırması için en iyi yerdir.  
  
> [!NOTE]
>  Belge verileri belgenin yıkıcı ayırması değil. SDI uygulamanın söz konusu olduğunda, belge nesnesi yeniden.  
  
 Bir görünümün yıkıcı ve yığında ayrılan bellek ayırması geçersiz kılabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlatma ve belgeleri ve görünümleri temizleme](../mfc/initializing-and-cleaning-up-documents-and-views.md)

