---
title: geçersiz kılma belirticisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- override Identifier
ms.assetid: b286fb46-9374-4ad8-b2e7-4607119b6133
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c95a67df03f62279b7b9c46ef41b6cafe7ff3df1
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408157"
---
# <a name="override-specifier"></a>override Tanımlayıcısı
Kullanabileceğiniz **geçersiz kılma** üye bir temel sınıf sanal işlevi geçersiz kılan işlevleri tanımlamak için anahtar sözcüğü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
function-declaration override;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **geçersiz kılma** duyarlıdır ve yalnızca kullanıldığında özel anlamı olan bir üye işlev bildiriminden sonra kullanılır; Aksi takdirde, ayrılmış bir anahtar değil.  
  
## <a name="example"></a>Örnek  
 Kullanım **geçersiz kılma** kodunuzda yanlışlıkla kalıtım davranışını önlemeye yardımcı olmak için. Aşağıdaki örnek, kullanmadan where gösterir **geçersiz kılma**, türetilen sınıfın üye işlev davranışının aktarmayı şablonlarınızı. Derleyici bu kod için herhangi bir hata vermez.  
  
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
  
 Kullanırken **geçersiz kılma**, derleyici sessiz bir şekilde yeni üye işlevleri oluşturmak yerine hatalar üretir.  
  
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
  
 İşlevlerin geçersiz kılınamaz ve sınıfların devralınamaz olduğunu belirtmek için kullanın [son](../cpp/final-specifier.md) anahtar sözcüğü.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [final tanımlayıcısı](../cpp/final-specifier.md)   
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)   