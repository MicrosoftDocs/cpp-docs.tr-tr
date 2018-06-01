---
title: Yardım dosyaları (HTML Yardım) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], HTML Help files
ms.assetid: d30a1b1b-318f-4a78-8b60-93da53a224a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d180fe4f9cf1baf26b27423ffda975bfe0fe85ba
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33325081"
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