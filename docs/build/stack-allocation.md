---
title: Yığın ayırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 098e51f2-eda6-40d0-b149-0b618aa48b47
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 514b20847f588dab7a5c205be36c1fbd725df17d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="stack-allocation"></a>Yığın Ayırma
Bir işlevin giriş yerel değişkenler için yığın alanı ayırma için sorumlu, kaydedilmiş yazmaçlar, parametreleri yığın ve parametreleri kaydedin.  
  
 (Alloca kullanılır) parametre alanını her zaman yığının sonuna olsa dahi, böylece her zaman herhangi bir işlev çağrısı sırasında dönüş adresi bitişik olacak. En az dört girdiler içeriyor ancak her zaman tüm parametreleri tutmak için yeterli alan çağrılabilir herhangi bir işlev gerekli. Parametreleri kendilerini hiçbir zaman yığına barındırılan olsa bile alan kayıt parametreleri için her zaman ayrılır unutmayın; bir Aranan alanı tüm parametreleri için ayrıldı garanti edilmez. Çağrılan işlev bağımsız değişken listesi (va_list) ya da tek bir bağımsız değişkeni adresini yapılacak gerekebileceği ardışık bir alanı kullanılabilir olacak şekilde ev adresleri kayıt bağımsız değişkenleri için gereklidir. Bu alan aynı zamanda kayıt bağımsız değişkenleri dönüştürücü yürütme sırasında ve hata ayıklama seçeneği olarak kaydetmek için uygun bir yer sağlar (örneğin, bağımsız değişkenleri giriş kodunda ev adreslerini depolanıyorsa hata ayıklama sırasında bulmayı kolaylaştırır). Çağrılan işlev 4 adetten daha az parametreleri olsa bile bu 4 yığının konumları etkili bir şekilde çağrılan işlev tarafından sahip olunan ve parametre kayıt değerlerini kaydetme yanı sıra diğer amaçlar için çağrılan işlev tarafından kullanılıyor olabilir.  Bu nedenle arayan bilgileri yığınının bu bölgede bir işlev aramasıyla kaydedemeyebilir.  
  
 Alan bir işlevde (alloca) dinamik olarak ayrılır, kalıcı bir kayıt temeli yığın sabit bir parçası olan işaretlemek için bir çerçeve işaretçisi olarak kullanılması gerekir ve bu kayıt kaydedilir ve giriş başlatıldı. Alloca kullanıldığında, aynı Aranan çağrıları aynı kayıt parametreleri için farklı ev adresleri gerekebileceğini unutmayın.  
  
 Yığın her zaman 16 bayt sürdürüleceği hizalanmış olarak dışındaki giriş (örneğin dönüş adresi gönderilen sonra) içinde ve belirtilen yerlerde dışındaki [işlev türleri](../build/function-types.md) çerçeve işlevlerin belirli bir sınıf için.  
  
 Burada bir işlev çağrılarını yaprak olmayan B. işlev A'ın giriş işlev yığın düzeni örneği zaten alt kısmındaki yığın b'de gerektirdiği tüm kayıt ve yığın parametreleri için alan ayırdığı verilmiştir. Dönüş adresi çağrı iter, B'nin giriş kendi yerel değişkenler, kalıcı Yazmaçları ve işlevleri çağırmak için ihtiyaç duyulan alanı için alan ayırır. B alloca kullanıyorsa, alan yerel değişken/kalıcı kayıt kaydetme alanı ve parametre yığın alanı arasında ayrılır.  
  
 ![AMD Dönüşüm örneği](../build/media/vcamd_conv_ex_5.png "vcAmd_conv_ex_5")  
  
 Dönüş adresi B işlevi başka bir işlevi aradığında, yalnızca aşağıdaki ev adresi RCX için gönderilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yığın Kullanımı](../build/stack-usage.md)