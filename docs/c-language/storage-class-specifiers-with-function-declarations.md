---
title: İşlev bildirimli depolama sınıfı tanımlayıcıları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function specifiers, storage class
- declaring functions, specifiers
- external declarations
- specifiers, function
- external linkage, function declarations
- external linkage, storage-class specifiers
ms.assetid: 801d7df2-efa9-4924-a725-274a5654cfd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8816ac8917281ed19dfc1afe9e12d302a3423f74
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111413"
---
# <a name="storage-class-specifiers-with-function-declarations"></a>İşlev Bildirimli Depolama Sınıfı Tanımlayıcıları

Kullanabilirsiniz **statik** veya `extern` işlev bildirimleri depolama sınıfı belirticisini. İşlevlerin her zaman genel kullanım ömürleri vardır.

**Microsoft'a özgü**

İç düzeydeki işlev bildirimleri, dış düzeydeki işlev bildirimleri ile aynı anlama sahiptir. Bu, yerel kapsamda bildirilmiş olsa bile bir işlevin, çeviri biriminin geri kalanında, bildirim noktasında görülebilir olması anlamına gelir.

**END Microsoft özgü**

İşlevler için görünürlük kuralları, aşağıdaki belirtildiği gibi değişkenlerle ilgili kurallara göre biraz farklıdır:

- Olarak bildirilen bir işlev **statik** içinde tanımlanmış olduğu yalnızca kaynak dosyasında görülebilir. Aynı kaynak dosyasındaki işlevler çağırabilir **statik** işlevi, ancak diğer kaynak dosyalarındaki işlevleri erişemez, doğrudan adını kullanarak. Başka bir bildirebilirsiniz **statik** işlevi çakışma olmadan farklı kaynak dosyada aynı ada sahip.

- Olarak bildirilen işlevlerin `extern` programdaki tüm kaynak dosyaları boyunca görünürdür (böyle bir işlevi olarak yeniden bildirmek sürece **statik**). Herhangi bir işlev `extern` işlevini çağırabilir.

- Depolama sınıfı belirticisini atlayan işlev bildirimleri varsayılan olarak `extern`'dir.

**Microsoft'a özgü**

Microsoft şemadaki sağlayan bir `extern` tanımlayıcı olarak **statik**.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[C Depolama Sınıfları](../c-language/c-storage-classes.md)