---
title: rename (#import)
ms.date: 10/18/2018
f1_keywords:
- Rename
helpviewer_keywords:
- rename attribute
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
ms.openlocfilehash: 15673a8b9ebaf298ae1b2b45c9a76a1691e681b1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514198"
---
# <a name="rename-import"></a>Yeniden Adlandır (\#içeri aktarma)

**C++ özgü**

Ad çakışması sorunlarını geçici olarak çalışır.

## <a name="syntax"></a>Sözdizimi

```
rename("OldName","NewName")
```

### <a name="parameters"></a>Parametreler

*OldName*<br/>
Eski tür kitaplığı adı.

*Yeni ad*<br/>
Eski adı yerine kullanılacak adı.

## <a name="remarks"></a>Açıklamalar

Bu öznitelik belirtilmezse, derleyici tüm oluşumlarını değiştirir *OldName* kullanıcı tarafından sağlanan ile bir tür kitaplığındaki *NewName* elde edilen üstbilgi dosyalarında.

Bu öznitelik, bir tür kitaplığı adı bir sistem üst bilgi dosyaları Makro tanımında ile örtüşür olduğunda kullanılabilir. Bu durum çözümlenmedi sonra çeşitli söz dizimi hatalarını, gibi oluşturulacak [derleyici hatası C2059](../error-messages/compiler-errors-1/compiler-error-c2059.md) ve [derleyici hatası C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md).

> [!NOTE]
> Sonuçta elde edilen üstbilgi dosyasında kullanılan bir ad tür kitaplığındaki kullanılan adı yerini almaktadır.

Örneğin, adında bir özellik varsayalım `MyParent` bir tür kitaplığı ve makro var. `GetMyParent` üstbilgi dosyasında tanımlanır ve önce kullanılan `#import`. Bu yana `GetMyParent` bir sarmalayıcı işlevi hata işleme için varsayılan adı `get` özelliği, bir ad çakışması gerçekleşir. Sorunu çözmek için şu özniteliği kullanın. `#import` deyimi:

```cpp
rename("MyParent","MyParentX")
```

adı yeniden adlandırır `MyParent` tür kitaplığında. Yeniden adlandırma denemesi `GetMyParent` sarmalayıcı adı başarısız olur:

```cpp
rename("GetMyParent","GetMyParentX")
```

Bunun nedeni, adı `GetMyParent` yalnızca elde edilen tür kitaplığı üstbilgi dosyası oluşur.

**END C++ özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)