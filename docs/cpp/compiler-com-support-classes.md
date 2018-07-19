---
title: Derleyici COM desteği sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eba4ae92f9db67dfff58ec111b294b6cd26eff5a
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939825"
---
# <a name="compiler-com-support-classes"></a>Derleyici COM Desteği Sınıfları
**Microsoft'a özgü**  
  
 Standart sınıfları, COM türlerinin bazılarını desteklemek için kullanılır. Sınıfları, şurada tanımlanan \<comdef.h > ve tür kitaplığından oluşturulan üst bilgi dosyaları.  
  
|örneği|Amaç|  
|-----------|-------------|  
|[_bstr_t](../cpp/bstr-t-class.md)|Sarmalar `BSTR` yararlı işleçler ve yöntemler sağlamak için türü.|  
|[_com_error](../cpp/com-error-class.md)|Tarafından oluşturulan hata nesnesi tanımlar [_com_raise_error](../cpp/com-raise-error.md) içinde çoğu hata.|  
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|COM arabirim işaretçilerini kapsayan ve gerekli çağrıları otomatikleştirir `AddRef`, `Release`, ve `QueryInterface`.|  
|[_variant_t](../cpp/variant-t-class.md)|Sarmalar `VARIANT` yararlı işleçler ve yöntemler sağlamak için türü.|  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici COM desteği](../cpp/compiler-com-support.md)   
 [Derleyici Global COM işlevleri](../cpp/compiler-com-global-functions.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)