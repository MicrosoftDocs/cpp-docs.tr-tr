---
title: naked (C++)
ms.date: 11/04/2016
f1_keywords:
- naked_cpp
helpviewer_keywords:
- __declspec keyword [C++], naked
- naked __declspec keyword
ms.assetid: 69723241-05e1-439b-868e-20a83a16ab6d
ms.openlocfilehash: cfe3631086515e4e31c7d4188d46e3a7440662b7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177956"
---
# <a name="naked-c"></a>naked (C++)

**Microsoft 'a özgü**

**Naked** özniteliğiyle belirtilen işlevler için derleyici, giriş ve bitiş kodu olmadan kod oluşturur. Satır içi derleyici kodunu kullanarak kendi giriş/sonuç kodu dizilerinizi yazmak için bu özelliği kullanabilirsiniz. Çıplak işlevler, özellikle sanal cihaz sürücülerinin yazılmasında yararlıdır.  **Çıplak** özniteliğin yalnızca x86 ve ARM üzerinde geçerli olduğunu ve x64 üzerinde kullanılabilir olduğunu unutmayın.

## <a name="syntax"></a>Sözdizimi

```
__declspec(naked) declarator
```

## <a name="remarks"></a>Açıklamalar

**Naked** özniteliği yalnızca bir işlevin tanımına uygun olduğundan ve bir tür değiştiricisi olmadığından, naked işlevlerin genişletilmiş öznitelik sözdizimini ve [__declspec](../cpp/declspec.md) anahtar sözcüğünü kullanması gerekir.

Derleyici, [__forceinline](inline-functions-cpp.md) anahtar sözcüğüyle de işaretlenmiş olsa bile, bir işlev için naked özniteliğiyle işaretlenmiş bir satır içi işlev üretemiyor.

, **Naked** özniteliği üye olmayan bir yöntemin tanımı dışında bir şeye uygulanırsa derleyici bir hata verir.

## <a name="examples"></a>Örnekler

Bu kod, **çıplak** özniteliğe sahip bir işlevi tanımlar:

```
__declspec( naked ) int func( formal_parameters ) {}
```

Ya da alternatif olarak:

```
#define Naked __declspec( naked )
Naked int func( formal_parameters ) {}
```

**Naked** özniteliği, işlevin giriş ve bitiş dizileri için yalnızca derleyicinin kod üretimi yapısını etkiler. Bu tür işlevleri çağırmak için oluşturulan kodu etkilemez. Bu nedenle, **Naked** özniteliği işlevin türünün bir parçası olarak kabul edilmez ve işlev işaretçilerinin **çıplak** özniteliği olamaz. Ayrıca, **Naked** özniteliği bir veri tanımına uygulanamaz. Örneğin, bu kod örneği bir hata oluşturur:

```
__declspec( naked ) int i;
// Error--naked attribute not permitted on data declarations.
```

**Naked** özniteliği yalnızca işlevin tanımına uygundur ve işlevin prototipinizde belirtilemez. Örneğin, bu bildirim bir derleyici hatası oluşturur:

```
__declspec( naked ) int func();  // Error--naked attribute not permitted on function declarations
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[Naked İşlevi Çağrıları](../cpp/naked-function-calls.md)
