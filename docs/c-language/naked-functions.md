---
title: Naked işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- naked functions
- functions [C++], naked
- prolog code
- epilog code
ms.assetid: 2543c8af-00d4-4a2a-8a87-e746da1f9929
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 134584ed1acd502ecbf74fe755850761df8c08e1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061493"
---
# <a name="naked-functions"></a>Naked İşlevleri

**Microsoft'a özgü**

`naked` depolama sınıfı özniteliği, C diline yönelik Microsoft'a özgü bir uzantıdır. `naked` depolama sınıfı özniteliğiyle bildirilen işlevler için derleyici giriş ve sonuç kodu olmadan kod oluşturur. Satır içi derleyici kodunu kullanarak kendi giriş/sonuç kodu dizilerinizi yazmak için bu özelliği kullanabilirsiniz. Çıplak işlevler, özellikle sanal cihaz sürücülerinin yazılmasında yararlıdır.

Çünkü `naked` özniteliği yalnızca bir işlev tanımı için geçerlidir ve bir tür değiştiricisi değil, naked işlevlerini kullanmak açıklanan genişletilmiş öznitelik söz dizimi [genişletilmiş depolama sınıfı öznitelikleri](../c-language/c-extended-storage-class-attributes.md).

Aşağıdaki örnekte, `naked` özniteliğine sahip bir işlev tanımlanmaktadır:

```
__declspec( naked ) int func( formal_parameters )
{
   /* Function body */
}
```

Veya alternatif olarak:

```
#define Naked   __declspec( naked )

Naked int func( formal_parameters )
{
   /* Function body */
}
```

`naked` özniteliği, yalnızca işlevin giriş ve sonuç dizileri için derleyicinin kod oluşturma yapısını etkiler. Bu tür işlevleri çağırmak için oluşturulan kodu etkilemez. Bu nedenle, `naked` özniteliği işlev türünün bir parçası olarak kabul edilmez ve işlev işaretçileri `naked` özniteliğine sahip olamaz. Ayrıca, `naked` özniteliği veri tanımına uygulanamaz. Örneğin, aşağıdaki kod hatalar oluşturur:

```
__declspec( naked ) int i;  /* Error--naked attribute not */
                            /* permitted on data declarations. */
```

`naked` özniteliği, yalnızca işlevin tanımıyla ilgilidir ve işlevin prototipinde belirtilemez. Aşağıdaki bildirim, bir derleyici hatası oluşturur:

```
__declspec( naked ) int func();   /* Error--naked attribute not */
                     /* permitted on function declarations.    */   \
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[C İşlev Tanımları](../c-language/c-function-definitions.md)