---
title: Düzenlenmiş Adlar
ms.date: 09/05/2018
helpviewer_keywords:
- decorated names, definition
- name decoration [C++]
- names [C++], decorated
ms.assetid: a4e9ae8e-b239-4454-b401-4102793cb344
ms.openlocfilehash: f6d81029d20d9aaca96ff184f48e94a9ce35d56e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320508"
---
# <a name="decorated-names"></a>Düzenlenmiş Adlar

C ve C++ programlarındaki işlevler, veriler ve nesneler, dekore edilmiş adlarıyla dahili olarak temsil edilir. *Dekore edilmiş ad,* derleyici tarafından bir nesnenin, verinin veya işlev tanımının derlemi sırasında oluşturulan kodlanmış bir dizedir. Çağrı kurallarını, türlerini, işlev parametrelerini ve diğer bilgileri adla birlikte kaydeder. Bu ad dekorasyonu, *ad mangling*olarak da bilinir, bağlayıcı bir yürütülebilir bağlanırken doğru işlevleri ve nesneleri bulmanıza yardımcı olur.

Dekore adlandırma kuralları Visual Studio çeşitli sürümlerinde değişti ve aynı zamanda farklı hedef mimarileri farklı olabilir. Visual Studio, C ve C++ DLL'leri kullanılarak oluşturulan kaynak dosyalarla doğru bağlantı kurmak için aynı derleyici araç kümesi, bayraklar ve hedef mimarisi kullanılarak derlenmiş olmalıdır.

> [!NOTE]
> Visual Studio 2015 ile inşa edilen kütüphaneler Visual Studio 2017 veya Visual Studio 2019 ile yapılan uygulamalar tarafından tüketilebilir.

## <a name="using-decorated-names"></a><a name="Using"></a>Dekore edilmiş adları kullanma

Normalde, başarılı bir şekilde derleyen ve bağlantı veren kod yazmak için dekore edilmiş adı bilmeniz gerekir. Dekore edilmiş adlar derleyici ve bağlayıcı için dahili bir uygulama ayrıntısıdır. Araçlar genellikle adını dekore edilmemiş biçiminde işleyebilir. Ancak, bağlayıcıya ve diğer araçlara bir işlev adı belirttiğiniz zaman, süslü bir ad bazen gereklidir. Örneğin, aşırı yüklü C++ işlevlerini, ad alanlarının üyeleri, sınıf yapıcıları, yıkıcıları ve özel üye işlevleri eşleştirmek için, dekore edilmiş adı belirtmeniz gerekir. Seçenek bayrakları ve süslü adlar gerektiren diğer durumlar hakkında ayrıntılar için, kullanmakta olduğunuz araçlar ve seçenekler için belgelere bakın.

İşlev adını, sınıfı, çağrı kuralını, iade türünü veya herhangi bir parametreyi değiştirirseniz, dekore edilen ad da değişir. Bu durumda, yeni dekore adı almak ve dekore adı belirtilen her yerde kullanmanız gerekir.

Ad süslemesi, diğer programlama dillerinde yazılan koda bağlantı verirken veya diğer derleyiciler kullanırken de önemlidir. Farklı derleyiciler farklı isim dekorasyon kuralları kullanın. Başka bir dilde yazılmış koda yürütülebilir bağlantılarınız olduğunda, dışa aktarılan ve alınan adlarla ve çağrı kurallarıyla eşleşecek özel özen gerekir. Derleme dil kodu, MSVC kullanılarak yazılmış kaynak koduna bağlanmak için MSVC dekore edilmiş adları ve çağrı kurallarını kullanmalıdır.

## <a name="format-of-a-c-decorated-name"></a><a name="Format"></a>C++ dekore edilmiş bir ismin biçimi

C++ işlevinin dekore edilmiş adı aşağıdaki bilgileri içerir:

- Işlev adı.

- Bir üye işlev ise, işlevin üyesi olduğu sınıf. Bu, işlevi içeren sınıfı içine alan sınıfı ve benzeri ni içerebilir.

- Ad alanının bir parçasıysa, işlevin ait olduğu ad alanı.

- İşlev parametrelerinin türleri.

- Çağrı sözleşmesi.

- İşlevin dönüş türü.

İşlev ve sınıf adları dekore edilen adla kodlanır. Dekore edilen adın geri kalanı, yalnızca derleyici ve bağlayıcı için iç anlamı olan bir koddur. Aşağıda dekore edilmemiş ve dekore edilmiş C++ adlarının örnekleri verilmiştir.

|Dekore edilmemiş ad|Dekore edilmiş ad|
|----------------------|--------------------|
|`int a(char){int i=3;return i;};`|`?a@@YAHD@Z`|
|`void __stdcall b::c(float){};`|`?c@b@@AAGXM@Z`|

## <a name="format-of-a-c-decorated-name"></a><a name="FormatC"></a>C dekore edilmiş bir ismin biçimi

C işlevi için dekorasyon biçimi, aşağıdaki tabloda gösterildiği gibi, beyannamesinde kullanılan çağrı kuralına bağlıdır. Bu aynı zamanda C++ kodu `extern "C"` bağlantı olarak beyan edildiğinde kullanılan dekorasyon biçimidir. Varsayılan çağrı `__cdecl`kuralı. 64 bit'lik bir ortamda işlevlerin dekore edilemediğini unutmayın.

|Arama kuralı|Dekorasyon|
|------------------------|----------------|
|`__cdecl`|Satır başları (**_**)|
|`__stdcall`|Satır başları (**_**) ve**\@** işareti bir iz ( ) ondalık parametre listesinde bayt sayısı takip|
|`__fastcall`|Parametre listesindeki bayt sayısını temsil eden ondalık sayı ile işaretlerde**\@** öncü ve iz bırakan|
|`__vectorcall`|İki işaret (**\@**) parametre listesinde ki bayt sayısı|

## <a name="viewing-decorated-names"></a><a name="Viewing"></a>Dekore edilmiş adları görüntüleme

Verileri, nesneyi veya işlev tanımını veya prototipini içeren kaynak dosyayı derledikten sonra bir sembol adının dekore edilmiş biçimini alabilirsiniz. Programınızda dekore edilmiş adları incelemek için aşağıdaki yöntemlerden birini kullanabilirsiniz:

#### <a name="to-use-a-listing-to-view-decorated-names"></a>Dekore edilmiş adları görüntülemek için giriş kullanmak için

1. Kaynak Kodu **(/FAs)** ile Assembly'e ayarlanmış [Listeleme Dosya Türü](fa-fa-listing-file.md) derleyici seçeneği yle veri, nesne veya işlev tanımı veya prototipiçeren kaynak dosyayı derleyerek bir giriş oluşturun.

   Örneğin, bir `cl /c /FAs example.cpp` giriş dosyası oluşturmak için bir geliştirici komut istemi girin, örnek.asm.

2. Elde edilen listeleme dosyasında, PUBLIC ile başlayan ve dekore edilmemiş verileri veya işlev adını izleyen bir yarı nokta noktasını sona erdirebilen satırı bulun. PUBLIC ve semicolon arasındaki sembol süslenmiş adıdır.

#### <a name="to-use-dumpbin-to-view-decorated-names"></a>Dekore edilmiş adları görüntülemek için DUMPBIN'i kullanmak için

1. Dışa aktarılan sembolleri bir .obj veya `dumpbin /symbols` `objfile` .lib dosyasında görmek için geliştirici komut istemine girin.

2. Bir sembolün dekore edilmiş biçimini bulmak için, parantez içinde dekore edilmemiş adı arayın. Dekore edilmiş ad aynı satırda, bir boru (&#124;) karakterinden sonra ve dekore edilmemiş addan öncedir.

## <a name="viewing-undecorated-names"></a><a name="Undecorated"></a>Dekore edilmemiş adları görüntüleme

Dekore edilmiş bir adı dekore edilmemiş biçimine dönüştürmek için undname.exe'yi kullanabilirsiniz. Bu örnek, nasıl çalıştığını gösterir:

```
C:\>undname ?func1@a@@AAEXH@Z
Microsoft (R) C++ Name Undecorator
Copyright (C) Microsoft Corporation. All rights reserved.

Undecoration of :- "?func1@a@@AAEXH@Z"
is :- "private: void __thiscall a::func1(int)"
```

## <a name="see-also"></a>Ayrıca bkz.

[Ek MSVC Oluşturma Araçları](c-cpp-build-tools.md)<br/>
[Bağlantıyı Belirtmek için extern Kullanma](../../cpp/using-extern-to-specify-linkage.md)
