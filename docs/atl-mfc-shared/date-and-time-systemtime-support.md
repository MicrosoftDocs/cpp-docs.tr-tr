---
title: 'Tarih ve saat: SYSTEMTIME destek | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- SYSTEMTIME
dev_langs:
- C++
helpviewer_keywords:
- system time
- FILETIME structure, with CTime class
- time [C++], formatting
- SYSTEMTIME structure
- dates [C++], MFC
- formatting [C++], time
ms.assetid: 201528e4-2ffa-48fc-af8f-203aa86d942a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 405c245cdab6426330915c945cd77f8336e68c9d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="date-and-time-systemtime-support"></a>Tarih ve saat: SYSTEMTIME desteği
[CTime](../atl-mfc-shared/reference/ctime-class.md) sınıfı Win32 sistem ve dosya sürelerinden kabul oluşturucular sahiptir. Kullanırsanız `CTime` nesneleri bu amaçlar için kendi başlatma bu makalede anlatıldığı gibi uygun şekilde değiştirmeniz gerekir.  
  
 SYSTEMTIME yapısı hakkında daha fazla bilgi için bkz: [SYSTEMTIME](../mfc/reference/systemtime-structure1.md). FILETIME yapısı hakkında daha fazla bilgi için bkz: [FILETIME](../mfc/reference/filetime-structure.md).  
  
 MFC hala sağlar `CTime` zamanı bağımsız değişkenlerini MS-DOS stilde, ancak MFC sürüm 3.0, başlangıç ele oluşturucular `CTime` sınıfı ayrıca bir Win32 alan bir oluşturucu destekler `SYSTEMTIME` yapısı ve başka bir Win32 alan `FILETIME` yapısı.  
  
 Yeni `CTime` oluşturucular şunlardır:  
  
-   CTime (const SYSTEMTIME & `sysTime`);  
  
-   CTime (const FILETIME & `fileTime`);  
  
 `fileTime` Parametredir Win32 başvuru `FILETIME` yapısı, zaman iç depolama için daha uygun bir biçim 64-bitlik bir değer olarak temsil eden bir `SYSTEMTIME` yapısını ve dosya zamanı temsil etmesi için Win32 tarafından kullanılan biçimi oluşturma.  
  
 Kodunuzu içeriyorsa bir `CTime` sistem saatiyle başlatılmamış nesne kullanması gereken `SYSTEMTIME` Win32 Oluşturucu.  
  
 Büyük olasılıkla kullanmaz `CTime` `FILETIME` doğrudan başlatma. Kullanırsanız, bir `CFile` bir dosyayı değiştirmek için nesne [CFile::GetStatus](../mfc/reference/cfile-class.md#getstatus) , dosyası zaman damgasına alır bir `CTime` nesne başlatılmış olan bir `FILETIME` yapısı.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Genel tarih ve saat programlama MFC içinde](../atl-mfc-shared/date-and-time.md)  
  
-   [Tarih ve saat programlama Otomasyon desteği](../atl-mfc-shared/date-and-time-automation-support.md)  
  
-   [Tarih ve saat programlama için genel amaçlı sınıfları](../atl-mfc-shared/date-and-time-general-purpose-classes.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tarih ve Saat](../atl-mfc-shared/date-and-time.md)

