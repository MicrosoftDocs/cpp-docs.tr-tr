---
title: "Yardım dosyaları (HTML Yardım) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: file types [C++], HTML Help files
ms.assetid: d30a1b1b-318f-4a78-8b60-93da53a224a8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c96cd6ad904439f556f2baa51602353ea00c5ac7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="help-files-html-help"></a>Yardım Dosyaları (HTML Yardım)
Yardım desteği HTML Yardım türünü seçerek uygulamanızı eklediğinizde, aşağıdaki dosyalar oluşturulur **bağlama duyarlı Yardım** onay kutusunu ve ardından seçerek **HTML Yardım biçimine** içinde[Gelişmiş Özellikler](../mfc/reference/advanced-features-mfc-application-wizard.md) MFC Uygulama Sihirbazı sayfası.  
  
|Dosya adı|Dizin konumu|Çözüm Gezgini konumu|Açıklama|  
|---------------|------------------------|--------------------------------|-----------------|  
|*PROJNAME*.hhp|*PROJNAME*\hlp|HTML Yardım dosyaları|Yardım proje dosyası. Yardım dosyaları .hxs dosyasına veya bir .chm dosyasını derlemek için gereken verileri içerir.|  
|*PROJNAME*.hhk|*PROJNAME*\hlp|HTML Yardım dosyaları|Bir dizin Yardım konularını içerir.|  
|*PROJNAME*.hhc|*PROJNAME*\hlp|HTML Yardım dosyaları|Yardım projesi içerikleri.|  
|Makehtmlhelp.bat|*PROJNAME*|Kaynak dosyaları|Projesi derlendiğinde Yardım Projeyi derlemek için sistem tarafından kullanılır.|  
|Afxcore.htm|*PROJNAME*\hlp|HTML Yardım konuları|Standart MFC komutları ve ekran nesneler için standart Yardım konularını içerir. Kendi Yardım konuları bu dosyaya ekleyin.|  
|Afxprint.htm|*PROJNAME*\hlp|HTML Yardım konuları|Yazdırma komutlar için Yardım konularını içerir.|  
|*.jpg; \*.gif|*PROJNAME*\hlp\Images|Kaynak Dosyalar|Görüntüler için farklı oluşturulan Yardım dosyası konuları içerir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ Projeleri için Oluşturulan Dosya Türleri](../ide/file-types-created-for-visual-cpp-projects.md)