---
title: İşlev Bildirimli Depolama Sınıfı Tanımlayıcıları
ms.date: 11/04/2016
helpviewer_keywords:
- function specifiers, storage class
- declaring functions, specifiers
- external declarations
- specifiers, function
- external linkage, function declarations
- external linkage, storage-class specifiers
ms.assetid: 801d7df2-efa9-4924-a725-274a5654cfd4
ms.openlocfilehash: 69d6fa2b17523f2bb4068cd05a11265d91750021
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157889"
---
# <a name="storage-class-specifiers-with-function-declarations"></a>İşlev Bildirimli Depolama Sınıfı Tanımlayıcıları

İşlev bildirimlerinde **statik** veya `extern` depolama sınıfı belirticisini kullanabilirsiniz. İşlevlerin her zaman genel kullanım ömürleri vardır.

**Microsoft'a Özgü**

İç düzeydeki işlev bildirimleri, dış düzeydeki işlev bildirimleri ile aynı anlama sahiptir. Bu, yerel kapsamda bildirilmiş olsa bile bir işlevin, çeviri biriminin geri kalanında, bildirim noktasında görülebilir olması anlamına gelir.

**SON Microsoft 'a özgü**

İşlevler için görünürlük kuralları, aşağıdaki belirtildiği gibi değişkenlerle ilgili kurallara göre biraz farklıdır:

- **Statik** olarak belirtilen bir işlev, yalnızca tanımlandığı kaynak dosya içinde görünür. Aynı kaynak dosyasındaki işlevler **statik** işlevi çağırabilir, ancak diğer kaynak dosyalardaki işlevler doğrudan adına göre erişemez. Çakışma olmadan farklı bir kaynak dosyasında aynı ada sahip başka bir **statik** işlev bildirebilirsiniz.

- Olarak `extern` belirtilen işlevler, programdaki tüm kaynak dosyaları boyunca görünür (daha sonra bu tür bir işlevi **statik**olarak yeniden bildirmediğiniz sürece). Herhangi bir işlev `extern` işlevini çağırabilir.

- Depolama sınıfı belirticisini atlayan işlev bildirimleri varsayılan olarak `extern`'dir.

**Microsoft'a Özgü**

Microsoft bir `extern` tanımlayıcının **statik**olarak yeniden tanımlanması sağlar.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Depolama Sınıfları](../c-language/c-storage-classes.md)
