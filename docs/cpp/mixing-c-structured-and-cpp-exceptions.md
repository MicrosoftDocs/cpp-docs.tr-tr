---
title: C (yapılandırılmış) ile C++ özel durumlarını karıştırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e632faddb3b4f59733710a915ed121a12f4e0c6
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404869"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>C (Yapılandırılmış) ile C++ Özel Durumlarını Karıştırma
Daha taşınabilir kod yazmak istiyorsanız, yapılandırılmış özel durum işlemeyi C++ programında kullanılması önerilmez. Ancak, bazen ile derleme isteyebileceğiniz **/eha** yapılandırılmış özel durumları ve C++ kaynak kodunu karışımı ve her iki tür özel durumları işlemek için bazı özellik gerekir. Yapılandırılmış özel durum işleyicisi nesneleri veya belirlenmiş özel durumlar kavramı olduğundan, C++ kodu tarafından oluşturulan özel durumları işlemek olamaz; Bununla birlikte, C++ **catch** işleyicileri, yapılandırılmış özel durumları işleyebilir. Bu, C++ özel durum işleme sözdizimini olarak (**deneyin**, **throw**, **catch**) C derleyicisi ancak yapılandırılmış özel durum işleme sözdizimini tarafından kabul edilmiyor (**__try** , **__except**, **__finally**) C++ Derleyici tarafından desteklenir.  
  
 Bkz: [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) yapılandırılmış özel durumları C++ özel durum işleme hakkında bilgi.  
  
 Karışık, yapılandırılmış ve C++ özel durumlarını, aşağıdakileri unutmayın:  
  
1.  C++ özel durumlarını ve yapılandırılmış özel durumları aynı işlevin içinde karıştırılamaz.  
  
2.  Sonlandırma işleyicileri (**__finally** blokları) her zaman, bir özel durum oluştuktan sonra bile geriye doğru izleme sırasında yürütülür.  
  
3.  C++ özel durum işleme yakalayabilir ve koruma geriye doğru izleme semantiği ile derlenmiş tüm modüllerin [/EH](../build/reference/eh-exception-handling-model.md) derleyici seçeneği (Bu seçenek geriye doğru izleme semantiği sağlar).  
  
4.  Hangi yıkıcı işlevleri tüm nesneleri için çağrılmaz bazı durumlar olabilir. Örneğin, işlev çağrısı bir başlatılmamış işlev işaretçisi yapmaya çalışırken bir yapılandırılmış özel durum oluşur ve bu işlev çağrısından önce oluşturulmuş parametreleri nesneleri alır, nesneleri, Yıkıcılar olmaz yığın bırakma sırasında çağrılır.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [C++ programlarında setjmp veya longjmp kullanma](../cpp/using-setjmp-longjmp.md)  
  
-   [SEH ve C++ EH arasındaki farklar](../cpp/exception-handling-differences.md)  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [C++ Özel Durum İşleme](../cpp/cpp-exception-handling.md)