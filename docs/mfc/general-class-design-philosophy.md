---
title: "Genel sınıf tasarımı felsefesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c174b06b27e78ca61d2608b8e04205068ac436e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="general-class-design-philosophy"></a>Genel Sınıf Tasarımı Felsefesi
C++ dili uzun popüler hale geldi önce Microsoft Windows tasarlanmıştır. Uygulamaları binlerce C dili Windows uygulama programlama arabirimi (API) kullandığından, bu arabirim için yakın gelecekte korunur. Herhangi bir C++ Windows arabirimi, bu nedenle yordam C dili API üstünde yerleştirilmiş olabilir. Bu C++ uygulamaları C uygulamaları ile bir arada mümkün olacağını garanti eder.  
  
 Microsoft Foundation Class Kitaplığı aşağıdaki tasarım hedefleri karşılayan Windows nesne yönelimli bir arabirimine verilmiştir:  
  
-   Windows için bir uygulama yazmak için çaba, önemli ölçüde azalma.  
  
-   Yürütme hızı, C dili API karşılaştırılabilir.  
  
-   En az kod boyutu yükü.  
  
-   Herhangi bir Windows C işlev doğrudan çağırma yeteneği.  
  
-   C++ varolan C uygulamalarını daha kolay dönüştürme.  
  
-   C dili Windows deneyimi programlama varolan temelden yararlanan yeteneği.  
  
-   Windows API ile C++ c ile daha kolay kullanımı  
  
-   ActiveX denetimleri, veritabanı desteği, yazdırma, araç çubukları ve durum çubukları gibi özellikleri daha kolay kullanım henüz, güçlü soyutlamalar karmaşık.  
  
-   C++ dil özellikleri etkili bir şekilde kullanan C++ için doğru Windows API.  
  
 MFC kitaplığını tasarımı hakkında daha fazla bilgi için bkz:  
  
-   [Uygulama Çerçevesi](../mfc/application-framework.md)  
  
-   [C Dili API'sına yönelik ilişki](../mfc/relationship-to-the-c-language-api.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

