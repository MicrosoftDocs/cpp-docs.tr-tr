---
title: '&lt;stdexcept&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <stdexcept>
dev_langs: C++
helpviewer_keywords: stdexcept header
ms.assetid: 495c10b1-1e60-4514-9f8f-7fda11a2f522
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1cebff3122ed32a8c166324283a8e18f3b247361
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltstdexceptgt"></a>&lt;stdexcept&gt;
Raporlama özel durumlar için kullanılan birkaç standart sınıfları tanımlar. Türetme hiyerarşi tüm sınıfından türetilen sınıflar form [özel durum](../standard-library/exception-class.md) ve özel durumları iki genel türleri şunlardır: mantıksal hataları ve çalışma zamanı hataları. Mantıksal hataları Programcı hatalar nedeniyle oluşur. Bunlar, temel sınıf logic_error türetilen ve şunları içerir:  
  
-   `domain_error`  
  
-   `invalid_argument`  
  
-   `length_error`  
  
-   `out_of_range`  
  
 Kitaplık işlevleri veya çalışma zamanı sistem hataları nedeniyle çalışma zamanı hataları oluşur. Bunlar, temel sınıf runtime_error türetilen ve şunları içerir:  
  
-   `overflow_error`  
  
-   `range_error`  
  
-   `underflow_error`  
  
### <a name="classes"></a>Sınıflar  
  
|||  
|-|-|  
|[domain_error sınıfı](../standard-library/domain-error-class.md)|Sınıfı, bir etki alanı hatayı bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.|  
|[invalid_argument sınıfı](../standard-library/invalid-argument-class.md)|Sınıfı, geçersiz bir bağımsız değişken bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.|  
|[length_error sınıfı](../standard-library/length-error-class.md)|Sınıfın belirtilmesi çok uzun bir nesne oluşturma girişimi bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.|  
|[logic_error sınıfı](../standard-library/logic-error-class.md)|Sınıf, mantıksal önkoşulları ihlalleri gibi program yürütülmeden önce hatalarını raporlamak için büyük olasılıkla algılanabilir oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.|  
|[out_of_range sınıfı](../standard-library/out-of-range-class.md)|Sınıfı, geçerli aralığın dışında bir bağımsız değişken bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.|  
|[overflow_error sınıfı](../standard-library/overflow-error-class.md)|Sınıfı, aritmetik taşma bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.|  
|[range_error sınıfı](../standard-library/range-error-class.md)|Sınıfı, bir aralık hatayı bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.|  
|[runtime_error sınıfı](../standard-library/runtime-error-class.md)|Sınıfı yalnızca program yürüttüğünde hatalarını raporlamak için büyük olasılıkla algılanabilir oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.|  
|[underflow_error sınıfı](../standard-library/underflow-error-class.md)|Sınıfı, bir aritmetik underflow bildirmek için oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

