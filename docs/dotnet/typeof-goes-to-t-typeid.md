---
title: "typeof t:: typeid'e gider | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- typeid operator
- __typeof keyword
- typeid keyword [C++]
ms.assetid: 6a0d35a7-7a1a-4070-b187-cff37cfdc205
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4433061fceef455685b6588c81c8c2e434253433
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374687"
---
# <a name="typeof-goes-to-ttypeid"></a>typeof T::typeid'e gider

`typeof` C++ almıştır için Yönetilen Uzantılar'kullanılan işleci `typeid` Visual c++ anahtar sözcüğü.

Yönetilen Uzantılar `__typeof()` işleci ilişkili döndürür `Type*` nesnesi bir yönetilen türün adını geçirildiğinde. Örneğin:

```
// Creates and initializes a new Array instance.
Array* myIntArray =
   Array::CreateInstance( __typeof(Int32), 5 );
```

Yeni sözdiziminde `__typeof` ek bir tür tarafından değiştirilmiştir `typeid` döndüren bir `Type^` yönetilen türü belirtildiğinde.

```
// Creates and initializes a new Array instance.
Array^ myIntArray =
   Array::CreateInstance( Int32::typeid, 5 );
```

## <a name="see-also"></a>Ayrıca Bkz.

[Genel Dil Değişiklikleri (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)<br/>
[typeid](../windows/typeid-cpp-component-extensions.md)