---
title: Kopyalama oluşturucuları ve kopya atama işleçleri (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- = operator [C++], copying objects
- assignment statements [C++], copying objects
- assignment operators [C++], for copying objects
- objects [C++], copying
- initializing objects, by copying objects
- copying objects
- assigning values to copy objects
ms.assetid: a94fe1f9-0289-4fb9-8633-77c654002c0d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 249182277473eebf5f11d4f6f3de1e8e7d275b61
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032620"
---
# <a name="copy-constructors-and-copy-assignment-operators-c"></a>Kopya Oluşturucuları ve Kopya Atama İşleçleri (C++)

> [!NOTE]
> C ++ 11'de başlayarak, iki tür ataması dilinde desteklenir: *kopyalama ataması* ve *atama taşıma*. Bu makalede "atama" açıkça aksi belirtilmediği sürece kopyalama ataması anlamına gelir. Taşıma ataması hakkında daha fazla bilgi için bkz: [taşıma oluşturucuları ve taşıma atama işleçleri (C++)](move-constructors-and-move-assignment-operators-cpp.md).
>
> Hem atama işlemi hem de başlatma işlemi kopyalanacak nesneleri neden.

- **Atama**: bir nesnenin değerini başka bir nesneye atandığında, ikinci nesne ilk nesnenin kopyalanır. Bu nedenle,

    ```cpp
    Point a, b;
    ...
    a = b;
    ```

   değerini neden `b` kopyalanacağı `a`.

- **Başlatma**: yeni bir nesne bildirildiğinde bağımsız değişkenleri değere göre işleve geçirildiğinde ya da değerler işlevlerden değer tarafından döndürülür başlatma gerçekleşir.

Sınıf türü nesneler için "Kopyala" semantiği tanımlayabilirsiniz. Örneğin, aşağıdaki kodu düşünün:

```cpp
TextFile a, b;
a.Open( "FILE1.DAT" );
b.Open( "FILE2.DAT" );
b = a;
```

Yukarıdaki kod, "fıle1'de, içeriğini kopyalayın. gelebilir DAT dosya2 için. DAT"veya"dosya2 yoksayın. gelebilir DAT ve `b` FILE1.DAT için ikinci bir tanıtıcı. " Şu şekilde her sınıf için uygun kopyalama semantiği eklemeniz gerekir.

- Atama işleci kullanarak **işleç =** dönüş türü tarafından geçirilen parametre olarak sınıf türüne yapılan başvuru birlikte **const** başvuru — örneğin `ClassName& operator=(const ClassName& x);`.

- Kopya Oluşturucusu kullanarak.

Kopya Oluşturucu bildirmeyin, derleyici member-wise kopya Oluşturucu oluşturur.  Kopya atama işlecine bildirmeyin, derleyici member-wise kopya atama işlecine sizin için oluşturur. Bir kopya Oluşturucu bildirilerek derleyici tarafından üretilen kopya atama işleci gizlemiyor ya da tam tersi. Tek uygularsanız, böylece kodun anlamı açıktır, ayrıca diğeri uygulamanız önerilir.

Kopya Oluşturucu türünde bir bağımsız değişken alan <em>sınıf adı</em><strong>&</strong>burada *sınıf adı* Oluşturucu tanımlanır sınıf adıdır. Örneğin:

```cpp
// spec1_copying_class_objects.cpp
class Window
{
public:
    Window( const Window& ); // Declare copy constructor.
    // ...
};

int main()
{
}
```

> [!NOTE]
> Kopya Oluşturucunun bağımsız değişken türünü olun **const** <em>sınıf adı</em> <strong>&</strong> mümkün olduğunda. Bu, kopya Oluşturucu içinden kopyalıyor nesne yanlışlıkla değiştirmesini engeller. Ayrıca, kopyalama sağlar **const** nesneleri.

## <a name="compiler-generated-copy-constructors"></a>Derleyicinin ürettiği kopya oluşturucuları

Kullanıcı tanımlı kopya oluşturucuları gibi derleyici tarafından üretilen kopya oluşturucuları sahip tek bir bağımsız değişken türü "başvurusu *sınıf adı*." Tüm temel sınıflar ve üye sınıfların türünde tek bir bağımsız değişken alacağı bildirilen kopya oluşturucuları olması durumudur bir istisnası **const** <em>sınıf adı</em><strong>&</strong>. Böyle bir durumda, derleyici tarafından üretilen kopya Oluşturucunun bağımsız değişkeni de olan **const**.

Kopya oluşturucusunun bağımsız değişken türü olmadığında **const**, kopyalayarak yapılan başlatma bir **const** hata nesnesi oluşturur. Tersi doğru değildir: bağımsız değişken ise **const**, olmayan bir nesneyi kopyalayarak başlatabilirsiniz **const**.

Derleyici tarafından üretilen atama işleçleri ile aynı deseni takip **const.** Tek bir bağımsız değişken türü aldıkları <em>sınıf adı</em> <strong>&</strong> tüm temel ve üye sınıflardaki atama işleçleri türünde bağımsız değişken almadıkları sürece **const** <em>sınıf adı</em><strong>&</strong>. Atama işleci alır bu durumda, sınıfın üretilmiş bir **const** bağımsız değişken.

> [!NOTE]
> Sanal temel sınıflar, derleyici tarafından oluşturulan veya kullanıcı tanımlı kopya oluşturucular tarafından başlatıldığında, yalnızca bir kez başlatılırlar: Oluşturuldukları noktada.

Etkileri, kopya oluşturucusununkine benzer. Bağımsız değişken türü olmadığında **const**, atamadan bir **const** hata nesnesi oluşturur. Tersi doğru değildir: varsa bir **const** değeri olmayan bir değer atanır **const**, ataması başarılı olur.

Aşırı yüklenmiş atama işleçleri hakkında daha fazla bilgi için bkz: [atama](../cpp/assignment.md).