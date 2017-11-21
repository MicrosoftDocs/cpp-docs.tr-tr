---
title: 'typeof t:: typeid''e gider | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- typeid operator
- __typeof keyword
- typeid keyword [C++]
ms.assetid: 6a0d35a7-7a1a-4070-b187-cff37cfdc205
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 90c75b67dc6496f51d335f83a49242b7f7ae0b29
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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