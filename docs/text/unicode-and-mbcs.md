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
ms.openlocfilehash: 9cd3e3369e2da18d707de20afc900a0bc4c9f249
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020388"
---
# <a name="unicode-and-mbcs"></a>Unicode ve MBCS
Microsoft Foundation sınıfları (MFC) kitaplığı, Visual c++ C çalışma zamanı kitaplığı ve Visual C++ geliştirme ortamı, uluslararası programlamanıza yardımcı olmak için etkinleştirilir. Şunları sağlar:  
  
-   Windows üzerinde Unicode standardı için destek. Unicode geçerli standart ve mümkün olduğunda kullanılmalıdır.  
  
     Unicode kodlama, tüm diller için yeterli sağlayan bir 16 bit karakterdir. Tüm ASCII karakterleri Unicode genişletti karakterleri dahil edilir.  
  
-   Tüm platformlarda çift baytlı karakter kümesi (DBCS) adlı bir tür bir çok baytlı karakter kümesi (MBCS) desteği.  
  
     1 veya 2 bayt DBCS karakterden oluşur. Bazı bayt aralıkları, kullanım için kenara ön bayt olarak ayarlanır. Ve aşağıdaki bayt oluşturan tek bir 2-bayt genişliğinde karakter baytı belirtir. Ön bayt hangi bayt olduğunu takip gerekir. Baytlar gibi belirli bir çok baytlı karakter kümesi içinde belirli bir aralıkta ön baytlar ayrılır. Bu aralıklar üst üste, belirli bir bayt bir ön bayt veya bir bayt olarak çalışıp çalışmadığını belirlemek için bağlam değerlendirilecek gerekli olabilir.  
  
-   MBCS uluslararası pazarlar için yazılmış uygulamaların programlamasını basitleştiren Araçlar desteği.  
  
     Bir MBCS etkinleştirilmiş Windows işletim sistemi sürümü, Visual C++ geliştirme sistemi üzerinde çalıştırdığınızda — tümleşik Kaynak Kod Düzenleyicisi, hata ayıklayıcı ve komut satırı araçları dahil olmak üzere — tamamen MBCS etkinleştirilir. Daha fazla bilgi için [Visual C++'ta MBCS Desteği](../text/mbcs-support-in-visual-cpp.md).  
  
> [!NOTE]
>  Bu belgede, MBCS, Unicode olmayan çok baytlı karakter desteği tüm tanımlamak için kullanılır. Visual c++'ta MBCS DBCS her zaman anlamına gelir. Karakter uzunluğundan için 2 bayt desteklenmeyen ayarlar.  
  
 Tanımı gereği, ASCII karakter kümesi tüm çok baytlı karakter kümeleri bir alt kümesidir. Çok baytlı karakter kümelerinin her karakter aralığı 0x00 - 0x7F aynı değere sahip ASCII karakter kümesinden karakter aynıdır. Örneğin, ASCII ve MBCS karakter dizeleri, 1-bayt NULL karakteri ('\0') 0x00 değerine sahiptir ve sondaki boş karakter gösterir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Metin ve dizeler](../text/text-and-strings-in-visual-cpp.md)   
 [Uluslararası Etkinleştirme](../text/international-enabling.md)