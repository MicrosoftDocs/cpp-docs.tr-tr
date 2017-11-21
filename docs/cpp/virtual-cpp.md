---
title: Sanal (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- virtual_cpp
- virtual
dev_langs: C++
helpviewer_keywords:
- virtual base classes [C++], declaring
- base classes [C++], virtual
- virtual functions [C++], declaring
- virtual keyword [C++]
ms.assetid: c2eb987d-6cf3-43b6-aa0c-29a6f561b1ae
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f8d029ce5a75da7c3c5642912c3d2a418183eee0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="virtual-c"></a>virtual (C++)
`virtual` Anahtar sözcüğü bir sanal işlev veya sanal bir temel sınıf bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
virtual [type-specifiers] member-function-declarator  
virtual [access-specifier] base-class-name  
```  
  
#### <a name="parameters"></a>Parametreler  
 `type-specifiers`  
 Sanal üye işlevi dönüş türünü belirtir.  
  
 `member-function-declarator`  
 Üye işlevi bildirir.  
  
 `access-specifier`  
 Taban sınıfı için erişim düzeyini tanımlayan `public`, `protected` veya `private`. Önce veya sonra görünebilir `virtual` anahtar sözcüğü.  
  
 `base-class-name`  
 Daha önce bildirilen sınıf türü tanımlar.  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [sanal işlevler](../cpp/virtual-functions.md) daha fazla bilgi için.  
  
 Ayrıca bkz. aşağıdaki anahtar sözcükler: [sınıfı](../cpp/class-cpp.md), [özel](../cpp/private-cpp.md), [ortak](../cpp/public-cpp.md), ve [korumalı](../cpp/protected-cpp.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../cpp/keywords-cpp.md)