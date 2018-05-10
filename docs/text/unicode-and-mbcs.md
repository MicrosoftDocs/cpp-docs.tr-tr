---
title: Unicode ve MBCS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- _mbcs
dev_langs:
- C++
helpviewer_keywords:
- MBCS [C++], Unicode
- MFC [C++], character sets
- character sets [C++], multibyte
- run-time libraries [C++], language portability
- character sets [C++], Unicode
- Unicode [C++], MFC and C run-time functions
- multibyte characters [C++]
- runtime [C++], language portability
ms.assetid: 677baec6-71b4-4579-94df-64f18bc117c4
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e10c07e11cbe940b5f7cfee460ddd33f6f5ff1f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="unicode-and-mbcs"></a>Unicode ve MBCS
Uluslararası programlama yardımcı olmak için Microsoft Foundation sınıfları (MFC) kitaplığı, Visual c++ C çalışma zamanı kitaplığı ve Visual C++ geliştirme ortamı etkin. Bunlar sağlar:  
  
-   Windows'da Unicode standart desteği. Unicode geçerli standarttır ve mümkün olduğunda kullanılmalıdır.  
  
     Unicode kodlama, tüm diller için yeterli Kodlamalar sağlayan bir 16 bit karakterdir. Tüm ASCII karakterleri Unicode genişletmiştir karakter olarak dahil edilir.  
  
-   Tüm platformlarda çift bayt karakter kümesi (DBCS) adlı bir form birden çok baytlı karakter kümesi (MBCS) desteği.  
  
     DBCS karakterleri 1 veya 2 bayt oluşur. Bazı bayt aralıkları ön bayt olarak kullanılmak üzere ayrılan. Bu ve aşağıdaki sondaki bayt tek bir 2 bayt geniş karakter oluşturan baytı belirtir. Hangi baytların ön bayt olduğunu izlemek gerekir. Baytlar gibi belirli bir çok baytlı karakter kümesinde belirli bir aralığa ön baytlar ayrılır. Bu aralıklar üst üste, verilen baytın baytı veya sondaki bayt olarak çalışıp çalışmadığını belirlemek için bağlamı değerlendirmek gerekli olabilir.  
  
-   MBCS programlama için Uluslararası pazarda yazılmış uygulamaların kolaylaştıran Araçlar desteği.  
  
     Bir MBCS etkinleştirilmiş Windows işletim sistemi, Visual C++ geliştirme sistemi sürümünde çalıştırdığınızda — tümleşik kaynak kod düzenleyicisinde, hata ayıklayıcı ve komut satırı araçları dahil olmak üzere — tamamen MBCS etkindir. Daha fazla bilgi için bkz: [Visual C++'ta MBCS Desteği](../text/mbcs-support-in-visual-cpp.md).  
  
> [!NOTE]
>  Bu belgede MBCS birden çok baytlı karakterler tüm Unicode olmayan desteği açıklamak için kullanılır. Visual c++'ta MBCS her zaman DBCS anlamına gelir. Karakter 2 bayt desteklenmez uzunluğundan ayarlar.  
  
 Tanımı gereği, ASCII karakter kümesi tüm çok baytlı karakter kümeleri bir alt kümesidir. Çok baytlı karakter kümelerinin her karakter aralığı 0x00 - 0x7F aynı değere sahip ASCII karakter kümesinden karakter aynıdır. Örneğin, ASCII ve MBCS karakter dizeleri, 1-bayt olarak **NULL** karakteri ('\0') 0x00 değerine sahiptir ve sonlandırıcı boş karakteri gösterir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Metin ve dizeler](../text/text-and-strings-in-visual-cpp.md)   
 [Uluslararası Etkinleştirme](../text/international-enabling.md)