---
title: Dil anahtar sözcükleri (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keywords [C++]
ms.assetid: 021013b2-70ac-4df9-aa77-4af1c67a1a67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0b9deb25e203ea805b1430b2ec8e56f17a50123b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445444"
---
# <a name="language-keywords-ccli"></a>Dil Anahtar Sözcükleri (C++/CLI)

Yönetilen Uzantılar'dan C++ için Visual C++ için değiştirildi. birden çok dil anahtar sözcükleri.

Yeni Visual C++ söz diziminde tüm anahtar sözcükler önekten olarak çift alt çizgi kaldırılır (bir özel durum: `__identifier` tutulur). Örneğin, bir özelliği artık olarak bildirilir `property`değil `__property`.

Yönetilen Uzantılar ' çift alt çizgi önekini kullanarak iki birincil nedeni vardı:

- Bu yerel uzantılara ISO C++ standardı ile sağlama uyumlu yöntemdir. Yeni anahtar sözcükleri ve belirteçleri gibi standart dil uyumsuzluklar İstemediğimiz için Yönetilen Uzantılar tasarım işleminin birincil amacı, oldu. Bu nedenle, yönetilen başvuru türündeki nesnelerin bildirimi için işaretçi sözdizimi seçimi motive büyük bölümü içindeydi.

- Kılması dışında çift alt çizgi kullanımı, aynı zamanda müdahaleci dil kullanıcılar var olan kod tabanı ile olma makul bir garanti sağlar. Bu Yönetilen Uzantılar tasarımı ikinci birincil amacı değildi.

Çift alt çizgi kaldırma artma Microsoft uyumlu olmak için kaydedilmiş kalır. Ancak, yeni ve güçlü bir programlama modelini CLR dinamik Nesne modelini gösteren için destek. Bu yeni paradigma desteği, kendi üst düzey anahtar sözcükleri ve belirteçleri gerektirir. Tümleştirip standart dili destekleyen bu yeni paradigma birinci sınıf bir ifade sağlamanız amaçladık. Yeni sözdizimi tasarımı, bu iki farklı nesne modeli, birinci sınıf bir programlama deneyimi sağlar.

Benzer şekilde, bu yeni dil anahtar sözcükleri müdahaleci yapısını en üst düzeye ile ilgili duyuyoruz. Bu bağlamsal ve boşluklu anahtar sözcüklerin kullanımı ile gerçekleştirilir. Gerçek yeni dil sözdizimine baktığımızda önce bu iki özel anahtar sözcüğü özellikleri anlamlı deneyelim.

Bağlamsal anahtar sözcük belirli bir programı bağlamları içinde özel bir anlamı vardır. Genel programda, örneğin, `sealed` normal bir tanımlayıcı olarak kabul edilir. Ancak, bir yönetilen başvuru sınıfı türü bildirimi bölümü içinde ortaya çıktığında, bir anahtar sözcüğü, sınıf bildirimi bağlamında olarak kabul edilir. Bu en aza indirir dilde yeni bir anahtar sözcüğü bir şey ile tanışın olası bozucu etkisi, varolan bir kod tabanına sahip kullanıcılar için çok önemli olduğunu düşünüyor. Aynı anda ek dil özelliği - Yönetilen Uzantılar'ile mümkün olmayan bir şey için birinci sınıf bir deneyim sağlamak kullanıcıların yeni işlevleri sağlar. İlişkin bir örnek için `sealed` kullanılan bkz [bir yönetilen sınıf türü bildirimi](../dotnet/declaration-of-a-managed-class-type.md).

Boşluklu anahtar sözcüğü gibi `value class`, bağlamsal anahtar sözcüğü, özel bir durumdur. Bir boşluk ile ayrılan bağlamsal bir değiştiricisi var olan bir anahtar çiftlerini. Çifti tek bir birim yerine iki ayrı anahtar olarak kabul edilir.

## <a name="see-also"></a>Ayrıca Bkz.

[C++/CLI Geçiş Öncüsü](../dotnet/cpp-cli-migration-primer.md)<br/>
[Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)