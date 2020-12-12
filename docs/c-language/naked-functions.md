---
description: 'Daha fazla bilgi edinin: Naked Işlevleri'
title: Naked İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- naked functions
- functions [C++], naked
- prolog code
- epilog code
ms.assetid: 2543c8af-00d4-4a2a-8a87-e746da1f9929
ms.openlocfilehash: 1cea9bf2497a14bc7007f97b2c3db68eafc15059
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243360"
---
# <a name="naked-functions"></a>Naked İşlevleri

**Microsoft'a Özgü**

`naked` depolama sınıfı özniteliği, C diline yönelik Microsoft'a özgü bir uzantıdır. `naked` depolama sınıfı özniteliğiyle bildirilen işlevler için derleyici giriş ve sonuç kodu olmadan kod oluşturur. Satır içi derleyici kodunu kullanarak kendi giriş/sonuç kodu dizilerinizi yazmak için bu özelliği kullanabilirsiniz. Çıplak işlevler, özellikle sanal cihaz sürücülerinin yazılmasında yararlıdır.

`naked`Özniteliği yalnızca bir işlevin tanımına uygun olduğundan ve bir tür değiştiricisi olmadığından, naked Işlevleri [genişletilmiş Storage-Class özniteliklerde](../c-language/c-extended-storage-class-attributes.md)açıklanan genişletilmiş öznitelik sözdizimini kullanır.

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

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Işlev tanımları](../c-language/c-function-definitions.md)
