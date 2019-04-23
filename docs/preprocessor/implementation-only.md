---
title: implementation_only
ms.date: 11/04/2016
f1_keywords:
- implementation_only
helpviewer_keywords:
- implementation_only attribute
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
ms.openlocfilehash: c1435ca74ac2b5a73c308592b1affe6fca097d1b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026662"
---
# <a name="implementationonly"></a>implementation_only
**C++ özgü**

.Tlh üst bilgi dosyası (birincil üstbilgi dosyası) oluşturulmasını engeller.

## <a name="syntax"></a>Sözdizimi

```
implementation_only
```

## <a name="remarks"></a>Açıklamalar

Bu dosya, tür kitaplığı içeriğini göstermek için kullanılan tüm bildirimleri içerir. .TLI üstbilgi dosyası uygulamaları kapsayıcı üye işlevleri ile oluşturulan ve derlemeye dahil.

Bu öznitelik belirtildiğinde .tli üstbilgisinin .tlh üstbilgisinde normalde kullanılan ile aynı ad alanında içeriktir. Ayrıca, üye işlevleri satır içi olarak bildirilmedi.

**İmplementation_only** özniteliği ile birlikte kullanılmak için tasarlanmıştır [no_implementation](../preprocessor/no-implementation.md) uygulamaları (PCH) önceden derlenmiş üst bilgi dosyasının dışında tutma bir yolu olarak özniteliği. Bir `#import` deyimiyle `no_implementation` özniteliği PCH oluşturmak için kullanılan kaynak bölgede yerleştirilir. Sonuçta elde edilen PCH sayıda kaynak dosya tarafından kullanılır. Bir `#import` deyimiyle **implementation_only** özniteliği PCH bölgelerin dışına taşımaz kullanılır. Bu bildirimi yalnızca bir kez kaynak dosyalarından birini kullanmak için gerekli değildir. Bu ek gerekmeksizin her kaynak dosyası için tüm gerekli kapsayıcı üye işlevleri oluşturur.

> [!NOTE]
> **İmplementation_only** bir öznitelik `#import` kullanılmak üzere başka bir deyim olmalıdır `#import` deyimi, aynı tür kitaplığı `no_implementation` özniteliği. Aksi halde, derleyici hatalar oluşturulur. Sarmalayıcı sınıf tanımları tarafından oluşturulan olmasıdır `#import` deyimiyle `no_implementation` tarafından oluşturulan uygulamaları derlemek için gerekli özniteliği **implementation_only** özniteliği.

**END C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)