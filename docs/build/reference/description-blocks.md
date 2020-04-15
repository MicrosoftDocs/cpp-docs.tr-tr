---
title: Açıklama blokları
description: NMAKE, bir makefiledeki hedefleri, bağımlılıkları ve komutları ilişkilendirmek için açıklama bloklarını kullanır.
ms.date: 10/29/2019
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
ms.openlocfilehash: e4e80b59d3d30b3b34c55b40d337ef5c078e6404
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322257"
---
# <a name="description-blocks"></a>Açıklama blokları

Açıklama blokları bir makefilenin çekirdeğini oluşturur. *Hedefleri*veya oluşturulacak dosyaları ve *bunların bağımlılıklarını,* hedefleri oluşturmak için gereken dosyaları açıklarlar. Açıklama bloğu, bağımlılıklardan hedeflerin nasıl oluşturulabileceğini açıklayan *komutlar*içerebilir. Açıklama bloğu, isteğe bağlı olarak komutbloğu tarafından izlenen bir bağımlılık çizgisidir:

```makefile
targets... : dependents...
    commands...
```

## <a name="dependency-lines"></a>Bağımlılık çizgileri

*Bağımlılık satırı* bir veya daha fazla hedef ve sıfır veya daha fazla bağımlı belirtir. Bir hedef yoksa veya bağımlı dan daha erken bir zaman damgası varsa, NMAKE komut bloğundaki komutları yürütür. Hedef [sözde hedef](pseudotargets.md)ise NMAKE komut bloğunu da yürütür. Aşağıda bir örnek bağımlılık satırı verilmiştir:

```makefile
hi_bye.exe : hello.obj goodbye.obj helper.lib
```

Bu bağımlılık satırında, `hi_bye.exe` hedeftir. Bağımlılıkları `hello.obj`, `goodbye.obj`ve `helper.lib`. Bağımlılık satırı NMAKE'e hedefi oluşturmasını `hello.obj` `goodbye.obj`söyler, `helper.lib` ne zaman `hi_bye.exe`, ne zaman , veya daha yakın zamanda değişti .

Bir hedef hattın başında olmalıdır. Herhangi bir boşluk veya sekmeyle girintisi olamaz. Hedefleri bağımlılardan`:`ayırmak için bir iki nokta üst üste ( ) kullanın. Boşluklar veya sekmeler hedefler, iki nokta`:`üst üste ayırıcı ( ), ve bağımlıları arasında izin verilir. Bağımlılık çizgisini bölmek için, hedeften`\`veya bağımlıdan sonra ters eğik çizgi () kullanın.

Komut bloklarını yürütmeden önce, NMAKE bağımlılık *ağacı*oluşturmak için tüm bağımlılıkları ve geçerli çıkarım kurallarını tarar. Bağımlılık ağacı, hedefi tam olarak güncelleştirmek için gereken adımları belirtir. NMAKE, bağımlının başka bir bağımlılık listesinde hedef olup olmadığını özyinelemeli olarak denetler. Bağımlılık ağacını inşa ettikten sonra, NMAKE zaman damgalarını denetler. Ağaçtaki bağımlılar hedeften daha yeniyse, Hedefi NMAKE oluşturur.

## <a name="targets"></a><a name="targets"></a>Hedef

Bağımlılık satırının hedefler bölümü bir veya daha fazla hedef belirtir. Hedef herhangi bir geçerli dosya adı, dizin adı veya [pseudotarget](pseudotargets.md)olabilir. Bir veya daha fazla boşluk veya sekme kullanarak birden çok hedefi ayırın. Hedefler büyük/küçük harf duyarlı değildir. Dosya adlarıyla yollara izin verilir. Bir hedef ve yolu 256 karakteri geçemez. Üst üste gelen hedef tek bir karakterse, ayıran boşluk kullanın. Aksi takdirde, NMAKE bir sürücü belirtimi olarak harf-kolon kombinasyonu yorumlar.

### <a name="multiple-targets"></a><a name="multiple-targets"></a>Birden çok hedef

NMAKE, her biri ayrı bir açıklama bloğunda belirtilmiş gibi tek bir bağımlılıkta birden çok hedefi değerlendirir.

Örneğin, bu kural:

```makefile
bounce.exe leap.exe : jump.obj
   echo Building...
```

olarak değerlendirilir:

```makefile
bounce.exe : jump.obj
   echo Building...

leap.exe : jump.obj
   echo Building...
```

### <a name="cumulative-dependencies"></a><a name="cumulative-dependencies"></a>Kümülatif bağımlılıklar

Bir hedef yinelenirse, bağımlılıklar bir açıklama bloğunda birikmelidir.

Örneğin, bu kurallar kümesi,

```makefile
bounce.exe : jump.obj
bounce.exe : up.obj
   echo Building bounce.exe...
```

olarak değerlendirilir:

```makefile
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

Tek bir açıklama bloğunda birden çok bağımlılık satırında birden çok hedefiniz varsa, NMAKE bunları her biri ayrı bir açıklama bloğunda belirtilmiş gibi değerlendirir. Ancak, yalnızca son bağımlılık satırındaki hedefler komutbloğunu kullanır. NMAKE diğer hedefler için bir çıkarım kuralı kullanmaya çalışır.

Örneğin, bu kurallar kümesi,

```makefile
leap.exe bounce.exe : jump.obj
bounce.exe climb.exe : up.obj
   echo Building bounce.exe...
```

olarak değerlendirilir:

```makefile
leap.exe : jump.obj
# invokes an inference rule

bounce.exe : jump.obj up.obj
   echo Building bounce.exe...

climb.exe : up.obj
   echo Building bounce.exe...
```

### <a name="targets-in-multiple-description-blocks"></a><a name="targets-in-multiple-description-blocks"></a>Birden çok açıklama bloğundaki hedefler

Bir hedefi farklı komutlar kullanarak birden fazla açıklama bloğunda güncelleştirmek için art arda iki nokta üst üste (::) hedefler ve bağımlılar arasında.

```makefile
target.lib :: one.asm two.asm three.asm
    ml one.asm two.asm three.asm
    lib target one.obj two.obj three.obj
target.lib :: four.c five.c
    cl /c four.c five.c
    lib target four.obj five.obj
```

### <a name="dependency-side-effects"></a><a name="dependency-side-effects"></a>Bağımlılık yan etkileri

Bir iki nokta üst üste bir hedef belirtebilirsiniz (:) farklı konumlarda iki bağımlılık satırında. Komutlar satırlardan yalnızca birinden sonra görünürse, NMAKE bağımlılıkları satırlar bitişik veya birleştirilmiş gibi yorumlar. Komutları olmayan bağımlılık için çıkarım kuralı nı çağırmaz. Bunun yerine, NMAKE bağımlılıkların bir açıklama bloğuna ait olduğunu varsayar ve diğer bağımlılıkla belirtilen komutları yürütür. Bu kurallar kümesini göz önünde bulundurun:

```makefile
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
```

olarak değerlendirilir:

```makefile
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

Çift kolon (`::`) kullanılırsa bu etki oluşmaz. Örneğin, bu kurallar kümesi:

```makefile
bounce.exe :: jump.obj
   echo Building bounce.exe...

bounce.exe :: up.obj
```

olarak değerlendirilir:

```makefile
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
# invokes an inference rule
```

### <a name="pseudotargets"></a><a name="pseudotargets"></a>Sözde hedefler

*Sözde hedef,* bağımlılık satırındaki bir dosya adının yerine kullanılan bir etikettir. Var olmayan bir dosya olarak yorumlanır, ve bu yüzden güncel değildir. NMAKE, bir sözde hedefin zaman damgasının tüm bağımlılarının en sonuncusuyla aynı olduğunu varsayar. Bağımlısı yoksa, geçerli saat varsayılılır. Sözde hedef hedef olarak kullanılırsa, komutları her zaman yürütülür. Bağımlı olarak kullanılan bir sözde hedef, başka bir bağımlılıkta hedef olarak da görünmelidir. Ancak, bu bağımlılık bir komutbloğu olması gerekmez.

Pseudotarget adları hedefler için dosya adı sözdizimi kurallarını izler. Ancak, adında bir uzantı yoksa, dosya adları için 8 karakter sınırını aşabilir ve en fazla 256 karakter uzunluğunda olabilir.

Sözde hedefler, NMAKE'nin otomatik olarak birden fazla hedef oluşturmasını istediğinizde yararlıdır. NMAKE yalnızca komut satırında belirtilen hedefleri oluşturur. Veya, komut satırı hedefi belirtilmemişse, makefiledeki ilk bağımlılıkta yalnızca ilk hedefi oluşturur. NMAKE'e, komut satırında tek tek listelemeden birden çok hedef oluşturmasını söyleyebilirsiniz. Sözde hedef içeren bir bağımlılık içeren bir açıklama bloğu yazın ve oluşturmak istediğiniz hedefleri bağımlıları olarak listele. Ardından, bu açıklama bloğunu önce makefile'ye yerleştirin veya NMAKE komut satırındaki sözde hedefi belirtin.

Bu örnekte, UPDATE bir sözde hedeftir.

```makefile
UPDATE : *.*
!COPY $** c:\product\release
```

UPDATE değerlendirildiğinde, NMAKE geçerli dizindeki tüm dosyaları belirtilen sürücü ve dizin için kopyalar.

Aşağıdaki makefilede, sözde `all` hedef her `project1.exe` `project2.exe` ikisini `all` de oluşturur ve komut satırında hedeften biri veya hiç belirtilmemişse. Sözde hedef, `setenv` dosyalar güncelleştirilmeden `.exe` önce LIB ortamı değişkenini değiştirir:

```makefile
all : setenv project1.exe project2.exe

project1.exe : project1.obj
    LINK project1;

project2.exe : project2.obj
    LINK project2;

setenv :
    set LIB=\project\lib
```

## <a name="dependents"></a><a name="dependents"></a>Bağımlı

Bağımlılık satırında, geçerli bir dosya adı veya`:` [pseudotarget](pseudotargets.md)kullanarak`::`iki nokta üst üste ( ) veya çift üst üste (), sonra sıfır veya daha fazla bağımlı belirtin. Bir veya daha fazla boşluk veya sekme kullanarak birden çok bağımlıyı ayırın. Bağımlılar vakaya duyarlı değildir. Dosya adlarıyla yollara izin verilir.

### <a name="inferred-dependents"></a><a name="inferred-dependents"></a>Çıkarılan bağımlılar

Bağımlılık satırında açıkça listelediğiniz bağımlılarla birlikte, NMAKE çıkarılan bir *bağımlı*yı varsayabilir. Çıkarım bağımlısı bir çıkarım kuralından türetilir ve açık bağımlılardan önce değerlendirilir. Çıkarılan bir bağımlı hedefiyle karşılaştırıldığında güncel olmadığında, NMAKE bağımlılık için komut bloğunu çağırır. Çıkarılan bir bağımlı yoksa veya kendi bağımlılarına göre güncel değilse, NMAKE ilk olarak çıkarılan bağımlıyı güncelleştirir. Çıkarılan bağımlılar hakkında daha fazla bilgi için [Çıkarım kurallarına](inference-rules.md)bakın.

### <a name="search-paths-for-dependents"></a><a name="search-paths-for-dependents"></a>Bağımlılar için arama yolları

Bağımlı her biri için isteğe bağlı bir arama yolu belirtebilirsiniz. Arama yapmak için bir dizi dizin belirtmek için sözdizimi aşağıda veda eder:

> **{**_dizin_\[**;** _dizin_...] **}**_bağımlı_

Dizin adlarını ayraçlara`{ }`ekle ( ). Bir yarı kolon ile ayrı`;`birden fazla dizin ( ). Boşluk veya sekme lere izin verilmez. NMAKE, geçerli dizinde önce bağımlıyı, daha sonra belirtilen sırada dizinler listesinde arar. Bir arama yolunun bir kısmını veya tamamını belirtmek için makro kullanabilirsiniz. Yalnızca belirtilen bağımlı bu arama yolunu kullanır.

#### <a name="directory-search-path-example"></a>Dizin arama yolu örneği

Bu bağımlılık satırı, arama için dizin belirtiminin nasıl oluşturulabildiğini gösterir:

```makefile
reverse.exe : {\src\omega;e:\repo\backwards}retro.obj
```

Hedefin `reverse.exe` bir bağımlısı `retro.obj`var. Ayraç ekteki liste iki dizin belirtir. NMAKE ilk `retro.obj` geçerli dizinde arar. Orada değilse, NMAKE `\src\omega` dizini arar, sonra `e:\repo\backwards` dizin.

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE Referans](nmake-reference.md)
