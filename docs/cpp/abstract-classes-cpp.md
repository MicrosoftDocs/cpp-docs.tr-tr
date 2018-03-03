---
title: "Soyut sınıflar (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], abstract
- base classes [C++], abstract classes [C++]
- abstract classes [C++]
- derived classes [C++], abstract classes [C++]
ms.assetid: f0c5975b-39de-4d68-9640-6ce57f4632e6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 23cdff4d0e2eb213a98b2e90d7df41af226edd86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="abstract-classes-c"></a>Soyut Sınıflar (C++)
Soyut sınıflar daha belirli sınıfları türetilebilir genel kavramlar ifadeleri olarak davranır. Bir Özet sınıf türünde bir nesne oluşturulamıyor; Ancak, soyut sınıf türleri için işaretçiler ve başvurular kullanabilirsiniz.  
  
 En az bir saf sanal işlev içeren bir sınıf, soyut bir sınıf olarak kabul edilir. Soyut sınıftan türetilen sınıflara saf sanal işlev uygulamalıdır ya da, çok, soyut sınıflar.  
  
 Kullanarak bir sanal işlev "saf" olarak bildirilmiş *belirticisi saf* sözdizimi (açıklanan [sınıfı protokol uygulanması](http://msdn.microsoft.com/en-us/a319f1b3-05e8-400e-950a-1ca6eb105ab5)). İçinde sunulan örneği göz önünde bulundurun [sanal işlevler](../cpp/virtual-functions.md). Sınıf amacı `Account` genel işlevi, ancak nesne türü sağlamaktır `Account` kullanışlı olması için genel niteliktedir. Bu nedenle, `Account` bir Özet sınıf için iyi bir adaydır:  
  
```  
// deriv_AbstractClasses.cpp  
// compile with: /LD  
class Account {  
public:  
   Account( double d );   // Constructor.  
   virtual double GetBalance();   // Obtain balance.  
   virtual void PrintBalance() = 0;   // Pure virtual function.  
private:  
    double _balance;  
};  
  
```  
  
 Bu bildirim ve önceki arasındaki tek fark `PrintBalance` saf tanımlayıcısı ile bildirilmiş (`= 0`).  
  
## <a name="restrictions-on-abstract-classes"></a>Soyut sınıflar kısıtlamalar  
 Soyut sınıflar şunlar için kullanılamaz:  
  
-   Değişkenler veya üye verileri  
  
-   Bağımsız değişken türleri  
  
-   İşlev dönüş türleri  
  
-   Açık dönüştürme türleri  
  
 Başka bir kısıtlama da soyut bir sınıfa yönelik bir oluşturucu doğrudan veya dolaylı olarak saf bir sanal işlevi çağırıyorsa, sonucun tanımsız olmasıdır. Bununla birlikte, soyut sınıflara yönelik oluşturucular ve yıkıcılar diğer üye işlevlerini çağırabilir.  
  
 Saf sanal işlevler soyut sınıflar için tanımlanabilir, ancak doğrudan yalnızca şu sözdizimi kullanılarak çağrılabilir:  
  
 *soyut sınıf adı* `::` *işlev adı***)**  
  
 Bu, temel sınıf yıkıcıları her zaman bir nesne yıkılırken çağrıldığı için temel sınıfları saf sanal yıkıcılar içeren sınıf hiyerarşilerinin tasarlanmasına yardımcı olur. Aşağıdaki örnek göz önünde bulundurun:  
  
```  
// Declare an abstract base class with a pure virtual destructor.  
// deriv_RestrictionsonUsingAbstractClasses.cpp  
class base {  
public:  
    base() {}  
    virtual ~base()=0;  
};  
  
// Provide a definition for destructor.  
base::~base() {}  
  
class derived:public base {  
public:  
    derived() {}  
    ~derived(){}  
};  
  
int main() {  
    derived *pDerived = new derived;  
    delete pDerived;  
}  
```  
  
 `pDerived` tarafından işaret edilen nesne silindiğinde, `derived` sınıfına yönelik yıkıcı ve ardından `base` sınıfına yönelik yıkıcı çağrılır. Saf sanal işleve yönelik boş uygulama, işlev için en azından bazı uygulamaların var olmasını sağlar.  
  
> [!NOTE]
>  Yukarıdaki örnekte, `base::~base` saf sanal işlevi `derived::~derived` öğesinden örtük olarak çağrılır. Saf sanal işlevler, tam üye işlevi adı kullanılarak örtük bir şekilde çağrılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devralma](../cpp/inheritance-cpp.md)