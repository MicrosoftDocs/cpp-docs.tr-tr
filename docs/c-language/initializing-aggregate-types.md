---
title: Toplama Türlerini Başlatma
ms.date: 11/04/2016
helpviewer_keywords:
- aggregate types [C++]
- union keyword [C], declarations
- types [C], initializing
- union keyword [C]
- aggregates [C++], initializing
ms.assetid: a8f8ed75-39db-4592-93b9-d3920d915810
ms.openlocfilehash: f6816a6f63de262b927a3c5aeed8774ba29c2eaa
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56151500"
---
# <a name="initializing-aggregate-types"></a>Toplama Türlerini Başlatma

Bir *toplama* türü, bir yapı, birlik veya dizi türü. Bir toplama türünü toplama türlerin üyelerini içeriyorsa, başlatma kurallar özyinelemeli olarak uygulanır.

## <a name="syntax"></a>Sözdizimi

*Başlatıcı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{***başlatıcı listesi***}** / * için toplu başlatma \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{***başlatıcı listesi***,}**

*Başlatıcı listesi*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Başlatıcı*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Başlatıcı listesi* **,** *Başlatıcı*

*Başlatıcı listesi* başlatıcılar virgülle ayrılmış listesidir. Listedeki her Başlatıcısı sabit bir ifade ya da bir başlatıcı listesi değil. Bu nedenle, başlatıcı listeleri yuvalanabilir. Bu formu, bu bölümdeki örneklerde gösterildiği gibi bir toplama türü üyeleri toplama başlatmak için yararlı olur. Ancak, tek bir ifade otomatik tanımlayıcı için Başlatıcı ise sabit bir ifade olmamalıdır; Bu yalnızca uygun bir tür tanımlayıcı atama için sahip olması gerekir.

Her başlatıcı listesi için değerleri sabit ifadeler, sırasıyla toplam değişken karşılık gelen üyelerine atanır.

Varsa *başlatıcı listesi* bir toplama türünü, kalan üyeleri veya toplama türü öğeler 0 olarak başlatılır çok daha az sayıda değer içeriyor. Açıkça başlatılan otomatik bir tanımlayıcının ilk değeri tanımsızdır. Varsa *başlatıcı listesi* bir toplama türünü daha fazla değer varsa, bir hata oluşur. Bu kurallar, toplamanın yanı sıra her katıştırılmış başlatıcı listesi, bir bütün olarak uygular.

Bir yapının Başlatıcı bir ifade aynı türde veya küme ayraçları içine alınmış üyeleri için başlatıcılar listesi olan (**{}**). Adlandırılmamış bir bit alanı üyeleri başlatılmadı.

Bir birleşim başlatıldığında *başlatıcı listesi* tek bir sabit ifade olmalıdır. Sabit ifade değeri, birleşimin ilk üye için atanır.

Bilinmeyen bir dizi varsa, başlatıcılar dizinin boyutunu belirler ve türünü tamamlandığında boyutu. C dilinde bir başlatıcı yineleneceğini belirtir ya da bir öğe dizisi ortasında önceki tüm değerleri de sağlamadan başlatmak için bir yolu yoktur. Programınızda bu işlemi gerekiyorsa, yordamı derleme dilinde yazın.

Not: başlatıcılar sayısını dizinin boyutunu ayarlayabilirsiniz

```C
int x[ ] = { 0, 1, 2 }
```

Bununla birlikte, boyutu belirtin ve başlatıcılar yanlış sayıda verin, derleyici bir hata oluşturur.

**Microsoft'a özgü**

Bir dizi boyutu üst sınırı tarafından tanımlanır **size_t**. STDDEF üstbilgi dosyasında tanımlanır. H **size_t** olduğu bir `unsigned int` 0x00000000 için 0x7CFFFFFF aralıkla.

**END Microsoft özgü**

## <a name="examples"></a>Örnekler

Bu örnek, bir dizi başlatıcıları gösterir.

```C
int P[4][3] =
{
    { 1, 1, 1 },
    { 2, 2, 2 },
    { 3, 3, 3,},
    { 4, 4, 4,},
};
```

Bu ifade `P` dört üçüncü dizi ve 1, 2, vb. aracılığıyla Dördüncü satır için ikinci satırına öğelerinin ilk satırına öğelerini başlatır. Başlatıcı listesi üçüncü ve dördüncü satır için son sabit ifadeden sonra virgül içerdiğine dikkat edin. Son başlatıcı listesi (`{4, 4, 4,},`) da virgül tarafından izlenir. Bu ek virgül, izin verilen ancak gerekli değildir; sabit ifadeler birbirinden ve başka bir uygulamadan bir başlatıcı listesi ayrı o ayıran virgüller gereklidir.

Bir üye katıştırılmış başlatıcı listesi yoksa, değerleri yalnızca, sırasıyla her üyesine subaggregate atanır. Bu nedenle, başlatma önceki örnekte aşağıdakine eşdeğerdir:

```C
int P[4][3] =
{
   1, 1, 1, 2, 2, 2, 3, 3, 3, 4, 4, 4
};
```

Küme ayraçları listesinde ayrı başlatıcılar etrafında görünebilir ve yukarıdaki örnekte açıklamak için yardımcı olur.

Bir toplama değişkeni başlattığınızda, küme ayraçları kullanmak dikkatli olmanız gerekir ve Başlatıcı düzgün listeler. Aşağıdaki örnekte, derleyicinin yorumu daha ayrıntılı küme ayraçlarının gösterilmektedir:

```C
typedef struct
{
    int n1, n2, n3;
} triplet;

triplet nlist[2][3] =
{
    { {  1, 2, 3 }, {  4, 5, 6 }, {  7, 8, 9 } },  /* Row 1 */
    { { 10,11,12 }, { 13,14,15 }, { 16,17,18 } }   /* Row 2 */
};
```

Bu örnekte, `nlist` yapıları 2 ile 3 bir dizi olarak üç üyesi olan her yapısı bildirilir. Başlatma 1 satırının ilk satırının değerleri atar `nlist`gibi:

1. 1. satırda ilk sol ayraç derleyici ilk toplama üyesinin başlatmanın sinyalleri `nlist` (diğer bir deyişle, `nlist[0]`) başlangıcıdır.

1. İkinci bir sol ayraç ilk toplama üyesinin başlatmanın gösterir `nlist[0]` (diğer bir deyişle, yapıda `nlist[0][0]`) başlangıcıdır.

1. İlk sağ ayraç sonlandırır yapısının başlatma `nlist[0][0]`; sonraki sol ayraç başlatılıyor `nlist[0][1]`.

1. İşlem başlangıcına doğru kapanış ayracı sona ereceği satırın sonuna kadar devam eder `nlist[0]`.

Satır 2 ikinci satıra değerleri atar `nlist` benzer bir şekilde. 1. ve 2 numaralı satırda başlatıcılar kapsayan küme ayraçlarının dış ayarlar gerekli olduğunu unutmayın. Dış küme ayraçları atlar, aşağıdaki yapı hataya neden olur:

```C
triplet nlist[2][3] =  /* THIS CAUSES AN ERROR */
{
     {  1, 2, 3 },{  4, 5, 6 },{  7, 8, 9 },   /* Line 1 */
     { 10,11,12 },{ 13,14,15 },{ 16,17,18 }    /* Line 2 */
};
```

Bu oluşturma, 1. satırına ilk sol ayraç başlatma başlar `nlist[0]`, üç yapılarının dizisi. Değerler 1, 2 ve 3 üç ilk yapı üyelerine atanır. Sonraki sağ ayraç karşılaşıldı (sonra değeri 3) başlatılması olduğunda `nlist[0]` tamamlandıktan ve üç yapısı dizideki iki kalan yapılarını otomatik olarak 0 olarak başlatılır. Benzer şekilde, `{ 4,5,6 }` ikinci satırındaki ilk yapısı başlatır `nlist`. Kalan iki yapıları `nlist[1]` 0 olarak ayarlayın. Sonraki başlatıcı listesi karşılaştığında derleyici ( `{ 7,8,9 }` ), başlatmaya çalıştığında `nlist[2]`. Bu yana `nlist` yalnızca iki satır varsa, bu deneme bir hataya neden olur.

Bu bir sonraki örnekte, üç `int` üyeleri `x` sırasıyla 1, 2 ve 3 ' için başlatılır.

```C
struct list
{
    int i, j, k;
    float m[2][3];
} x = {
        1,
        2,
        3,
       {4.0, 4.0, 4.0}
      };
```

İçinde `list` yukarıdaki yapısı, ilk satırında üç öğe `m` 4.0; başlatılır kalan satırının öğeleri `m` 0.0, varsayılan olarak başlatılır.

```C
union
{
    char x[2][3];
    int i, j, k;
} y = { {
            {'1'},
            {'4'}
        }
      };
```

Birleşim değişkenini `y`, bu örnekte, başlatılır. Başlatıcı bir toplu Başlatıcı birleşimin ilk öğeyi bir dizi olduğundan. Başlatıcı listesi `{'1'}` dizinin ilk satırına değerleri atar. Yalnızca bir değer listede görünür olduğundan, öğeyi ilk sütunda karakter başlatılır `1`, ve kalan iki öğe sıradaki değeri 0 varsayılan olarak başlatılır. Benzer şekilde, ikinci satırının ilk öğeyi `x` karakter başlatılır `4`, ve kalan iki öğe sıradaki değeri 0 olarak başlatılır.

## <a name="see-also"></a>Ayrıca bkz.

[Başlatma](../c-language/initialization.md)
