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
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2019
ms.locfileid: "62326085"
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

Bir dizi için en büyük boyut, **size_t**tarafından tanımlanır. STDDEF başlık dosyasında tanımlanmıştır. H, **size_t** 0x00000000 `unsigned int` Ile 0x7CFFFFFF arasındadır.

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

Bu ifade, `P` dört-by-üç dizisi olarak bildirir ve ilk satırının öğelerini 1, ikinci satırının öğelerini ise dördüncü satır boyunca başlatır. Üçüncü ve dördüncü satırlara yönelik Başlatıcı listesinin, son sabit ifadeden sonra virgüller içerdiğini unutmayın. Son başlatıcı listesi (`{4, 4, 4,},`) Ayrıca bir virgül ile izlenir. Bu ek virgüller izin verilir ancak gerekli değildir; yalnızca bir kümeden sabit ifadeleri ayıran ve bir başlatıcı listesini diğerinden ayıran virgüller gereklidir.

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

Bu örnekte, `nlist` 2-3 yapıların dizi olarak bildirildiği, her yapının üç üyesi vardır. Başlatmanın 1. satırı `nlist`, aşağıdaki gibi ilk satırına değerler atar:

1. Satır 1 ' deki ilk sol ayraç, derleyicinin ilk toplama üyesini `nlist` (yani, `nlist[0]`) başlatmasını bildirir.

1. İkinci sol ayraç, öğesinin `nlist[0]` ilk toplama üyesini (yani, ' deki `nlist[0][0]`yapıyı) başlatmanın başladığını gösterir.

1. İlk sağ ayraç yapının `nlist[0][0]`başlatılmasını sonlandırır; sonraki sol ayraç başlatması başlatılır `nlist[0][1]`.

1. İşlem satırın sonuna kadar devam eder; burada sağ sağ ayraç, ' ın `nlist[0]`başlatılma işlemini sonlandırır.

Satır 2 değeri, benzer bir şekilde ikinci satırına `nlist` değer atar. 1 ve 2. satırlardaki başlatıcıları kapsayan küme ayracı dış kümelerinin gerekli olduğunu unutmayın. Dış küme ayraçlarını atladığında aşağıdaki oluşturma bir hataya neden olur:

```C
triplet nlist[2][3] =  /* THIS CAUSES AN ERROR */
{
     {  1, 2, 3 },{  4, 5, 6 },{  7, 8, 9 },   /* Line 1 */
     { 10,11,12 },{ 13,14,15 },{ 16,17,18 }    /* Line 2 */
};
```

Bu yapıta, 1. satırdaki ilk sol ayraç, üç yapının dizisi olan `nlist[0]`' nin başlatılmasına başlar. 1, 2 ve 3 değerleri, ilk yapının üç üyesine atanır. Sonraki sağ küme ayracı ile karşılaşıldığında (3. değerden sonra), başlatma `nlist[0]` tamamlanmıştır ve üç yapıda dizideki kalan iki yapı otomatik olarak 0 olarak başlatılır. Benzer şekilde `{ 4,5,6 }` , ikinci satırındaki ilk yapıyı başlatır `nlist`. Öğesinin `nlist[1]` kalan iki yapısı 0 olarak ayarlanır. Derleyici bir sonraki Başlatıcı listesi ( `{ 7,8,9 }` ) ile karşılaştığında başlatmaya `nlist[2]`çalışır. Bu `nlist` yana yalnızca iki satır içerdiğinden, bu deneme hataya neden olur.

Bu sonraki örnekte, öğesinin `int` `x` üç üyesi sırasıyla 1, 2 ve 3 olarak başlatılır.

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

Yukarıdaki `list` yapıda, öğesinin `m` ilk satırındaki üç öğe 4,0 olarak başlatılır; kalan satırının `m` öğeleri varsayılan olarak 0,0 olarak başlatılır.

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

Bu örnekteki UNION `y`değişkeni başlatılır. Birleşimin ilk öğesi bir dizidir, bu nedenle başlatıcı bir toplama başlatıcısı olur. Başlatıcı listesi `{'1'}` , dizinin ilk satırına değerler atar. Listede yalnızca bir değer göründüğünden, ilk sütundaki öğe karakter `1`olarak başlatılır ve satırdaki kalan iki öğe varsayılan olarak 0 değerine başlatılır. Benzer şekilde, ikinci satırının `x` ilk öğesi karakteriyle `4`başlatılır ve satırdaki kalan iki öğe 0 değerine başlatılır.

## <a name="see-also"></a>Ayrıca bkz.

[Başlatılmasında](../c-language/initialization.md)
