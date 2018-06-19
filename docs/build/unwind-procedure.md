---
title: Bırakma yordamı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 82c5d0ca-70be-4d1a-a306-bfe01c29159f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e2a5af5d8db5974aa10595bbd3bac1cd032a0f4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32382029"
---
# <a name="unwind-procedure"></a>Bırakma Yordamı
Geriye doğru izleme kod dizisi azalan düzende sıralanır. Özel durum oluştuğunda tam bağlamı bir bağlam kaydında işletim sistemi tarafından depolanır. Özel durum dağıtma mantığı sonra çağrılan bir özel durum işleyicisi bulmak için aşağıdaki adımları, sürekli olarak yürütür.  
  
1.  Bağlam kayıt içinde depolanan geçerli RIP geçerli işlevi (veya zincirleme UNWIND_INFO girişleri durumunda işlevi bölümü) açıklayan bir RUNTIME_FUNCTION tablo girişi aramak için kullanın.  
  
2.  Hiçbir işlev tablosu girdisi bulunursa, bir yaprak işlevinde ise ve RSP doğrudan dönüş işaretçisi ele alınacaktır. [Rsp] Dönüş işaretçisi güncellenen bağlamda saklanır, benzetimli RSP 8 ile artırılır ve adım 1 tekrarlanır.  
  
3.  Bir işlevin tablo girişi bulunursa, RIP üç bölgeler a) bir bitiş, (b) içinde giriş veya c) içinde bir özel durum işleyici tarafından kapsanan kod içinde kalabileceği.  
  
    -   Büyük bir) bir bitiş içinde olduğu sonra denetim işlevi bırakarak, bu işlev için bu özel durumla ilişkili hiçbir özel durum işleyicisi olamaz ve çağıran işlevi bağlamında hesaplamak için bitiş etkilerini devam gerekir. RIP RIP kod akışından bir bitiş içinde üzerinde olup olmadığını belirlemek için incelenir. Bu kod akış yasal bitiş sonunda bölümüne eşleştirilmesini sonra bir bitiş ise ve bitiş geri kalan bölümü benzetimli, her yönerge olarak güncelleştirilen içerik kaydı ile işlenir. Bundan sonra adım 1 tekrarlanır.  
  
    -   Denetim RIP giriş içinde yer alıyorsa durumda b) işlevi girilen, bu işlev için bu özel durumla ilişkili hiçbir özel durum işleyicisi olamaz ve giriş etkilerini çağıran işlevi bağlamında işlem geri alınmalıdır. RIP işlevi başından uzaklık bırakma bilgisinin kodlanmış giriş boyutuna eşit veya daha azsa RIP giriş içindedir. Giriş etkilerini bırakma kodları dizi işlev başlangıcından RIP uzaklığını eşit veya daha az bir uzaklık ile ilk giriş için aracılığıyla İleri tarama sonra bırakma kodu dizisinin kalan tüm öğelerin etkisini geri alma tarafından sapmasına. 1. adım sonra yinelenir.  
  
    -   Örnek c) RIP bir giriş veya bitiş ve işlev içinde değil (UNW_FLAG_EHANDLER ayarlanır) bir özel durum işleyici sahipse, ardından dile özel işleyici olarak adlandırılır. İşleyicisi verilerini tarar ve uygun olarak işlev çağrıları filtreleyebilirsiniz. Dile özel işleyici, özel durumun işlendiğini veya arama devam olduğunu geri dönebilirsiniz. Bırakmayla doğrudan de başlatabilirsiniz.  
  
4.  Dile özel işleyici işlenmiş durumu döndürürse durumunda yürütme devam özgün içerik kaydı kullanarak.  
  
5.  Dile özel işleyici yoksa veya işleyici bir "arama devam et" durumu verir, ardından bağlam kaydı çağıran durumuna çözülmelidir. Bu, tüm her etkisini geri alma bırakma kodu dizi öğeleri işleyerek gerçekleştirilir. 1. adım sonra yinelenir.  
  
 Olduğunda zincirleme bırakma bilgi eklendiyse, bu temel adımları hala izlenir. Tek fark, dizinin sonuna ulaşıldığında, bir girişin etkileri bırakma için bırakma kodu dizisinin taramasını, sonra üst bırakma bilgi'ye bağlı olduğu ve burada bulunan tüm bırakma kodu dizisinin İlerliyor olmasıdır. Bu bağlama bırakma bilgisi UNW_CHAINED_INFO bayrağı olmadan geliş kadar devam eder ve onun bırakma kodu dizisinin son.  
  
 En küçük veri bırakma 8 bayt'tır. Bu, yalnızca 128 bayt veya daha az yığın tahsis ve büyük olasılıkla bir kalıcı kayıt kaydedilen bir işlevi temsil eder. Bu ayrıca bir zincirleme boyutudur hiçbir bırakma kodlarıyla sıfır uzunluklu giriş için bilgi yapısı bırakma.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Durum İşleme (x64)](../build/exception-handling-x64.md)