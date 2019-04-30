---
title: '&lt;iOS&gt;'
ms.date: 11/04/2016
f1_keywords:
- <ios>
- ios/std::<ios>
helpviewer_keywords:
- ios header
ms.assetid: d3d4c161-2f37-4f04-93cc-0a2a89984a9c
ms.openlocfilehash: 1566f9105a61b1c037e86fd2e4b280ed6dd2020e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385225"
---
# <a name="ltiosgt"></a>&lt;iOS&gt;

İostreams çalışması için çeşitli türleri ve işlevleri temel tanımlar. Bu üstbilginin başka bir iostream üstbilgi tarafından sizin için genellikle bulunur; nadiren doğrudan dahil.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <ios>
```

## <a name="remarks"></a>Açıklamalar

Çok sayıda işlevleri manipülatörleri var. Bildirilen bir işleyici \<ios > sınıfının, bağımsız değişken nesnede depolanan değerleri değiştirir [ios_base](../standard-library/ios-base-class.md). Diğer manipülatörleri akışlarında nesnelerin bir şablon sınıfının bir özelleştirme gibi bu sınıftan türetilmiş bir tür tarafından denetlenen eylemleri gerçekleştirme [basic_istream](../standard-library/basic-istream-class.md) veya [basic_ostream](../standard-library/basic-ostream-class.md). Örneğin, [noskipws](../standard-library/ios-functions.md#noskipws)(**str**) biçimi bayrağını temizler `ios_base::skipws` nesnesindeki `str`, olabilen bu türlerden biri.

Elem ekleyerek bir işleyici çağırabilir veya sınıfından türetilen sınıflar için sağlanan özel ekleme ve çıkarma işlemleri nedeniyle, giriş akışından ayıklama `ios_base`. Örneğin:

```cpp
istr>> noskipws;
```

çağrıları [noskipws](../standard-library/ios-functions.md#noskipws)(**istr**).

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[iOS](../standard-library/ios-typedefs.md#ios)|Eski iostream Kitaplığı'ndan ios sınıf destekler.|
|[streamoff](../standard-library/ios-typedefs.md#streamoff)|İç işlemlerini destekler.|
|[streampos](../standard-library/ios-typedefs.md#streampos)|Arabelleğin işaretçisini veya dosya işaretçisi konumunu içerir.|
|[streamsize](../standard-library/ios-typedefs.md#streamsize)|Akış boyutunu belirtir.|
|[wios](../standard-library/ios-typedefs.md#wios)|Eski iostream kitaplığı wios sınıftan destekler.|
|[wstreampos](../standard-library/ios-typedefs.md#wstreampos)|Arabelleğin işaretçisini veya dosya işaretçisi konumunu içerir.|

### <a name="manipulators"></a>Manipülatörleri

|||
|-|-|
|[boolalpha](../standard-library/ios-functions.md#boolalpha)|Belirtir, türü değişkenlerindeki [bool](../cpp/bool-cpp.md) olarak görünür **true** veya **false** akış.|
|[Ara](../standard-library/ios-functions.md#dec)|Tamsayı değişkenleri taban 10 gösteriminde görüneceğini belirtir.|
|[defaultfloat](../standard-library/ios-functions.md#ios_defaultfloat)|Bayraklarını yapılandırır bir `ios_base` kayan nokta değerleri için varsayılan görüntüleme biçimi kullanılacak nesne.|
|[düzeltildi](../standard-library/ios-functions.md#fixed)|Bir kayan noktalı sayı sabit ondalık gösteriminde görüntüleneceğini belirtir.|
|[onaltılık](../standard-library/ios-functions.md#hex)|Tamsayı değişkenleri temel 16 gösteriminde görüneceğini belirtir.|
|[internal](../standard-library/ios-functions.md#internal)|Bir sayının işaretini sola hizalı olarak ve sağa hizalı olarak sayı neden olur.|
|[Sol](../standard-library/ios-functions.md#left)|Sol kenar boşluğu ile stream temizleme görünmesini çıkış olarak geniş olmayan metin neden olur.|
|[noboolalpha](../standard-library/ios-functions.md#noboolalpha)|Belirten bu türü değişkenlerindeki [bool](../cpp/bool-cpp.md) 1 veya 0 akışı gibi görünür.|
|[noshowbase](../standard-library/ios-functions.md#noshowbase)|Bir sayı görüntülendiği notational temel belirten devre dışı bırakır.|
|[noshowpoint](../standard-library/ios-functions.md#noshowpoint)|Kayan noktalı sayıların, kesirli bölümü sıfırdır. yalnızca tam sayı bölümünü görüntüler.|
|[noshowpos](../standard-library/ios-functions.md#noshowpos)|Pozitif sayı değil açıkça imzalanmasını neden olur.|
|[noskipws](../standard-library/ios-functions.md#noskipws)|Giriş akışı tarafından okunacak alanları neden.|
|[nounitbuf](../standard-library/ios-functions.md#nounitbuf)|Arabelleğe alınan ve arabelleği dolu olduğunda işlenen nedenleri çıktı.|
|[nouppercase](../standard-library/ios-functions.md#nouppercase)|Onaltılık basamak ve bilimsel gösterimde üs küçük harflerle görüneceğini belirtir.|
|[Eki](../standard-library/ios-functions.md#oct)|Tamsayı değişkenleri temel 8 gösteriminde görüneceğini belirtir.|
|[sağ](../standard-library/ios-functions.md#right)|Sağ kenar boşluğu ile stream temizleme görünmesini çıkış olarak geniş olmayan metin neden olur.|
|[Bilimsel](../standard-library/ios-functions.md#scientific)|Kayan noktalı sayılar bilimsel gösterim kullanılarak görüntüleneceğini neden olur.|
|[showbase](../standard-library/ios-functions.md#showbase)|Bir sayı görüntülendiği notational temel gösterir.|
|[showpoint](../standard-library/ios-functions.md#showpoint)|Kesirli bölümü sıfır olsa bile tam sayı bölümü bir kayan noktalı sayı ve sayılar ondalık noktasının sağında görüntüler.|
|[showpos](../standard-library/ios-functions.md#showpos)|Pozitif sayıları açıkça imzalanmasını neden olur.|
|[skipws](../standard-library/ios-functions.md#skipws)|Giriş akışı tarafından okunur olmayan alanları neden.|
|[unitbuf](../standard-library/ios-functions.md#unitbuf)|Çıkış arabelleği boş olmadığında işlenmesi için neden olur.|
|[büyük harf](../standard-library/ios-functions.md#uppercase)|Onaltılık basamak ve bilimsel gösterimde üs büyük harf olarak görüneceğini belirtir.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_ios](../standard-library/basic-ios-class.md)|Şablon sınıfı için her iki giriş akışları genel depolama ve üye işlevleri tanımlar (şablon sınıfının [basic_istream](../standard-library/basic-istream-class.md)) ve çıkış akışlarına (şablon sınıfının [basic_ostream](../standard-library/basic-ostream-class.md)) bağlı olduğu Şablon parametreleri.|
|[fpos](../standard-library/fpos-class.md)|Şablon sınıfı, yükün herhangi bir rastgele dosya konumu göstergesi geri yüklemek için gerekli tüm bilgileri depolayan nesneyi tanımlar.|
|[ios_base](../standard-library/ios-base-class.md)|Depolama sınıfı açıklar ve üye işlevleri, şablon parametrelerine bağlı olmayan giriş ve çıkış yaygın olarak kullanılan akış.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
