---
title: '#yönergesi (C/C++)'
ms.date: 11/04/2016
f1_keywords:
- '#define'
helpviewer_keywords:
- define directive (#define), syntax
- preprocessor, directives
- define directive (#define)
- '#define directive, syntax'
- '#define directive'
ms.assetid: 33cf25c6-b24e-40bf-ab30-9008f0391710
ms.openlocfilehash: 8a0cc7e7836a0c82c72055fe8d9e7497995485d0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039518"
---
# <a name="define-directive-cc"></a>#define Yönergesi (C/C++)

**#Define** oluşturur bir *makrosu*, tanımlayıcı veya parametreli tanımlayıcısı ilişkisini bir belirteç dizesiyle olduğu. Makro tanımlandıktan sonra derleyici her kaynak dosyasındaki tanımlayıcı tekrarı için belirteç dizesini birbirinin yerine kullanabilir.

## <a name="syntax"></a>Sözdizimi

`#define` *tanımlayıcı* *belirteç dizesinde*<sub>iyileştirilmiş</sub>

`#define` *tanımlayıcı* `(` *tanımlayıcı*<sub>iyileştirilmiş</sub> `,` *...*  `,` *tanımlayıcı*<sub>iyileştirilmiş</sub> `)` *belirteç dizesinde*<sub>iyileştirilmiş</sub>

## <a name="remarks"></a>Açıklamalar

**#Define** yönergesi neden olan derleyiciye *belirteç dizesinde* her geçtiği yeri *tanımlayıcı* kaynak dosyadaki. *Tanımlayıcı* yalnızca belirteç oluşturduğunda değiştirilir. Diğer bir deyişle, *tanımlayıcı* bir yorum, bir dize ya da daha uzun bir tanımlayıcının bir parçası olarak görünüyorsa değiştirilmez. Daha fazla bilgi için [belirteçleri](../cpp/tokens-cpp.md).

*Belirteç dizesinde* belirteçleri, anahtar sözcükler, sabitler veya tam ifadeler gibi bir dizi bağımsız değişken oluşur. Bir veya daha fazla beyaz boşluk karakterleri ayırmalıdır *belirteç dizesinde* gelen *tanımlayıcı*. Bu boşluk, değiştirilen metnin bir parçası olarak kabul edilmez ve metnin son belirtecinin izleyen tüm boşluk.

A `#define` olmadan bir *belirteç dizesinde* kaldırır *tanımlayıcı* kaynak dosyasından. *Tanımlayıcı* tanımlı kalır ve kullanılarak test edilebilir `#if defined` ve `#ifdef` yönergeleri.

İkinci sözdizimi formu, parametreler içeren işleve benzer bir makro tanımlar. Bu form, parantez içinde görünmesi gereken parametreleri isteğe bağlı bir listesini kabul eder. Makro tanımlı, daha sonraki oluşumunu sonra *tanımlayıcı*( *tanımlayıcı*<sub>iyileştirilmiş</sub>,..., *tanımlayıcı* <sub>iyileştirilmiş</sub> ) bir sürümle değiştirilir *belirteç dizesinde* biçimsel parametrelerin yerine geçen gerçek bağımsız değişkenlere sahip bağımsız değişken.

Biçimsel parametre adları görünür *belirteç dizesinde* yeri gerçek değerleri yerine konumları işaretlemek için. Her parametre adı içindeki birden çok kez görünebilir *belirteç dizesinde*, ve adlar herhangi bir sırada görünebilir. Çağrıdaki bağımsız değişkenlerin sayısı makro tanımındaki parametrelerin sayısı ile eşleşmelidir. Serbest ayraç kullanımı karmaşık gerçek bağımsız değişkenlerin doğru olarak yorumlanmasını sağlar.

Listedeki biçimsel parametreler virgülle ayrılır. Listedeki her ad benzersiz olmalıdır ve liste parantez içine alınmalıdır. Boşluk olmayan ayırabilirsiniz *tanımlayıcı* ve açma parantezi. Satır bitiştirme kullanın — bir ters eğik çizgi yerleştirmek (`\`) hemen önce yeni satır karakterini — birden çok kaynak satırları uzun yönergeler için. Bir biçimsel parametrenin ad kapsamı ile biten yeni satıra uzanır *belirteç dizesinde*.

İkinci sözdizimi formunda bir makro tanımlandığında, sonraki metin örnekleri bir bağımsız değişken listesi tarafından izlenen, makro çağrısını belirtir. Örneğini izleyen fiili bağımsız değişkenler *tanımlayıcı* kaynak dosyada Makro tanımında karşılık gelen biçimsel parametrelerle eşleştirilir. Her biçimsel parametre *belirteç dizesinde* öncesinde bir dizeleştirici (`#`), karakterleştirici (`#@`), veya belirteç Yapıştırıcı (`##`) işleç veya arkasından değil bir `##` işlecidir karşılık gelen gerçek bağımsız değişkeni tarafından değiştirildi. Gerçek bağımsız makrolar, yönerge biçimsel parametrenin yerini almadan önce genişletilir. (İşleçler açıklanan [önişlemci işleçleri](../preprocessor/preprocessor-operators.md).)

Aşağıdaki bağımsız değişken içeren makro örnekleri ikinci formunu gösterir **#define** söz dizimi:

```C
// Macro to define cursor lines
#define CURSOR(top, bottom) (((top) << 8) | (bottom))

// Macro to get a random integer with a specified range
#define getrandom(min, max) \
    ((rand()%(int)(((max) + 1)-(min)))+ (min))
```

Yan etkileri olan bağımsız değişkenler bazen makroların beklenmedik sonuçlar doğurmasına yol. Verilen bir biçimsel parametre birden fazla kez görünebilir *belirteç dizesinde*. Bu biçimsel parametre yan etkileri olan bir ifade tarafından değiştirilirse, yan etkileriyle birlikte bu ifade birden fazla kez değerlendirilebilir. (Altındaki örneklere bakın [belirteç yapıştıran işleç (##)](../preprocessor/token-pasting-operator-hash-hash.md).)

`#undef` Yönergesi bir tanımlayıcının önişlemci tanımını unutmasına neden olur. Bkz: [#undef yönergesi](../preprocessor/hash-undef-directive-c-cpp.md) daha fazla bilgi için.

Tanımlanmakta olan makro adı içinde oluşursa *belirteç dizesinde* (hatta başka bir makronun sonucu), genişletilmez.

İkinci **#define** ikinci belirteç sırası birinciyle aynı olmadığı sürece bir makro aynı ada sahip bir uyarı oluşturur.

**Microsoft'a özgü**

Microsoft C/C++ yeni tanım sözdizimi kurallarına göre orijinal tanımla özdeş bir makroyu yeniden tanımlamanıza olanak sağlar. Diğer bir deyişle, iki tanımın farklı parametre adları olabilir. Bu davranış, iki tanımın sözcüksel olarak aynı olmasını gerektiren ANSI C farklıdır.

Örneğin, aşağıdaki iki makro parametre adları hariç olmak üzere aynıdır. ANSI C böyle bir yeniden tanımlamaya izin vermez ancak Microsoft C/C++ bunu hata olmadan derler.

```C
#define multiply( f1, f2 ) ( f1 * f2 )
#define multiply( a1, a2 ) ( a1 * a2 )
```

Öte yandan, aşağıdaki iki makro aynı değildir ve Microsoft C/C++'da bir uyarı oluşturur.

```C
#define multiply( f1, f2 ) ( f1 * f2 )
#define multiply( a1, a2 ) ( b1 * b2 )
```

**END Microsoft özgü**

Bu örnekte **#define** yönergesi:

```C
#define WIDTH       80
#define LENGTH      ( WIDTH + 10 )
```

İlk deyim tanımlayıcısını tanımlar `WIDTH` 80 tamsayı sabiti olarak tanımlar `LENGTH` açısından `WIDTH` ve tamsayı sabiti 10. Her geçtiği `LENGTH` değiştirilir (`WIDTH + 10`). Buna karşılık her geçtiği `WIDTH + 10` ifadeyle değiştirilir (`80 + 10`). Çevresindeki parantezler `WIDTH + 10` bunlar aşağıdakiler gibi ifadelerin yorumlanmasını denetlemek için önemlidir:

```C
var = LENGTH * 20;
```

Ön işleme aşamasından sonra deyim olur:

```C
var = ( 80 + 10 ) * 20;
```

1800 olarak değerlendirilir. Parantez olmadan sonuç olur:

```C
var = 80 + 10 * 20;
```

hangi 280 için değerlendirir.

**Microsoft'a özgü**

Makrolar ve sabitler ile tanımlama [/D](../build/reference/d-preprocessor-definitions.md) derleyici seçeneğini kullanmakla aynı etkiye sahip bir **#define** dosyanızın başında ön işleme yönergesi. /D seçeneğiyle en fazla 30 makro tanımlanabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Ön işlemci Yönergeleri](../preprocessor/preprocessor-directives.md)