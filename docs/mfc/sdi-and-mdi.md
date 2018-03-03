---
title: SDI ve MDI | Microsoft Docs
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
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7109651bc250f83d8ee7e162b647ef54dd5308d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="sdi-and-mdi"></a>SDI ve MDI
MFC tek belge arabirimi (SDI) ve birden çok belge arabirimi (MDI) uygulamaları ile çalışmak kolaylaştırır.  
  
 SDI uygulamaları, aynı anda yalnızca bir açık belge çerçeve penceresi izin verin. MDI uygulamaları birden çok belge çerçeve pencereleri uygulama aynı örneğinde açık olmasını sağlar. Bir MDI uygulama içeren her ayrı bir belge çerçeve pencereleri kendilerini olan alt windows içinde birden çok hangi MDI açılabilen bir pencere sahiptir. Bazı uygulamalarda, alt öğe pencerelerini grafik windows ve elektronik tablo windows gibi farklı türlerde olabilir. Bu durumda, menü çubuğundaki MDI alt pencereleri farklı türlerde etkinleştirilir gibi değiştirebilirsiniz.  
  
> [!NOTE]
>  İşletim sistemi "Belge merkezli" görünümü benimsemiştir çünkü Windows 95 altında ve daha sonra yaygın olarak SDI uygulamalarıdır.  
  
 Daha fazla bilgi için bkz: [belgeler, görünümler ve çerçeve](../mfc/documents-views-and-the-framework.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Uygulamaları Yazmak için Sınıfları Kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md)
