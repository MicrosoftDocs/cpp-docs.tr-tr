---
title: "Toplama türlerini başlatma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- aggregate types [C++]
- union keyword [C], declarations
- types [C], initializing
- union keyword [C]
- aggregates [C++], initializing
ms.assetid: a8f8ed75-39db-4592-93b9-d3920d915810
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8656d1c9f5f08e8736ee83705ea2daf9031c2446
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-aggregate-types"></a>Toplama Türlerini Başlatma
Bir "aggregate" yapısı, UNION veya dizi türü türüdür. Bir toplama türü toplama türleri üyeleri içeriyorsa, başlatma kurallar yinelemeli olarak uygulanır.  
  
## <a name="syntax"></a>Sözdizimi  
 *Başlatıcı*:  
 **{***başlatıcı listesi***}** / * toplu başlatma için    \*/  
  
 **{***başlatıcı listesi***,}**   
  
 *Başlatıcı listesi*:  
 *Başlatıcı*  
  
 *Başlatıcı listesi***,***Başlatıcı*   
  
 *Başlatıcı listesi* başlatıcıları virgülle ayrılmış bir listesi verilmiştir. Listedeki her başlatıcısı, sabit bir ifade ya da bir başlatıcı listesi değil. Bu nedenle, başlatıcı listeleri iç içe. Bu form, bu bölümdeki örneklerde gösterildiği gibi bir toplama türü üyeleri toplama başlatmak için faydalı olur. Başlatıcı otomatik tanımlayıcı için tek bir ifade ise, ancak bunu sabit bir ifade olması gerekmez; Bunu yalnızca tanımlayıcısına atama için uygun türü olmalıdır.  
  
 Her başlatıcı listesi için sabit ifadeler değerler, sırasıyla toplama değişkeni karşılık gelen üyelerine atanır.  
  
 Varsa *başlatıcı listesi* bir toplama türü, kalan üyeleri veya toplama türündeki öğeler 0 olarak başlatılır daha az değerlere sahip. Açıkça başlatılan otomatik bir tanımlayıcıda başlangıç değeri tanımlanmamıştır. Varsa *başlatıcı listesi* bir toplama türü daha fazla değer varsa, bir hata oluşur. Bu kurallar, bir bütün olarak her katıştırılmış başlatıcı listesi ve aynı zamanda toplama uygulanır.  
  
 Aynı türde bir ifade ya da süslü ayraçlar içindeki üyeleri için başlatıcıları listesini bir yapısı Başlatıcı olduğu (**{}**). Adlandırılmamış bit alan üyeleri başlatılmadı.  
  
 UNION başlatıldığında *başlatıcı listesi* tek sabit bir ifade olması gerekir. Sabit ifadenin değerini Birliği ilk üye için atanır.  
  
 Bilinmeyen bir dizi olması durumunda boyut başlatıcıları sayısını dizinin boyutunu belirler ve türünü tam haline gelir. C'de bir başlatıcı yinelenmesinin belirtin veya bir dizi ortasında bir öğenin de tüm önceki değerleri sağlamadan başlatmak için bir yolu yoktur. Bu işlem, programınıza gerekiyorsa, yordam derleme dili yazma.  
  
 Not başlatıcıları sayısı dizinin boyutunu ayarlayabilirsiniz:  
  
```  
int x[ ] = { 0, 1, 2 }  
```  
  
 Ancak, boyut belirtin ve başlatıcılar yanlış sayıda verin, derleyici bir hata oluşturur.  
  
 **Microsoft özel**  
  
 Bir dizi boyutu üst sınırı tarafından tanımlanan **size_t**. Üstbilgi dosyası STDDEF tanımlanır. H **size_t** olan bir `unsigned int` 0x00000000 için 0x7CFFFFFF aralığına sahip.  
  
 **SON Microsoft özel**  
  
## <a name="examples"></a>Örnekler  
 Bu örnek, bir dizi başlatıcıları gösterir.  
  
```  
int P[4][3] =   
{  
    { 1, 1, 1 },  
    { 2, 2, 2 },  
    { 3, 3, 3,},  
    { 4, 4, 4,},  
};  
```  
  
 Bu ifade bildirir `P` üç tarafından dört dizi ve 1, 2 vb. Dördüncü satır aracılığıyla kendi ikinci satır öğelerini ilk satırına öğelerini başlatır. Üçüncü ve dördüncü satırlar için başlatıcı listesi sonra son sabit ifadesine virgül içerdiğine dikkat edin. Son başlatıcı listesi (`{4, 4, 4,},`) de virgül ve. Bu ek virgül izin verilen ancak gerekli değildir; yalnızca sabit ifadeler birbirinden ve bu bir başlatıcı listesi diğerinden, ayrı ayrı virgül gereklidir.  
  
 Birleşik bir üye katıştırılmış başlatıcı listesi yoksa, değerler yeterlidir, sırayla subaggregate her bir üyesi atanır. Bu nedenle, önceki örnekte başlatma şuna eşdeğerdir:  
  
```  
int P[4][3] =   
{  
   1, 1, 1, 2, 2, 2, 3, 3, 3, 4, 4, 4  
};  
```  
  
 Küme parantezleri listesindeki tek tek başlatıcıları geçici da görüntülenebilir ve yukarıdaki örnekte açıklamak için yardımcı.  
  
 Bir toplama değişkeni başlattığınızda, köşeli parantez kullanma konusunda dikkatli olmanız gerekir ve Başlatıcı düzgün listeler. Aşağıdaki örnekte, küme ayraçları daha ayrıntılı derleyicinin yorumu gösterilmektedir:  
  
```  
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
  
 Bu örnekte, `nlist` üç üyesi olan her yapısı yapıları 2 ile 3 dizisi olarak bildirilmedi. Başlatma 1 satırının ilk satırının değerleri atar `nlist`aşağıdaki gibi:  
  
1.  1 satırda ilk sol ayraç derleyici ilk toplama üyesinin başlatmanın sinyalleri `nlist` (diğer bir deyişle, `nlist[0]`) başlangıçtır.  
  
2.  İkinci sol ayraç ilk toplama üyesinin başlatmanın gösterir `nlist[0]` (diğer bir deyişle, yapısı, `nlist[0][0]`) başlangıçtır.  
  
3.  İlk kuşak bitip yapısı başlatma `nlist[0][0]`; sonraki sol ayraç başlatılıyor `nlist[0][1]`.  
  
4.  İşlem kapatılan sağ parantez başlatılması bittiği satırın sonuna kadar devam eder `nlist[0]`.  
  
 Satır 2 ikinci satırının değerleri atar `nlist` benzer şekilde. 1 ve 2 satırda başlatıcıları kapsayan kaşlı dış kümesi gerekli olduğunu unutmayın. Dış küme ayraçları atlar, aşağıdaki yapım hataya neden olur:  
  
```  
triplet nlist[2][3] =  /* THIS CAUSES AN ERROR */  
{  
     {  1, 2, 3 },{  4, 5, 6 },{  7, 8, 9 },   /* Line 1 */  
     { 10,11,12 },{ 13,14,15 },{ 16,17,18 }    /* Line 2 */  
};  
```  
  
 Bu yapı, 1. satırına ilk sol ayraç başlatılması başlatır `nlist[0]`, üç yapıları dizisi olduğu. Değerler 1, 2 ve 3 ilk yapısı üç üyelerine atanır. Sonraki kuşak karşılaşıldı (sonra değeri 3) başlatılması olduğunda `nlist[0]` tamamlandıktan ve üç yapısı dizi iki kalan yapılarda 0'a otomatik olarak başlatılır. Benzer şekilde, `{ 4,5,6 }` ikinci satırında ilk yapısı başlatır `nlist`. Kalan iki yapılarını `nlist[1]` 0 olarak ayarlayın. Derleyici sonraki başlatıcı listesi karşılaştığında ( `{ 7,8,9 }` ), başlatmak çalışır `nlist[2]`. Bu yana `nlist` yalnızca iki satır varsa, bu deneme bir hataya neden olur.  
  
 Bu bir sonraki örnekte, üç `int` üyeleri `x` 1, 2 ve 3, sırasıyla başlatılır.  
  
```  
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
  
 İçinde `list` yukarıdaki yapısı, ilk satırının üç öğeleri `m` 4.0 için; başlatılmış kalan satırının öğelerini `m` 0,0 olarak varsayılan olarak başlatılır.  
  
```  
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
  
 Birleşim değişkeni `y`, bu örnekte, başlatılır. Birleşik bir başlatıcı Başlatıcı olacak şekilde ilk birleşim bir dizi öğedir. Başlatıcı listesi `{'1'}` değerleri dizinin ilk satırına atar. Tek bir değer listede görünür olduğundan, ilk sütun öğesinde karakter başlatılmadan `1`, ve kalan iki öğe satırda 0 değeri varsayılan olarak başlatılır. Benzer şekilde, ikinci satırında, ilk öğe `x` karakter başlatılmış `4`, ve kalan iki öğe satırda değeri 0 başlatılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlatma](../c-language/initialization.md)