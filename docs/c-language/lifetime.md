---
title: Yaşam süresi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34873681d0bc33cede9cda994aa9684e04a689e4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113779"
---
# <a name="lifetime"></a>Ömür

"Ömür" olan bir programın yürütülmesi sırasında bir süre içinde bir değişken veya işlev yok. Depolama süresi tanımlayıcısının ömrü belirler.

Bildirilmiş bir tanımlayıcı ile *depolama sınıfı tanımlayıcısı* **statik** statik depolama süresine sahip. Tanımlayıcılar ("Genel" da denir) statik depolama süresine sahip, bir program süresince depolama ve tanımlı bir değer sahip. Depolama ayrılır ve tanımlayıcının depolanan değeri yalnızca bir kez, program başlatma önce başlatılır. Bildirilmiş bir tanımlayıcı ile dış veya iç bağlantı ayrıca statik depolama süresine sahip (bkz [bağlantı](../c-language/linkage.md)).

Olmadan bildirilmiş bir tanımlayıcı **statik** depolama sınıfı belirticisi, bir işlev içinde bildirilirse otomatik depolama süresine sahip. Otomatik depolama süresine sahip bir tanımlayıcı depolama ve yalnızca burada tanımlayıcı tanımlandı veya bildirildi bloğu içinde tanımlı bir değer ("Yerel tanımlayıcı") sahiptir. Otomatik bir tanımlayıcı, program o blok girer her zaman yeni depolama ayrılır ve depolamasını (ve değerinin) kaybeder blok çıktığında program. Bağlantısı olmayan adlar bir işlev içinde bildirilen tanımlayıcılar, ayrıca otomatik depolama süresine sahip.

Aşağıdaki kurallar, bir tanımlayıcı genel (statik) veya yerel (otomatik) ömrü olup olmadığını belirleyin:

- Tüm İşlevler statik ömre sahiptir. Bu nedenle bunlar, her zaman program yürütme sırasında mevcut. Tanımlayıcılar dış düzeyinde bildirilen (diğer bir deyişle, dışındaki tüm işlev tanımlarının aynı düzeyde programı engeller) her zaman genel (statik) ömre sahip.

- Yerel bir değişken bir başlatıcı varsa, her zaman oluşturulduğu değişkeni başlatılır (olarak bildirilmedikleri sürece **statik**). İşlev parametreleri de yerel kullanım ömrüne sahip. Dahil ederek bir blok içerisindeki tanımlayıcının genel ömrünü belirtebilirsiniz **statik** kendi bildiriminde depolama sınıfı tanımlayıcısı. Bir kez bildirilen **statik**, değişken blok bir girdi değerinden sonraki korur.

Bir tanımlayıcı ile küresel bir ömrü kaynak programın yürütülmesini mevcut olsa da (örneğin, harici olarak bildirilmiş bir değişken veya ile bildirilen yerel değişken **statik** anahtar sözcüğü), tüm görünür olmayabilir program bölümleri. Bkz: [kapsam ve görünürlük](../c-language/scope-and-visibility.md) görmek ve görünürlüğü hakkında bilgi için [depolama sınıfları](../c-language/c-storage-classes.md) bir irdelemesi *depolama sınıfı tanımlayıcısı* bildirimlere.

Bellek ayrılan (dinamik) gibi özel kitaplık yordamları kullanarak oluşturduysanız, gerektiğinde `malloc`. Dinamik bellek ayırma kitaplık yordamları kullandığından, bu dilinin bir parçası olarak kabul edilmez. Bkz: [malloc](../c-runtime-library/reference/malloc.md) işlevi *çalışma zamanı kitaplığı başvurusu*.

## <a name="see-also"></a>Ayrıca Bkz.

[Ömür, Kapsam, Görünürlük ve Bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md)