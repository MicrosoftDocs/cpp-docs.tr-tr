---
description: 'Daha fazla bilgi edinin: içeri aktarma özniteliğini yeniden adlandırma'
title: İçeri aktarma özniteliğini yeniden adlandır
ms.date: 08/29/2019
helpviewer_keywords:
- rename attribute
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
ms.openlocfilehash: 3003300887dadbab5cf05396ff3fa38b6dd29026
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176606"
---
# <a name="rename-import-attribute"></a>İçeri aktarma özniteliğini yeniden adlandır

**C++ özel**

Ad çakışma sorunları etrafında çalışmaktadır.

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **yeniden adlandırma (** "*OldName*" **,** "*YeniAd*" **)**

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

Örneğin, `MyParent` bir tür kitaplığı içinde adlı bir özelliğin var olduğunu ve bir makronun bir `GetMyParent` başlık dosyasında tanımlandığını ve daha önce kullanıldığını varsayalım `#import` . , `GetMyParent` Hata işleme özelliği için bir sarmalayıcı işlevinin varsayılan adı olduğundan `get` , bir ad çakışması meydana gelir. Sorunu geçici olarak çözmek için, bildiriminde aşağıdaki özniteliği kullanın `#import` :

```cpp
#import MyTypeLib.tlb rename("MyParent","MyParentX")
```

tür kitaplığındaki adı yeniden adlandırır `MyParent` . Sarmalayıcı adını yeniden adlandırma girişimi `GetMyParent` başarısız olur:

```cpp
#import MyTypeLib.tlb rename("GetMyParent","GetMyParentX")
```

Bunun nedeni, adın `GetMyParent` yalnızca ortaya çıkan tür kitaplığı üst bilgi dosyasında gerçekleşmesinden kaynaklanır.

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
