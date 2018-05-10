---
title: İzleme başvurusu işleci (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- '%'
dev_langs:
- C++
helpviewer_keywords:
- tracking references
- '% tracking reference [C++]'
ms.assetid: 142a7269-ab69-4b54-a6d7-833bef06228f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c460174fad6a287acfd434b1589e73153aa0b121
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="tracking-reference-operator-c-component-extensions"></a>İzleme Başvurusu İşleci (C++ Bileşen Uzantıları)
A *izleme başvurusu* (`%`) normal bir C++ başvurusu gibi davranır (`&`) dışında bir nesne için izleme başvurusu atandığında, nesnenin başvuru sayısı artırılır.  
  
## <a name="all-platforms"></a>Tüm Platformlar  
 İzleme başvurusu, aşağıdaki özelliklere sahiptir.  
  
-   İzleme başvurusu bir nesnenin atama artırılması gereken nesnenin başvuru sayısı neden olur.  
  
-   Yerel bir başvuru (&), başvuru sonucu olduğunda bir *. İzleme başvurusu (%), başvuru sonucu olduğunda bir ^. % Bir nesne için sahip olduğu sürece, nesne belleğinde etkin kalır.  
  
-   Nokta (`.`) üye erişimi işleci nesne üyesi erişmek için kullanılır.  
  
-   İzleme başvuruları geçerli değer türleri ve tanıtıcıları için (örneğin `String^`).  
  
-   İzleme başvurusu null atanamaz veya `nullptr` değeri. İzleme başvurusu başka bir geçerli nesneye gerektiği gibi birçok kez atanabilir.  
  
-   İzleme başvurusu birli Al adresi operatör olarak kullanılamaz.  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 Başvuruları sayılan bir % olması dışında izleme başvurusu standart C++ başvurusu gibi davranır. Aşağıdaki kod parçacığında % arasında dönüştürme gösterir ve ^ türleri:  
  
```  
Foo^ spFoo = ref new Foo();  
Foo% srFoo = *spFoo;  
Foo^ spFoo2 = %srFoo;  
```  
  
 Aşağıdaki örnekte nasıl iletileceğini gösterir bir ^ % bir alan bir işlev.  
  
```  
  
ref class Foo sealed {};  
  
    // internal or private  
    void UseFooHelper(Foo% f)  
    {  
        auto x = %f;  
    }  
  
    // public method on ABI boundary  
    void UseFoo(Foo^ f)  
    {  
        if (f != nullptr) { UseFooHelper(*f); }  
    }  
```  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı 
 C + +/ CLI, kullanabileceğiniz bir tanıtıcı izleme başvuru atık toplanan yığında CLR türünde bir nesne için bağ olduğunda.  
  
 Değer CLR'de atık toplayıcı başvurulan nesnenin getirdiğinde bir izleme başvurusu değişkeni otomatik olarak güncelleştirilir.  
  
 İzleme başvurusu yalnızca yığında bildirilebilir. İzleme başvurusu bir sınıf üyesi olamaz.  
  
 Çöp toplanan yığında yerel C++ başvurusu bir nesne için sahip mümkün değil.  
  
 C + başvuruları izleme hakkında daha fazla bilgi için +/ CLI, bkz:  
  
-   [Nasıl yapılır: C++/CLI Üzerinde İzleme Başvurularını Kullanma](../dotnet/how-to-use-tracking-references-in-cpp-cli.md)
  
### <a name="examples"></a>Örnekler  
 **Örnek**  
  
 Aşağıdaki örnek C + +/ CLI nasıl yerel ve yönetilen türleriyle izleme başvurusu kullanılacağını gösterir.  
  
```  
// tracking_reference_1.cpp  
// compile with: /clr  
ref class MyClass {  
public:  
   int i;  
};  
  
value struct MyStruct {  
   int k;  
};  
  
int main() {  
   MyClass ^ x = ref new MyClass;  
   MyClass ^% y = x;   // tracking reference handle to reference object   
  
   int %ti = x->i;   // tracking reference to member of reference type  
  
   int j = 0;  
   int %tj = j;   // tracking reference to object on the stack  
  
   int * pi = new int[2];  
   int % ti2 = pi[0];   // tracking reference to object on native heap  
  
   int *% tpi = pi;   // tracking reference to native pointer  
  
   MyStruct ^ x2 = ref new MyStruct;  
   MyStruct ^% y2 = x2;   // tracking reference to value object  
  
   MyStruct z;  
   int %tk = z.k;   // tracking reference to member of value type  
  
   delete[] pi;  
}  
  
```  
  
 **Örnek**  
  
 Aşağıdaki örnek C + +/ CLI nasıl bir dizi izleme başvurusu bağlanacağını gösterir.  
  
```  
// tracking_reference_2.cpp  
// compile with: /clr  
using namespace System;  
  
int main() {  
   array<int> ^ a = ref new array<Int32>(5);  
   a[0] = 21;  
   Console::WriteLine(a[0]);  
   array<int> ^% arr = a;  
   arr[0] = 222;  
   Console::WriteLine(a[0]);  
}  
```  
  
 **Output**  
  
```Output  
21  
222  
```