---
title: ASSERT yerine VERIFY kullanma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: assert
dev_langs: C++
helpviewer_keywords:
- ASSERT statements
- debugging [MFC], ASSERT statements
- VERIFY macro
- assertions, troubleshooting ASSERT statements
- debugging assertions
- assertions, debugging
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4ffe046a281bbbbefc251b48df55ecd275515e60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-verify-instead-of-assert"></a>ASSERT Yerine VERIFY Kullanma
Hata ayıklama sürümü, MFC Uygulama çalıştırdığınızda, olduğunu herhangi bir sorun varsayalım. Ancak, aynı uygulama sürümünü kilitlenmeler, hatalı sonuçlar döndürür ve/veya başka bir anormal davranışı sergiler.  
  
 Doğru bir şekilde gerçekleştirir doğrulamak için bir onay deyimi önemli kod yerleştirdiğinizde bu soruna neden olabilir. ASSERT deyimleri bir MFC programı yayın derleme dışı bırakılır olduğundan, bir yayın derleme kodu çalışmaz.  
  
 Bir işlev çağrısı başarılı olduğunu doğrulamak için ASSERT kullanıyorsanız kullanmayı [doğrula](../../mfc/reference/diagnostic-services.md#verify) yerine. VERIFY makrosu hem hata ayıklama kendi değişkenlerinde değerlendirir ve uygulamanın sürüm oluşturur.  
  
 Başka bir işlevin dönüş değeri geçici bir değişkene atayın ve ardından değişkeni bir onay deyimi sınamak için bir tekniktir tercih edilir.  
  
 Aşağıdaki kod parçası inceleyin:  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 Bu kodu bir hata ayıklama MFC uygulaması sürümünde kusursuz şekilde çalışır. Varsa çağrısı `calloc( )` başarısız dosya ve satır numarası içeren bir tanılama iletisi görüntülenir. Ancak, bir perakende bir MFC uygulamasına oluşturun:  
  
-   çağrı `calloc( )` hiçbir zaman oluşur, bırakarak `buf` başlatılmadı, veya  
  
-   `strcpy_s( )`kopya "`Hello, World`" bellek, büyük olasılıkla uygulama kilitlenen veya yanıt vermeyi sisteme neden rastgele bir parçası olarak veya  
  
-   `free()`hiçbir zaman ayrılmış Bellek boşaltmak çalışır.  
  
 ASSERT doğru bir şekilde kullanmak için kodu örneği aşağıdaki değiştirilmelidir:  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
buf = (char *) calloc(sizeOfBuffer, sizeof(char) );  
ASSERT( buf != NULL );  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
 Veya bunun yerine doğrula kullanabilirsiniz:  
  
```  
enum {  
    sizeOfBuffer = 20  
};  
char *buf;  
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));  
strcpy_s( buf, sizeOfBuffer, "Hello, World" );  
free( buf );  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yayın Derlemesi Sorunlarını Giderme](../../build/reference/fixing-release-build-problems.md)