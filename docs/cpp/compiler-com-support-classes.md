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
ms.openlocfilehash: 0e2ec9f0814c976a5ea175e0cd62ab8e57b02f1c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-com-support-classes"></a>Derleyici COM Desteği Sınıfları
**Microsoft özel**  
  
 Standart sınıfları bazı COM türlerini desteklemek için kullanılır. Sınıflar comdef.h içinde tanımlanır ve başlık dosyaları tür kitaplığından oluşturulur.  
  
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