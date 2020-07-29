---
title: Düzenlenmiş Adlar
ms.date: 09/05/2018
helpviewer_keywords:
- decorated names, definition
- name decoration [C++]
- names [C++], decorated
ms.assetid: a4e9ae8e-b239-4454-b401-4102793cb344
ms.openlocfilehash: 20e7f5855b771caf23217e5c17db50a890e28113
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223856"
---
# <a name="decorated-names"></a>Düzenlenmiş Adlar

C ve C++ programlarındaki işlevler, veriler ve nesneler kendi kendilerini düzenlenmiş adlarıyla temsil edilir. *Düzenlenmiş bir ad* , bir nesne, veri veya işlev tanımının derlenmesi sırasında derleyici tarafından oluşturulan kodlanmış bir dizedir. Kural, tür, işlev parametreleri ve diğer bilgileri birlikte çağıran bir adla kaydeder. *Ad değiştirmeyi*olarak da bilinen bu ad dekorasyonu, bağlayıcının bir yürütülebilir dosyayı bağlarken doğru işlevleri ve nesneleri bulmasına yardımcı olur.

Düzenlenmiş adlandırma kuralları, Visual Studio 'nun çeşitli sürümlerinde değiştirilmiştir ve farklı hedef mimarilerde de farklı olabilir. Visual Studio kullanılarak oluşturulan kaynak dosyalarla doğru bir şekilde bağlantı sağlamak için C ve C++ dll 'Leri ve kitaplıkları aynı derleyici araç takımı, bayraklar ve hedef mimari kullanılarak derlenmelidir.

> [!NOTE]
> Visual Studio 2015 ile oluşturulan kitaplıklar, Visual Studio 2017 veya Visual Studio 2019 ile oluşturulmuş uygulamalar tarafından kullanılabilir.

## <a name="using-decorated-names"></a><a name="Using"></a>Düzenlenmiş adlar kullanma

Normal olarak, derlenen ve başarıyla bağlanan kodu yazmak için düzenlenmiş adı bilmeniz gerekmez. Düzenlenmiş adlar, derleyici ve bağlayıcının iç bir uygulama ayrıntısıyla yapılır. Araçlar genellikle adı kendi kendine ait olmayan biçimde işleyebilir. Ancak, bağlayıcı ve diğer araçlara bir işlev adı belirttiğinizde, bazen düzenlenmiş bir ad gerekir. Örneğin, aşırı yüklenmiş C++ işlevleri, ad alanları, sınıf oluşturucular, Yıkıcılar ve özel üye işlevleri ile eşleştirmek için, düzenlenmiş adı belirtmeniz gerekir. Seçenek bayrakları ve düzenlenmiş adlar gerektiren diğer durumlar hakkında daha fazla bilgi için, kullandığınız araçlar ve seçenekler için belgelere bakın.

İşlev adı, sınıf, çağırma kuralı, dönüş türü veya herhangi bir parametreyi değiştirirseniz, düzenlenmiş ad de değişir. Bu durumda, yeni düzenlenmiş adı almalısınız ve düzenlenmiş adın belirtildiği her yerde kullanmanız gerekir.

Ad dekorasyonu, diğer programlama dillerinde yazılmış veya diğer derleyicilerin kullanıldığı koda bağlanırken de önemlidir. Farklı derleyiciler farklı ad dekorasyon kuralları kullanır. Yürütülebilir dosya, başka bir dilde yazılmış kodla bağlantılarsa, aktarılan ve içeri aktarılan adları ve çağırma kurallarını eşleştirmek için özel dikkatli olunması gerekir. Derleme dili kodu, MSVC kullanılarak yazılmış kaynak koda bağlantı sağlamak için MSVC ile düzenlenmiş adları ve çağırma kurallarını kullanmalıdır.

## <a name="format-of-a-c-decorated-name"></a><a name="Format"></a>C++ ile düzenlenmiş adın biçimi

C++ işlevi için düzenlenmiş bir ad aşağıdaki bilgileri içerir:

- İşlev adı.

- Bir üye işleviniz ise, işlevin üyesi olduğu sınıf. Bu, işlevi içeren sınıfını kapsayan sınıfı içerebilir ve bu şekilde devam eder.

- Bir ad alanının parçasıysa işlevin ait olduğu ad alanı.

- İşlev parametrelerinin türleri.

- Çağırma kuralı.

- İşlevin dönüş türü.

İşlev ve sınıf adları, düzenlenmiş adda kodlanır. Düzenlenmiş adın geri kalanı yalnızca derleyici ve bağlayıcı için iç anlamı olan bir koddur. Aşağıda, süslenmiş ve düzenlenmiş C++ adlarının örnekleri verilmiştir.

|Süslenmiş ad|Düzenlenmiş ad|
|----------------------|--------------------|
|`int a(char){int i=3;return i;};`|`?a@@YAHD@Z`|
|`void __stdcall b::c(float){};`|`?c@b@@AAGXM@Z`|

## <a name="format-of-a-c-decorated-name"></a><a name="FormatC"></a>C ile düzenlenmiş adın biçimi

Bir C işlevinin dekoratinin biçimi, aşağıdaki tabloda gösterildiği gibi bildiriminde kullanılan çağırma kuralına bağlıdır. Bu Ayrıca, C++ kodu bağlantısına sahip olacak şekilde bildirildiğinde kullanılan dekoronun biçimidir `extern "C"` . Varsayılan çağırma kuralı **`__cdecl`** . 64 bitlik bir ortamda işlevler tasarlanmadığını unutmayın.

|Çağırma kuralı|Düzenlemenin|
|------------------------|----------------|
|**`__cdecl`**|Baştaki alt çizgi ( **`_`** )|
|**`__stdcall`**|Baştaki alt çizgi ( **`_`** ) ve sondaki işareti ( **`@`** ), ardından parametre listesindeki bayt sayısı ile ondalık olarak|
|**`__fastcall`**|Baştaki ve sondaki işaretleri ( **`@`** ), ardından parametre listesindeki bayt sayısını temsil eden bir ondalık sayı izler|
|**`__vectorcall`**|İki sonda işareti ( **`@@`** ), ardından parametre listesinde ondalık sayı|

## <a name="viewing-decorated-names"></a><a name="Viewing"></a>Düzenlenmiş adları görüntüleme

Veri, nesne veya işlev tanımı ya da prototipi içeren kaynak dosyayı derledikten sonra sembol adının düzenlenmiş biçimini alabilirsiniz. Programınızda düzenlenmiş adları incelemek için aşağıdaki yöntemlerden birini kullanabilirsiniz:

#### <a name="to-use-a-listing-to-view-decorated-names"></a>Düzenlenmiş adları görüntülemek için bir liste kullanmak

1. Veri, nesne veya işlev tanımı ya da prototip içeren kaynak dosyayı, kaynak kodu (**/Fas**) olan derleme olarak ayarlanmış şekilde ayarlayarak [bir liste oluşturun](fa-fa-listing-file.md) .

   Örneğin, bir `cl /c /FAs example.cpp` liste dosyası oluşturmak için bir geliştirici komut istemine girin, örneğin. asm.

2. Elde edilen liste dosyasında, genel ile başlayan satırı bulun ve ardından, bir noktalı virgülden sonra, açıklanarak verilerin veya işlev adının sonuna kadar sonlandırır. ORTAK ve noktalı virgül arasındaki simge, düzenlenmiş addır.

#### <a name="to-use-dumpbin-to-view-decorated-names"></a>Düzenlenmiş adları görüntülemek için DUMPBIN 'i kullanmak için

1. Bir. obj veya. lib dosyasında, içe aktarılmış sembolleri görmek için, `dumpbin /symbols` `objfile` bir geliştirici komut istemine girin.

2. Bir simgenin düzenlenmiş biçimini bulmak için, parantez içinde açıklanedilmemiş adı arayın. Düzenlenmiş ad, bir kanal (&#124;) karakterinden sonra ve ardışık olmayan ad ile aynı satırda bulunur.

## <a name="viewing-undecorated-names"></a><a name="Undecorated"></a>Açıklanmamalıdır adları görüntüleme

Düzenlenmiş bir adı kendi kendine ait olmayan biçime dönüştürmek için undname.exe kullanabilirsiniz. Bu örnekte nasıl çalıştığı gösterilmektedir:

```
C:\>undname ?func1@a@@AAEXH@Z
Microsoft (R) C++ Name Undecorator
Copyright (C) Microsoft Corporation. All rights reserved.

Undecoration of :- "?func1@a@@AAEXH@Z"
is :- "private: void __thiscall a::func1(int)"
```

## <a name="see-also"></a>Ayrıca bkz.

[Ek MSVC derleme araçları](c-cpp-build-tools.md)<br/>
[Bağlantıyı Belirtmek için extern Kullanma](../../cpp/using-extern-to-specify-linkage.md)
