---
title: Genel (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: public_cpp
dev_langs: C++
helpviewer_keywords: public keyword [C++]
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0ff41d2b12f43deabd82538a3e2fb10eb35ead16
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="public-c"></a>public (C++)
## <a name="syntax"></a>Sözdizimi  
  
```  
public:  
   [member-list]  
public base-class  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıf üyeleri listesi önceki zaman **ortak** anahtar sözcüğü, bu üyeler herhangi bir işlev erişilebilir olduğunu belirtir. Bu sonraki erişim belirticisi veya sınıf sonuna kadar bildirilen tüm üyeleri için geçerlidir.  
  
 Bir taban sınıf adını önceki zaman **ortak** anahtar sözcüğü belirtir temel sınıfın ortak ve korumalı üyeleri ortak ve korumalı üyeler, sırasıyla türetilmiş sınıf.  
  
 Varsayılan erişim bir sınıf üyelerinin özeldir. Varsayılan erişim yapısı veya birleşim üyeleri herkes tarafından kullanılabilir.  
  
 Varsayılan bir taban sınıfın sınıfları için özel ve genel yapılar için erişilebilir. Birleşimler temel sınıflar sahip olamaz.  
  
 Daha fazla bilgi için bkz: [özel](../cpp/private-cpp.md), [korumalı](../cpp/protected-cpp.md), [arkadaş](../cpp/friend-cpp.md)ve üye erişimi tabloda [sınıf üyelerine erişimi denetleme](member-access-control-cpp.md) .  
  
## <a name="clr-specific"></a>/clr Özel  
 CLR Türleri'nde, C++ erişim belirteci anahtar sözcükler (**ortak**, `private`, ve `protected`) türlerini ve derlemeleri açısından yöntemleri görünürlüğünü etkileyebilir. Daha fazla bilgi için bkz: [üye erişim denetimi](member-access-control-cpp.md).  
  
> [!NOTE]
>  Derlenmiş dosyalar [/LN](../build/reference/ln-create-msil-module.md) Bu davranış tarafından etkilenmez. Bu durumda, tüm yönetilen sınıflar (ortak veya özel) görünür.  
  
## <a name="end-clr-specific"></a>END /clr Özel  
  
## <a name="example"></a>Örnek  
  
```  
// keyword_public.cpp  
class BaseClass {  
public:  
   int pubFunc() { return 0; }  
};  
  
class DerivedClass : public BaseClass {};  
  
int main() {  
   BaseClass aBase;  
   DerivedClass aDerived;  
   aBase.pubFunc();       // pubFunc() is accessible   
                          //    from any function  
   aDerived.pubFunc();    // pubFunc() is still public in   
                          //    derived class  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıf üyelerine erişimi denetleme](member-access-control-cpp.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)