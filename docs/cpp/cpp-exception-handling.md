---
title: C++ özel durum işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling
- Visual C++, exception handling
ms.assetid: 65f80b44-9d0f-4d17-b910-07205a5c5c40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ce782000ac1767034d00aa3e0280b8e3820e3d7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="c-exception-handling"></a>C++ Özel Durum İşleme
C++ dili özel durum oluşturmak ve yakalamak için yerleşik destek sağlar. C++'ta programlarken, yerleşik C++ özel durum desteğini hemen hemen her zaman bu bölümde açıklandığı gibi kullanmalısınız.  
  
 C++ özel durum kodunuzda işleme etkinleştirmek için [/EHsc](../build/reference/eh-exception-handling-model.md).  
  
## <a name="in-this-section"></a>Bu Bölümde  
 C++ özel durum işlemesi hakkındaki bu tartışma şunları içerir:  
  
-   [Try catch ve throw deyimleri](../cpp/try-throw-and-catch-statements-cpp.md)  
  
-   [Yakala Bloğu Nasıl Değerlendirilir](../cpp/how-catch-blocks-are-evaluated-cpp.md)  
  
-   [Özel durumlar ve yığını geriye doğru izleme](../cpp/exceptions-and-stack-unwinding-in-cpp.md)  
  
-   [Özel durum belirtimleri](../cpp/exception-specifications-throw-cpp.md)  
  
-   [noexcept](../cpp/noexcept-cpp.md)  
  
-   [İşlenilmeyen C++ Özel Durumları](../cpp/unhandled-cpp-exceptions.md)  
  
-   [C (Yapılandırılmış) ile C++ Özel Durumlarını Karıştırma](../cpp/mixing-c-structured-and-cpp-exceptions.md)  
  
## <a name="support-for-earlier-mfc-exceptions"></a>Önceki MFC Özel Durumları için Destek  
 Sürüm 4. 0'dan sonra C++ özel durum mekanizması işleme kullanarak MFC başlamıştır. C++ özel durum işlemeyi yeni kod içinde kullanmanız teşvik edilse de, MFC sürüm 4.0 ve sonraki sürümler önceki sürümlerdeki MFC makroları korur, böylece eski kodlar bozulmaz. Makrolar ile yeni bir mekanizma da birleştirilebilir. Makrolar ve C++ özel durum işleme karıştırma ve yeni mekanizmasını kullanmak için eski kod dönüştürme makaleleri bilgi için [özel durumlar: kullanarak MFC makroları ve C++ özel durumlarını](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) ve [özel durumlar: MFC'den dönüştürme Özel durum makroları](../mfc/exceptions-converting-from-mfc-exception-macros.md). Eski MFC özel durum makrolarını hala kullanmaya devam ediyorsanız, C++ özel durum anahtar sözcüklerini değerlendirin. Bkz: [özel durumlar: sürüm 3. 0'da özel durum makrolarındaki değişiklikler](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Durum İşleme](../cpp/exception-handling-in-visual-cpp.md)