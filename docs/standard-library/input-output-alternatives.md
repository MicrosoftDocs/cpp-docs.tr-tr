---
title: "Giriş-Çıkış Seçenekleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: edf17c4524fd42fd0db327aca9de85e9d63eb651
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="inputoutput-alternatives"></a>Giriş/Çıkış Seçenekleri
Visual C++ g/ç programlama için birçok seçenek sağlar:  
  
-   C çalışma zamanı kitaplığı doğrudan, arabellekten çıkarılan g/ç.  
  
-   ANSI C çalışma zamanı kitaplığı akış g/ç.  
  
-   Konsol ve bağlantı noktası doğrudan g/ç.  
  
-   Microsoft Foundation Class Kitaplığı.  
  
-   Microsoft C++ Standart Kitaplığı.  
  
 İostream sınıfları için yararlı olan arabelleğe, biçimlendirilmiş metin g/ç. Bir C++ programlama arabirimi gerekir ve Microsoft Foundation Class (MFC) kitaplığı kullanmamaya karar verirseniz, bunlar ayrıca arabellekten çıkarılan veya ikili g/ç için kullanışlıdır. İostream sınıfları bir nesne yönelimli g/ç C çalışma zamanı işlevleri alternatiftir.  
  
 Microsoft Windows işletim sistemiyle iostream sınıfları kullanabilirsiniz. Dize hem dosya akışları iş kısıtlamaları, ancak karakter modu akışı nesneleri `cin`, `cout`, `cerr`, ve `clog` Windows grafik kullanıcı arabirimi ile tutarsız. Ayrıca, doğrudan Windows ortamı ile etkileşim özel stream sınıfları türetilemeyeceğini.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ne bir akışı](../standard-library/what-a-stream-is.md)

