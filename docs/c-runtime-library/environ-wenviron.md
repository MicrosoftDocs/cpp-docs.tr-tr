---
title: _environ, _wenviron | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- environ
- wenviron
- _wenviron
- _environ
dev_langs: C++
helpviewer_keywords:
- environ function
- _environ function
- _wenviron function
- process environment
- wenviron function
ms.assetid: 7e639962-6536-47cd-8095-0cbe44a56e03
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f20054dac02857187ef4507b0b4ebfd6b7c6fe0e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="environ-wenviron"></a>_environ, _wenviron
`_environ` İşlem ortamını oluşturan çok baytlı karakter dizeleri işaretçiler dizisi için bir işaretçi bir değişkendir. Bu genel değişkeni daha güvenli işlevsel sürümleri için kullanım dışı [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md) ve [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md), hangi kullanılmalıdır yerine genel değişkeni. `_environ`içinde Stdlib.h bildirildi.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
extern char **_environ;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanan bir programda `main` işlevi, `_environ` işletim sistemi ortamdan alınan ayarlara göre program başlangıçta başlatıldı. Bir veya daha fazla form girişlerinin ortam oluşur  
  
 `ENVVARNAME``=string`  
  
 `getenv_s`ve `putenv_s` kullanmak `_environ` erişme ve ortam Tablo değiştirme değişkeni. Zaman `_putenv` eklemek veya ortam ayarları silmek için adlı ortamı tablo boyutu değişir. Bellek konumunda, programın bellek gereksinimlerine bağlı olarak değişebilir. Değeri `_environ` otomatik olarak uygun şekilde ayarlanır.  
  
 `_wenviron` Değişken Stdlib.h içinde bildirilen:  
  
```  
extern wchar_t **_wenviron;  
```  
  
 bir joker karakter sürümü `_environ`. Kullanan bir programda `wmain` işlevi, `_wenviron` işletim sistemi ortamdan alınan ayarlara göre program başlangıçta başlatıldı.  
  
 Kullanan bir programda `main`, `_wenviron` başlangıçta `NULL` çok baytlı karakter dizeleri oluşturulan ortam olduğundan. İlk çağrıda `_wgetenv` veya `_wputenv`, karşılık gelen bir joker karakter dizesi ortamı oluşturulur ve işaret ediyor `_wenviron`.  
  
 Benzer şekilde, kullanan bir programda `wmain`, `_environ` başlangıçta `NULL` joker karakter dizelerini oluşturulan ortam olduğundan. İlk çağrıda `_getenv` veya `_putenv`, karşılık gelen bir çok baytlı karakter dizesi ortamı oluşturulur ve işaret ediyor `_environ`.  
  
 Ortam (MBCS ve Unicode) iki kopyasını aynı anda bir program varsa, çalışma zamanı sistem kaynaklanan yavaş yürütme süresi içinde her iki kopya bulundurmanız gerekir. Örneğin, her çağırmanız `_putenv`, çağrı `_wputenv` böylece iki ortam dizeleri karşılık da otomatik olarak yürütülür.  
  
> [!CAUTION]
>  Çalışma zamanı sistem Unicode sürümü ve ortam, birden çok baytlı sürümü korurken nadir durumlarda, bu iki ortam sürümleri tam olarak karşılık gelmeyebilir. Benzersiz bir UNICODE dizesi herhangi bir benzersiz çok baytlı karakter dizesini eşleştirir ancak çok baytlı karakter dizesi için benzersiz bir UNICODE dizesi eşlemesinden mutlaka benzersiz olmadığından budur. Bu nedenle, iki farklı Unicode dizeleri aynı birden çok baytlı dizeye eşleyebilir.  
  
 Yoklama `_environ` bir Unicode bağlam anlamsız olduğunda [/MD](../build/reference/md-mt-ld-use-run-time-library.md) veya `/MDd` bağlantı kullanılır. CRT DLL için program türü (geniş veya birden çok baytlı) bilinmiyor. En olası senaryo olduğundan yalnızca birden çok baytlı türü oluşturulur.  
  
 Aşağıdaki sözde kod nasıl gerçekleşebilir gösterir.  
  
```  
int i, j;  
i = _wputenv( "env_var_x=string1" );  // results in the implicit call:  
                                      // putenv ("env_var_z=string1")  
j = _wputenv( "env_var_y=string2" );  // also results in implicit call:  
                                      // putenv("env_var_z=string2")  
```  
  
 Bu örnek için kullanılan gösterimde karakter dizelerini C dize değişmez değerleri değildir; Unicode ortam dizelerini temsil eden yer tutucular yerine, oldukları `_wputenv` çağrısı ve çok baytlı Ortam dizeleri `putenv` çağırın. Karakter tutucular`x`'ve'`y`' iki ayrı Unicode olarak Ortam dizeleri benzersiz olarak geçerli MBCS karakter eşleme yok. Bunun yerine, her ikisi de bazı MBCS karakterle eşleştirmek '`z`' diğer bir deyişle dizeleri dönüştürme girişimi varsayılan sonucu.  
  
 Bu nedenle, ortamında birden çok baytlı değerini "`env_var_z`" ilk örtük çağrısından sonra `putenv` olacaktır "`string1`", ancak bu değer ikinci örtük çağrıda yazılmasını `putenv`, ne zaman değerini "`env_var_z`" olan ayarlamak "`string2`". Unicode ortam (içinde `_wenviron`) ve çok baytlı ortamını (içinde `_environ`) bu nedenle bu dizi çağrısı aşağıdaki farklı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel değişkenler](../c-runtime-library/global-variables.md)   
 [GETENV, _wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)   
 [getenv_s, _wgetenv_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [_putenv, _wputenv](../c-runtime-library/reference/putenv-wputenv.md)   
 [_putenv_s, _wputenv_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)