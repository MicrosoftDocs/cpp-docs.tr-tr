---
title: '##define yönergesi (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#define'
helpviewer_keywords:
- define directive (#define), syntax
- preprocessor, directives
- define directive (#define)
- '#define directive, syntax'
- '#define directive'
ms.assetid: 33cf25c6-b24e-40bf-ab30-9008f0391710
ms.openlocfilehash: e9e5b7a02ee55c05aa44278fbceb9c42f372c443
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506668"
---
# <a name="define-directive-cc"></a>#define yönergesi (C/C++)

**#Define** bir tanımlayıcı ya da bir belirteç dizesiyle parametreli tanımlayıcı ilişkisi olan bir *makro*oluşturur. Makro tanımlandıktan sonra derleyici, kaynak dosyadaki her bir tanımlayıcı oluşumu için belirteç dizesini değiştirebilir.

## <a name="syntax"></a>Sözdizimi

> **#define** *tanımlayıcı* *belirteci-dize*<sub>katılımı</sub>\
> **#define** *tanımlayıcı* **(** *tanımlayıcı*<sub>opt</sub>**,** ... **,** *tanımlayıcı*<sub>opt</sub> **)** *belirteç-dize*<sub>katılımı</sub>

## <a name="remarks"></a>Açıklamalar

**#Define** yönergesi, derleyicinin kaynak dosyadaki her bir *tanımlayıcı* oluşumu için *belirteç dizesini* yerine getirmesine neden olur. *Tanımlayıcı* yalnızca bir belirteç formlarında değişir. Diğer bir deyişle, bir açıklamada, bir dizede veya daha uzun bir tanımlayıcının parçası olarak görünürse *tanımlayıcı* değiştirilmez. Daha fazla bilgi için bkz. [belirteçler](../cpp/character-sets.md).

*Belirteç dize* bağımsız değişkeni, anahtar sözcükler, sabitler veya tam deyimler gibi bir dizi belirteçten oluşur. Bir veya daha fazla boşluk karakteri, *tanımlayıcıdan* *belirteç dizesini* ayırmalıdır. Bu boşluk, değiştirilen metnin bir parçası olarak kabul edilmez ve metnin son belirtecini takip eden herhangi bir boşluk değildir.

`#define` *Belirteç dizesi* olmayan bir, kaynak dosyadan *tanımlayıcının* oluşumlarını kaldırır. *Tanımlayıcı* tanımlı kalır ve ve yönergeleri kullanılarak test edilebilir `#if defined` `#ifdef` .

İkinci sözdizimi formu, parametrelere sahip bir işlev benzeri makroyu tanımlar. Bu form, parantez içinde görünmesi gereken parametrelerin isteğe bağlı bir listesini kabul eder. Makro tanımlandıktan sonra, sonraki *tanımlayıcı*( *tanımlayıcı*<sub>opt</sub>,..., *tanımlayıcı*<sub>opt</sub> ) tekrarının her biri, biçimsel parametreler için değiştirilen gerçek bağımsız değişkenlere sahip *belirteç dize* bağımsız değişkeninin bir sürümüyle değiştirilir.

Biçimsel parametre adları, gerçek değerlerin yerine geçen konumları işaretlemek için *token-string* içinde görünür. Her parametre adı, *belirteç dizesinde*birden çok kez görünebilir ve adlar herhangi bir sırada görünebilir. Çağrıdaki bağımsız değişkenlerin sayısı, makro tanımındaki parametre sayısıyla eşleşmelidir. Parantez kullanımı, karmaşık gerçek bağımsız değişkenlerin doğru şekilde yorumlanmasına karşı garanti garantisi sağlar.

Listedeki biçimsel parametreler virgülle ayrılır. Listedeki her adın benzersiz olması ve listenin parantez içine alınması gerekir. Hiçbir boşluk *tanımlayıcıyı* ve açma parantezini ayırabilirler. Çizgi birleştirme kullanın — `\` birden çok kaynak satırındaki uzun yönergeler için, yeni satır karakterinden hemen önce bir ters eğik çizgi () koyun. Biçimsel parametre adının kapsamı, *token-string*' i sonlandıran yeni satıra genişletilir.

İkinci sözdizimi formunda bir makro tanımlandığında, sonraki metinsel örnekleri bir bağımsız değişken listesi tarafından izlenen bir makro çağrısını gösterir. Kaynak dosyadaki *tanımlayıcı* örneğini izleyen gerçek bağımsız değişkenler, makro tanımındaki karşılık gelen biçimsel parametrelerle eşleştirilir. *Belirteç dizesindeki* her biçimsel parametre, öncesinde bir stringize ( `#` ), charize () `#@` veya Token-yapıştırmayı () `##` işleci veya arkasından bir `##` işleç tarafından değiştirilmediyse, karşılık gelen gerçek bağımsız değişkenle değiştirilmiştir. Gerçek bağımsız değişkendeki tüm makrolar, yönerge biçimsel parametrenin yerini almadan önce genişletilir. (İşleçler [Önişlemci işleçleri](../preprocessor/preprocessor-operators.md)içinde açıklanır.)

Aşağıdaki bağımsız değişkenlerle makrolar aşağıda verilmiştir **#define** sözdiziminin ikinci biçimi gösterilmektedir:

```C
// Macro to define cursor lines
#define CURSOR(top, bottom) (((top) << 8) | (bottom))

// Macro to get a random integer with a specified range
#define getrandom(min, max) \
    ((rand()%(int)(((max) + 1)-(min)))+ (min))
```

Yan etkileri olan bağımsız değişkenler bazen makroların beklenmedik sonuçlar üretmesine neden olur. Belirli bir biçimsel parametre, *belirteç dizesinde*birden fazla kez görünebilir. Bu biçimsel parametre yan etkileri olan bir ifadeyle değiştirilirse ifade, yan etkileri olan bir kez daha fazla değerlendirilemeyebilir. ( [Belirteç yapıştırma işleci (# #)](../preprocessor/token-pasting-operator-hash-hash.md)altındaki örneklere bakın.)

`#undef`Yönergesi, bir tanımlayıcının Önişlemci tanımının unutmasına neden olur. Daha fazla bilgi için [#undef yönergesine](../preprocessor/hash-undef-directive-c-cpp.md) bakın.

Tanımlanmakta olan makronun adı, *belirteç dizesinde* oluşursa (başka bir makro genişletmesinin sonucu olarak bile), genişletilmez.

Aynı ada sahip bir makro için ikinci **#define** , ikinci belirteç sırası birinciyle özdeş olmadığı takdirde bir uyarı oluşturur.

**Microsoft'a Özgü**

Microsoft C/C++, yeni tanım sözdizimi özgün tanımıyla özdeş ise makroyu yeniden tanımlamayı sağlar. Diğer bir deyişle, iki tanım farklı parametre adlarına sahip olabilir. Bu davranış, iki tanımın sözcüksel özdeş olmasını gerektiren ANSI C 'den farklıdır.

Örneğin, aşağıdaki iki makro parametre adları dışında aynıdır. ANSI C böyle bir yeniden tanımlama kullanılmasına izin vermez, ancak Microsoft C/C++ bunu hata olmadan derler.

```C
#define multiply( f1, f2 ) ( f1 * f2 )
#define multiply( a1, a2 ) ( a1 * a2 )
```

Öte yandan, aşağıdaki iki makro aynı değildir ve Microsoft C/C++ içinde bir uyarı oluşturur.

```C
#define multiply( f1, f2 ) ( f1 * f2 )
#define multiply( a1, a2 ) ( b1 * b2 )
```

**SON Microsoft 'a özgü**

Bu örnek **#define** yönergesini göstermektedir:

```C
#define WIDTH       80
#define LENGTH      ( WIDTH + 10 )
```

İlk ifade, tanımlayıcıyı `WIDTH` tamsayı sabiti 80 olarak tanımlar ve `LENGTH` hüküm `WIDTH` ve tamsayı sabiti 10 ' da tanımlar. Her oluşumu `LENGTH` () ile değiştirilmiştir `WIDTH + 10` . Sırasıyla, her oluşumu `WIDTH + 10` () ifadesiyle değiştirilmiştir `80 + 10` . Etrafındaki parantezler, `WIDTH + 10` aşağıdaki gibi deyimlerde yorumu denetlemediğinden önemlidir:

```C
var = LENGTH * 20;
```

Ön işleme aşamasına geçtikten sonra deyimin şu şekilde olur:

```C
var = ( 80 + 10 ) * 20;
```

1800 olarak değerlendirilir. Parantezler olmadan sonuç şu şekilde olur:

```C
var = 80 + 10 * 20;
```

280 olarak değerlendirilir.

**Microsoft'a Özgü**

[/D](../build/reference/d-preprocessor-definitions.md) derleyici seçeneği ile makrolar ve sabitler tanımlamak, dosyanızın başlangıcında **#define** ön işleme yönergesini kullanmayla aynı etkiye sahiptir. En fazla 30 makro/D seçeneği kullanılarak tanımlanabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Ön işlemci yönergeleri](../preprocessor/preprocessor-directives.md)
