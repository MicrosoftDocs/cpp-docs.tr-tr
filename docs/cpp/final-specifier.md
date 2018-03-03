---
title: "final tanımlayıcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- final_CPP
dev_langs:
- C++
helpviewer_keywords:
- final Identifier
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a3f7c5afd4010983ea943193b7abfb99f22eda38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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