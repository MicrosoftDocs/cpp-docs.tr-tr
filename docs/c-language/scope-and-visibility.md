---
title: Kapsam ve görünürlük | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- scope, levels
- visibility
- file scope [C++]
ms.assetid: a019eb7c-66ed-46a7-bc9f-89a963930a56
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b10902d44d8bc2e24a94123cc198a3b7606dac43
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136055"
---
# <a name="scope-and-visibility"></a>Kapsam ve Görünürlük

Bir tanımlayıcının "görünürlüğünü" içinde bu başvurulabilir programın bölümlerini belirler — "kapsamı." Tanımlayıcının görünür (yani, kullanılabilir) (, restrictiveness artan sırada), dosya, işlev, blok veya işlev prototipi göründüğü sınırlı, "kapsam tarafından" çevrelenmiş bir programın kısımları içinde. Kapsamı bir tanımlayıcının adı kullanılabilir program parçasıdır. Bu bazen "sözcük kapsamı." olarak adlandırılır. Kapsam dört çeşit vardır: işlev, dosya, blok ve işlev prototipi.

Etiketler dışında tüm tanımlayıcılar bildirimi oluştuğu düzeyi tarafından belirlenen kapsamlarına sahip. Her türden bir kapsam için aşağıdaki kurallar, bir program içindeki tanımlayıcıları görünürlüğünü yöneten:

Dosya kapsamı bildirimci veya tür tanımlayıcısında tanımlayıcının dosya kapsamı ile herhangi bir blok veya parametrelerin listesi dışında görünür ve bildiriminden sonra çeviri birimi içinde herhangi bir yerden erişilebilir. Dosya kapsamına sahip tanımlayıcı adları genellikle "Genel" veya "dış" adı verilir Genel tanımlayıcı kapsamını, kendi tanımında veya bildiriminde noktasında başlar ve çeviri biriminde sonunda sona erer.

İşlevi bir kapsam etiketi yalnızca işlev kapsamı tanımlayıcısı türüdür. Bir etiket deyimindeki kullanımı tarafından örtük olarak bildirilmiş. Etiket adları bir işlev içinde benzersiz olmalıdır. (Etiketler ve etiket adları hakkında daha fazla bilgi için bkz: [goto ve etiketli deyimleri](../c-language/goto-and-labeled-statements-c.md).)

Blok kapsamı bildirimcide veya tür tanımlayıcısında blok kapsamı olan bir tanımlayıcı için bir blok içinde veya bir işlev tanımı bildirimlerinde biçimsel parametre listesi içinde görünür. Bunu yalnızca noktasından bildirim veya tanım, bildirim veya tanım içeren bloğun sonuna kadar görülebilir. Kapsamı, o blok ve o blok içinde iç içe geçmiş herhangi bir bloğu sınırlıdır ve ilişkili blok kapatır küme ayracı sona erer. Tür tanımlayıcıları adlandırılan "yerel değişkenler."

İşlev prototipi kapsam bildirimci veya tür tanımlayıcısında işlev prototipi kapsamlı bir tanımlayıcı için bir işlev prototipi (olmayan işlev bildiriminin bir parçası) bildirimlerinde parametre listesi içinde görünür. Kapsamı işlev bildirimcisinden sonunda sona erer.

Değişkenleri başka kaynak dosyalarında görünür yapmak için uygun bildirimleri açıklanan [depolama sınıfları](../c-language/c-storage-classes.md). Ancak, değişkenlerin ve işlevlerin bildirilen dış düzeyi ile **statik** yalnızca bunların tanımlandığı kaynak dosyasında görünür depolama sınıfı tanımlayıcısı. Diğer tüm işlevleri genel olarak görülebilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Ömür, Kapsam, Görünürlük ve Bağlantı](../c-language/lifetime-scope-visibility-and-linkage.md)