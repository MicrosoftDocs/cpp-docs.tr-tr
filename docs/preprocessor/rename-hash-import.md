---
title: İçeri aktarma özniteliğini yeniden adlandır
ms.date: 08/29/2019
f1_keywords:
- Rename
helpviewer_keywords:
- rename attribute
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
ms.openlocfilehash: ef1f64e0c268f850899efe499f7b1ad3991dd570
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216668"
---
# <a name="rename-import-attribute"></a>İçeri aktarma özniteliğini yeniden adlandır

**C++Belirli**

Ad çakışma sorunları etrafında çalışmaktadır.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **yeniden adlandır (** "*OldName*" **,** "*YeniAd*" **)**

### <a name="parameters"></a>Parametreler

*OldName*\
Tür kitaplığındaki eski ad.

*Ad*\
Eski ad yerine kullanılacak ad.

## <a name="remarks"></a>Açıklamalar

**Rename** özniteliği belirtildiğinde, derleyici, *Type-Library* içindeki *OldName* öğesinin tüm oluşumlarını, sonuçta elde edilen üst bilgi dosyalarında Kullanıcı tarafından sağlanan *YeniAd* ile değiştirir.

**Yeniden Adlandır** özniteliği, tür kitaplığı 'ndaki bir ad, sistem üstbilgi dosyalarındaki bir makro tanımıyla saatle çakışan, kullanılabilir. Bu durum çözümlenmemişse, derleyici [derleyici hatası C2059](../error-messages/compiler-errors-1/compiler-error-c2059.md) ve [derleyici hatası C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md)gibi çeşitli sözdizimi hataları verebilir.

> [!NOTE]
> Değişiklik, sonuç üst bilgi dosyasında kullanılan bir ad için değil tür kitaplığında kullanılan bir addır.

Örneğin, bir tür kitaplığı içinde adlı `MyParent` bir özelliğin var olduğunu ve bir makronun `GetMyParent` bir başlık dosyasında tanımlandığını ve daha önce `#import`kullanıldığını varsayalım. , Hata işleme `get` özelliği için bir sarmalayıcı işlevinin varsayılan adı olduğundan,biradçakışmasımeydanagelir.`GetMyParent` Sorunu geçici olarak çözmek için, `#import` bildiriminde aşağıdaki özniteliği kullanın:

```cpp
#import MyTypeLib.tlb rename("MyParent","MyParentX")
```

tür kitaplığındaki adı `MyParent` yeniden adlandırır. `GetMyParent` Sarmalayıcı adını yeniden adlandırma girişimi başarısız olur:

```cpp
#import MyTypeLib.tlb rename("GetMyParent","GetMyParentX")
```

Bunun nedeni, adın `GetMyParent` yalnızca ortaya çıkan tür kitaplığı üst bilgi dosyasında gerçekleşmesinden kaynaklanır.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
