---
title: Ömür
ms.date: 11/04/2016
helpviewer_keywords:
- local variables, lifetime
- variables, automatic
- storage classes, lifetime
- variables, lifetime
- automatic storage class
- automatic storage class, duration
- storage class specifiers, storage duration
- memory allocation, dynamic allocation
- functions [C++], lifetime
- storage duration
- dynamic memory allocation
- memory allocation, dynamic
- lifetime
- global variables, lifetime
ms.assetid: ff0b42cb-3f0f-49a3-a94f-d1d825d8ddfe
ms.openlocfilehash: 962e5ef4cae1be142091d2a209b4c60c0b789e74
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62232782"
---
# <a name="lifetime"></a>Ömür

"Ömür", bir değişken veya işlevin bulunduğu bir programın yürütülmesi sırasında nokta. Tanımlayıcının depolama süresi ömrünü belirler.

*Depolama sınıfı Belirleyicisi* **statik** ile belirtilen tanımlayıcı statik depolama süresine sahip. Statik depolama süresine sahip tanımlayıcılar ("Global" olarak da bilinir), bir programın süresi boyunca depolama ve tanımlı bir değere sahiptir. Depolama ayrılmıştır ve tanımlayıcı depolanan değeri, program başlatılmadan önce yalnızca bir kez başlatılır. Dış veya iç bağlantı ile tanımlanan bir tanımlayıcının aynı zamanda statik depolama süresi (bkz. [bağlantı](../c-language/linkage.md)) vardır.

**Statik** depolama sınıfı Belirleyicisi olmadan belirtilen tanımlayıcı, bir işlev içinde bildirilirse otomatik depolama süresine sahip olur. Otomatik depolama süresine sahip bir tanımlayıcı ("yerel tanımlayıcı") depolama alanına sahiptir ve yalnızca tanımlayıcının tanımlandığı veya bildirildiği blok içinde tanımlı bir değer vardır. Bir otomatik tanımlayıcı, program bu bloğa her girdiğinde yeni depolama alanı tahsis edilir ve program bloğundan çıktığında depolama alanını (ve değerini) kaybeder. Bağlantısı olmayan bir işlevde belirtilen tanımlayıcıların otomatik depolama süresi de vardır.

Aşağıdaki kurallar, bir tanımlayıcının genel (statik) veya yerel (otomatik) yaşam süresine sahip olup olmadığını belirtir:

- Tüm işlevlerin statik ömrü vardır. Bu nedenle, program yürütme sırasında her zaman vardır. Dış düzeyde (diğer bir deyişle, programdaki tüm blokların dışında, işlev tanımlarının tümünde) belirtilen tanımlayıcılar her zaman genel (statik) ömürleri vardır.

- Yerel bir değişkende bir başlatıcı varsa, değişken her oluşturulduğunda başlatılır ( **statik**olarak bildirilmemiş olmadığı sürece). İşlev parametrelerinin yerel ömrü de vardır. Bir blok içindeki tanımlayıcı için genel ömür değerini, bildiriminde **statik** depolama sınıfı Belirleyicisi ekleyerek belirtebilirsiniz. **Statik**olarak bildirildiğinde, değişken değerini bir bloğun bir girdisinden sonrakine tutar.

Genel yaşam süresine sahip bir tanımlayıcı, kaynak programın yürütülmesi boyunca (örneğin, dışarıdan tanımlanmış bir değişken veya **static** anahtar sözcüğüyle belirtilen bir yerel değişken) mevcut olsa da programın tüm bölümlerinde görünmeyebilir. Görünürlük hakkında daha fazla bilgi için [kapsam ve görünürlük](../c-language/scope-and-visibility.md) bölümüne bakın ve depolama *sınıfı-tanımlayıcı* olmayan Terminal tartışması için [depolama sınıflarını](../c-language/c-storage-classes.md) görüntüleyin.

Bellek gerektiği gibi (dinamik), gibi özel kitaplık yordamları kullanılarak oluşturulduysa, bu şekilde tahsis edilebilir `malloc`. Dinamik bellek ayırma kitaplık yordamlarını kullandığından, dilin bir parçası olarak kabul edilmez. *Çalışma zamanı kitaplık başvurusunda* [malloc](../c-runtime-library/reference/malloc.md) işlevine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Ömür, Kapsam, Görünürlük ve Bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md)
