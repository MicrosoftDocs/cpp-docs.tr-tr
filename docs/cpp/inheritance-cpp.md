---
title: Devralma (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- derived classes [C++]
- derived classes [C++], about derived classes
- classes [C++], derived
ms.assetid: 3534ca19-d9ed-4a40-be1b-b921ad0e6956
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: decef38bc69ea2b9a45005627b984c1f240afe13
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="inheritance--c"></a>Devralma (C++)
Bu bölümde, genişletilebilir programlar oluşturmak için türetilmiş sınıfların nasıl kullanılacağı açıklanmaktadır.  
  
## <a name="overview"></a>Genel Bakış  
 Yeni sınıflar "devralma" adlı bir mekanizma kullanarak mevcut sınıflarından türetilmiş (bilgi başına bkz [tek devralma](../cpp/single-inheritance.md)). Türetme için kullanılan sınıflara belirli bir türetilmiş sınıfın "temel sınıflar" denir. Türetilmiş bir sınıf aşağıdaki sözdizimini kullanarak bildirilmiştir:  
  
```  
 class Derived : [virtual] [access-specifier] Base  
{  
   // member list  
};  
 class Derived : [virtual] [access-specifier] Base1,  
 [virtual] [access-specifier] Base2, . . .  
{  
   // member list  
};  
```  
  
 Sınıfın etiketinden (ad) sonra, temel özellikler listesinin ardından bir "iki nokta üst üste" işareti görünür.  Bu şekilde adlandırılmış temel sınıflar önceden bildirilmiş olmalıdır.  Temel belirtimleri anahtar sözcüklerden biri olan bir erişim belirteci içerebilir **ortak**, `protected` veya `private`.  Bu erişim belirticileri temel sınıf adından önce görünür ve yalnızca o temel sınıfa uygulanır.  Bu tanımlayıcılar türetilmiş sınıfın temel sınıf üyelerini kullanma iznini denetler.  Bkz: [üye erişim denetimi](../cpp/member-access-control-cpp.md) taban sınıf üyelerine erişimi hakkında bilgi için.  Erişim belirticisi atlanırsa, söz konusu temele erişim `private` olarak kabul edilir.  Temel belirtimleri anahtar sözcüğü içerebilir **sanal** sanal devralma belirtmek için.  Bu anahtar sözcük erişim belirticisinden (varsa) önce veya sonra görünebilir.  Sanal devralma kullanılıyorsa, temel sınıf sanal bir temel sınıf olarak kabul edilir.  
  
 Virgülle ayırarak birden çok temel sınıf belirtilebilir.  Tek bir temel sınıf belirtilirse, devralma modeldir [tek devralma](../cpp/single-inheritance.md). Birden fazla temel sınıf belirtilmemişse, devralma modeli adı verilir [birden çok devralma](http://msdn.microsoft.com/en-us/3b74185e-2beb-4e29-8684-441e51d2a2ca),  
  
 Aşağıdaki konular bulunur:  
  
-   [Tek devralma](../cpp/single-inheritance.md)  
  
-   [Birden çok devralma](http://msdn.microsoft.com/en-us/3b74185e-2beb-4e29-8684-441e51d2a2ca)  
  
-   [Birden çok taban sınıfı](../cpp/multiple-base-classes.md)  
  
-   [Sanal işlevler](../cpp/virtual-functions.md)  
  
-   [Açık geçersiz kılmalar](../cpp/explicit-overrides-cpp.md)  
  
-   [Soyut sınıflar](../cpp/abstract-classes-cpp.md)  
  
-   [Kapsam kuralları özeti](../cpp/summary-of-scope-rules.md)  
  
 [__Super](../cpp/super.md) ve [__interface](../cpp/interface.md) anahtar sözcükler, bu bölümünde belgelenmiştir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)