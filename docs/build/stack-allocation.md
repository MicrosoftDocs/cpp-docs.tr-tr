---
title: Yığın ayırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 098e51f2-eda6-40d0-b149-0b618aa48b47
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9e0210239f2d915fcc3445a74cfdf5b0d1796df7
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701505"
---
# <a name="stack-allocation"></a>Yığın Ayırma

Bir işlevin giriş yığın alanı yerel değişkenler için sorumlu olan, kaydedilmiş yazmaçlar, parametreleri yığın ve parametreleri kaydedin.

Parametre alanı (alloca kullanılsa bile), her zaman yığının en altında olan, böylece bu her zaman herhangi bir işlev çağrısı sırasında dönüş adresi için bitişik olacaktır. En az dört girişler içeriyor, ancak tüm parametreleri tutmak için yeterli alan çağrılabilir hiçbir işlev tarafından her zaman gerekli. Parametreleri yığına hiçbir zaman barındırılan olsa bile alan kayıt parametreleri için her zaman ayrılır dikkat edin. bir çağrılan alanı tüm parametreleri için ayrıldı garanti edilir. Bağımsız değişken listesi (va_list) ya da tek bir bağımsız değişken adresini almak çağrılan işlev ihtiyacı ardışık bir alanı kullanılabilir olması, ev adresleri yazmaç bağımsız değişkenleri gereklidir. Bu alan ayrıca kayıt bağımsız değişkenleri dönüştürücü yürütme sırasında ve hata ayıklama seçeneği olarak kaydetmek için uygun bir yer sağlar (örneğin, bağımsız değişkenler ev adreslerini giriş kodu içinde depolanıyorsa hata ayıklama sırasında bulmayı kolaylaştırır). Çağrılan işlev en az 4 parametreleri olsa bile, bu 4 yığın konumlarının etkili bir şekilde çağrılan işlev tarafından sahip olunan ve parametre kayıt değerlerini kaydetme yanı sıra diğer amaçlar için çağrılan işlev tarafından kullanılıyor olabilir.  Bu nedenle arayan bilgileri yığınının bu bölgede bir işlev çağrısı kaydedemeyebilir.

Alan bir işlevde (alloca) dinamik olarak ayrılır, yığın sabit parçası tabanı işaretlemek için bir çerçeve işaretçisi olarak kalıcı bir kayıt kullanılmalıdır ve konusu kasaya kaydedilir ve giriş bölümünde başlatılır. Alloca kullanıldığında, aynı çağrılan çağrıları aynı kayıt parametreleri için farklı ev adresleri gerekebileceğini unutmayın.

Yığın her zaman 16 baytlık korunur hizalanmış, giriş (örneğin, sonra dönüş adresi gönderilir) ve belirtilen belirtilmediği [işlev türleri](../build/function-types.md) çerçeve işlevlerinin belirli bir sınıf için.

Burada A'dan B'ye işlevi giriş yaprak olmayan bir işlev çağrıları işlev yığın düzeni örneği zaten yığının sonuna B için gerekli tüm kayıt ve yığın parametreler için alanı ayırdığı verilmiştir. Çağrının dönüş adresi gönderir ve yerel değişkenleri ve kalıcı kayıtlar işlevleri çağırmak için ihtiyaç duyulan alanı B kullanıcısının giriş alanı ayırır. B alloca kullanıyorsa, yerel değişken/kalıcı kayıt kaydetme alanı arasında parametre yığın alanı alanı ayrılır.

![AMD dönüştürme örnek](../build/media/vcamd_conv_ex_5.png "AMD dönüştürme örneği")

Dönüş adresi B işlevi başka bir işlevi çağırdığında, yalnızca aşağıdaki ev adresi RCX için gönderilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Yığın Kullanımı](../build/stack-usage.md)