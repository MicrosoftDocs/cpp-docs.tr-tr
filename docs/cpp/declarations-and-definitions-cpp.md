---
title: Bildirimler ve Tanımlar (C++)
ms.date: 11/04/2016
ms.assetid: 678f1424-e12f-45e0-a957-8169e5fef6cb
ms.openlocfilehash: 1e76f636a6efd652ac629ad2f97f0b09f6171f9c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432120"
---
# <a name="declarations-and-definitions-c"></a>Bildirimler ve Tanımlar (C++)

Bildirimleri adları programında, örneğin değişkenler, ad alanları, işlevleri ve sınıfları adlarını tanıtır. Bildirimleri ayrıca tür bilgilerin yanı sıra diğer bildirilmiş nesne özelliklerini belirtin. Bir ad kullanılmadan önce bildirilmelidir; c++'ta, bir ad bildirildiği noktası derleyiciye görünür olup olmadığını belirler. Bir işlev veya derleme biriminde daha sonraki bir noktada bildirilen sınıf başvuramaz; kullanabileceğiniz *iletme bildirimleri* bu sınırlamayı alınamıyor.

Hangi kod veya veri adı açıklar tanımlarını belirtin. Derleme tanımı bildirilmiş şey için depolama alanı ayırdığınızdan olması gerekir.

## <a name="declarations"></a>Bildirimler

Bir bildirimi, bir programa bir veya daha çok sunar. Bildirimleri bir programda birden çok kez gerçekleşebilir. Bu nedenle, sınıflar, yapılar, numaralandırılan türleri ve diğer kullanıcı tanımlı türler için her derleme biriminde bildirilebilir. Bu birden çok bildiriminde tüm bildirimler aynı sınırlamadır. Bildirimleri Ayrıca hizmet tanımları, aşağıdakiler haricinde olarak bildirimi:

1. Bir işlev prototipi (bir işlev bildirimi ile hiçbir işlev gövdesi) olur.

1. İçeren **extern** belirtici ancak hiçbir Başlatıcı (nesneler ve değişkenler) veya işlev gövdesi (işlevler). Bu tanımı geçerli çeviri biriminde olmak zorunda değildir ve adı dış bağlantısı sağlar gösterir.

1. Bir sınıf bildirimi içinde statik veri üyesi değil.

   Statik sınıf veri üyeleri ayrık sınıfın tüm nesneleri tarafından paylaşılan değişkenleri olduğundan, bunlar gerekir tanımlanabilir ve sınıf bildirimi dışında başlatıldı. (Sınıflar ve sınıf üyeleri hakkında daha fazla bilgi için bkz: [sınıfları](../cpp/classes-and-structs-cpp.md).)

1. Aşağıdaki tanım, sınıf adı bildirimiyle olduğu gibi `class T;`.

1. Olan bir **typedef** deyimi.

Ayrıca tanımları, bildirimleri örnekleri şunlardır:

```cpp
// Declare and define int variables i and j.
int i;
int j = 10;

// Declare enumeration suits.
enum suits { Spades = 1, Clubs, Hearts, Diamonds };

// Declare class CheckBox.
class CheckBox : public Control
{
public:
            Boolean IsChecked();
    virtual int     ChangeState() = 0;
};
```

Tanımları olmayan bazı bildirimlerini şunlardır:

```cpp
extern int i;
char *strchr( const char *Str, const char Target );
```

Kendi bildirimci hemen sonra ancak (isteğe bağlı) başlatıcısı önce bildirilmesi için bir ad olarak kabul edilir. Daha fazla bilgi için [bildirim noktası](../cpp/point-of-declaration-in-cpp.md).

Bildirimleri gerçekleştirilir bir *kapsam*. Kapsam bildirilen ad görünürlüğünü ve tanımlı, nesne süresi varsa denetler. Kapsam kuralları bildirimleri ile nasıl etkileşim hakkında daha fazla bilgi için bkz. [kapsam](../cpp/scope-visual-cpp.md).

İçerdiği sürece nesne bildirimi de bir tanımıdır **extern** depolama sınıfı tanımlayıcısı açıklanan [depolama sınıfları](storage-classes-cpp.md). Bir prototip olmadığı sürece bir işlev bildirimi de bir tanımıdır. Bir prototip olmadan tanımlayan bir işlev gövdesi bir işlev üstbilgisi ' dir. Bir nesnenin tanımı, depolama ve bu nesne için uygun başlatmalar ayırma neden olur.

## <a name="definitions"></a>Tanımlar

Bir nesne veya değişkenin, işlev, sınıf veya numaralandırıcı benzersiz bir belirtimi tanımıdır. Bir program, tanımları benzersiz olması gerektiğinden, belirtilen program öğesi için yalnızca bir tanım içerebilir. Bildirimler ve tanımlar arasında çok-bir ilişkiyi olabilir. İçinde bir program öğesi bildirilebileceği ve tanımlı iki durum vardır:

1. Bir işlev bildirildi, ancak bir işlev çağrısıyla veya işlevin adresini alır bir ifadeyle nikdy neodkazovalo.

1. Bir sınıf tanımı bilinir gerektirmeyen bir biçimde kullanılır. Ancak, sınıf bildirilmelidir. Aşağıdaki kod, böyle bir durumda göstermektedir:

    ```cpp
    // definitions.cpp
    class WindowCounter;   // Forward declaration; no definition

    class Window
    {
       // Definition of WindowCounter not required
       static WindowCounter windowCounter;
    };

    int main()
    {
    }
    ```

## <a name="see-also"></a>Ayrıca bkz.

[Temel Kavramlar](../cpp/basic-concepts-cpp.md)<br/>
[Bildirim noktası](../cpp/point-of-declaration-in-cpp.md)