---
title: Kopya Oluşturucuları ve Kopya Atama İşleçleri (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- = operator [C++], copying objects
- assignment statements [C++], copying objects
- assignment operators [C++], for copying objects
- objects [C++], copying
- initializing objects, by copying objects
- copying objects
- assigning values to copy objects
ms.assetid: a94fe1f9-0289-4fb9-8633-77c654002c0d
ms.openlocfilehash: beabe4c6219975d33c7af98a94498188c9abfa55
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189539"
---
# <a name="copy-constructors-and-copy-assignment-operators-c"></a>Kopya Oluşturucuları ve Kopya Atama İşleçleri (C++)

> [!NOTE]
> C++ 11 ' den başlayarak, dilde iki tür atama desteklenir: *kopyalama ataması* ve *taşıma ataması*. Bu makalede, "atama" açıkça belirtilmediği takdirde kopya atama anlamına gelir. Taşıma ataması hakkında daha fazla bilgi için bkz. [Taşıma Oluşturucuları ve taşıma atamaC++işleçleri ()](move-constructors-and-move-assignment-operators-cpp.md).
>
> Atama işleminin ve başlatma işleminin her ikisi de nesnelerin kopyalanmasına neden olur.

- **Atama**: bir nesnenin değeri başka bir nesneye atandığında, ilk nesne ikinci nesneye kopyalanır. Bu nedenle,

    ```cpp
    Point a, b;
    ...
    a = b;
    ```

   `b` değerinin `a`kopyalanmasına neden olur.

- **Başlatma**: başlatma, yeni bir nesne bildirildiğinde, bağımsız değişkenler değere göre işlevlere geçirildiğinde veya değerlere göre işlevlerden değer döndürüldüğünde oluşur.

Sınıf türündeki nesneler için "Kopyala" semantiğini tanımlayabilirsiniz. Örneğin, aşağıdaki kodu düşünün:

```cpp
TextFile a, b;
a.Open( "FILE1.DAT" );
b.Open( "FILE2.DAT" );
b = a;
```

Yukarıdaki kod "FıLE1 içeriğini Kopyala" anlamına gelebilir. DAT to DOSYA2. DAT "veya" Ignore DOSYA2 "anlamına gelebilir. DAT ve FıLE1. DAT için ikinci bir tanıtıcı `b` yapın. " Aşağıdaki gibi, her sınıfa uygun kopyalama semantiğini iliştirmelidir.

- Atama işleci **işlecini** kullanarak, dönüş türü olarak sınıf türüne başvuru ve **const** başvurusu tarafından geçirilen parametre (örneğin `ClassName& operator=(const ClassName& x);`) ile birlikte.

- Kopya oluşturucuyu kullanarak.

Bir kopya Oluşturucu bildirmezsiniz, derleyici sizin için üye Wise bir kopya Oluşturucu oluşturur.  Bir kopya atama işleci bildirmezsiniz, derleyici sizin için üye odaklı bir kopya atama işleci oluşturur. Bir kopya Oluşturucu bildirmek derleyicinin ürettiği kopya atama işlecini göstermez, tersi de geçerlidir. Bunlardan birini uygularsanız, kodun anlamının açık olması için diğerini de uygulamanızı öneririz.

Kopya Oluşturucu, Class <em>-</em> Name<strong>&</strong>türünde bir bağımsız değişken alır; burada *sınıf adı* , oluşturucunun tanımlandığı sınıfın adıdır. Örneğin:

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
> Kopya oluşturucunun bağımsız değişkeninin **const** <em>sınıf-adı</em> <strong>&</strong> türünü mümkün olduğunca yapın. Bu, kopya oluşturucunun kopyalama yaptığı nesneyi yanlışlıkla değiştirmesini engeller. Ayrıca **const** nesnelerinden kopyalamayı da mümkün kılar.

## <a name="compiler-generated-copy-constructors"></a>Derleyicinin oluşturduğu kopya oluşturucuları

Kullanıcı tanımlı kopya oluşturucuları gibi derleyicinin ürettiği kopya oluşturucuları, " *sınıf-adı*başvurusu" türünde tek bir bağımsız değişkene sahiptir. Tüm temel sınıfların ve üye sınıfların, **const** <em>class-name</em> <strong>&</strong>türünde tek bir bağımsız değişken alan olarak bildirildiği kopya oluşturucuları olduğunda bir özel durum oluşur. Böyle bir durumda, derleyici tarafından oluşturulan kopya oluşturucusunun bağımsız değişkeni de **const**olur.

Kopya oluşturucusuna bağımsız değişken türü **const**olmadığında, bir **const** nesnesi kopyalayarak başlatma bir hata oluşturur. Ters doğru değil: bağımsız değişken **const**ise, **const**olmayan bir nesneyi kopyalayarak başlatabilirsiniz.

Derleyici tarafından oluşturulan atama işleçleri, const ile ilgili olarak aynı kalıbı izler **.** Tüm taban ve üye sınıflardaki atama işleçleri **const** <em>class-name</em> <strong>&</strong>türünde bağımsız değişkenler alıp etmediği müddetçe, <em>class-name</em> <strong>&</strong> türünde tek bir bağımsız değişken alırlar. Bu durumda, sınıfın oluşturulan atama işleci bir **const** bağımsız değişkeni alır.

> [!NOTE]
> Sanal temel sınıflar, derleyici tarafından oluşturulan veya kullanıcı tanımlı kopya oluşturucular tarafından başlatıldığında, yalnızca bir kez başlatılırlar: Oluşturuldukları noktada.

Etkileri, kopya oluşturucusununkine benzer. Bağımsız değişken türü **const**olmadığında, bir **const** nesnesinden atama bir hata oluşturur. Ters değer **doğru değil: const olmayan bir**değere **const** değeri atanırsa atama başarılı olur.

Aşırı yüklenmiş atama işleçleri hakkında daha fazla bilgi için bkz. [atama](../cpp/assignment.md).
