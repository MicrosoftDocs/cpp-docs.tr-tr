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
ms.openlocfilehash: 0ae9f772a68735555748e6edbeb6196f1a73d2c9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164524"
---
# <a name="typeof-goes-to-ttypeid"></a>typeof T::typeid'e gider
`typeof` C++ almıştır için Yönetilen Uzantılar'da kullanılan işleç `typeid` Visual C++'ta anahtar sözcüğü.  
  
 Yönetilen Uzantılar `__typeof()` işleci döndürür ilişkili `Type*` nesne bir yönetilen türü adı geçirildiğinde. Örneğin:  
  
```  
// Creates and initializes a new Array instance.  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 Yeni sözdiziminde `__typeof` ek bir form tarafından değiştirildiğini `typeid` döndüren bir `Type^` yönetilen tür belirtildiğinde.  
  
```  
// Creates and initializes a new Array instance.  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel dil değişiklikleri (C + +/ CLI)](../dotnet/general-language-changes-cpp-cli.md)   
 [TypeId](../windows/typeid-cpp-component-extensions.md)