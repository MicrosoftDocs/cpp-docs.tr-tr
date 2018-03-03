---
title: "Proje derleme uyarısı PRJ0049 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- PRJ0049
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f87bc7e26fd7cc50defbc086594c92a3ea339ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-warning-prj0049"></a>Proje Derleme Uyarısı PRJ0049
Başvurulan hedef '\<başvuru >'.NET Framework gerektirir \<MinFrameworkVersion > ve bu projenin hedef çerçevesi üzerinde çalıştırmak başarısız olur  
  
 Visual Studio 2008 kullanılarak oluşturulan uygulamaların hangi sürümünün belirtebilirsiniz [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)] hedef. Bir derlemeyi ya da bir sürümüne bağlıdır proje başvuru eklerseniz [!INCLUDE[dnprdnshort](../../error-messages/tool-errors/includes/dnprdnshort_md.md)] hedeflenen sürümden daha sonra bu uyarı derleme zamanında alırsınız.  
  
### <a name="to-correct-this-warning"></a>Bu uyarı düzeltmek için  
  
1.  Aşağıdakilerden birini seçin:  
  
    -   Projenin hedef çerçevesini değiştirebilir **özellik sayfaları** iletişim kutusunu tüm başvurulan derlemeler ve projeleri en az framework sürümüne eşit veya daha sonraki bir. Daha fazla bilgi için bkz: [başvuruları ekleme](../../ide/adding-references-in-visual-cpp-projects.md).  
  
    -   Derleme veya hedef çerçeveyi sonraki bir minimal framework sürümüne sahip proje başvurusunu kaldırın. Bu öğeler, projenin bir uyarı simgesiyle işaretlenir **özellik sayfaları**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje Derleme Hataları ve Uyarıları (PRJxxxx)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)