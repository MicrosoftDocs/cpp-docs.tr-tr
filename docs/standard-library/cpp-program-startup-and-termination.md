---
title: "C++ Program başlatma ve sonlandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- C++ Standard Library, program startup and termination
- terminating execution
- Function Main procedures
- control text streams
- startup code, and C++ program termination
- main function, program startup
ms.assetid: f72c8f76-f507-4ddd-a270-7b60f4fed625
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 42baa08777e8e898ee4c6e49ce74b03c293c9b96
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="c-program-startup-and-termination"></a>C++ Program Başlatma ve Sonlandırma
Program başlatma ve program sonlandırma yanı sıra daha Burada özetlenen birkaç C programı yaptığı gibi bir C++ programı aynı işlemleri gerçekleştirir.  
  
 Önce hedef ortam işlevi çağırır `main`, ve statik süresi olan tüm nesneleri belirttiğiniz herhangi bir sabit ilk değeri depolar sonra kalan tüm oluşturucuları statik tür nesneler için programı yürütür. Çeviri birimleri arasında yürütme sırasını belirtilmedi, ancak, Bununla birlikte, bazı kabul edilebilir [iostreams](../standard-library/iostreams-conventions.md) nesneleri bu statik oluşturucular tarafından kullanılmak üzere doğru başlatılır. Bu denetim metin akışları şunlardır:  
  
-   [cin](../standard-library/iostream.md#cin) — standart giriş için.  
  
-   [cout](../standard-library/iostream.md#cout) — standart çıktı.  
  
-   [cerr](../standard-library/iostream.md#cerr) — arabellekten çıkarılan standart hata çıktısı için.  
  
-   [clog](../standard-library/iostream.md#clog) — için arabelleğe alınan standart hata çıktısı.  
  
 Bu nesneler statik nesneler için program sonlandırma sırasında adlı Yıkıcılar içinde de kullanabilirsiniz.  
  
 Visual c gibi döndürme `main` veya çağırma `exit` kayıtlı tüm işlevleri çağıran `atexit` ters sırada, kayıt defteri. Kayıtlı işlevi Studio'yu ayrı bir özel durum çağrı `terminate`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığına genel bakış](../standard-library/cpp-standard-library-overview.md)   
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)


