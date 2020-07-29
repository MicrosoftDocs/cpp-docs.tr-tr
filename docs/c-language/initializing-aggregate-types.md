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
ms.openlocfilehash: b4b0dd82263781966760b6e21ef24ded56b06a01
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229629"
---
# <a name="initializing-aggregate-types"></a>Toplama Türlerini Başlatma

*Toplama* türü bir yapı, birleşim veya dizi türüdür. Toplama türü, toplama türlerinin üyelerini içeriyorsa, başlatma kuralları yinelemeli olarak uygulanır.

## <a name="syntax"></a>Sözdizimi

*Başlatıcı*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;toplu başlatma için **{***Başlatıcı-listesi***}** /*    \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**{**  *Başlatıcı-listesi*  **,}**

*Başlatıcı-Liste*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*izer*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Başlatıcı-Liste*  **,**  *Başlatıcı*

*Başlatıcı listesi* , virgülle ayrılmış başlatıcıların bir listesidir. Listedeki her başlatıcı sabit bir ifade ya da Başlatıcı listesidir. Bu nedenle, başlatıcı listeleri iç içe olabilir. Bu form, bu bölümdeki örneklerde gösterildiği gibi, bir toplama türünün toplam üyelerini başlatmak için yararlıdır. Ancak, bir otomatik tanımlayıcının başlatıcısı tek bir ifadesiyse, sabit bir ifade olması gerekmez; yalnızca tanımlayıcıya atama için uygun türe sahip olması gerekir.

Her başlatıcı listesi için, sabit ifadelerin değerleri, toplama değişkeninin ilgili üyelerine sırasıyla atanır.

*Başlatıcı listesi* , bir toplama türünden daha az değere sahipse, kalan Üyeler veya toplama türünün öğeleri 0 olarak başlatılır. Açıkça başlatılmamış bir otomatik tanımlayıcının ilk değeri tanımsız. *Başlatıcı listesi* , bir toplama türünden daha fazla değere sahipse bir hata oluşur. Bu kurallar, her gömülü Başlatıcı listesi için ve toplama için de geçerlidir.

Bir yapının Başlatıcısı aynı türdeki bir ifadedir veya küme ayraçları (**{}**) içine alınmış Üyeler için bir başlatıcı listesi olur. Adlandırılmamış bit alanı üyeleri başlatılmaz.

Bir UNION başlatıldığında, *Başlatıcı listesi* tek bir sabit ifade olmalıdır. Sabit ifadenin değeri, birleşimin ilk üyesine atanır.

Bir dizinin boyutu bilinmiyor ise, başlatıcıların sayısı dizinin boyutunu belirler ve türü tamamlandı olur. C 'de bir başlatıcısının yinelemesini belirtmenin veya bir dizinin ortasında bir öğeyi önceki tüm değerleri sağlamadan başlatmanın bir yolu yoktur. Programınızda bu işleme ihtiyacınız varsa, yordamı derleme dilinde yazın.

Başlatıcıların sayısının dizinin boyutunu ayarlayabileceğini unutmayın:

```C
int x[ ] = { 0, 1, 2 }
```

Ancak boyutu belirtir ve yanlış sayıda başlatıcıya sahipseniz, derleyici bir hata oluşturur.

**Microsoft'a Özgü**

Bir dizi için en büyük boyut, **size_t**tarafından tanımlanır. STDDEF başlık dosyasında tanımlanmıştır. H, **size_t** **`unsigned int`** 0x00000000 Ile 0x7CFFFFFF arasındadır.

**SON Microsoft 'a özgü**

## <a name="examples"></a>Örnekler

Bu örnek, bir dizi için başlatıcıları gösterir.

```C
int P[4][3] =
{
    { 1, 1, 1 },
    { 2, 2, 2 },
    { 3, 3, 3,},
    { 4, 4, 4,},
};
```

Bu ifade, `P` dört-by-üç dizisi olarak bildirir ve ilk satırının öğelerini 1, ikinci satırının öğelerini ise dördüncü satır boyunca başlatır. Üçüncü ve dördüncü satırlara yönelik Başlatıcı listesinin, son sabit ifadeden sonra virgüller içerdiğini unutmayın. Son başlatıcı listesi ( `{4, 4, 4,},` ) Ayrıca bir virgül ile izlenir. Bu ek virgüller izin verilir ancak gerekli değildir; yalnızca bir kümeden sabit ifadeleri ayıran ve bir başlatıcı listesini diğerinden ayıran virgüller gereklidir.

Bir toplama üyesinin gömülü Başlatıcı listesi yoksa, her bir alt ggregate üyesine, değerler sırayla atanır. Bu nedenle, önceki örnekteki başlatma aşağıdakilere eşdeğerdir:

```C
int P[4][3] =
{
   1, 1, 1, 2, 2, 2, 3, 3, 3, 4, 4, 4
};
```

Küme ayraçları, listedeki bireysel başlatıcıların etrafında de görünebilir ve yukarıdaki örneği açıklığa kavuşturmasına yardımcı olur.

Bir toplama değişkenini başlattığınızda, küme ayraçları ve Başlatıcı listelerini doğru şekilde kullanmaya dikkat etmeniz gerekir. Aşağıdaki örnek, derleyicinin küme ayraçlarının yorumunu daha ayrıntılı olarak göstermektedir:

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

Bu örnekte, `nlist` 2-3 yapıların dizi olarak bildirildiği, her yapının üç üyesi vardır. Başlatmanın 1. satırı, aşağıdaki gibi ilk satırına değerler atar `nlist` :

1. Satır 1 ' deki ilk sol ayraç, derleyicinin ilk toplama üyesini (yani,) başlatmasını bildirir `nlist` `nlist[0]` .

1. İkinci sol ayraç, öğesinin ilk toplama üyesini `nlist[0]` (yani, ' deki yapıyı) başlatmanın başladığını gösterir `nlist[0][0]` .

1. İlk sağ küme ayracı yapının başlatılmasını sonlandırır `nlist[0][0]` ; sonraki sol ayraç, öğesinin başlatılmasına başlar `nlist[0][1]` .

1. İşlem satırın sonuna kadar devam eder; burada sağ sağ ayraç, ' ın başlatılma işlemini sonlandırır `nlist[0]` .

Satır 2 değeri, benzer bir şekilde ikinci satırına değer atar `nlist` . 1 ve 2. satırlardaki başlatıcıları kapsayan küme ayracı dış kümelerinin gerekli olduğunu unutmayın. Dış küme ayraçlarını atladığında aşağıdaki oluşturma bir hataya neden olur:

```C
triplet nlist[2][3] =  /* THIS CAUSES AN ERROR */
{
     {  1, 2, 3 },{  4, 5, 6 },{  7, 8, 9 },   /* Line 1 */
     { 10,11,12 },{ 13,14,15 },{ 16,17,18 }    /* Line 2 */
};
```

Bu yapıta, 1. satırdaki ilk sol ayraç, `nlist[0]` üç yapının dizisi olan ' nin başlatılmasına başlar. 1, 2 ve 3 değerleri, ilk yapının üç üyesine atanır. Sonraki sağ küme ayracı ile karşılaşıldığında (3. değerden sonra), başlatma `nlist[0]` tamamlanmıştır ve üç yapıda dizideki kalan iki yapı otomatik olarak 0 olarak başlatılır. Benzer şekilde, `{ 4,5,6 }` ikinci satırındaki ilk yapıyı başlatır `nlist` . Öğesinin kalan iki yapısı `nlist[1]` 0 olarak ayarlanır. Derleyici bir sonraki Başlatıcı listesi () ile karşılaştığında `{ 7,8,9 }` başlatmaya çalışır `nlist[2]` . `nlist`Bu yana yalnızca iki satır içerdiğinden, bu deneme hataya neden olur.

Bu sonraki örnekte, **`int`** öğesinin üç üyesi `x` sırasıyla 1, 2 ve 3 olarak başlatılır.

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

`list`Yukarıdaki yapıda, öğesinin ilk satırındaki üç öğe `m` 4,0 olarak başlatılır; kalan satırının öğeleri `m` Varsayılan olarak 0,0 olarak başlatılır.

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

`y`Bu örnekteki UNION değişkeni başlatılır. Birleşimin ilk öğesi bir dizidir, bu nedenle başlatıcı bir toplama başlatıcısı olur. Başlatıcı listesi, `{'1'}` dizinin ilk satırına değerler atar. Listede yalnızca bir değer göründüğünden, ilk sütundaki öğe karakter olarak başlatılır `1` ve satırdaki kalan iki öğe varsayılan olarak 0 değerine başlatılır. Benzer şekilde, ikinci satırının ilk öğesi `x` karakteriyle başlatılır `4` ve satırdaki kalan iki öğe 0 değerine başlatılır.

## <a name="see-also"></a>Ayrıca bkz.

[Başlatma](../c-language/initialization.md)
