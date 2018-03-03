---
title: "C (yapılandırılmış) ile C++ özel durumlarını karıştırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 375f954f3df300b50a11067b009614ff8879b9b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mixing-c-structured-and-c-exceptions"></a>C (Yapılandırılmış) ile C++ Özel Durumlarını Karıştırma
Daha fazla taşınabilir kod yazmak istiyorsanız, yapılandırılmış özel durum işlemeyi C++ programında kullanmanız önerilmez. Ancak, bazen ile derleme isteyebilirsiniz **/EHa** yapılandırılmış özel durumlar ve C++ kaynak kodu karıştırmak ve her iki tür özel durumları işlemek için bazı tesis gerekir. Yapılandırılmış özel durum işleyici nesneleri veya yazılan özel durumları kavramına sahip olduğundan, C++ kodu tarafından oluşturulan özel durumları işleyemiyor; Ancak, C++ **catch** yapılandırılmış özel durum işleyicileri işleyebilir. Bu tür, C++ özel durum işleme sözdizimi olarak (**deneyin**, `throw`, **catch**) C derleyici ancak yapılandırılmış özel durum işleme sözdizimi tarafından kabul edilmedi (`__try`, `__except`, `__finally`) C++ derleyicisi tarafından desteklenir.  
  
 Bkz: [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) C++ özel durum olarak yapılandırılmış özel durum işleme hakkında bilgi için.  
  
 Karışık yapılandırılmış ve C++ özel durumlarını, aşağıdakileri unutmayın:  
  
1.  Aynı işlev içinde karma C++ özel durumlarını ve yapılandırılmış özel durum.  
  
2.  Sonlandırma işleyicileri (`__finally` blokları) her zaman, bir özel durum oluşturulduktan sonra bile geriye doğru izleme sırasında yürütülür.  
  
3.  C++ özel durum işleme yakalayabilir ve koruma bırakma semantiği ile derlenmiş tüm modüllerdeki [/EH](../build/reference/eh-exception-handling-model.md) derleyici seçeneği (Bu seçeneği etkinleştirir bırakma semantiği).  
  
4.  Hangi yıkıcı işlevler tüm nesneler için çağrılır olmayan bazı durumlar olabilir. Örneğin, işlev çağrısı başlatılmamış işlev işaretçisi yapmaya çalışırken yapılandırılmış özel durum oluşur ve bu işlev çağrısından önce oluşturulmuş parametreleri nesneleri alır, bu nesneler kendi Yıkıcılar olmaz yığın geriye doğru izleme sırasında çağrılır.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [C++ programlarında setjmp veya longjmp kullanma](../cpp/using-setjmp-longjmp.md)  
  
-   [SEH ve C++ EH arasındaki farklar](../cpp/exception-handling-differences.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Özel Durum İşleme](../cpp/cpp-exception-handling.md)