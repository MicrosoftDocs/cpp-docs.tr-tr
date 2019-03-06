---
title: Düzenlenmiş Adlar
ms.date: 09/05/2018
helpviewer_keywords:
- decorated names, definition
- name decoration [C++]
- names [C++], decorated
ms.assetid: a4e9ae8e-b239-4454-b401-4102793cb344
ms.openlocfilehash: d9d3db9a3db1943581e5fd603ba85777cb49b863
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423319"
---
# <a name="decorated-names"></a>Düzenlenmiş Adlar

İşlevleri, verileri ve nesneleri C ve C++ programları, dahili olarak düzenlenmiş adlarıyla gösterilir. A *ile düzenlenmiş adın* bir nesne, veri veya işlev tanımı bir derleme sırasında derleyici tarafından oluşturulan kodlanmış bir dize. Bu, çağırma kuralları, türleri, işlev parametrelerini ve diğer bilgileri adı ile birlikte kaydeder. Olarak da bilinen bu ad düzenlemesi *ad değiştirmeyi*nesneleri bir yürütülebilir dosya bağlanırken ve doğru işlevlerin bulunacağı bağlayıcı yardımcı olur.

Düzenlenmiş adlandırma kuralları çeşitli Visual C++ sürümlerinde değişmiş ve farklı bir hedef mimarilerde farklı da olabilir. Visual C++, C ve C++ DLL'leri ve kitaplıkları kullanılarak oluşturulan kaynak dosyaları ile doğru şekilde bağlamak için aynı derleyici araç takımı, bayraklar ve hedef mimari kullanarak derlenmelidir.

##  <a name="Using"></a> Düzenlenmiş adları kullanma

Normalde, derleme kod yazmak için düzenlenmiş adı ve bağlantı başarıyla bilmeniz gerekmez. İç derleyici ve bağlayıcı için bir uygulama ayrıntısı düzenlenmiş adlarıdır. Araçlar ve biçimde adı genellikle başa çıkabilir. Bağlayıcı ve diğer araçlar için bir işlev adı belirttiğinizde ancak düzenlenmiş adı bazen gereklidir. Örneğin, ad alanları, sınıf Oluşturucular, Yıkıcılar ve özel üye işlevleri, üye aşırı yüklenmiş C++ işlevlerini eşleştirilecek düzenlenmiş adı belirtmeniz gerekir. Düzenlenmiş adları seçeneği bayraklar ve gerektiren diğer durumlar hakkında ayrıntılar için kullanmakta olduğunuz seçenekleri ve Araçları belgelerine bakın.

İşlev adı, sınıf, çağırma kuralı, dönüş türü veya herhangi bir parametre değiştirirseniz düzenlenmiş adı da değişir. Bu durumda, yeni düzenlenmiş adı almak ve her yerde düzenlenmiş adı belirtilen kullanmanız gerekir.

Ad düzenlemesi, ayrıca diğer programlama veya diğer derleyiciler kullanarak içinde yazılan koda bağlarken önemlidir. Farklı derleyiciler farklı ad düzenlemesi kuralları kullanın. Yürütülebilir dosyanın başka bir dilde yazılan koda bağlantılar, dışarı aktarılan ve içeri aktarılan ad ve çağırma kuralları eşleştirmek için özel dikkatli olunması gerekir. Assembly dili kod Visual C++ kullanılarak yazılmış kaynak koda bağlamak için Visual C++ ile düzenlenmiş adları ve çağırma kurallarını kullanmanız gerekir.

##  <a name="Format"></a> İle düzenlenmiş adın biçimi bir C++

Bir C++ işlevi için düzenlenmiş bir ad, aşağıdaki bilgileri içerir:

- İşlev adı.

- Üye işlevi ise işlevi, üyesi olduğu sınıf. Bu işlevini içeren sınıf kapsayan bir sınıf içerir ve benzeri.

- Bir ad alanı bir parçası ise ad işlevi için ait.

- İşlev parametrelerinin türleri.

- Çağırma kuralı.

- İşlev dönüş türü.

İşlev ve sınıf adları düzenlenmiş adı kodlanır. Kalan düzenlenmiş adı, derleyici ve bağlayıcı için yalnızca iç anlamı bir koddur. Tamamlanmamış ve düzenlenmiş C++ adları örnekleri aşağıda verilmiştir.

|Tamamlanmamış adı|Düzenlenmiş adı|
|----------------------|--------------------|
|`int a(char){int i=3;return i;};`|`?a@@YAHD@Z`|
|`void __stdcall b::c(float){};`|`?c@b@@AAGXM@Z`|

##  <a name="FormatC"></a> İle düzenlenmiş adın biçimi c

C işlev için düzenleme formu, bildirimde kullanılan çağırma kuralı aşağıdaki tabloda gösterildiği gibi bağlıdır. C++ kodu için bildirildiğinde kullanılan düzenleme biçimi de budur `extern "C"` bağlantı. Çağırma kuralı varsayılan `__cdecl`. Bir 64-bit ortamında işlevleri değil düzenlenmiş unutmayın.

|Çağırma kuralı|Düzenleme|
|------------------------|----------------|
|`__cdecl`|Önünde alt çizgi (**_**)|
|`__stdcall`|Önünde alt çizgi (**_**) ve sondaki işaretini (**\@**) ondalık parametre listesindeki bayt sayısı ardından|
|`__fastcall`|Baştaki ve sondaki işaretleri (**\@**) parametre listesindeki bayt sayısını temsil eden bir ondalık sayı ardından|
|`__vectorcall`|İki işaretleri sonda (**\@\@**) ondalık parametre listesindeki bayt sayısı ardından|

##  <a name="Viewing"></a> Görüntüleme düzenlenmiş adlar

Verileri, nesne veya işlev tanımı veya prototip içeren kaynak dosyayı derledikten sonra bir sembol adı düzenlenmiş biçiminde alabilirsiniz. Düzenlenmiş adlar programınızdaki incelemek için aşağıdaki yöntemlerden birini kullanabilirsiniz:

#### <a name="to-use-a-listing-to-view-decorated-names"></a>Düzenlenmiş adları görüntülemek için liste kullanma

1. Verileri, nesne veya işlev tanımı veya Prototiple içeren kaynak dosyanın derleme tarafından listesini oluşturmak [listeleme dosya türü](../../build/reference/fa-fa-listing-file.md) kaynak kodlu bütünleştirilmiş kod olarak derleyici seçeneği (**/Fas**).

   Örneğin, `cl /c /FAs example.cpp` bir listeleme dosyası oluşturmak için geliştirici komut isteminde example.asm.

2. Sonuçta ortaya çıkan döküm dosyasında ortak ile başlar ve ardından ve veri veya işlev adı noktalı virgül biten satırını bulun. Genel ve noktalı virgül arasında simge düzenlenmiş bir addır.

#### <a name="to-use-dumpbin-to-view-decorated-names"></a>Düzenlenmiş adları görüntülemek için DUMPBIN kullanma

1. Dışarı aktarılan bir .obj veya .lib dosyası sembolleri görmek için girin `dumpbin /symbols` `objfile` bir geliştirici komut isteminde.

2. Bir simgenin düzenlenmiş formunu bulmak için parantez içinde düzenlenmemiş adını arayın. Düzenlenmiş adı bir kanal sonra aynı satırda olduğu (&#124;) ve adından önce ve karakter.

##  <a name="Undecorated"></a> Adları ve görüntüleme

Düzenlenmiş adları ve kendi biçimine dönüştürmek için undname.exe kullanabilirsiniz. Bu örnek nasıl çalıştığını gösterir:

```
C:\>undname ?func1@a@@AAEXH@Z
Microsoft (R) C++ Name Undecorator
Copyright (C) Microsoft Corporation. All rights reserved.

Undecoration of :- "?func1@a@@AAEXH@Z"
is :- "private: void __thiscall a::func1(int)"
```

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Araçları](../../build/reference/c-cpp-build-tools.md)<br/>
[Bağlantıyı Belirtmek için extern Kullanma](../../cpp/using-extern-to-specify-linkage.md)
