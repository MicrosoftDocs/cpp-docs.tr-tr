---
title: Şablonlar ve Ad Çözümü
ms.date: 11/04/2016
ms.assetid: 519ba7b5-cd25-4549-865a-9a7b9dffdc28
ms.openlocfilehash: e4a53df0a192c1d7b7f376e4401eb99fcbf7d481
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266757"
---
# <a name="templates-and-name-resolution"></a>Şablonlar ve Ad Çözümü

Şablon tanımlarında üç ad türü vardır.

- Şablonun adını ve şablon tanımının içinde bildirilen tüm adları içeren yerel olarak bildirilen adlar.

- Şablon tanımının dışındaki kapsayan kapsamın adları.

- Bağımlı adlar olarak bilinen, bir şekilde şablon bağımsız değişkenlerine bağımlı olan adlar.

İlk iki ad, sınıf ve işlev kapsamlarıyla ilgili olsa da, bağımlı adların ek karmaşıklığını gidermek için şablon tanımlarından ad çözümlemeye yönelik özel kurallar gereklidir. Bunun nedeni, derleyicinin şablon örneği oluşturulana dek adlarla ilgili çok az şey bilmesidir; çünkü hangi şablon bağımsız değişkenlerinin kullanıldığına bağlı olarak tamamen farklı olabilirler. Bağımlı olmayan adlar, normal kurallara göre ve şablon tanımlarken aranır. Şablon bağımsız değişkenlerinden bağımsız olan bu adlar, tüm şablon uzmanlıkları için bir kez aranır. Bağımlı adlar, şablon örneği oluşturulana dek aranmaz ve her uzmanlık için ayrı olarak aranır.

Bir tür, şablon bağımsız değişkenlerine bağlıysa bağımlıdır. Bir tür, özellikle şu koşullarda bağımlıdır:

- Şablon bağımsız değişkeni:

    ```cpp
    T
    ```

- Bağımlı türü içeren bir niteliğe sahip tam ad:

    ```cpp
    T::myType
    ```

- Nitelenmemiş bölüm bağımlı bir türü tanımlıyorsa tam ad:

    ```cpp
    N::T
    ```

- Temel türün bağımlı bir tür olduğu const veya volatile türü:

    ```cpp
    const T
    ```

- Bağımı türü temel alan bir işaretçi, başvuru, dizi ya da işlev işaretçisi türü:

    ```cpp
    T *, T &, T [10], T (*)()
    ```

- Boyutu bir şablon parametresini temel alan bir dizi:

    ```cpp
    template <int arg> class X {
    int x[arg] ; // dependent type
    }
    ```

- bir şablon parametresinden oluşturulan şablon türü:

    ```cpp
    T<int>, MyTemplate<T>
    ```

## <a name="type-dependence-and-value-dependence"></a>Tür Bağımlılığı ve Değer Bağımlılığı

Şablon parametresine bağımlı olan adlar ve ifadeler, şablon parametresinin bir tür parametresi mi, yoksa bir değer parametresi mi olduğuna bağlı olarak türe bağımlı veya değere bağımlı şeklinde kategorilere ayrılır. Ayrıca, değere bağımlı bir ifadeyle başlatılan bir integral veya numaralandırma türünde olduğu gibi şablon bağımsız değişkenine bağımlı bir türle bir şablonda bildirilen tüm tanımlayıcılar değere bağımlı olarak kabul edilir.

Türe bağımlı ve değere bağımlı ifadeler, türe bağımlı veya değere bağımlı değişkenler içeren ifadelerdir. Bu ifadeler, şablon için kullanılan parametrelere göre farklı semantiklere sahip olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Şablonlar](../cpp/templates-cpp.md)