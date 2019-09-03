---
title: no_namespace içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- no_namespace
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
ms.openlocfilehash: ba52aed69cdbb46c135e6de5078d718e93f99c87
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220730"
---
# <a name="no_namespace-import-attribute"></a>no_namespace içeri aktarma özniteliği

**C++Belirli**

Derleyicinin ad alanı adı üretmediğini belirtir.

## <a name="syntax"></a>Sözdizimi

> **#import** *tür kitaplığı* **no_namespace**

## <a name="remarks"></a>Açıklamalar

`#import` Üstbilgi dosyasındaki tür kitaplığı içerikleri normalde bir ad alanında tanımlanır. Ad alanı adı, orijinal IDL dosyasının `library` bildiriminde belirtilir. **No_namespace** özniteliği belirtilmişse, bu ad alanı derleyici tarafından oluşturulmaz.

Farklı bir ad alanı adı kullanmak istiyorsanız bunun yerine [rename_namespace](../preprocessor/rename-namespace.md) özniteliğini kullanın.

**SONA C++ özgü**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
