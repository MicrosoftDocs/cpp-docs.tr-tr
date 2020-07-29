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
ms.openlocfilehash: e27cc6ac748c0af3063dbc5b608114761da8b7dc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211703"
---
# <a name="storage-class-specifiers-with-function-declarations"></a>İşlev Bildirimli Depolama Sınıfı Tanımlayıcıları

**`static`** **`extern`** İşlev bildirimlerinde ya da depolama sınıfı belirticisini kullanabilirsiniz. İşlevlerin her zaman genel kullanım ömürleri vardır.

**Microsoft'a Özgü**

İç düzeydeki işlev bildirimleri, dış düzeydeki işlev bildirimleri ile aynı anlama sahiptir. Bu, yerel kapsamda bildirilmiş olsa bile bir işlevin, çeviri biriminin geri kalanında, bildirim noktasında görülebilir olması anlamına gelir.

**SON Microsoft 'a özgü**

İşlevler için görünürlük kuralları, aşağıdaki belirtildiği gibi değişkenlerle ilgili kurallara göre biraz farklıdır:

- Olarak belirtilen bir işlev, **`static`** yalnızca tanımlandığı kaynak dosya içinde görünür. Aynı kaynak dosyasındaki işlevler **`static`** işlevi çağırabilir, ancak diğer kaynak dosyalardaki işlevler doğrudan adına göre erişemez. **`static`** Çakışma olmadan farklı bir kaynak dosyasında aynı ada sahip başka bir işlev bildirebilirsiniz.

- Olarak belirtilen işlevler **`extern`** , programdaki tüm kaynak dosyaları boyunca görünür (daha sonra böyle bir işlevi olarak yeniden bildirmediğiniz sürece **`static`** ). Herhangi bir işlev, bir **`extern`** işlevi çağırabilir.

- Depolama sınıfı belirticisini atlayan işlev bildirimleri **`extern`** Varsayılan olarak ' dir.

**Microsoft'a Özgü**

Microsoft, bir tanımlayıcının olarak yeniden tanımlanması sağlar **`extern`** **`static`** .

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Depolama sınıfları](../c-language/c-storage-classes.md)
