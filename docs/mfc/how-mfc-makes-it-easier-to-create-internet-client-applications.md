---
title: "Nasıl MFC Internet istemci uygulamaları oluşturmayı kolaylaştırması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
- MFC, Internet applications
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f6270cdd3e64d24f1c2000acb9e8466f8c85edba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-mfc-makes-it-easier-to-create-internet-client-applications"></a>MFC'nin Internet İstemci Uygulamaları Oluşturmayı Kolaylaştırması
Microsoft Foundation sınıfları MFC programcıları için tanıdık bir bağlam sağlar bir şekilde Win32 Internet uzantısı (WinINet) işlevleri kapsüller. MFC üç Internet dosya sınıfları sağlar ([CInternetFile](../mfc/reference/cinternetfile-class.md), [CHttpFile](../mfc/reference/chttpfile-class.md), ve [CGopherFile](../mfc/reference/cgopherfile-class.md)) türetilen [CStdioFile](../mfc/reference/cstdiofile-class.md) sınıfı . Yalnızca bu alma ve Internet veri düzenleme kullanmış olan programcıları sınıflarının `CStdioFile` yerel dosyalar için ancak bu sınıflarla yerel dosyaları ve Internet dosyaları tutarlı ve saydam bir şekilde işleyebilir.  
  
 MFC WinINet sınıfları ile aynı işlevselliği sağlayan `CStdioFile` Internet üzerinden aktarılan veriler için. Bu sınıfların Internet protokolleri, bir üst düzey uygulama programlama arabirimi, Internet kullanan uygulamalar yapmak için hızlı ve kolay bir yol sağlayan HTTP, FTP ve gopher soyut. Örneğin, bir FTP sunucusuna bağlanırken hala en düşük düzeyde birkaç adım gerektiriyor, ancak bir MFC geliştiricisi olarak, yalnızca yapılan bir çağrı yapmanız gereken `CInternetSession::GetFTPConnection` o bağlantı oluşturmak için.  
  
 Ek olarak, MFC WinINet sınıfları aşağıdaki avantajları sağlar:  
  
-   Arabelleğe alınan g/ç  
  
-   Tür kullanımı uyumlu verileriniz için işleme  
  
-   Birçok işlevleri için varsayılan parametreleri  
  
-   Özel durum için ortak Internet hataları işleme  
  
-   Otomatik temizleme açık tanıtıcıların ve bağlantıları  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Win32 Internet Uzantıları (WinINet)](../mfc/win32-internet-extensions-wininet.md)   
 [WinInet'in Internet İstemci Uygulamaları Oluşturmayı Kolaylaştırması](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)

