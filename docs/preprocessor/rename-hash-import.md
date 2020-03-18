---
title: İçeri aktarma özniteliğini yeniden adlandır
ms.date: 08/29/2019
helpviewer_keywords:
- rename attribute
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
ms.openlocfilehash: 520369f0308078fead2947e27a512f25a3ad3fab
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447489"
---
# <a name="rename-import-attribute"></a>İçeri aktarma özniteliğini yeniden adlandır

**C++Belirli**

Ad çakışma sorunları etrafında çalışmaktadır.

## <a name="syntax"></a>Sözdizimi

> **#import** *türü-kitaplık* **yeniden adlandırma (** "*OldName*" **,** "*YeniAd*" **)**

### <a name="parameters"></a>Parametreler

*OldName*\
Tür kitaplığındaki eski ad.

*Yeniad*\
Eski ad yerine kullanılacak ad.

## <a name="remarks"></a>Açıklamalar

**Rename** özniteliği belirtildiğinde, derleyici, *Type-Library* içindeki *OldName* öğesinin tüm oluşumlarını, sonuçta elde edilen üst bilgi dosyalarında Kullanıcı tarafından sağlanan *YeniAd* ile değiştirir.

**Yeniden Adlandır** özniteliği, tür kitaplığı 'ndaki bir ad, sistem üstbilgi dosyalarındaki bir makro tanımıyla saatle çakışan, kullanılabilir. Bu durum çözümlenmemişse, derleyici [derleyici hatası C2059](../error-messages/compiler-errors-1/compiler-error-c2059.md) ve [derleyici hatası C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md)gibi çeşitli sözdizimi hataları verebilir.

> [!NOTE]
> Değişiklik, sonuç üst bilgi dosyasında kullanılan bir ad için değil tür kitaplığında kullanılan bir addır.

Örneğin, `MyParent` adlı bir özelliğin tür kitaplığında var olduğunu ve bir makro `GetMyParent` bir başlık dosyasında tanımlandığını ve `#import`önce kullanıldığını varsayın. `GetMyParent`, hata işleme `get` özelliği için bir sarmalayıcı işlevinin varsayılan adı olduğundan, bir ad çakışması meydana gelir. Sorunu geçici olarak çözmek için `#import` deyimindeki aşağıdaki özniteliği kullanın:

```cpp
#import MyTypeLib.tlb rename("MyParent","MyParentX")
```

Bu, tür kitaplığındaki `MyParent` adı yeniden adlandırır. `GetMyParent` sarmalayıcı adını yeniden adlandırma girişimi başarısız olur:

```cpp
#import MyTypeLib.tlb rename("GetMyParent","GetMyParentX")
```

Bunun nedeni `GetMyParent` adı yalnızca elde edilen tür kitaplığı üst bilgi dosyasında gerçekleştiğinden oluşur.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
