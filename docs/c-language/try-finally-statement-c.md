---
title: try-Statement (C) finally | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- try-finally keyword [C]
- __finally keyword [C], try-finally statement syntax
- __finally keyword [C]
- structured exception handling, try-finally
ms.assetid: 514400c1-c322-4bf3-9e48-3047240b8a82
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 82e8f55d927edbad4812e23b96ad806510d39b85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="try-finally-statement-c"></a>try-finally Deyimi (C)
**Microsoft özel**  
  
 `try-finally` Kod bloğunu yürütülmesi kesintiye uğradığında oluşan temizleme kodu yürütme güvence altına almak uygulamalar sağlayan C dili için bir Microsoft uzantısı bir ifadedir. Bellek ayırmayı kaldırma, dosyaları kapatma ve dosya işleyicilerini serbest gibi görevler temizleme oluşur. `try-finally` Burada bir denetimi yapılır neden olabilecek bir hata için erken çeşitli yerlerde sahip yordamları yordamından dönmek için deyimi özellikle yararlı.  
  
 *try-finally-ifadesi*:  
 **__try***bileşik deyim*   
  
 **__finally***bileşik deyim*   
  
 Bileşik deyim sonra `__try` yan tümcesi olan korumalı bölüm. Bileşik deyim sonra `__finally` yan tümcesi olan sonlandırma işleyicisi. İşleyici korunmuş bölümü çıktı, standart sonbaharda (normal sonlandırma) üzerinden veya bir özel durum (anormal sonlandırma) tarafından korunmuş bölümü çıktı olup olmadığını yürütün eylemleri kümesini belirtir.  
  
 Denetim ulaştığında bir `__try` ifadesinin basit sıralı yürütme (sonbaharda aracılığıyla). Denetim girdiğinde `__try` deyimi, ilişkili işleyicisi etkin hale gelir. Yürütme gibi çalışır:  
  
1.  Korunan bölüm yürütülür.  
  
2.  Sonlandırma işleyicisi çağrılır.  
  
3.  Sonlandırma işleyicisi tamamlandığında sonra yürütülmeye `__finally` deyimi. Bağımsız olarak nasıl bölüm uçları guarded (örneğin, aracılığıyla bir `goto` deyimi korunmuş gövde dışında veya aracılığıyla bir `return` deyimi), denetim akışını dışında korunmuş bölümüne geçmeden önce sonlandırma işleyicisi yürütülür.  
  
 `__leave` Sözcüktür içinde geçerli bir `try-finally` deyimi bloğu. Etkisini `__leave` sonuna atlamak için `try-finally` bloğu. Sonlandırma işleyicisi hemen çalıştırılır. Ancak bir `goto` deyimi, aynı sonucu gerçekleştirmek için kullanılabilir bir `goto` deyimi neden yığını geriye doğru izleme. `__leave` Deyimi olduğundan daha verimli yığını geriye doğru izleme gerektirmez.  
  
 Çıkma bir `try-finally` deyimi kullanarak bir `return` deyimi veya `longjmp` çalışma zamanı işlevi anormal sonlandırma olarak kabul edilir. İçine atlamak için geçersiz bir `__try` deyimi, ancak bir dışı atlamak için yasal. Tüm `__finally` etkin ayrılma noktası ve hedef deyimleri çalıştırılması gerekir. Bu bir "yerel bırakma." olarak adlandırılır  
  
 Bir işlem yürütülürken sonlandırılırsa sonlandırma işleyicisi çağrılmaz bir `try-finally` deyimi.  
  
> [!NOTE]
>  Yapılandırılmış özel durum işleme C ve C++ kaynak dosyalar üzerinde çalışır. Ancak, özellikle C++ için tasarlanmamıştır. C++ özel durum işlemeyi kullanarak kodunuzun daha taşınabilir olduğundan emin olabilirsiniz. Ayrıca, C++ özel durum mekanizması işleme çok daha esnek ve herhangi bir tür özel durumlar işleyebilir olmamasıdır.  
  
> [!NOTE]
>  C++ programları için C++ özel durum işleme yapılandırılmış özel durum işleme yerine kullanılmalıdır. Daha fazla bilgi için bkz: [özel durum işleme](../cpp/exception-handling-in-visual-cpp.md) içinde *C++ dil başvurusu*.  
  
 Örneğin bkz [deneyin-except deyimi](../c-language/try-except-statement-c.md) görmek için nasıl `try-finally` deyimi çalışır.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [try-finally Deyimi](../cpp/try-finally-statement.md)