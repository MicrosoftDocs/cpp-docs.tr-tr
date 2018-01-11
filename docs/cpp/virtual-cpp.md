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
ms.workload: cplusplus
ms.openlocfilehash: 041939197f18861d27d1f99708e27415de2b7787
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)