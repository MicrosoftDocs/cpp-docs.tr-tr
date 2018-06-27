---
title: korumalı (C++ bileşen uzantıları) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- sealed_cpp
- sealed
dev_langs:
- C++
helpviewer_keywords:
- sealed keyword [C++]
ms.assetid: 3d0d688a-41aa-45f5-a25a-65c44206521e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05c75aef047e914086aaf4ae2c0d0d3bdd04e8c7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890870"
---
# <a name="sealed--c-component-extensions"></a>mühürlü (C++ Bileşen Uzantıları)
`sealed` Sanal üyesi geçersiz kılınamaz ya da bir tür bir taban türü kullanılamaz gösteren bir bağlama duyarlı anahtar sözcüğü ref sınıfları için adıdır.  
  
> [!NOTE]
>  ISO C ++ 11 standart dil sahip [son](../cpp/final-specifier.md) Visual Studio'da desteklenen anahtar sözcüğü. Kullanım `final` standart sınıfları ve `sealed` ref sınıfları.  
  
## <a name="all-runtimes"></a>Tüm Çalışma Zamanları  
  
## <a name="syntax"></a>Sözdizimi
  
```  
ref class identifier sealed {...};  
virtual return-type identifier() sealed {...};  
```  
  
### <a name="parameters"></a>Parametreler  
  
 *Tanımlayıcı*  
 İşlev veya sınıf adı.  
  
 *dönüş türü*  
 Bir işlev tarafından döndürülen türü.  
  
## <a name="remarks"></a>Açıklamalar  
  
 İlk sözdizimi örnekte bir sınıf korumalı değil. İkinci örnekte, bir sanal işlev korumalı değil.  
  
 `sealed` Sözcüktür yerel hedefler için ve ayrıca Windows çalışma zamanı ve ortak dil çalışma zamanı (CLR) için geçerli. Daha fazla bilgi için bkz: [geçersiz kılma tanımlayıcıları ve yerel derleme](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
 Bir türü kullanarak korumalı olup olmadığını derleme zamanında algılayabilir `__is_sealed(type)` türü ayırdedici nitelik. Daha fazla bilgi için bkz: [tür özellikleri için derleyici desteği](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 `sealed` bağlama duyarlı bir anahtar sözcüktür.  Daha fazla bilgi için bkz: [Context-Sensitive anahtar sözcükleri](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 Bkz: [Ref sınıflar ve yapılar](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı  
 (Yalnızca ortak dil çalışma zamanı için geçerli hiçbir açıklamalar için bu dil özelliği vardır.)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
### <a name="examples"></a>Örnekler  
 Bu aşağıdaki kod örneğinde etkisini gösterir `sealed` sanal üyesi üzerinde.  
  
```cpp  
// sealed_keyword.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
   virtual void g();  
};  
  
ref class X : I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
  
   virtual void g() sealed {  
      System::Console::WriteLine("X::f override of I1::g");  
   }  
};  
  
ref class Y : public X {  
public:  
   virtual void f() override {  
      System::Console::WriteLine("Y::f override of I1::f");  
   }  
  
   /*  
   // the following override generates a compiler error  
   virtual void g() override {  
      System::Console::WriteLine("Y::g override of I1::g");  
   }    
   */  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
   MyI -> g();  
  
   I1 ^ MyI2 = gcnew Y;  
   MyI2 -> f();  
}  
```  
  
```Output  
X::f override of I1::f  
X::f override of I1::g  
Y::f override of I1::f  
```  
  
 Sonraki kod örneği, bir sınıf korumalı olarak işaretlemek gösterilmiştir.  
  
```cpp  
// sealed_keyword_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X sealed : I1 {  
public:  
   virtual void f() override {}  
};  
  
ref class Y : public X {   // C3246 base class X is sealed  
public:  
   virtual void f() override {}  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)