---
description: 'Daha fazla bilgi edinin: Naked (C++)'
title: naked (C++)
ms.date: 11/04/2016
f1_keywords:
- naked_cpp
helpviewer_keywords:
- __declspec keyword [C++], naked
- naked __declspec keyword
ms.assetid: 69723241-05e1-439b-868e-20a83a16ab6d
ms.openlocfilehash: 1f416f116d7d2a3179dc43545f1302fcd9c7d101
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313833"
---
# <a name="naked-c"></a>naked (C++)

**Microsoft'a Özgü**

Özniteliği ile belirtilen işlevler için **`naked`** derleyici, giriş ve bitiş kodu olmadan kod oluşturur. Satır içi derleyici kodunu kullanarak kendi giriş/sonuç kodu dizilerinizi yazmak için bu özelliği kullanabilirsiniz. Çıplak işlevler, özellikle sanal cihaz sürücülerinin yazılmasında yararlıdır.  **`naked`** Özniteliğinin yalnızca x86 ve ARM üzerinde geçerli olduğunu ve x64 üzerinde kullanılabilir olduğunu unutmayın.

## <a name="syntax"></a>Syntax

```
__declspec(naked) declarator
```

## <a name="remarks"></a>Açıklamalar

**`naked`** Özniteliği yalnızca bir işlevin tanımına uygun olduğundan ve bir tür değiştiricisi olmadığından, naked işlevlerin genişletilmiş öznitelik sözdizimini ve [__declspec](../cpp/declspec.md) anahtar sözcüğünü kullanması gerekir.

Derleyici, [__forceinline](inline-functions-cpp.md) anahtar sözcüğüyle de işaretlenmiş olsa bile, bir işlev için naked özniteliğiyle işaretlenmiş bir satır içi işlev üretemiyor.

**`naked`** Öznitelik üye olmayan bir yöntemin tanımı dışında bir şeye uygulanırsa derleyici bir hata verir.

## <a name="examples"></a>Örnekler

Bu kod, özniteliğine sahip bir işlevi tanımlar **`naked`** :

```
__declspec( naked ) int func( formal_parameters ) {}
```

Ya da alternatif olarak:

```
#define Naked __declspec( naked )
Naked int func( formal_parameters ) {}
```

**`naked`** Özniteliği, işlevin giriş ve bitiş dizileri için yalnızca derleyicinin kod üretimi yapısını etkiler. Bu tür işlevleri çağırmak için oluşturulan kodu etkilemez. Bu nedenle, **`naked`** öznitelik işlevin türünün bir parçası olarak kabul edilmez ve işlev işaretçilerinin **`naked`** özniteliği olamaz. Ayrıca, **`naked`** öznitelik bir veri tanımına uygulanamaz. Örneğin, bu kod örneği bir hata oluşturur:

```
__declspec( naked ) int i;
// Error--naked attribute not permitted on data declarations.
```

**`naked`** Özniteliği yalnızca işlevin tanımına uygundur ve işlevin prototipte belirtilemez. Örneğin, bu bildirim bir derleyici hatası oluşturur:

```
__declspec( naked ) int func();  // Error--naked attribute not permitted on function declarations
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[Naked Işlev çağrıları](../cpp/naked-function-calls.md)
