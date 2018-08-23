---
title: Genel türler ve temsilciler (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- generics [C++], vs. templates
- templates, C++
ms.assetid: 63adec79-b1dc-4a1a-a21d-b8a72a8fce31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f8a58e26b571c119d45cb981c582ebec335eface
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591008"
---
# <a name="generics-and-templates-visual-c"></a>Genel Türler ve Temsilciler (Visual C++)

Genel türler ve temsilciler parametreli türler için destek sağlayan her iki dil özellikleridir. Ancak, farklıdır ve farklı kullanır sahip. Bu konu, pek çok fark genel bir bakış sağlar.

Daha fazla bilgi için [Windows çalışma zamanı ve yönetilen şablonlar](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md).

## <a name="comparing-templates-and-generics"></a>Şablonları ve genel türler karşılaştırma

Genel türler ve C++ şablonları arasındaki temel farklar:

- Bunlar için çalışma zamanında başvurulduğunda tür kadar genel türler geneldir. Çalışma zamanında hala parametreli türler olmadıkları için derleme zamanında özelleştirilmiş şablonları

- Ortak dil çalışma zamanı, genel türler özellikle MSIL destekler. Çalışma zamanı, genel türler hakkında bildiğinden, belirli türler genel türler için genel bir tür içeren bir derlemenin başvururken yerine kullanılabileceği. Şablonlar, buna karşılık, sıradan tür olarak derleme zamanında çözmek ve sonuç türleri diğer derlemelerde özelleştirilmesi değil.

- Genel türler, iki farklı derlemelerde özelleştirilmiş ile aynı türde bağımsız değişkenleri aynı türdedir. Şablon bağımsız değişkenleri çalışma zamanı tarafından farklı değerlendirilir aynı türde iki farklı derlemelerde anlayışıyla çalışır.

- Genel türler (Bu değer türü başına benzersiz bir uygulama olan değer türleri için doğru değil) tüm başvuru türü bağımsız değişkenleri için kullanılan yürütülebilir kod tek bir parçası olarak oluşturulur. JIT Derleyici, genel türler hakkında bilir ve tür bağımsız değişkenleri kullanılan başvuru veya değer türleri için kod iyileştirebilir. Şablon, her uzmanlık için ayrı bir çalışma zamanı kodu oluşturma.

- Genel türler, tür olmayan şablon parametreleri gibi verme `template <int i> C {}`. Şablonlar, bunları sağlar.

- Genel türler (diğer bir deyişle, bir özel uygulanışı belirli bir tür için bir şablon) açık özelleştirme izin vermez. Şablonları yapın.

- Genel türler (özel bir uygulama için bir alt tür bağımsız değişkenlerini) kısmi özelleştirmede izin vermez. Şablonları yapın.

- Genel türler tür parametresi, genel tür için temel sınıf olarak kullanılacak izin vermez. Şablonları yapın.

- Şablonları destekleyen şablonu şablon parametreleri (örneğin `template<template<class T> class X> class MyClass`), ancak genel türler kullanmayın.

## <a name="combining-templates-and-generics"></a>Birleştirme şablonları ve genel türler

Genel türler temel fark, şablonları ve genel türler birleştiren uygulamalar oluşturmaya yönelik etkilere sahiptir. Örneğin, diğer diller için o şablon genel olarak kullanıma sunmak için genel bir sarmalayıcı oluşturmak istediğiniz bir şablon sınıfı olduğunu varsayalım. Genel sınav zamanı şablonu, derleme zamanında bu tür parametresi olması gerekiyorsa bu yana, daha sonra şablona rağmen geçirir bir tür parametresine sahip olamaz, ancak genel tür parametresi çalışma zamanına kadar çözmez. Çalışma zamanında oluşturulabilir rastgele genel türler için derleme zamanında şablonları genişletmek için hiçbir yolu olmadığından bir şablon genel içinde iç içe ya da işe yaramaz.

## <a name="example"></a>Örnek

### <a name="description"></a>Açıklama

Aşağıdaki örnek şablonları ve genel türler birlikte kullanarak basit bir örneğini gösterir. Bu örnekte, Şablon sınıfı için genel tür parametresi üzerinden geçirir. Ters mümkün değildir.

Bu deyim, bir Visual C++ derleme için yerel bir şablon kod ile var olan bir genel API oluşturmak istediğinizde veya şablon olmayan supporte belirli özelliklerden yararlanmak için genel tür için fazladan bir Parametreleştirme katmanı eklemek, ihtiyacınız olduğunda kullanılabilir genel türler d.

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

## <a name="see-also"></a>Ayrıca Bkz.

[Genel Türler](../windows/generics-cpp-component-extensions.md)