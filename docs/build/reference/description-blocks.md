---
title: Açıklama blokları
description: NMAKE, bir Makefile içindeki hedefleri, bağımlılıkları ve komutları ilişkilendirmek için açıklama blokları kullanır.
ms.date: 10/29/2019
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
ms.openlocfilehash: fb9cf4400c96b588e8704e972dd29ab27f41cae9
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856942"
---
# <a name="description-blocks"></a>Açıklama blokları

Açıklama blokları, derleme görevleri dosyasının çekirdeğini oluşturur. *Hedefleri veya*oluşturulacak dosyaları ve bunların *bağımlılıklarını*, hedefleri oluşturmak için gereken dosyaları tanımlarlar. Bir açıklama bloğu, bağımlılıklardan hedefleri oluşturmayı betimleyen *komutları*içerebilir. Açıklama bloğu, isteğe bağlı olarak bir komut bloğu tarafından izlenen bir bağımlılık hatlığıdır:

```makefile
targets... : dependents...
    commands...
```

## <a name="dependency-lines"></a>Bağımlılık çizgileri

Bir *bağımlılık çizgisi* , bir veya daha fazla hedefi ve sıfır veya daha fazla bağımlılığı belirtir. Bir hedef yoksa veya daha önce bağımlı bir zaman damgasına sahipse NMAKE komutları komut bloğunda yürütür. NMAKE, hedef bir [sözde hedef](pseudotargets.md)ise, komut bloğunu de yürütür. Aşağıda örnek bir bağımlılık satırı verilmiştir:

```makefile
hi_bye.exe : hello.obj goodbye.obj helper.lib
```

Bu bağımlılık satırında `hi_bye.exe` hedeftir. Bağımlılıkları `hello.obj`, `goodbye.obj`ve `helper.lib`. Bağımlılık çizgisi, `hello.obj`, `goodbye.obj`veya `helper.lib` `hi_bye.exe`'tan daha yeni bir kez değiştirildiğinde, NMAKE 'in hedefi oluşturmasını söyler.

Bir hedefin satırın başlangıcında olması gerekir. Boşluk veya sekme ile girintilenebilir. Hedefleri bağımlılardan ayırmak için iki nokta üst üste (`:`) kullanın. Hedefler, iki nokta ayırıcısı (`:`) ve bağımlılar arasında boşluk veya sekmeye izin verilir. Bağımlılık çizgisini ayırmak için bir hedefin veya bağımlı bir ters eğik çizgi (`\`) kullanın.

Komut bloklarını yürütmeden önce NMAKE, *bağımlılık ağacı*oluşturmak için tüm bağımlılıkları ve ilgili tüm çıkarım kurallarını tarar. Bir bağımlılık ağacı, hedefi tamamen güncelleştirmek için gereken adımları belirtir. NMAKE, bir bağımlı, başka bir bağımlılık listesindeki bir hedef olup olmadığını yinelemeli olarak denetler. Bağımlılık ağacını oluşturduktan sonra NMAKE, zaman damgalarını denetler. Ağaçtaki herhangi bir bağımlı, hedeften daha yeniyse, NMAKE hedefi oluşturur.

## <a name="targets"></a>Lerden

Bir bağımlılık satırının hedefler bölümü bir veya daha fazla hedef belirtir. Hedef herhangi bir geçerli dosya adı, dizin adı veya [sözde hedef](pseudotargets.md)olabilir. Birden çok hedefi bir veya daha fazla boşluk veya sekme kullanarak ayırın. Hedefler büyük/küçük harfe duyarlı değildir. Dosya adlarıyla yollara izin verilir. Hedef ve yolu 256 karakterden uzun olamaz. İki nokta üst üste gelen hedef tek bir karakter ise, ayrılan alan kullanın. Aksi halde NMAKE, harf iki nokta bileşimini bir sürücü tanımlayıcısı olarak yorumlar.

### <a name="multiple-targets"></a>Birden çok hedef

NMAKE, her biri ayrı bir açıklama bloğunda belirtilmiş gibi birden çok hedefi tek bir bağımlılığa göre değerlendirir.

Örneğin, bu kural:

```makefile
bounce.exe leap.exe : jump.obj
   echo Building...
```

şöyle değerlendirilir:

```makefile
bounce.exe : jump.obj
   echo Building...

leap.exe : jump.obj
   echo Building...
```

### <a name="cumulative-dependencies"></a>Birikmeli bağımlılıklar

Bir hedef tekrarlandığında, bir açıklama bloğunda bağımlılıklar birikimlidir.

Örneğin, bu kurallar kümesi,

```makefile
bounce.exe : jump.obj
bounce.exe : up.obj
   echo Building bounce.exe...
```

şöyle değerlendirilir:

```makefile
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

Tek bir açıklama bloğunda birden çok bağımlılık satırı içinde birden çok hedef olduğunda NMAKE, her biri ayrı bir açıklama bloğunda belirtilmiş gibi değerlendirilir. Ancak, yalnızca son bağımlılık satırındaki hedefler, komutlar bloğunu kullanır. NMAKE diğer hedefler için bir çıkarım kuralı kullanmaya çalışır.

Örneğin, bu kurallar kümesi,

```makefile
leap.exe bounce.exe : jump.obj
bounce.exe climb.exe : up.obj
   echo Building bounce.exe...
```

şöyle değerlendirilir:

```makefile
leap.exe : jump.obj
# invokes an inference rule

bounce.exe : jump.obj up.obj
   echo Building bounce.exe...

climb.exe : up.obj
   echo Building bounce.exe...
```

### <a name="targets-in-multiple-description-blocks"></a>Birden çok açıklama bloklarında hedefler

Farklı komutlar kullanarak birden fazla açıklama bloğunda bir hedefi güncelleştirmek için iki ardışık çift nokta (::)) belirtin hedefler ve bağımlılıklar arasında.

```makefile
target.lib :: one.asm two.asm three.asm
    ml one.asm two.asm three.asm
    lib target one.obj two.obj three.obj
target.lib :: four.c five.c
    cl /c four.c five.c
    lib target four.obj five.obj
```

### <a name="dependency-side-effects"></a>Bağımlılık yan etkileri

İki nokta üst üste (:)) bir hedef belirtebilirsiniz iki bağımlılık satırı içinde farklı konumlarda. Komutlar yalnızca bir satırdan sonra görünürse, NMAKE, çizgileri satır bitişik veya birleştirilmiş olarak yorumlar. Komutu olmayan bağımlılık için bir çıkarım kuralı çağırmaz. Bunun yerine, NMAKE bağımlılıkların bir açıklama bloğuna ait olduğunu varsayar ve diğer bağımlılıkla belirtilen komutları yürütür. Bu kural kümesini göz önünde bulundurun:

```makefile
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
```

şöyle değerlendirilir:

```makefile
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

Çift iki nokta (`::`) kullanılırsa bu efekt oluşmaz. Örneğin, bu kurallar kümesi:

```makefile
bounce.exe :: jump.obj
   echo Building bounce.exe...

bounce.exe :: up.obj
```

şöyle değerlendirilir:

```makefile
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
# invokes an inference rule
```

### <a name="pseudotargets"></a>Sözde hedefler

*Sözde hedef* , bir bağımlılık satırındaki dosya adı yerine kullanılan bir etikettir. Mevcut olmayan bir dosya olarak yorumlanır ve bu nedenle güncel değildir. NMAKE, sözde hedefin zaman damgasının, tüm bağımlılarından en son ile aynı olduğunu varsayar. Bağımlı değilse, geçerli zaman varsayılır. Bir sözde hedef, hedef olarak kullanılıyorsa, komutları her zaman yürütülür. Bağımlı olarak kullanılan bir sözde hedef, başka bir bağımlılıkta hedef olarak da görünmelidir. Ancak, bu bağımlılığın bir komut bloğuna sahip olması gerekmez.

Sözde hedef adları, hedefler için dosya adı sözdizimi kurallarını izler. Ancak, adın bir uzantısı yoksa, dosya adları için 8 karakterlik sınırı aşabilir ve en fazla 256 karakter uzunluğunda olabilir.

Sözde hedefler, NMAKE 'in birden fazla hedefi otomatik olarak oluşturmasını istediğinizde faydalıdır. NMAKE yalnızca komut satırında belirtilen hedefleri oluşturur. Ya da hiçbir komut satırı hedefi belirtilmemişse, derleme görevleri dosyasının ilk bağımlılığında yalnızca ilk hedefi oluşturur. NMAKE 'e, komut satırında ayrı ayrı listelemeden birden çok hedef oluşturmasını söyleyebilirsiniz. Sözde hedef içeren bir bağımlılığı olan bir açıklama bloğu yazın ve bağımlılığı olarak derlemek istediğiniz hedefleri listeleyin. Ardından, bu açıklama bloğunu önce derleme görevleri dosyasına yerleştirin veya NMAKE komut satırında sözde hedefi belirtin.

Bu örnekte, UPDATE sözde bir hedeftir.

```makefile
UPDATE : *.*
!COPY $** c:\product\release
```

GÜNCELLEŞTIRME değerlendirildiğinde, NMAKE geçerli dizindeki tüm dosyaları belirtilen sürücü ve dizine kopyalar.

Aşağıdaki derleme görevleri dosyasında, sözde hedef `all`, komut satırında `all` veya hiçbir hedef belirtilmemişse hem `project1.exe` hem de `project2.exe` oluşturur. Sözde hedef `setenv`, `.exe` dosyalar güncelleştirildikten sonra LıB ortam değişkenini değiştirir:

```makefile
all : setenv project1.exe project2.exe

project1.exe : project1.obj
    LINK project1;

project2.exe : project2.obj
    LINK project2;

setenv :
    set LIB=\project\lib
```

## <a name="dependents"></a>Uyar

Bir bağımlılık satırında, herhangi bir geçerli dosya adı veya [sözde hedef](pseudotargets.md)kullanarak, iki nokta üst üste (`:`) veya iki nokta üst üste (`::`) sonra sıfır veya daha fazla bağımlı belirtin. Bir veya daha fazla boşluk veya sekme kullanarak birden çok etkilenenleri ayırın. Bağımlılar büyük/küçük harfe duyarlı değildir. Dosya adlarıyla yollara izin verilir.

### <a name="inferred-dependents"></a>Gösterilen etkilenenler

Bağımlılık satırında açıkça listeettiğiniz bağımlılarla birlikte, NMAKE, *gösterilen bir bağımlı*olduğunu varsayabilir. Çıkarılan bir bağımlı, çıkarım kuralından türetilir ve açık bağımlılardan önce değerlendirilir. Çıkarılan bir bağımlı, hedefine kıyasla güncel olmadığında NMAKE, bağımlılık için komut bloğunu çağırır. Çıkarsanan bağımlı yoksa veya kendi bağımlılarına kıyasla güncel değilse, NMAKE önce gösterilen bağımlı ' ı günceller. Çıkartılan bağımlılar hakkında daha fazla bilgi için bkz. [çıkarım kuralları](inference-rules.md).

### <a name="search-paths-for-dependents"></a>Bağımlılıklar için arama yolları

Her bağımlı için isteğe bağlı bir arama yolu belirtebilirsiniz. Aranacak Dizin kümesini belirten sözdizimi aşağıda verilmiştir:

> **{** _Dizin_\[ **;** _Dizin_...] **}** _bağımlı_

Dizin adlarını ayraç içine alın (`{ }`). Birden çok dizini noktalı virgülle ayırın (`;`). Boşluk veya sekmeye izin verilmez. NMAKE, ilk olarak geçerli dizinde ve ardından dizin listesinde belirtilen sırada bağlı olarak görünür. Bir arama yolunun bir kısmını veya tamamını belirtmek için bir makro kullanabilirsiniz. Yalnızca belirtilen bağımlı bu arama yolunu kullanır.

#### <a name="directory-search-path-example"></a>Dizin arama yolu örneği

Bu bağımlılık satırı, bir arama için Dizin belirtiminin nasıl oluşturulacağını gösterir:

```makefile
reverse.exe : {\src\omega;e:\repo\backwards}retro.obj
```

Hedef `reverse.exe` bir bağımlı `retro.obj`sahip. Küme ayracı içine alınmış liste iki dizin belirtir. NMAKE önce geçerli dizinde `retro.obj` arar. Orada yoksa, NMAKE `\src\omega` dizininde ve sonra `e:\repo\backwards` dizininde arama yapar.

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE Başvurusu](nmake-reference.md)
