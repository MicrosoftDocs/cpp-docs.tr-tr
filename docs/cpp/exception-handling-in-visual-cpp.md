---
title: "Özel durum işleme Visual c++'ta | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: try-catch keyword [C++], exception handling
ms.assetid: a6aa08de-669d-4ce8-9ec3-ec20d1354fcf
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 33ec97d5f29398e9e20be9609573eecf33894948
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="exception-handling-in-visual-c"></a>Visual C++'da Özel Durum İşleme
Bir özel durum denetimi dışında kalan program kendi normal yürütme yol boyunca devam etmesini engelleyen büyük olasılıkla programın, bir hata durumudur. Nesne oluşturma, dosya giriş/çıkış ve diğer modüllerden yapılan işlev çağrıları gibi bazı işlemleri bile programınız düzgün çalışmasını özel durumların tüm olası kaynakları olur. Sağlam kod düşünmektedir ve özel durumları işler.  
  
 Mantık hataları tek bir program veya modülü içinde algılamak için özel durumlar yerine onaylar kullanır (bkz [kullanarak onaylar](/visualstudio/debugger/c-cpp-assertions)).  
  
 Visual C++ özel durum işleme üç tür destekler:  
  
-   [C++ özel durum işleme](../cpp/cpp-exception-handling.md)  
  
     C++ programları için tür kullanımı uyumlu olan ve yığını geriye doğru izleme sırasında Yıkıcılar çağrılan söz konusu nesne sağlar, C++ özel durum işleme kullanmanız gerekir.  
  
-   [Yapılandırılmış özel durum işleme](../cpp/structured-exception-handling-c-cpp.md)  
  
     Windows SEH adı verilen kendi özel durum mekanizması sağlar. C++ ya da MFC programlama için önerilmez. SEH yalnızca MFC C programları kullanın.  
  
-   [MFC özel durumları](../mfc/exception-handling-in-mfc.md)  
  
     Sürüm 3.0, bu yana MFC C++ özel durumlarını kullandı ancak hala eski kendi özel durum C++ özel durumlarını formunda benzer makroları işleme destekler. Bu makroları yeni programlama için Önerilmemesine rağmen hala geriye dönük uyumluluk için desteklenir. Zaten makroları kullanmak programlarda da C++ özel durumlarını ücretsiz olarak kullanabilirsiniz. Ön işleme sırasında özel durum Visual C++ sürüm 2. 0'dan sonra C++ dili Visual C++ uygulamasında tanımlı anahtar sözcükler işleme için makroları değerlendirin. C++ özel durumlarını kullanılacak başlatırken var olan özel durum makroları yerinde bırakın.  
  
 Kullanmak [/EH](../build/reference/eh-exception-handling-model.md) projede; kullanmak için işleme özel durumun türünü belirtmek için derleyici seçeneği C++ özel durum işleme varsayılandır. Hata işleme mekanizmaları karışık kullanmayın; Örneğin, C++ özel durum ile yapılandırılmış özel durum işleme kullanmayın. C++ özel durum işleme kullanarak kodunuzu daha taşınabilir hale getirir ve herhangi bir türde özel durumları işleme izin verir. Yapılandırılmış özel durum işleme dezavantajları hakkında daha fazla bilgi için bkz: [yapılandırılmış özel durum işleme](../cpp/structured-exception-handling-c-cpp.md). MFC makroları ve C++ özel durumlarını karıştırma hakkında öneriler için bkz: [özel durumlar: kullanarak MFC makroları ve C++ özel durumlarını](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).  
  
 CLR uygulamalarda özel durum işleme hakkında daha fazla bilgi için bkz: [özel durum işleme](../windows/exception-handling-cpp-component-extensions.md).  
  
 Özel durum x64 üzerinde işleme hakkında bilgi için bkz: işlemciler, [özel durum işleme (x64)](../build/exception-handling-x64.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)