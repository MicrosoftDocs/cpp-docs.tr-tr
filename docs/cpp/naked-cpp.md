---
title: naked (C++)
ms.date: 11/04/2016
f1_keywords:
- naked_cpp
helpviewer_keywords:
- __declspec keyword [C++], naked
- naked __declspec keyword
ms.assetid: 69723241-05e1-439b-868e-20a83a16ab6d
ms.openlocfilehash: 951760d7f9566c084bbe3d5a574d006020576c61
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478383"
---
# <a name="naked-c"></a>naked (C++)

**Microsoft'a özgü**

Bildirilen işlevler **naked** özniteliği, derleyici giriş ve sonuç kodu olmadan kod oluşturur. Satır içi derleyici kodunu kullanarak kendi giriş/sonuç kodu dizilerinizi yazmak için bu özelliği kullanabilirsiniz. Çıplak işlevler, özellikle sanal cihaz sürücülerinin yazılmasında yararlıdır.  Unutmayın **naked** özniteliği yalnızca x86 ve ARM geçerlidir ve x64 üzerinde kullanılabilir değil.

## <a name="syntax"></a>Sözdizimi

```
__declspec(naked) declarator
```

## <a name="remarks"></a>Açıklamalar

Çünkü **naked** özniteliği yalnızca bir işlev tanımı için geçerlidir ve bir tür değiştiricisi değil, naked işlevleri, genişletilmiş öznitelik söz dizimi kullanmalıdır ve [__declspec](../cpp/declspec.md) anahtar sözcüğü.

İşlev ayrıca ile işaretlenmiş olsa bile derleyici, çıplak özniteliği ile işaretlenmiş bir işlevin satır içi işlev oluşturulamıyor [__forceinline](inline-functions-cpp.md) anahtar sözcüğü.

Varsa derleyici bir hata verir **naked** öznitelik, bir üye olmayan yöntem tanımının dışında her şey için uygulanır.

## <a name="examples"></a>Örnekler

Bu kod, bir işlev ile tanımlar **naked** özniteliği:

```
__declspec( naked ) int func( formal_parameters ) {}
```

Veya alternatif olarak:

```
#define Naked __declspec( naked )
Naked int func( formal_parameters ) {}
```

**Naked** özniteliği, yalnızca işlevin giriş ve sonuç dizileri için derleyicinin kod oluşturma yapısını etkiler. Bu tür işlevleri çağırmak için oluşturulan kodu etkilemez. Bu nedenle, **naked** özniteliği işlev türünün bir parçası değil değerlendirilir ve işlev işaretçileri olamaz **naked** özniteliği. Ayrıca, **naked** özniteliği veri tanımına uygulanamaz. Örneğin, bu kod örneği, bir hata oluşturur:

```
__declspec( naked ) int i;
// Error--naked attribute not permitted on data declarations.
```

**Naked** özniteliği yalnızca işlevin tanımıyla ilgilidir ve işlevin prototipinde belirtilemez. Örneğin, bu bildirim, bir derleyici hatası oluşturur:

```
__declspec( naked ) int func();  // Error--naked attribute not permitted on function declarations
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[Naked İşlevi Çağrıları](../cpp/naked-function-calls.md)