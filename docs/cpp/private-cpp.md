---
title: "Özel (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: private_cpp
dev_langs: C++
helpviewer_keywords: private keyword [C++]
ms.assetid: 94e99983-46a5-4e21-800c-28f8a7c6a8ff
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4f6a60a1e152d211ea3894d6dcd221ab543d3997
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="private-c"></a>private (C++)
## <a name="syntax"></a>Sözdizimi  
  
```  
private:  
   [member-list]  
private base-class  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıf üyeleri listesi önceki zaman `private` anahtar sözcüğü, bu üyeler yalnızca üye işlevleri ve arkadaş sınıfının erişilebilir olduğunu belirtir. Bu sonraki erişim belirticisi veya sınıf sonuna kadar bildirilen tüm üyeleri için geçerlidir.  
  
 Bir taban sınıf adını önceki zaman `private` anahtar sözcüğü temel sınıfı ortak ve korumalı üyeleri türetilmiş sınıf özel üyeleri olduğunu belirtir.  
  
 Varsayılan erişim bir sınıf üyelerinin özeldir. Varsayılan erişim yapısı veya birleşim üyeleri herkes tarafından kullanılabilir.  
  
 Varsayılan bir taban sınıfın sınıfları için özel ve genel yapılar için erişilebilir. Birleşimler temel sınıflar sahip olamaz.  
  
 İlgili bilgi için bkz: [arkadaş](../cpp/friend-cpp.md), [ortak](../cpp/public-cpp.md), [korumalı](../cpp/protected-cpp.md)ve üye erişimi tabloda [sınıf üyelerineerişimidenetleme](member-access-control-cpp.md).  
  
## <a name="clr-specific"></a>/clr Özel  
 CLR Türleri'nde, C++ erişim belirteci anahtar sözcükler (**ortak**, `private`, ve `protected`) türlerini ve derlemeleri açısından yöntemleri görünürlüğünü etkileyebilir. Daha fazla bilgi için bkz: [üye erişim denetimi](member-access-control-cpp.md).  
  
> [!NOTE]
>  Derlenmiş dosyalar [/LN](../build/reference/ln-create-msil-module.md) Bu davranış tarafından etkilenmez. Bu durumda, tüm yönetilen sınıflar (ortak veya özel) görünür.  
  
## <a name="end-clr-specific"></a>END /clr Özel  
  
## <a name="example"></a>Örnek  
  
```  
// keyword_private.cpp  
class BaseClass {  
public:  
   // privMem accessible from member function  
   int pubFunc() { return privMem; }  
private:  
   void privMem;  
};  
  
class DerivedClass : public BaseClass {  
public:  
   void usePrivate( int i )  
      { privMem = i; }   // C2248: privMem not accessible  
                         // from derived class  
};  
  
class DerivedClass2 : private BaseClass {  
public:  
   // pubFunc() accessible from derived class  
   int usePublic() { return pubFunc(); }  
};  
  
int main() {  
   BaseClass aBase;  
   DerivedClass aDerived;  
   DerivedClass2 aDerived2;  
   aBase.privMem = 1;     // C2248: privMem not accessible  
   aDerived.privMem = 1;  // C2248: privMem not accessible  
                          //    in derived class  
   aDerived2.pubFunc();   // C2247: pubFunc() is private in  
                          //    derived class  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıf üyelerine erişimi denetleme](member-access-control-cpp.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)