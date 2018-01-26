---
title: "Derleyici COM desteği sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_raise_error
dev_langs: C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 54377893135c2b933c25387bccbb750d2f3eb734
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="compiler-com-support-classes"></a>Derleyici COM Desteği Sınıfları
**Microsoft Specific**  
  
 Standart sınıfları bazı COM türlerini desteklemek için kullanılır. Sınıfları tanımlanan \<comdef.h > ve tür kitaplığından oluşturulan üstbilgi dosyaları.  
  
|örneği|Amaç|  
|-----------|-------------|  
|[_bstr_t](../cpp/bstr-t-class.md)|Sarmalar `BSTR` türü yararlı operatörleri ve yöntemleri sağlar.|  
|[_com_error](../cpp/com-error-class.md)|Tarafından oluşturulan hata nesnesi tanımlar [_com_raise_error](../cpp/com-raise-error.md) çoğu hata içinde.|  
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|COM arabirimi işaretçileri yalıtır ve gerekli çağrıları otomatikleştirir `AddRef`, **sürüm**, ve `QueryInterface`.|  
|[_variant_t](../cpp/variant-t-class.md)|Sarmalar **değişken** türü yararlı operatörleri ve yöntemleri sağlar.|  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici COM desteği](../cpp/compiler-com-support.md)   
 [Derleyici Global COM işlevleri](../cpp/compiler-com-global-functions.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)