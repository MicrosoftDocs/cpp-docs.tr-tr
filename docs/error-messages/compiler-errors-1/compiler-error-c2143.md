---
title: "Derleyici Hatası C2143 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2143
dev_langs: C++
helpviewer_keywords: C2143
ms.assetid: 1d8d1456-e031-4965-9240-09a6e33ba81c
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 31ea645b9dd22fd15bbf4695935482d899a13386
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2143"></a>Derleyici Hatası C2143
sözdizimi hatası: eksik 'token2' önce ' token1'  
  
 Derleyici belirli bir belirteç (diğer bir deyişle, bir dil öğesi boşluk dışında) beklenen ve başka bir belirteç bulundu.  
  
 Bir işlev try bloğu kullanırken oluştuğunda, bu hata hakkında bilgi için bkz [Bilgi Bankası makalesi 241706](http://support.microsoft.com/kb/241706).  
  
 Denetleme [C++ dil başvurusu](../../cpp/cpp-language-reference.md) kod sözdizimsel olarak doğru olduğu belirlemek için. Soruna neden olan satır bulduğu sonra derleyici bu hatayı bildirin çünkü hata öncesinde birkaç satır kod denetleyin.  
  
 C2143 farklı durumlarda oluşabilir.  
  
 Bir ad nitelemek bir işleç olduğunda oluşabilir (`::`, `->`, ve `.`) anahtar sözcüğü tarafından uyulması gereken `template`, bu örnekteki gibi:  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::PutFuncType<Ty, PropTy> // error C2143  
    {  
    };  
};  
  
```  
  
 Varsayılan olarak, C++ varsayar `Ty::PutFuncType` olmayan bir şablon; bu nedenle, aşağıdaki `<` daha az yorumlanır-oturum daha.  Derleyici açıkça, size gereken `PutFuncType` açılı ayraç doğru ayrıştıramıyor böylece bir şablondur. Bu hatayı düzeltmek için kullanmak `template` anahtar sözcüğü aşağıda gösterildiği gibi bağımlı tür adı:  
  
```cpp  
class MyClass  
{  
    template<class Ty, typename PropTy>  
    struct PutFuncType : public Ty::template PutFuncType<Ty, PropTy> // correct  
    {  
    };  
};  
  
```  
  
 C2143 oluşabilir zaman **/CLR** kullanılır ve `using` yönergesi sözdizimi hatası var:  
  
```cpp  
// C2143a.cpp  
// compile with: /clr /c  
using namespace System.Reflection;   // C2143  
using namespace System::Reflection;  
```  
  
 Ayrıca kullanmadan CLR sözdizimini kullanarak bir kaynak kodu dosyasının derlemek çalışırken da oluşabilir **/CLR**:  
  
```cpp  
// C2143b.cpp  
ref struct A {   // C2143 error compile with /clr  
   void Test() {}  
};  
  
int main() {  
   A a;  
   a.Test();  
}  
```  
  
 İzleyen ilk boşluk olmayan karakter bir `if` deyimi, sol parantez olmalıdır. Derleyici başka bir şey çeviremez:  
  
```cpp  
// C2143c.cpp  
int main() {  
   int j = 0;  
  
   // OK  
   if (j < 25)  
      ;  
  
   if (j < 25)   // C2143  
}  
```  
  
 C2143 bir kapanış ayracı, parantez veya noktalı virgül nerede hata algılandığında satırda eksik olduğunda ortaya veya satırlardan birini yukarıda sadece:  
  
```cpp  
// C2143d.cpp  
// compile with: /c  
class X {  
   int member1;  
   int member2   // C2143  
} x;  
```  
  
 Ya da bir sınıf bildiriminde geçersiz bir etiket olduğunda:  
  
```cpp  
// C2143e.cpp  
class X {  
   int member;  
} x;  
  
class + {};   // C2143 + is an invalid tag name  
class ValidName {};   // OK  
```  
  
 Veya ne zaman bir etiket bir ifadesine eklenmedi. Örneğin, tek başına bir etiket yerleştirmeniz gerekir, bileşik deyim sonunda, boş bir deyim ekleyin:  
  
```cpp  
// C2143f.cpp  
// compile with: /c  
void func1() {  
   // OK  
   end1:  
      ;  
  
   end2:   // C2143  
}  
```  
  
 C++ Standart Kitaplığı'nda bir tür nitelenmemiş çağrısı yapıldığında hata oluşabilir:  
  
```cpp  
// C2143g.cpp  
// compile with: /EHsc /c  
#include <vector>  
static vector<char> bad;   // C2143  
static std::vector<char> good;   // OK  
```  
  
 Veya eksik bir `typename` anahtar sözcüğü:  
  
```cpp  
// C2143h.cpp  
template <typename T>  
struct X {  
   struct Y {  
      int i;  
   };  
   Y memFunc();  
};  
template <typename T>  
X<T>::Y X<T>::memFunc() {   // C2143  
// try the following line instead  
// typename X<T>::Y X<T>::memFunc() {  
   return Y();  
}  
```  
  
 Veya bir açık örnekleme tanımlamayı deneyin:  
  
```cpp  
// C2143i.cpp  
// compile with: /EHsc /c  
// template definition  
template <class T>  
void PrintType(T i, T j) {}  
  
template void PrintType(float i, float j){}   // C2143  
template void PrintType(float i, float j);   // OK  
```  
  
 Bir C programı değişkenleri işlevi başında bildirilmelidir ve işlev bildirimi olmayan yönergeleri yürütüldükten sonra bunlar bildirilemez.  
  
```C  
// C2143j.c  
int main()   
{  
    int i = 0;  
    i++;  
    int j = 0; // C2143  
}  
```  
