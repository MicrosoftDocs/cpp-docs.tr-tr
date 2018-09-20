---
title: Yönetilen sınıf türü bildirimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __gc types
- classes [C++], managed
- class keyword [C++], CLR
- __value keyword
- value types, declaring
- value keyword [C++]
- managed classes
- interface class keyword
- ref keyword [C++]
ms.assetid: 16de9c94-91d7-492f-8ac7-f0729cc627e9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0f9ceb0867fbdfbbdb46075662fca802d1ee0bba
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393678"
---
# <a name="declaration-of-a-managed-class-type"></a>Yönetilen Sınıf Türü Bildirimi

Yönetilen Uzantılar'dan Visual C++ için C++ için değiştirilmiş bir başvuru sınıfı türü bildirmek için yolu.

Yönetilen Uzantılar'bir başvuru sınıfı türü ile başlayan `__gc` anahtar sözcüğü. Yeni sözdiziminde `__gc` anahtar sözcüğü bir iki boşluklu anahtar tarafından değiştirilir: `ref class` veya `ref struct`. Seçimi `struct` veya `class` genel gösterir (için `struct`) veya özel (için `class`) varsayılan erişim düzeyi üyelerinin bildirilen türü gövdesi ilk etiketlenmemiş bölümünde.

Benzer şekilde, Yönetilen Uzantılar'değer sınıfı türü başında `__value` anahtar sözcüğü. Yeni sözdiziminde `__value` anahtar sözcüğü bir iki boşluklu anahtar tarafından değiştirilir: `value class` veya `value struct`.

Yönetilen Uzantılar bir arabirim türü ile anahtar sözcüğü belirtilirdi `__interface`. Yeni sözdiziminde, bu ile değiştirilir `interface class`.

Örneğin, aşağıdaki sınıf bildirimlerinde Yönetilen Uzantılar:

```
public __gc class Block {};     // reference class
public __value class Vector {}; // value class
public __interface IFooBar {};  // interface class
```

Yeni sözdiziminde bu eşdeğer şu şekilde bildirilir:

```
public ref class Block {};         // reference class
public value class Vector {};      // value class
public interface class IFooBar {}; // interface class
```

## <a name="specifying-the-class-as-abstract"></a>Sınıfı soyut olarak belirtme

Anahtar sözcüğü yerleştirdiğiniz Yönetilen Uzantılar'altında `__abstract` önce `class` anahtar sözcüğü (önce veya sonra `__gc`) sınıfı eksik olduğunu ve sınıfın nesneleri programında oluşturulan belirtmek için:

```
public __gc __abstract class Shape {};
public __gc __abstract class Shape2D: public Shape {};
```

Yeni sözdiziminde, belirttiğiniz `abstract` sınıfı adı ve sınıf gövdesine, temel sınıf türetme listesinden veya noktalı virgülden önce aşağıdaki bağlamsal anahtar sözcük.

```
public ref class Shape abstract {};
public ref class Shape2D abstract : public Shape{};
```

Elbette, anlam değiştirilmez.

## <a name="specifying-the-class-as-sealed"></a>Sınıfı kapalı olarak belirtme

Anahtar sözcüğü yerleştirdiğiniz Yönetilen Uzantılar'altında `__sealed` önce `class` anahtar sözcüğü (önce veya sonra `__gc`) nesneler sınıfın devralınamayacağını belirtmek için:

```
public __gc __sealed class String {};
```

Yeni sözdiziminde, belirttiğiniz `sealed` sınıfı adı ve sınıf gövdesine, temel sınıf türetme listesinden veya noktalı virgülden önce aşağıdaki bağlamsal anahtar sözcük.

Hem bir sınıf türetin ve kapatabilirsiniz. Örneğin, `String` sınıfı örtülü olarak türetilen `Object`. Statik çözümleme destekleyen bir sınıf mühürleme avantajı olduğu (diğer bir deyişle, derleme zamanında) korumalı başvuru sınıf nesnesi üzerinden tüm sanal işlev çağrılarının. Bunun nedeni, `sealed` belirticisi garanti `String` izleme işleyicisi çağrılmakta olan sanal yöntemini geçersiz kılan bir örnek verebilir daha sonra türetilmiş bir sınıfa başvuruda bulunamaz. Yeni sözdiziminde kapalı bir sınıf örneği aşağıdadır:

```
public ref class String sealed {};
```

Ayrıca hem soyut bir sınıf belirtebilirsiniz ve korumalı - bu statik sınıf gösteren bir özel durumdur. Bu CLR belgelerinde şu şekilde tanımlanır:

"Bir tür hem `abstract` ve `sealed` yalnızca statik üyeleri sahiptir ve ne olarak görev yapar bazı dillerde bir ad alanı çağırın."

Örneğin, Yönetilen Uzantılar'söz dizimini kullanarak bir Özet korumalı sınıf bildirimi şu şekildedir:

```
public __gc __sealed __abstract class State {
public:
   static State() {}
   static bool inParamList();

private:
   static bool ms_inParam;
};
```

ve yeni sözdizimine çevrilmiş bu bildirimi aşağıda verilmiştir:

```
public ref class State abstract sealed {
public:
   static State();
   static bool inParamList();

private:
   static bool ms_inParam;
};
```

## <a name="clr-inheritance-specifying-the-base-class"></a>CLR devralma: taban sınıf belirtme

CLR nesne modeli altında yalnızca ortak tek devralma desteklenir. Ancak, yönetilen uzantıları için temel sınıf olarak özel türetme belirten bir erişim anahtar sözcüğü olmadan ISO-C++ varsayılan yorumu korunur. Bu her CLR devralma bildirim sağlamak vardı `public` için varsayılan yorumu geçersiz kılmak için anahtar sözcüğü.

```
// Managed Extensions: error: defaults to private derivation
__gc class Derived : Base {};
```

Yeni sözdizimi tanımında bir erişim anahtar sözcüğü olmaması bir CLR devralma tanımı genel bir türetme gösterir. Bu nedenle, `public` erişim anahtar sözcüğü, artık isteğe bağlıdır. Bu Yönetilen Uzantılar'ın herhangi bir değişiklik için C++ kod gerektirmez, ancak ben eksiksiz olması için bu değişikliği burada listeleyin.

```
// New syntax: ok: defaults to public derivation
ref class Derived : Base{};
```

## <a name="see-also"></a>Ayrıca Bkz.

[Yönetilen türler (C + +/ CL)](../dotnet/managed-types-cpp-cl.md)<br/>
[Sınıflar ve Yapılar](../windows/classes-and-structs-cpp-component-extensions.md)<br/>
[abstract](../windows/abstract-cpp-component-extensions.md)<br/>
[sealed](../windows/sealed-cpp-component-extensions.md)