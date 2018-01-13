---
title: "Ortam adları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 9af409a5-e724-465a-9a21-88d3586c2e92
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: efae64f64ef6b5ed92dffafb9f83a0e32ab38513
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="environment-names"></a>Ortam Adları
**ANSI 4.10.4.4** ortam adları ve yöntemi tarafından kullanılan ortam listesi değiştirmeye yönelik kümesini [getenv](../c-runtime-library/reference/getenv-wgetenv.md) işlevi  
  
 Ortam adları sınırsız kümesidir.  
  
 Bir C programı içinden gelen ortam değişkenlerini değiştirmek için çağrı [_putenv](../c-runtime-library/reference/putenv-wputenv.md) işlevi. Windows komut satırından ortam değişkenlerini değiştirmek için SET komutunu kullanma (örneğin, AYARLAMAK LIB D:\ = KİTAPLIKLAR).  
  
 Yalnızca kendi ana bilgisayar işletim sistemi komut kabuğu kopyasını (cmd çalıştırıldığı sürece ortam değişkenleri C programı kümeden var EXE veya COMMAND.COM). Örneğin, satır  
  
```  
system( SET LIB = D:\LIBS );  
```  
  
 komut kabuğu'nu (cmd kopyasını çalıştırmanız EXE) LIB ortam değişkeni ayarlama ve C programına cmd ikincil kopyasını çıkma döndürme EXE. Cmd bu kopyası çıkma EXE geçici ortam değişkeni LIB kaldırır.  
  
 Benzer şekilde, tarafından yapılan değişiklikleri `_putenv` yalnızca program sonlanana kadar son işlev.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kitaplık işlevleri](../c-language/library-functions.md)   
 [_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)   
 [getenv, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)