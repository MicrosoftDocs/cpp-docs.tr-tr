---
title: "override tanımlayıcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: override Identifier
ms.assetid: b286fb46-9374-4ad8-b2e7-4607119b6133
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c182404618e36fe3b7fa0ed72d3a2e39569f7ac0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="override-specifier"></a>override Tanımlayıcısı
Kullanabileceğiniz `override` üye bir taban sınıf içinde sanal işlevi geçersiz kılma işlevleri belirlemek için anahtar sözcüğü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
function-declaration override;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `override`bağlama duyarlı ve yalnızca bir üye işlevi bildirimi sonra kullanıldığında özel anlamı olan; Aksi takdirde, ayrılmış bir anahtar değil.  
  
## <a name="example"></a>Örnek  
 Kullanım `override` kodunuzda yanlışlıkla devralma davranışı önlemek için. Aşağıdaki örnek, kullanmadan where gösterir `override`, türetilmiş sınıf üye işlevi davranışını değil hedeflenen. Derleyici Hataları bu kodun yayma değil.  
  
```cpp  
class BaseClass  
{  
    virtual void funcA();  
    virtual void funcB() const;  
    virtual void funcC(int = 0);  
    void funcD();  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void funcA(); // ok, works as intended  
  
    virtual void funcB(); // DerivedClass::funcB() is non-const, so it does not  
                          // override BaseClass::funcB() const and it is a new member function  
  
    virtual void funcC(double = 0.0); // DerivedClass::funcC(double) has a different  
                                      // parameter type than BaseClass::funcC(int), so  
                                      // DerivedClass::funcC(double) is a new member function  
  
};  
  
```  
  
 Kullandığınızda `override`, derleyici hataları sessizce yeni üye işlevleri oluşturmak yerine oluşturur.  
  
```cpp  
class BaseClass  
{  
    virtual void funcA();  
    virtual void funcB() const;  
    virtual void funcC(int = 0);  
    void funcD();  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void funcA() override; // ok  
  
    virtual void funcB() override; // compiler error: DerivedClass::funcB() does not   
                                   // override BaseClass::funcB() const  
  
    virtual void funcC( double = 0.0 ) override; // compiler error:   
                                                 // DerivedClass::funcC(double) does not   
                                                 // override BaseClass::funcC(int)  
  
    void funcD() override; // compiler error: DerivedClass::funcD() does not   
                           // override the non-virtual BaseClass::funcD()  
};  
  
```  
  
 İşlevleri geçersiz kılınamaz ve sınıfları devralınan belirtmek için kullanın [son](../cpp/final-specifier.md) anahtar sözcüğü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [final tanımlayıcısı](../cpp/final-specifier.md)   
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 