---
description: 'Hakkında daha fazla bilgi edinin: no_namespace Import özniteliği'
title: no_namespace içeri aktarma özniteliği
ms.date: 08/29/2019
f1_keywords:
- no_namespace
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
ms.openlocfilehash: e1503015f455af65a138e4e3e6843fd0516d2773
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333311"
---
# <a name="no_namespace-import-attribute"></a>no_namespace içeri aktarma özniteliği

**C++ özel**

Derleyicinin ad alanı adı üretmediğini belirtir.

## <a name="syntax"></a>Syntax

> **#import** *türü-kitaplık* **no_namespace**

## <a name="remarks"></a>Açıklamalar

Üstbilgi dosyasındaki tür kitaplığı içerikleri `#import` normalde bir ad alanında tanımlanır. Ad alanı adı, `library` ORIJINAL IDL dosyasının bildiriminde belirtilir. **No_namespace** özniteliği belirtilmişse, bu ad alanı derleyici tarafından oluşturulmaz.

Farklı bir ad alanı adı kullanmak istiyorsanız bunun yerine [rename_namespace](../preprocessor/rename-namespace.md) özniteliğini kullanın.

**Son C++ özel**

## <a name="see-also"></a>Ayrıca bkz.

[#import öznitelikleri](../preprocessor/hash-import-attributes-cpp.md)\
[#import yönergesi](../preprocessor/hash-import-directive-cpp.md)
