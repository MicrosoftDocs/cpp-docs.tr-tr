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
ms.openlocfilehash: 82fb9e13fc5dbbafcc37905716a37322b2966c6d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="final-specifier"></a>final Tanımlayıcısı
Türetilmiş bir sınıfta geçersiz kılınamayan sanal işlevler atamak için `final` anahtar sözcüğünü kullanabilirsiniz. Ayrıca devralınamaz sınıflar aramak için de onu kullanabilirsiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
function-declaration final;  
```  
  
```  
  
class class-name final base-classes  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `final` bağlama duyarlıdır ve yalnızca bir işlev bildiriminden veya sınıf adından sonra kullanıldığında özel anlamı olur; aksi takdirde, ayrılmış bir anahtar sözcük değildir.  
  
 `final` sınıf bildirimlerinde kullanıldığı zaman; `base-classes`, bildirimin isteğe bağlı bir parçasıdır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, sanal işlevin geçersiz kılınamayacağını belirtmek için `final` anahtar sözcüğü kullanılmaktadır.  
  
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
  
 Üye işlevlerini geçersiz kılınabilir belirtme hakkında daha fazla bilgi için bkz: [override tanımlayıcısı](../cpp/override-specifier.md).  
  
 Sonraki örnekte, bir sınıfın devralınamayacağını belirtmek için `final` anahtar sözcüğü kullanılmıştır.  
  
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
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [override Tanımlayıcısı](../cpp/override-specifier.md)