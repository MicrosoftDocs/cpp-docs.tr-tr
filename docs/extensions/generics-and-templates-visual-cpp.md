---
title: Genel türler ve şablonlarC++(/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- generics [C++], vs. templates
- templates, C++
ms.assetid: 63adec79-b1dc-4a1a-a21d-b8a72a8fce31
ms.openlocfilehash: 567286ee24e9df968b2d352489fe12f2735854eb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80172353"
---
# <a name="generics-and-templates-ccli"></a>Genel türler ve şablonlarC++(/CLI)

Genel türler ve şablonlar, parametreli türler için destek sağlayan dil özellikleridir. Ancak bunlar farklıdır ve farklı kullanımlar vardır. Bu konu, birçok farka genel bir bakış sağlar.

Daha fazla bilgi için bkz. [Windows çalışma zamanı ve yönetilen şablonlar](windows-runtime-and-managed-templates-cpp-component-extensions.md).

## <a name="comparing-templates-and-generics"></a>Şablonları ve genel türleri karşılaştırma

Genel türler ve C++ şablonlar arasındaki temel farklılıklar:

- Türler çalışma zamanında bunlar için yerine gelene kadar genel türler geneldir. Şablonlar derleme zamanında özelleştirilmiştir, bu nedenle çalışma zamanında hala parametreli türler olmamalıdır

- Ortak dil çalışma zamanı, MSIL 'deki genel türleri özellikle destekler. Çalışma zamanı, genel türler hakkında bilgi sahibi olduğu için, genel tür içeren bir derlemeye başvuru yaparken belirli türler genel türler için değiştirilebilir. Buna karşılık şablonlar, derleme zamanında sıradan türlere çözümleyin ve elde edilen türler diğer derlemelerde özelleştirilemez.

- Aynı tür bağımsız değişkenlerine sahip iki farklı derlemede özelleştirilmiş genel türler aynı türde. Aynı tür bağımsız değişkenlerine sahip iki farklı derlemede özelleştirilmiş şablonlar, çalışma zamanı tarafından farklı türlerde olacak şekilde değerlendirilir.

- Genel türler, tüm başvuru türü bağımsız değişkenleri için kullanılan tek bir yürütülebilir kod parçası olarak oluşturulur (değer türü başına benzersiz bir uygulama olan değer türleri için bu doğru değildir). JıT derleyicisi, genel türleri bilir ve tür bağımsız değişkenleri olarak kullanılan başvuru veya değer türleri için kodu iyileştirebilecektir. Şablonlar her özelleşmeye yönelik ayrı çalışma zamanı kodu oluşturur.

- Genel türler, `template <int i> C {}`gibi tür olmayan şablon parametrelerine izin vermez. Şablonlar bunlara izin verir.

- Genel türler açık özelleşmeye (yani, belirli bir tür için bir şablonun özel bir uygulamasına) izin vermez. Şablonlar.

- Genel türler kısmi özelleşmeye (tür bağımsız değişkenlerinin bir alt kümesi için özel bir uygulama) izin vermez. Şablonlar.

- Genel türler, tür parametresinin genel tür için temel sınıf olarak kullanılmasına izin vermez. Şablonlar.

- Şablonlar Şablon-şablon parametrelerini (örn. `template<template<class T> class X> class MyClass`) destekler, ancak genel türler değildir.

## <a name="combining-templates-and-generics"></a>Şablonları ve genel türleri birleştirme

Genel türlerde temel fark, şablonları ve genel türleri birleştiren uygulamalar oluşturmaya yönelik etkileri vardır. Örneğin, bu şablonu diğer dillere genel olarak göstermek için genel bir sarmalayıcı oluşturmak istediğiniz bir şablon sınıfınız olduğunu varsayalım. Şablon, derleme zamanında bu tür parametresine sahip olması gerektiğinden, genel bir tür parametresine, daha sonra şablona geçirmiş olamaz, ancak genel bir tür parametresi çalışma zamanına kadar çözümlenmez. Bir şablonun genel içine yerleştirilmesi, çalışma zamanında oluşturulabilecek rastgele genel türler için derleme zamanında şablonları genişletmenin bir yolu olmadığı için çalışmaz.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek, şablonları ve genel türleri birlikte kullanmanın basit bir örneğini göstermektedir. Bu örnekte, şablon sınıfı parametresini genel türe geçirir. Tersi mümkün değildir.

Bu deyim, bir C++/CLI derlemesinde yerel olan şablon kodu ile var olan BIR genel API 'yi oluşturmak istediğinizde veya genel bir türe bir ek bir Parametreleştirme katmanı eklemeniz gerektiğinde, genel türler tarafından desteklenmeyen şablonların belirli özelliklerinden faydalanmak için kullanılabilir.

### <a name="code"></a>Kod

```cpp
// templates_and_generics.cpp
// compile with: /clr
using namespace System;

generic <class ItemType>
ref class MyGeneric {
   ItemType m_item;

public:
   MyGeneric(ItemType item) : m_item(item) {}
   void F() {
      Console::WriteLine("F");
   }
};

template <class T>
public ref class MyRef {
MyGeneric<T>^ ig;

public:
   MyRef(T t) {
      ig = gcnew MyGeneric<T>(t);
      ig->F();
    }
};

int main() {
   // instantiate the template
   MyRef<int>^ mref = gcnew MyRef<int>(11);
}
```

```Output
F
```

## <a name="see-also"></a>Ayrıca bkz.

[Genel Türler](generics-cpp-component-extensions.md)
