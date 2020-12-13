---
description: 'Daha fazla bilgi edinin: kopya oluşturucuları ve kopya atama Işleçleri (C++)'
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
ms.openlocfilehash: 881470c92e0261dc5c4cd63876d7cb59fcc68fef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344581"
---
# <a name="copy-constructors-and-copy-assignment-operators-c"></a>Kopya Oluşturucuları ve Kopya Atama İşleçleri (C++)

> [!NOTE]
> C++ 11 ' den başlayarak, dilde iki tür atama desteklenir: *kopyalama ataması* ve *taşıma ataması*. Bu makalede, "atama" açıkça belirtilmediği takdirde kopya atama anlamına gelir. Taşıma ataması hakkında daha fazla bilgi için bkz. [Taşıma Oluşturucuları ve taşıma atama işleçleri (C++)](move-constructors-and-move-assignment-operators-cpp.md).
>
> Atama işleminin ve başlatma işleminin her ikisi de nesnelerin kopyalanmasına neden olur.

- **Atama**: bir nesnenin değeri başka bir nesneye atandığında, ilk nesne ikinci nesneye kopyalanır. Yani:

    ```cpp
    Point a, b;
    ...
    a = b;
    ```

   değerinin ' `b` e kopyalanmasına neden olur `a` .

- **Başlatma**: başlatma, yeni bir nesne bildirildiğinde, bağımsız değişkenler değere göre işlevlere geçirildiğinde veya değerlere göre işlevlerden değer döndürüldüğünde oluşur.

Sınıf türündeki nesneler için "Kopyala" semantiğini tanımlayabilirsiniz. Örneğin, aşağıdaki kodu düşünün:

```cpp
TextFile a, b;
a.Open( "FILE1.DAT" );
b.Open( "FILE2.DAT" );
b = a;
```

Yukarıdaki kod "FıLE1 içeriğini Kopyala" anlamına gelebilir. DAT to DOSYA2. DAT "veya" Ignore DOSYA2 "anlamına gelebilir. DAT ve `b` FILE1. dat için ikinci bir tanıtıcı yapın. " Aşağıdaki gibi, her sınıfa uygun kopyalama semantiğini iliştirmelidir.

- Atama işleci **işlecini** kullanarak, dönüş türü olarak sınıf türüne başvuru ve başvuru ile geçirilen parametre ile birlikte, **`const`** Örneğin `ClassName& operator=(const ClassName& x);` .

- Kopya oluşturucuyu kullanarak.

Bir kopya Oluşturucu bildirmezsiniz, derleyici sizin için üye Wise bir kopya Oluşturucu oluşturur.  Bir kopya atama işleci bildirmezsiniz, derleyici sizin için üye odaklı bir kopya atama işleci oluşturur. Bir kopya Oluşturucu bildirmek derleyicinin ürettiği kopya atama işlecini göstermez, tersi de geçerlidir. Bunlardan birini uygularsanız, kodun anlamının açık olması için diğerini de uygulamanızı öneririz.

Kopya Oluşturucu, sınıf <em>-</em>adı türünde bir bağımsız değişken alır <strong>&</strong> ; burada *sınıf adı* , oluşturucunun tanımlandığı sınıfın adıdır. Örneğin:

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
> Kopya oluşturucunun bağımsız değişken **`const`** <em>sınıf adı</em> türünü <strong>&</strong> mümkün olduğunca yapın. Bu, kopya oluşturucunun kopyalama yaptığı nesneyi yanlışlıkla değiştirmesini engeller. Ayrıca, nesnelerden kopyalamayı da mümkün kılar **`const`** .

## <a name="compiler-generated-copy-constructors"></a>Derleyicinin oluşturduğu kopya oluşturucuları

Kullanıcı tanımlı kopya oluşturucuları gibi derleyicinin ürettiği kopya oluşturucuları, " *sınıf-adı* başvurusu" türünde tek bir bağımsız değişkene sahiptir. Tüm temel sınıfların ve üye sınıfların **`const`** <em>sınıf adı</em>türünde tek bir bağımsız değişken alan olarak bildirildiği kopya oluşturucuları olduğunda bir özel durum oluşur <strong>&</strong> . Böyle bir durumda, derleyici tarafından oluşturulan kopya oluşturucusunun bağımsız değişkeni de olur **`const`** .

Kopya oluşturucusuna bağımsız değişken türü olmadığında **`const`** , bir nesneyi kopyalayarak başlatma **`const`** bir hata oluşturur. Tersi doğru değil: bağımsız değişken ise **`const`** , olmayan bir nesneyi kopyalayarak başlatabilirsiniz **`const`** .

Derleyici tarafından oluşturulan atama işleçleri, const ile ilgili olarak aynı kalıbı izler **.** <em></em> <strong>&</strong> Tüm taban ve üye sınıflardaki atama işleçleri **`const`** <em>sınıf adı</em>türünde bağımsız değişkenler almaz, sınıf-adı türünden tek bir bağımsız değişken alırlar <strong>&</strong> . Bu durumda, sınıfın oluşturulan atama işleci bir **`const`** bağımsız değişken alır.

> [!NOTE]
> Sanal temel sınıflar, derleyici tarafından oluşturulan veya kullanıcı tanımlı kopya oluşturucular tarafından başlatıldığında, yalnızca bir kez başlatılırlar: Oluşturuldukları noktada.

Etkileri, kopya oluşturucusununkine benzer. Bağımsız değişken türü olmadığında **`const`** , bir **`const`** nesneden atama bir hata oluşturur. Tersi doğru değil: bir değer bir **`const`** değere atanmışsa **`const`** atama başarılı olur.

Aşırı yüklenmiş atama işleçleri hakkında daha fazla bilgi için bkz. [atama](../cpp/assignment.md).
