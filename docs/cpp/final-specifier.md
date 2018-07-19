---
title: final tanımlayıcısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- final_CPP
dev_langs:
- C++
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 594bc432cb12b63c76172b06ee078d5b0f72de55
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948003"
---
# <a name="final-specifier"></a>final Tanımlayıcısı
Kullanabileceğiniz **son** türetilen bir sınıfta geçersiz kılınmış sanal işlevler atamak için anahtar sözcüğü. Ayrıca devralınamaz sınıflar aramak için de onu kullanabilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
function-declaration final;  
class class-name final base-classes  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Son** duyarlıdır ve bir işlev bildiriminden sonra ya da sınıf adı; Aksi takdirde, ayrılmış bir anahtar sözcük değil yalnızca özel bir anlamı vardır.  
  
 Zaman **son** sınıf bildirimlerinde kullanılır `base-classes` bildirimi isteğe bağlı bir parçasıdır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte **son** anahtar sözcüğü, bir sanal işlevi geçersiz kılınamaz belirtmek için.  
  
```cpp  
class BaseClass  
{  
    virtual void func() final;  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void func(); // compiler error: attempting to   
                         // override a final function  
};  
```  
  
 Üye işlevlerinin geçersiz kılınabileceğini belirtme hakkında daha fazla bilgi için bkz: [geçersiz kılma belirticisi](../cpp/override-specifier.md).  
  
 Sonraki örnekte **son** anahtar sözcüğü bir sınıfın devralınamayacağını belirtmek için.  
  
```cpp  
class BaseClass final   
{  
};  
  
class DerivedClass: public BaseClass // compiler error: BaseClass is   
                                     // marked as non-inheritable  
{  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [override Tanımlayıcısı](../cpp/override-specifier.md)