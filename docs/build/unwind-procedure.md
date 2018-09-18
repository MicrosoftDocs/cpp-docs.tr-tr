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
ms.openlocfilehash: 294353baf8c15818ba836bd3093226a78aa6e44c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700667"
---
# <a name="unwind-procedure"></a>Bırakma Yordamı

Geriye doğru izleme kodu dizisi, azalan düzende sıralanır. Bir özel durum oluştuğunda, bağlamı tam bir bağlam kaydını işletim sistemi tarafından depolanır. Özel durum dağıtma mantığı sonra çağrılır, özel durum işleyicisi bulmak için aşağıdaki adımları yineleyerek yürütür.

1. Bağlam kaydında depolanmış geçerli RIP geçerli işlevi (veya söz konusu olduğunda zincirleme UNWIND_INFO girişleri işlevi bölümü) açıklayan bir RUNTIME_FUNCTION tablo girişi aramak için kullanın.

1. İşlev tablo girişi bulunursa, bir yaprak işlevde ise ve RSP Dönüş işaretçisi doğrudan ele alınacaktır. [Rsp] dönüş işaretçi güncelleştirilmiş bağlamında depolanır, 8 ile sanal RSP artırılır ve 1. adım yinelenir.

1. İşlev bir tablo girişi bulunursa RIP üç bölgedeki bir) içinde bir sonuç, (b) giriş veya c) kodda özel durum işleyicisi tarafından kapsanan kalabileceği.

   - Büyük/küçük harf bir) bir sonuç içinde olduğu sonra denetim işlevi bırakarak, bu işlev için bu durumla ilişkili hiçbir özel durum işleyicisi olabilir ve çağıran işlevin bağlamında işlem bitiş etkilerini ettirilmelidir. RIP içinde bir sonuç, kod akışı üzerinde olup olmadığını belirlemek için incelenir. Bu kod akış için meşru bir sonuç son kısmını eşleştirilebildiği sonra onu içindedir ve sonuç kalan kısmı kullanılmıştır, her yönerge olarak güncelleştirilen içerik kaydı ile işlenir. Bundan sonra 1. adım yinelenir.

   - Denetim RIP prolog içinde yer alıyorsa durumda b) işlev girilmeden, bu işlev için bu durumla ilişkili hiçbir özel durum işleyicisi olabilir ve çağıran işlevin bağlamında işlem için giriş etkilerini geri alınmalıdır. RIP işlevi başından uzaklık geriye doğru izleme bilgilerini kodlanmış giriş boyutuna eşit veya küçükse RIP giriş içindedir. Giriş etkilerini, İleri aracılığıyla geriye doğru izleme kodları dizi işlevi başından uzaklığı RIP eşit veya daha az bir uzaklık ile ilk giriş için tarama, daha sonra geri kalan tüm öğelerin bırakma kod dizideki etkisini sapmasına. 1. adım daha sonra yinelenir.

   - RIP bir giriş veya epilog ve işlev içinde değilse, büyük/küçük harf c) (UNW_FLAG_EHANDLER ayarlanır) bir özel durum işleyicisine sahiptir ve dile özel işleyici çağrılır. İşleyici verilerini tarar ve çağrıları işlevleri uygun şekilde filtreleyin. Dile özel işleyici, özel durumu işlenmiş veya arama devam etmesi gereken olduğunu döndürebilir. Bir bırakma doğrudan de başlatabilirsiniz.

1. İşlenmiş durumu dile özel işleyici döndürür, ardından yürütme devam edilir, özgün içerik kaydı kullanarak.

1. Dile özel işleyici yok ya da "aramaya devam" durum işleyicisini döndürür, ardından bağlam kaydı çağıran durumunu çözülmelidir. Bu, her birinin etkisi geri alma tüm geriye doğru izleme kodu dizi öğeleri işleme tarafından gerçekleştirilir. 1. adım daha sonra yinelenir.

Olduğunda zincirleme bırakma bilgi dahil, temel adımları hala izlenir. Tek fark, dizinin sonuna ulaşıldığında, bir girişin etkileri geriye doğru izleme bırakma kod dizisi yürüyen, ardından üst geriye doğru izleme bilgilerine bağlı olduğu ve burada bulunan tüm geriye doğru izleme kodu dizisi öğrendiniz. Bu bağlama, bir geriye doğru izleme bilgisi UNW_CHAINED_INFO bayrağı olmadan kadar devam eder ve kendi geriye doğru izleme kodu dizisinin.

En küçük kümesini veri bırakma 8 bayt'tır. Bu, yalnızca 128 bayt veya daha az yığın ayrılan ve büyük olasılıkla bir kalıcı kayıt kaydedilmiş bir işlevi temsil eder. Bu da zincirleme bir boyutudur hiçbir geriye doğru izleme kodları ile sıfır uzunluklu giriş bilgileri yapısını geriye doğru izleme.

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme (x64)](../build/exception-handling-x64.md)