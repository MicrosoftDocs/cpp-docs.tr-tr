---
title: uuid (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: uuid_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad4362b8e84d7ffb4bb090a4e513538cdb26ae25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="uuid-c"></a>uuid (C++)
**Microsoft özel**  
  
 Bir sınıf veya bildirilen veya tanımlı yapısı (tam COM nesne tanımları yalnızca) ile bir GUID derleyici iliştirir `uuid` özniteliği.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
__declspec( uuid("  
ComObjectGUID  
") ) declarator  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `uuid` Özniteliği bağımsız değişkeni olarak bir dize alır. Bu dize bir GUID ile veya olmadan normal kayıt biçiminde adları **{}** sınırlayıcısı. Örneğin:  
  
```  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;  
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;  
```  
  
 Bu öznitelik bir yeniden bildirimi uygulanabilir. Bu sistem başlıklarının arabirimleri gibi tanımlarınızı sağlar **IUnknown**ve (örneğin, COMDEF diğer bazı üstbilgisinde yeniden bildirimi. Y) GUID sağlamak için kullanılır.  
  
 Anahtar sözcüğü [__uuidof](../cpp/uuidof-operator.md) GUID bağlı kullanıcı tanımlı bir tür sabiti almak için uygulanabilir.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__declspec](../cpp/declspec.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)