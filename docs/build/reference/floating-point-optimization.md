---
title: Microsoft Visual C++'ı kayan nokta iyileştirme | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 082cd3a7721f1bc72899130159b724b292e5e217
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595054"
---
# <a name="microsoft-visual-c-floating-point-optimization"></a>Microsoft Visual C++ kayan nokta iyileştirme

Kayan nokta semantiklerini yönetme Microsoft C++ derleyicisinin yöntemi kullanarak kayan nokta kodu en iyi duruma getirmek için bir tanıtıcı alın. Yalnızca güvenli iyileştirmeleri kayan nokta kodu gerçekleştirilen sağlarken hızlı programlar oluşturun.

## <a name="optimization-of-floating-point-code-in-c"></a>C++ kayan nokta kodu iyileştirme

En iyi duruma getirme bir C++ derleyicisi, kaynak kodu yalnızca makine koduna çevirir., makine yönergelerine verimliliği artırın ve/veya boyutunu küçültmek için farklı şekilde düzenler. Ne yazık ki, birçok genel iyileştirmeler için kayan nokta hesaplamalar uygulandığında mutlaka güvenli değildir. Bunun iyi bir örneği, "Ne her bilgisayar uzmanı gerektiğini bilmeniz hakkında Floating-Point aritmetik", David Goldberg alınan aşağıdaki toplama algoritması kullanılarak görülebilir. *bilgi işlem anketler*, Mart 1991, pg. 203:

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0, C=0, Y, T;
   for (int i=0; i<n; i++)
   {
      Y = A[i] - C;
      T = sum + Y;
      C = T - sum - Y;
      sum = T;
   }
   return sum;
}
```

Bu işlev n ekler **float** dizi vektördeki değerler `A`. Döngü gövdesi içinde algoritma çoğaltmayı toplamayı sonraki adıma uygulanır bir "düzeltme" değerini hesaplar. Bu yöntem, toplu yuvarlama hataları O(n) zaman karmaşıklığı korurken basit bir toplama karşılaştırıldığında büyük ölçüde azaltır.

Naïve C++ derleyicisi, kayan nokta aritmetiği gerçek sayı aritmetik cebirsel aynı kuralları izler varsayabilirsiniz. Böyle bir derleyici ardından deneyebileceğinizi, duymanıza neden olabilir

> C T - Toplam - Y = == > (Toplam + Y) - Toplam - Y == > 0;

Diğer bir deyişle, C algılanan değeri her zaman sabit sıfır olduğunu. Bu sabit değer ardından sonraki ifadelere yayılır, döngü gövdesi için basit bir toplama azaltılır. Kesin olarak için

> Y = C bir [i] - == > Y = [i]<br/>T = Toplam + Y == > T = toplam + [i]<br/>Sum T = == > toplam = toplam + [i]

Bu nedenle, mantıksal bir dönüştürme naïve derleyici için `KahanSum` işlevi olur:

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0; // C, Y & T are now unused
   for (int i=0; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

Dönüştürülen algoritması daha hızlı olmasına rağmen *hiç programcının engellemekse doğru bir gösterimi olan*. Özenle hazırlanmış hata düzeltme tamamen kaldırıldı ve biz bir basit, doğrudan toplama algoritması tüm ilişkili hata sol.

Kuşkusuz karmaşık bir C++ derleyicisi, cebirsel bilecektir kuralları gerçek aritmetik genellikle uygulanmaz için kayan nokta aritmetiği. Ancak, daha karmaşık bir C++ derleyicisi Programcı engellemekse hala yanlış yorumlayabilir.

Çok değerle (çağrılan "kayıt" değeri) mümkün olduğunca kayıtlara tutun dener ortak bir iyileştirme göz önünde bulundurun. İçinde `KahanSum` örnek, bu en iyi duruma getirme için yere değişkenleri çalışabilir `C`, `Y` ve `T` yalnızca döngü gövdesi içinde kullanıldıktan sonra. Kayıt duyarlık 23bits (tek) yerine 52bits (çift) ise, bu en iyi duruma getirme türü etkili bir şekilde yükseltir. `C`, `Y` ve `T` türüne **çift**. Toplam değişken benzer şekilde işlemiyor değilse tek duyarlıklı kodlanmış kalır. Bu semantiği dönüştüren `KahanSum` aşağıdaki

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0;
   double C=0, Y, T; // now held in-register
   for (int i=0; i<n; i++)
   {
      Y = A[i] - C;
      T = sum + Y;
      C = T - sum - Y;
      sum = (float) T;
   }
   return sum;
}
```

Ancak `Y`, `T` ve `C` artık hesaplanır yüksek kesinliği, bu yeni kodlama değerlere bağlı olarak daha az doğru bir sonuç oluşturabilir `A[]`. Bu nedenle görünüşte zararsız iyileştirmeleri olumsuz sonuçları olabilir.

Bu tür iyileştirme sorunları "karmaşık" kayan nokta kodu sınırlı değildir. Daha basit bir kayan nokta algoritmaları yanlış, iyileştirilmiş başarısız olabilir. Basit, doğrudan toplama algoritması göz önünde bulundurun:

```cpp
float Sum( const float A[], int n )
{
   float sum=0;
   for (int i=0; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

Bazı kayan nokta birimlerinin aynı anda birden çok işlem gerçekleştirme yetkinliğine sahip olduğundan, bir derleyici bir skalar azalma iyileştirme etkileşim kurmak isteyebilirsiniz. Bu iyileştirme etkili bir şekilde üstten basit Sum işlevi ve bunlar aşağıdaki şekilde dönüştürür:

```cpp
float Sum( const float A[], int n )
{
   int n4 = n-n%4; // or n4=n4&(~3)
   int i;
   float sum=0, sum1=0, sum2=0, sum3=0;
   for (i=0; i<n4; i+=4)
   {
      sum = sum + A[i];
      sum1 = sum1 + A[i+1];
      sum2 = sum2 + A[i+2];
      sum3 = sum3 + A[i+3];
   }
   sum = sum + sum1 + sum2 + sum3;
   for (; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

İşlevi, şimdi her adımda eşzamanlı olarak işlenebilecek dört ayrı matematiksel tutar. En iyi duruma getirilmiş işlevi artık çok daha hızlı olsa da, en iyi duruma getirilmiş sonuçları getirilmemiş sonuçlardan oldukça farklı olabilir. Bu değişiklik yaparken, derleyicinin ilişkilendirilebilir kayan nokta ekleme varsayılır; diğer bir deyişle, bu iki ifadeleri eşdeğerdir: `(a + b) + c == a + (b + c)`. Ancak, birleşim her zaman için kayan nokta sayıları true tutmaz. Toplam olarak bilgi işlem yerine:

```cpp
sum = A[0]+A[1]+A[2]+...+A[n-1];
```

Dönüştürülen işlev sonucu olarak artık hesaplar.

```cpp
sum = (A[0]+A[4]+A[8]+...)
    + (A[1]+A[5]+A[9]+...)
    + (A[2]+A[6]+A[10]+...)
    + (A[3]+A[7]+A[11]+...);
```

Bazı değerler için `A[]`, toplama işlemlerini farklı Bu sıralama, beklenmeyen sonuçlara neden olabilir. Daha fazla işleniyor, bazı programcılar gibi iyileştirmeler umuyor ve bunlar için uygun bir şekilde dengelemek tercih edebilirsiniz. Bu durumda, bir program dizi oluşturabilirsiniz `A` farklı bir düzende böylece en iyi duruma getirilmiş toplamı beklenen sonuçları üretir. Ayrıca, çoğu durumda en iyi duruma getirilmiş sonucu doğruluğunu "sağlayacak kadar yakındır" olabilir. İyileştirme ilgi çekici hızı avantaj sağlar, bu özellikle doğrudur. Video oyunları, örneğin, mümkün olduğunca çok hızlandırmak, ancak genellikle yüksek oranda doğru kayan nokta hesaplamalar gerektirmeyen gerektirir. Derleyici alıcılar, bu nedenle çoğunlukla birbirinden ayrı hedeflerinden biri, hızı ve doğruluğu denetlemek programcıları için bir mekanizma sağlamanız gerekir.

Bazı derleyiciler, hızı ve doğruluğu arasındaki her iyileştirme türü için ayrı bir anahtar sağlayarak çözümleyin. Bu, geliştiricilerin, belirli bir uygulama için kayan nokta doğruluğu değişiklikleri neden olan iyileştirmeleri devre dışı bırakma olanak tanır. Bu çözüm, derleyici bir denetime yüksek derecede sunabilir, ancak bazı ek sorunlar sunar:

- Bu genellikle, etkinleştirme veya devre dışı geçer anlaşılır değil.
- Hiçbir tek iyileştirme devre dışı bırakma kayan nokta olmayan kod performansını olumsuz etkileyebilir.
- Her bir ek anahtar birçok yeni geçiş birleşimleri artmasına neden olur; birleşim sayısını hızlı bir şekilde zahmetli hale gelir.

Her iyileştirme için ayrı anahtar sağlayan cazip görünebilir, ancak bu nedenle böyle derleyicileri kullanarak hantal ve güvenilir olabilir.

Birçok C++ Derleyicileri sunan bir *tutarlılık* kayan nokta modeli (aracılığıyla bir **; /OP &** veya **/fltconsistency** geçiş) uyumlu programlar oluşturmak için geliştirici sağlar katı kayan nokta semantiklerini ile. Bağlı olduğunda, bu modeli derleyici en iyileştirmelerini kayan nokta hesaplamalarında kullanarak bu iyileştirmeler olmayan-kayan nokta kodu için izin verirken engeller. Bir tutarlılık modelini ancak koyu tarafı sahiptir. Tahmin edilebilir sonuçlar farklı FPU mimarilerde, neredeyse tüm uygulamaları döndürmek için **; /OP &** kullanıcıya yuvarlak Ara ifadelerin Duyarlığı belirtildi; Örneğin, aşağıdaki ifadeyi göz önünde bulundurun:

```cpp
float a, b, c, d, e;
// . . .
a = b * c + d * e;
```

Tutarlı ve tekrarlanabilir sonuçlar altında için **; /OP &**, sanki gibi uygulandığına Bu ifade değerlendirilir:

```cpp
float x = b  *c;
float y = d * e;
a = x + y;
```

Nihai sonucu artık tek duyarlıklı yuvarlama hatalarından alternatife *ifadenin değerlendirilmesi, her bir adımı*. Bu yorumu herhangi bir C++ semantiği kural kesinlikle sonu gelmez olsa da, bunu neredeyse hiç kayan nokta ifadelerinin değerlendirmek için en iyi yoludur. Ara pratik duyarlık olarak yüksek sonuçlanır işlem genellikle daha tercih edilir. Örneğin, ifade hesaplamak daha iyi olacaktır `a = b * c + d * e` gibi daha yüksek bir duyarlık içinde

```cpp
double x = b * c;
double y = d * e;
double z = x + y;
a = (float)z;
```

veya henüz daha iyi

```cpp
long double x = b * c;
long double y = d * e
long double z = x + y;
a = (float)z;
```

Daha yüksek duyarlılık Ara sonuçların hesaplanırken, nihai sonucu önemli ölçüde daha doğru olur. Tam olarak güvenli olmayan iyileştirmeleri devre dışı bırakarak hata azaltmak kullanıcı çalıştığında ironically, tutarlılık modeli benimseyerek, hata olasılığını artar. Bu nedenle bir tutarlılık modelini aynı anda daha yüksek doğruluk garantisi sağlarken verimliliği ciddi da azaltabilir. Ciddi sayısal programcılar bu gibi çok iyi bir düşüş görülüyor ve model genellikle iyi alınmamışsa, birincil nedenidir.

8.0 (Visual C++® 2005), Microsoft C++'ın sürümünden başlayarak, derleyici bir çok daha iyi bir alternatif sağlar. Programcılar üç genel kayan nokta moddan birini seçmenize imkan tanır: fp: precise, FP: Fast ve fp: strict.

- Altında fp: precise, yalnızca güvenli iyileştirmeleri kayan nokta kodu ve farklı olarak gerçekleştirilen **; /OP &**, Ara hesaplamalar en yüksek pratik duyarlık tutarlı bir şekilde gerçekleştirilir.
- FP: Fast modu doğruluktan daha agresif iyileştirme izin vererek kayan nokta kurallarını rahatlatır;.
- FP: strict modu tüm genel fp doğruluğunu sağlar: etkinleştirme fp özel durum anlamsalları ve FPU ortam değişiklikler (ör. değişiklikleri yuvarlama yönünü vb. kayıt duyarlılığa) varlığında geçersiz dönüşümleri önleme kesin.

Kayan nokta özel durum anlamsalları bağımsız olarak bir komut satırı anahtarı veya derleyici pragması tarafından denetlenebilir; Varsayılan olarak, kayan nokta özel durum anlamsalları fp altında devre dışı bırakılır: kesin ve etkin altında fp: strict. Derleyici ayrıca FPU ortam duyarlılık ve kısaltmalar gibi belirli kayan nokta belirli iyileştirmelerde üzerinde denetim sağlar. Bu rahatça model geliştiricilere önemli miktarda yük çok fazla derleyici anahtarlarının veya Aday müşteri, istenmeyen yan etkileri olmadan kayan nokta kodu derlemesi üzerinde denetim sağlar.

## <a name="the-fpprecise-mode-for-floating-point-semantics"></a>Fp: precise modu için kayan nokta semantiklerini

Varsayılan kayan nokta semantiklerini moddur fp: precise. Bu modu seçildiğinde, derleyicinin kayan nokta işlemlerini iyileştirmek, kesin olarak güvenlik kural kümesine uyar. Bu kurallar, derleyicinin kayan nokta hesaplamalar doğruluğunu koruyarak verimli makine kodu oluşturmasına izin verir. Hızlı üretim kolaylaştırmak için programlar, fp: precise modeli devre dışı bırakır kayan nokta özel durum anlamsalları (bunlar açıkça etkin hale getirilebilir rağmen). Microsoft fp seçilen: hızlı ve doğru programlar oluşturduğundan kesin olarak varsayılan kayan nokta modu.

Fp istemenin: kullanım komut satırı derleyicisi kullanarak hassas modu [/FP: precise](fp-specify-floating-point-behavior.md) geçiş:

> cl/FP: precise source.cpp

Bu dp kullanılacağını derleyiciye: source.cpp dosyası için kodu oluşturulurken kesin semantiği. Fp: precise modeli da çağrılabilir bir işlev tarafından işlevi kullanarak [float_control derleyici pragma](#the-float-control-pragma).

Altında fp: precise modu, derleyici hiçbir zaman kayan nokta hesaplamalar doğruluğunu perturb tüm iyileştirmeler gerçekleştirir. Derleyici atamaları her zaman doğru yuvarlar, yuvarlamasını ve işlev çağrıları ve FPU kaydeder gibi ara yuvarlama tutarlı bir şekilde aynı duyarlık gerçekleştirilir. Kısaltmalardan gibi güvenli iyileştirmeleri, varsayılan olarak etkindir. Özel durum anlamsalları ve FPU ortam duyarlılık varsayılan olarak devre dışıdır.

|FP: precise semantiği|Açıklama|
|-|-|
|Semantik yuvarlama|Açık atamaları yuvarlama yuvarlamasını ve işlevini çağırır. Ara ifadelerin kayıt duyarlık olarak değerlendirilir.|
|Cebirsel dönüşümleri|Katı kayan nokta Cebir ilişkilendirilemez, dağılma olmayan kıldığı bir dönüştürme her zaman kesin olan sürece, aynı sonuçları üretir.|
|Kısaltmalar|Varsayılan olarak izin verilir. Daha fazla bilgi için bkz. [fp_contract pragması](#the-fp-contract-pragma).|
|Kayan nokta değerlendirme sırası|Son sonuçları değiştirilmediğini şartıyla, derleyicinin kayan nokta ifadeleri değerlendirme yeniden.|
|FPU ortam erişimi|Varsayılan olarak devre dışıdır. Daha fazla bilgi için bkz. [fenv_access pragma](#the-fenv-access-pragma). Varsayılan duyarlık ve yuvarlama modu olduğu varsayılır.|
|Kayan nokta özel durum anlamsalları|Varsayılan olarak devre dışıdır. Daha fazla bilgi için [/FP: except](fp-specify-floating-point-behavior.md).|

### <a name="rounding-semantics-for-floating-point-expressions-under-fpprecise"></a>Fp altında kayan nokta ifadeleri için semantiği yuvarlama: kesin

Fp: precise modeli her zaman açıkça ifade değerlendirmesindeki belirli noktalarda yalnızca yuvarlama yüksek pratik duyarlık sırasında Ara hesaplamalar gerçekleştirir. Yuvarlama için kullanıcı tarafından belirtilen duyarlığını her zaman içinde dört basamak gerçekleşir: (a) bir türü atayarak (b) gerçekleştirildiğinde atama ortaya çıktığında, (c) bir kayan nokta değeri geçirilir bağımsız değişken olarak bir işlev ve (d) bir kayan nokta değeri öğesinden döndürülen bir işlev. Ara hesaplamalar kayıt duyarlık her zaman gerçekleştirilir, Ara sonuçlar doğruluğunu platform bağımlı olduğundan (duyarlık her zaman en az belirtilen kullanıcı olarak doğru olur ancak duyarlık).

Aşağıdaki kodda atama ifadesi göz önünde bulundurun. Sağ taraftaki ifade atama işleci '=' kayıt duyarlık hesaplanan ve atamanın sol tarafı türüne açıkça yuvarlanır.

```cpp
float a, b, c, d;
double x;
...
x = a*b + c*d;
```

hesaplanır

```cpp
float a, b, c, d;
double x;
...
register tmp1 = a*b;
register tmp2 = c*d;
register tmp3 = tmp1+tmp2;
x = (double) tmp3;
```

Açıkça bir ara sonuç yuvarlak bir typecast dağıtır. Örneğin, önceki kod ekleyerek değiştirilmişse açık bir türü atayarak, Ara deyimi (c * d) typecast türüne yuvarlanır.

```cpp
float a, b, c, d;
double x;
// . . .
x = a*b + (float)(c*d);
```

hesaplanır

```cpp
float a, b, c, d;
double x;
// . . .
register tmp1 = a*b;
float tmp2 = c*d;
register tmp3 = tmp1+tmp2;
x = (double) tmp3;
```

Yuvarlama bu yöntemin bir olduğu çıkarımında görünüşte eşdeğer bazı dönüştürmeleri aslında aynı semantiği gerekmemesidir. Örneğin, aşağıdaki dönüştürme iki atama ifadeleri tek atama ifadeye ayırır.

```cpp
float a, b, c, d;
// . . .
a = b*(c+d);
```

değil eşdeğerdir

```cpp
float a, b, c, d;
// . . .
a = c+d;
a = b*a;
```

Benzer şekilde:

```cpp
a = b*(c+d);
```

değil eşdeğerdir

```cpp
a = b*(a=c+d);
```

İkinci kodlamalarının her bir ek atama işlemi sunulmuştur ve bu nedenle bir ek yuvarlama işaret bu kodlamalarda eşdeğer semantiği yoktur.

Bir işlev bir kayan nokta değeri döndürür, işlev türü için değer yuvarlanır. Bir kayan nokta değeri bir işleve parametre olarak geçirildiğinde parametresinin türü için değer yuvarlanır. Örneğin:

```cpp
float sumsqr(float a, float b)
{
   return a*a + b*b;
}
```

hesaplanır

```cpp
float sumsqr(float a, float b)
{
    register tmp3 = a*a;
    register tmp4 = b*b;
    register tmp5 = tmp3+tmp4;
    return (float) tmp5;
}
```

Benzer şekilde:

```cpp
float w, x, y, z;
double c;
...
c = symsqr(w*x+y, z);
```

hesaplanır

```cpp
float x, y, z;
double c;
...
register tmp1 = w*x;
register tmp2 = tmp1+y;
float tmp3 = tmp2;
c = symsqr( tmp3, z);
```

### <a name="architecture-specific-rounding-under-fpprecise"></a>Mimariye özgü yuvarlama altında fp: precise

|İşlemci|Ara ifadelerin duyarlığını yuvarlama|
|-|-|
|x86|Ara ifadelerin bir 16 bit üs tarafından sağlanan genişletilmiş bir aralıkla varsayılan 53-bit duyarlığa hesaplanır. Bu 53:16 değerler "(bir işlev çağrısı sırasında olabileceği gibi) bellek geçmiş"olduğunda, 11 bit genişletilmiş üstel aralık daraltıldığı. Diğer bir deyişle, geçmiş değerler yalnızca 11 bit üs ile standart çift duyarlık biçimine cast.<br/>Bir kullanıcı kullanarak kayan nokta denetim sözcüğünü değiştirerek Ara yuvarlama genişletilmiş 64 bit duyarlık geçin `_controlfp` ve FPU ortam erişimi etkinleştirerek (bkz [fenv_access pragma](#the-fenv-access-pragma)). Ancak, genişletilmiş duyarlık yazmaç değerlerini bellek geçmiş, Ara sonuçlar hala çift duyarlık yuvarlanır.<br/>Bu özellikle anlam tabi bir değişikliktir.|
|amd64|FP semantiği amd64 diğer platformlardan biraz farklıdır. Performansla ilgili nedenlerden dolayı yerine iki işlenenden kullanılabilir geniş duyarlık en geniş duyarlığını, Ara işlem hesaplanır.  İşlenenler daha geniş bir duyarlık kullanılarak hesaplanmasını hesaplamalar zorlamak için en az bir işlenen bir alt ifadede atama işleminde tanıtmak kullanıcıların gerekir.<br/>Bu özellikle anlam tabi bir değişikliktir.|

### <a name="algebraic-transformations-under-fpprecise"></a>Cebirsel dönüşümleri altında fp: precise

Zaman fp: precise modu etkin olduğunda, derleyici, hiçbir zaman cebirsel dönüşümleri gerçekleştirir *nihai sonucu kanıtlanabilir aynı olmadığı sürece*. Alışık olduğunuz aritmetik bir gerçek sayı cebirsel kurallarının çoğu için kayan nokta aritmetiği her zaman tutmayın. Örneğin, aşağıdaki deyimler eşdeğerdir Reals, ancak mutlaka float.

|Form|Açıklama|
|-|-|
|`(a+b)+c = a+(b+c)`|İlişkili kural ekleme|
|`(a*b)*c = a*(b*c)`|İlişkili kural çarpma için|
|`a*(b+c) = a*b + b*c`|Çarpma toplama üzerinden dağıtılması|
|`(a+b)(a-b) = a*a-b*b`|Cebirsel hesaba katacak şekilde|
|`a/b = a*(1/b)`|Multiplicative ters bölme|
|`a*1.0 = a`|Çarpma kimlik|

İşlevi ile giriş örnekte gösterildiği gibi `KahanSum`, derleyici, önemli ölçüde daha hızlı programlar oluşturmak için çeşitli cebirsel dönüşümleri gerçekleştirmenize olanak tempted. En iyi duruma getirme gibi cebirsel dönüşümleri üzerinde bağımlı neredeyse her zaman yanlış olsa da, mükemmel bir şekilde güvenli oldukları durumlar vardır. Örneğin, bazen bölme değiştirmek için tercih edilir bir *sabit* ters çarpma çarpım sabitinin değeriyle:

```cpp
const double four = 4.0;
double a, b;
...

a = b/four;
```

Olarak dönüştürülür

```cpp
const double four = 4.0;
const double tmp0 = 1/4.0;
double a, b;
...
a = b*tmp0;
```

İyileştirici derleme zamanında x'in belirleyebilirsiniz güvenli bir dönüştürme olmasıdır / 4.0 x*(1/4.0) x sonsuz ve NaN dahil olmak üzere tüm kayan nokta değerleri için ==. Bir bölme işleminde bir çarpma ile değiştirerek, derleyici birkaç döngü kaydedebilirsiniz; özellikle, doğrudan bölme uygulamayıp ancak derleyicinin tersini yaklaşık bir birleşimini oluşturup Çarp-Ekle ihtiyaç FPUs üzerinde yönergeler. Böyle bir iyileştirme altında fp derleyici gerçekleştirebilir: yalnızca tam değiştirme çarpma oluşturursa, kesin aynı bölüm sonucu. Derleyici ayrıca fp altında Önemsiz dönüştürmeleri gerçekleştirebilir: precise, sonuçları aynı olması koşuluyla. Bu güncelleştirmeler şunlardır:

|Form|Açıklama
|-|-|
|`(a+b) == (b+a)`|Yer değiştirebilirlik kuralı ekleme|
|`(a*b) == (b*a)`|Çarpma için yer değiştirebilirlik kuralı|
|`1.0*x*y == x*1.0*y == x*y*1.0 == x*y`|1.0 ile çarpım|
|`x/1.0*y == x*y/1.0 == x*y`|1.0 ile bölme|
|`2.0*x == x+x`|2.0 ile çarpım|

### <a name="contractions-under-fpprecise"></a>Kısaltmalar altında fp: precise

Bir anahtar mimari birçok modern kayan nokta birimi Ara yuvarlama hata ile tek bir işlem olarak bir toplama arkasından bir çarpma yeteneğini özelliğidir. Örneğin, Intel Itanium mimarisini Üçlü bu işlemlerden her biriyle birleştirmek için yönergeler sağlar (bir*b + c), (bir*b-c) ve (c-a * b), tek bir kayan nokta yönergesi içine (fma fms ve fnma sırasıyla). Bu tek yönergeleri ayrı yürütme daha hızlı çarpın ve yönergeler ekleyin ve Ara çarpımını yuvarlama olduğundan daha doğru. Bu iyileştirme, önemli ölçüde işlevlerini içeren birkaç birden çok kez aralıklı hızlandırmak ve işlemleri ekleyin. Örneğin, n-boyutlu iki vektörün nokta çarpımını hesaplar aşağıdaki algoritmasını göz önünde bulundurun.

```cpp
float dotProduct( float x[], float y[], int n )
{
   float p=0.0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

Bu hesaplama gerçekleştirilen bir dizi Çarp-Ekle p formun yönergeleri = p + x [i] * y [i].

Daraltmaya iyileştirme bağımsız olarak kullanılarak denetlenebilir `fp_contract` derleyici pragması. Varsayılan olarak, fp: precise modeli sağlar kısaltmalar için hem doğruluk ve hızı artırmak bu yana. Altında fp: precise, derleyici hiçbir zaman bir ifade açıkça yuvarlama ile sözleşme imzalarsınız.
Örnekler

```cpp
float a, b, c, d, e, t;
...
d = a*b + c;         // may be contracted
d += a*b;            // may be contracted
d = a*b + e*d;       // may be contracted into a mult followed by a mult-add
etc...

d = (float)a*b + c;  // won't be contracted because of explicit rounding

t = a*b;             // (this assignment rounds a*b to float)
d = t + c;           // won't be contracted because of rounding of a*b
```

### <a name="order-of-floating-point-expression-evaluation-under-fpprecise"></a>Fp altında kayan nokta ifade değerlendirme sırası: kesin

Kayan nokta ifade değerlendirme sırası korumak iyileştirmeleri her zaman güvenlidir ve bu nedenle fp altında izin verilir: kesin modu. Tek duyarlıklı olarak iki n-boyutlu vektörün nokta çarpımını hesaplar aşağıdaki işlevin göz önünde bulundurun. Programcı tarafından kodlanmış olarak ilk kod bloğu orijinal işlev kısmi bir döngü döngülerin iyileştirme sonrasında aynı işlev tarafından izlenir.

```cpp
//original function
float dotProduct( float x[], float y[], int n )
{
   float p=0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}

//after a partial loop-unrolling
float dotProduct( float x[], float y[], int n )
{
   int n4= n/4*4; // or n4=n&(~3);
   float p=0;
   int i;

   for (i=0; i<n4; i+=4)
   {
      p+=x[i]*y[i];
      p+=x[i+1]*y[i+1];
      p+=x[i+2]*y[i+2];
      p+=x[i+3]*y[i+3];
   }

   // last n%4 elements
   for (; i<n; i++)
      p+=x[i]*y[i];

   return p;
}
```

Bu iyileştirme birincil avantajı, koşullu döngü dallanma sayısı % 75 azaltmasıdır. Ayrıca, döngü gövdesi içinde işlemlerin sayısını artırarak, derleyici artık daha da iyileştirmek için daha fazla fırsat olabilir. Örneğin, bazı FPUs gerçekleştirmek mümkün olabilir Çarp-Ekle p += x [i] * y [i] x [i + 1] için değerler aynı anda getirilirken hatayla ve y [i + 1] bir sonraki adımda kullanmak üzere. Bu tür bir iyileştirme kayan nokta hesaplamaları için mükemmel bir şekilde güvenli çünkü işlemlerin sırasını korur.

Genellikle, derleyicinin tüm işlemleri daha hızlı kod üretmek için yeniden sıralamak de yararlıdır. Aşağıdaki kodu göz önünde bulundurun:

```cpp
double a, b, c, d;
double x, y, z;
...
x = a*a*a + b*b*b + c*c*c;
...
y = a*a + b*b + c*c;
...
z = a + b + c;
```

Anlam C++ kurallarını belirtmek ilk hesaplanan gibi program sonuçlar üretmelidir x, sonra y ve son olarak z. Yalnızca dört kullanılabilir kayan nokta kayıtlarını derleyici olduğunu varsayalım. Derleyici işlem zorunda kalıyorsa x, y ve z sırasıyla aşağıdaki semantiğine sahip kodu oluşturmak tercih edebilirsiniz:

```cpp
double a, b, c, d;
double x, y, z;
register r0, r1, r2, r3;
...
// Compute x
r0 = a;         // r1 = a*a*a
r1 = r0*r0;
r1 = r1*r0;
r0 = b;         // r2 = b*b*b
r2 = r0*r0;
r2 = r2*r0;
r0 = c;         // r3 = c*c*c
r3 = r0*r0;
r3 = r3*r0;
r0 = r1 + r2;
r0 = r0 + r3;
x = r0;         // x = r1+r2+r3
// . . .
// Compute y
r0 = a;         // r1 = a*a
r1 = r0*r0;
r0 = b;         // r2 = b*b
r2 = r0*r0;
r0 = c;         // r3 = c*c
r3 = r0*r0;
r0 = r1 + r2;
r0 = r0 + r3;
y = r0;         // y = r1+r2+r3
// . . .
// Compute z
r1 = a;
r2 = b;
r3 = c;
r0 = r1 + r2;
r0 = r0 + r3;
z = r0;         // z = r1+r2+r3
```

Birkaç açıkça yedekli işlemler olduğundan bu kodlama vardır. Derleyici kesinlikle C++ anlam kurallarını izliyorsa, bu sıralama, program her atama raflarının FPU ortam erişimi çünkü gereklidir. Ancak, fp için varsayılan ayarları: precise derleyicinin program ortam erişim değil gibi sorgulamanıza olanak Bu ifadeler yeniden sıralamak izin. Ardından, üç değerden bilgi işlem tarafından şu şekilde ters sırada fazlalıkları kaldırmak ücretsizdir:

```cpp
double a, b, c, d;
double x, y, z;
register r0, r1, r2, r3;
...
// Compute z
r1 = a;
r2 = b;
r3 = c;
r0 = r1+r2;
r0 = r0+r3;
z = r0;
...
// Compute y
r1 = r1*r1;
r2 = r2*r2;
r3 = r3*r3;
r0 = r1+r2;
r0 = r0+r3;
y = r0;
...
// Compute x
r0 = a;
r1 = r1*r0;
r0 = b;
r2 = r2*r0;
r0 = c;
r3 = r3*r0;
r0 = r1+r2;
r0 = r0+r3;
x = r0;
```

Bu kodlama fp yönerge sayısını yaklaşık 40 oranında azaltıldı açıkça üst. Sonuçlar için x, y ve z aynıdır önce olduğu gibi ancak daha az ek yük ile hesaplanır.

Altında fp: precise, derleyici de olabilir *titreşimli görüntü* daha hızlı kod üretmek için ortak bir alt ifadeler. Örneğin, bir dereceden Denklemin kökleri hesaplamak için kod şu şekilde yazılmış olabilir:

```cpp
double a, b, c, root0, root1;
...
root0 = (-b + sqrt(b*b-4*a*c))/(2*a);
root1 = (-b - sqrt(b*b-4*a*c))/(2*a);
```

Bu ifadeler, yalnızca tek bir işlem tarafından farklılık gösterse de Programcı bunu her bir kök değeri en yüksek pratik kesinlik hesaplanan güvence altına almak için bu şekilde yazmış. Altında fp: precise, derleyicinin root0 ve duyarlık kaybı olmadan ortak alt ifadeler kaldırmak için root1 hesaplama titreşimli görüntü ücretsiz olarak kullanılabilir. Örneğin, aşağıdaki birkaç ek adım tam aynı yanıtı üretilirken kaldırdı.

```cpp
double a, b, c, root0, root1;
...
register tmp0 = -b;
register tmp1 = sqrt(b*b-4*a*c);
register tmp2 = 2*a;
root0 = (tmp0+tmp1)/tmp2;
root1 = (tmp0-tmp1)/tmp2;
```

Diğer iyileştirmeler belirli bağımsız ifade değerlendirme taşıma girişiminde bulunabilir. Döngü gövdesi içinde koşullu dalı içeren aşağıdaki algoritmadan göz önünde bulundurun.

```cpp
vector<double> a(n);
double d, s;
// . . .
for (int i=0; i<n; i++)
{
   if (abs(d)>1.0)
      s = s+a[i]/d;
   else
      s = s+a[i]*d;
}
```

Derleyici, algılayabilir ifadenin değerini (abs(d) > 1) döngü gövdesi içinde değişmezdir. Bu "if çekmek" derleyici sağlar, yukarıdaki kod aşağıdaki dönüştürme döngü gövdesinin dışında bir deyim:

```cpp
vector<double> a(n);
double d, s;
// . . .
if (abs(d)>1.0)
   for (int i=0; i<n; i++)
      s = s+a[i]/d;
else
   for (int i=0; i<n; i++)
      s = s+a[i]*d;
```

Dönüştürme işleminin ardından artık yoktur koşullu bir dal dolayısıyla döngü genel performansını önemli ölçüde geliştirmeye döngü gövdelerini birini. Bu tür bir iyileştirme mükemmel güvenlidir çünkü ifadesi değerlendirmesi (abs(d) > 1.0) diğer ifadelerin bağımsızdır.

Bunlar anlam akışı değiştirmek için bu tür bir iyileştirme FPU ortam erişimi veya kayan nokta özel durumlarını saklanacaktır contraindicated. Bu iyileştirmeler yalnızca fp altında kullanılabilir: kesin modu FPU ortam erişimi ve kayan nokta özel durum anlamsalları varsayılan olarak devre dışı bırakıldığı için. FPU ortam erişimi işlevleri açıkça devre dışı bırakabilirsiniz gibi iyileştirmeler kullanarak `fenv_access` derleyici pragması. Benzer şekilde, kayan nokta özel durumlarını kullanma işlevleri kullanmalıdır `float_control(except ... )` derleyici pragması (veya **/FP: except** komut satırı anahtarı).

Özet olarak, fp: precise modu sağlar son sonuçları değiştirilmediğini koşuluyla, kayan nokta ifadelerinin değerlendirme yeniden sıralamak için derleyici ve sonuçları FPU ortam veya kayan nokta özel durumlarını bağımlı değildir.

### <a name="fpu-environment-access-under-fpprecise"></a>FPU ortam erişimi altında fp: precise

Zaman fp: precise modu etkin olduğunda, derleyici bir program erişemez ve FPU ortam alter olduğunu varsayar. Daha önce belirtildiği gibi bu varsayımı yeniden sıralayabilir veya fp altında verimliliğini artırmak için kayan nokta işlemleri taşımak için derleyiciyi etkinleştirir: kesin.

Bazı programlar kullanarak kayan nokta yuvarlama yönünü değiştirebilir `_controlfp` işlevi. Örneği için bazı programlar üst bilgi işlem ve iki kez aynı hesaplama gerçekleştirerek daha düşük hata sınırları üzerinde aritmetik işlemler ilk eksi sonsuza doğru yuvarlama çalışırken, ardından pozitif sonsuza doğru yuvarlama while. FPU yuvarlama denetlemek için kullanışlı bir yol sağlar. bu yana, programcı FPU ortam değiştirerek yuvarlama modunu değiştirmek tercih edebilirsiniz. Aşağıdaki kod, bir hatanın tam olarak bir kayan nokta çarpımı FPU ortam değiştirerek bağlı hesaplar.

```cpp
double a, b, cLower, cUpper;
// . . .
_controlfp( _RC_DOWN, _MCW_RC );    // round to -&infin;
cLower = a*b;
_controlfp( _RC_UP, _MCW_RC );    // round to +&infin;
cUpper = a*b;
_controlfp( _RC_NEAR, _MCW_RC );    // restore rounding mode
```

Fp altında: iyileştirici çağrıları yok saymak ücretsiz, bu nedenle precise, derleyici her zaman varsayılan FPU ortam varsayar `_controlfp` ve yukarıdaki atamaları cUpper azaltmak cLower = = bir * b; Bu açıkça hatalı sonuçlar verir. Bu iyileştirmeler önlemek için kullanarak FPU ortam erişimi etkinleştirmek `fenv_access` derleyici pragması.

Diğer programları FPU'ın durum sözcüğünü kontrol ederek belirli kayan nokta hataları algılamak deneyebilir. Örneğin, aşağıdaki kod sıfırla bölme ve filtresinin koşullarını denetler

```cpp
double a, b, c, r;
float x;
// . . .
_clearfp();
r = (a*b + sqrt(b*b-4*a*c))/(2*a);
if (_statusfp() & _SW_ZERODIVIDE)
   handle divide by zero as a special case
_clearfp();
x = r;
if (_statusfp() & _SW_INEXACT)
   handle inexact error as a special case
etc...
```

Altında fp: precise, ifade değerlendirmesi yeniden sıralama iyileştirmeleri belirli hataları oluşabilen değişim noktaları. Durum sözcüğü erişme programlar kullanarak FPU ortam erişimi etkinleştirmelisiniz `fenv_access` derleyici pragması.

Daha fazla bilgi için bkz. [fenv_access pragma](#the-fenv-access-pragma).

### <a name="floating-point-exception-semantics-under-fpprecise"></a>Kayan nokta özel durum anlamsalları altında fp: precise

Varsayılan olarak, kayan nokta özel durum anlamsalları fp altında devre dışı bırakılır: kesin. Çoğu C++ programcıları, sistem veya C++ özel durumlarını kullanmadan kayan nokta özel durumları işlemek tercih eder. Ayrıca, daha önce belirtildiği gibi kayan nokta özel durum anlamsalları devre dışı bırakma derleyici esneklik kayan nokta işlemleri iyileştirirken sağlar. Kullanın **/FP: dışında** geçiş veya `float_control` pragma fp kullanırken kayan nokta özel durum anlamsalları etkinleştirmek için: tam modeli.

Daha fazla bilgi için bkz. [kayan nokta özel durum anlamsalları etkinleştirme](#enabling-floating-point-exception-semantics).

## <a name="the-fpfast-mode-for-floating-point-semantics"></a>Kayan nokta semantiklerini FP: Fast modu

FP: Fast modu etkin olduğunda, derleyici bu fp kuralları rahatlatır: kayan nokta işlemlerini iyileştirmek, kesin kullanır. Bu moddur derleyicinin kayan nokta kodunun hızını çoğaltamaz kayan nokta doğruluk ve daha fazla izin verir. Yüksek oranda doğru kayan nokta hesaplamalarında güvenmeyin programlar önemli hızlı geliştirme FP: Fast Modu'nu etkinleştirerek karşılaşabilirsiniz.

FP: Fast kayan nokta modu kullanılarak etkinleştirilir [Fast](fp-specify-floating-point-behavior.md) aşağıdaki gibi derleyici komut satırı anahtarı:

> cl Fast source.cpp

Bu örnekte, derleyicinin FP: Fast semantiği source.cpp dosyası için kodu oluşturulurken kullanılacak sağlar. FP: Fast modeli kullanarak bir işlev tarafından işlevi olarak da çağrılabilir `float_control` derleyici pragması.

Daha fazla bilgi için bkz. [float_control pragması](#the-float-control-pragma).

FP: Fast modu altında derleyicinin kayan nokta hesaplamalar doğruluğunu etkileyen en iyi duruma getirme gerçekleştirebilir. Derleyici, doğru atamaları yuvarlak değil, yuvarlamasını veya işlev çağrıları ve Ara yuvarlama işlemi her zaman gerçekleştirilmez. Kısaltmalardan gibi belirli kayan nokta iyileştirmelerinin her zaman etkindir. Kayan nokta özel durum anlamsalları ve FPU ortam duyarlılık devre dışı bırakılmış ve kullanılamaz.

|FP: Fast semantiği|Açıklama
|-|-|
|Semantik yuvarlama|Açık atamaları yuvarlama yuvarlamasını ve işlev çağrıları yoksayılabilir.<br/>Daha az duyarlılık performans gereksinimlerine göre kayıt sırasında Ara ifadelerin yuvarlatılmış.|
|Cebirsel dönüşümleri|Derleyici, gerçek sayı ilişkilendirilebilir, dağılma Cebir göre ifadeler dönüştürme; Bu dönüştürmeler doğru ya da doğru olması garanti edilmez.|
|Kısaltmalar|Her zaman etkindir; pragma tarafından devre dışı bırakılamaz `fp_contract`|
|Kayan nokta değerlendirme sırası|Tür değişiklikler son sonuçları bile değiştirebilir, derleyicinin kayan nokta ifadeleri değerlendirme yeniden.|
|FPU ortam erişimi|Devre dışı. Yok|
|Kayan nokta özel durum anlamsalları|Devre dışı. Yok|

### <a name="rounding-semantics-for-floating-point-expressions-under-fpfast"></a>FP: Fast altında kayan nokta ifadeleri için semantiği yuvarlama

Farklı fp: precise modelinde, FP: Fast modelinde en kullanışlı duyarlık Ara hesaplamalar gerçekleştirir. Atamalar yuvarlama yuvarlamasını ve işlev çağrıları değil her zaman ortaya çıkabilir. Örneğin, üç tek duyarlıklı değişkenleri ilk işlev tanıtır (`C`, `Y` ve `T`). Derleyici, geçerli yükseltme türü, bu değişkenler için yere seçebilirsiniz `C`, `Y` ve `T` çift duyarlıklı için.

Özgün işlevi:

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0, C=0, Y, T;
   for (int i=0; i<n; i++)
   {
      Y = A[i] - C;
      T = sum + Y;
      C = T - sum - Y;
      sum = T;
   }
   return sum;
}
```

Değişkenlerin kaydedilme:

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0;
   double C=0, Y, T; // now held in-register
   for (int i=0; i<n; i++)
   {
      Y = A[i] - C;
      T = sum + Y;
      C = T - sum - Y;
      sum = (float) T;
   }
   return sum;
}
```

Bu örnekte, orijinal işlev amacı FP: Fast subverted. En son sonuç değişkeninde tutulan, iyileştirilmiş `sum`, doğru sonuç oldukça perturbed olabilir.

FP: Fast altında en az kaynak kod tarafından belirtilen duyarlık korumak genellikle derleyici çalışacaktır. Ancak, bazı durumlarda derleyici Ara ifadeleri gerçekleştirmek tercih edebilirsiniz bir *daha düşük hassasiyet* kaynak kodunda belirtilenden. Örneğin, aşağıdaki ilk kod bloğu bir çift duyarlık sürümünü kare kökünü işlevi çağırır. Ne zaman sonucu işlenenler işlevin açıkça tek duyarlıklı için dönüştürme ve belirli durumlarda FP: Fast altında derleyici çift duyarlık çağrısını seçebilirsiniz `sqrt` bir tek duyarlıklı çağrısıyla`sqrtf`işlevi. Yayınları girmeden değeri emin olun çünkü `sqrt` ve tek duyarlıklı olarak kavuşacak değer yuvarlanır, yalnızca bu yuvarlama yer değiştirir. Sqrt gelen değer bir çift duyarlıklı değerdi ve bu dönüşüm derleyici gerçekleştirilen, duyarlık BITS kadar yarısını yanlış olabilir.

Özgün işlevi

```cpp
double sqrt(double);
// . . .
double a, b, c;
float f1, f2;
// . . .
float length = (float)sqrt((float)(a*a + b*b + c*c));
float sum = (float) ((double)f1 + (double)f2);
```

En iyi duruma getirilmiş işlevi

```cpp
float sqrtf(float)...
// . . .
double a, b, c;
float f1, f2;
// . . .
double tmp0 = a*a + b*b + c*c;
float tmp1 = tmp0;    // round of parameter value
float length = sqrtf(tmp1); // rounded sqrt result
float sum = f1 + f2;
```

Ancak daha az doğru bu en iyi duruma getirme gibi tek duyarlıklı, işlevlerin iç sürümleri sağlayan bir işlemcileri hedeflerken özellikle yararlı olabilir `sqrt`. Derleyici gibi iyileştirmeler yalnızca tam olarak ne zaman kullanacağı hem platformu hem de bağlam bağlıdır.

Ayrıca, hiçbir garanti tutarlılık duyarlığını derleyici için kullanılabilir tüm duyarlılık düzeyinde gerçekleştirilebilir Ara hesaplamalar için yoktur. FP: Fast iyileştirici alt türe çevirme Ara hesaplamalar için derleyici en az kod tarafından belirtilen duyarlık düzeyini korumak çalışacak olsa da, daha hızlı veya daha küçük makine kodu oluşturmak için sağlar. Örneği için derleyici daha kodu yukarıdaki bazı Ara multiplications tek duyarlıklı için yuvarlamak için en iyi duruma.

```cpp
float sqrtf(float)...
// . . .
double a, b, c;
float f1, f2;
// . . .
float tmp0 = a*a;     // round intermediate a*a to single-precision
float tmp1 = b*b;     // round intermediate b*b to single-precision
double tmp2 = c*c;    // do NOT round intermediate c*c to single-precision
float tmp3 = tmp0 + tmp1 + tmp2;
float length = sqrtf(tmp3);
float sum = f1 + f2;
```

Ek bu tür bazı Ara hesaplamalar gerçekleştirmek için SSE2'gibi daha düşük hassasiyet bir kayan nokta birimi kullanarak neden olabilir. FP: Fast yuvarlama doğruluğu, böylece platform bağımlı olur; iyi bir işlemci için derleme kod başka bir işlemci için düzgün çalışmayabilir. Hızı doğruluğu problemleri basıyor varsa belirlemek için kullanıcıya kaldı.

FP: Fast iyileştirme için belirli bir işlevin özellikle sorunlu ise, kayan nokta modu yerel olarak fp için değiştirilebilir: kesin kullanarak `float_control` derleyici pragması.


### <a name="algebraic-transformations-under-fpfast"></a>FP: Fast altında cebirsel dönüşümleri

Belirli, derleyicinin FP: Fast modunu etkinleştirir integralden güvenli olmayan cebirsel dönüşümleri noktası ifadeler. Örneğin, aşağıdaki güvenli olmayan iyileştirmeleri FP: Fast altında çalışan.

||||
|-|-|-|
|Özgün kod|#1. adım|#2. adım
|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = y – a – b;`<br/><br/>`c = x – z;`<br/><br/>`c = x * z;`<br/><br/>`c = x - z;`<br/><br/>`c = x + z;`<br/><br/>`c = z-x;`|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = 0;`<br/><br/>`c = x – 0;`<br/><br/>`c = x * 0;`<br/><br/>`c = x - 0;`<br/><br/>`c = x + 0;`<br/><br/>`c = 0 - x;`|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = 0;`<br/><br/>`c = x;`<br/><br/>`c = 0;`<br/><br/>`c = x;`<br/><br/>`c = x;`<br/><br/>`c = -x;`|

Derleyici, 1. adımda gözlemler `z = y – a – b` her zaman sıfıra eşittir. Bu teknik olarak geçersiz gözlemi olsa da, FP: Fast altında izin verilir. Derleyici, daha sonra her değişken z art arda kullanılması için sabit değerin sıfır yayar. 2. adımda gözlemleyerek, derleyicinin daha fazla iyileştirir `x - 0 == x`, `x * 0 == 0`vb. Yeniden, bu gözlemler kesinlikle geçerli olmayan olsa da, bunlar FP: Fast altında izin verilir. İyileştirilmiş kod artık çok daha hızlıdır, ancak Ayrıca önemli ölçüde daha az doğru veya yanlış bile olabilir.

FP: Fast modu etkin olduğunda aşağıdaki (güvenli) cebirsel kurallardan herhangi birinin iyileştirici tarafından kullanılan:

|||
|-|-|
|Form|Açıklama|
|`(a + b) + c = a + (b + c)`|İlişkili kural ekleme|
|`(a * b) * c = a * (b * c)`|İlişkili kural çarpma için|
|`a * (b + c) = a * b + b * c`|Çarpma toplama üzerinden dağıtılması|
|`(a + b)(a - b) = a * a - b * b`|Cebirsel hesaba katacak şekilde|
|`a / b = a * (1 / b)`|Multiplicative ters bölme|
|`a * 1.0 = a, a / 1.0 = a`|Çarpma kimlik|
|`a ± 0.0 = a, 0.0 - a = -a`|Eklenebilir kimlik|
|`a / a = 1.0, a - a = 0.0`|İptal Etme|

FP: Fast iyileştirme için belirli bir işlev özellikle sorunlu ise, kayan nokta modu yerel olarak fp için değiştirilebilir: kesin kullanarak `float_control` derleyici pragması.

### <a name="order-of-floating-point-expression-evaluation-under-fpfast"></a>FP: Fast altında kayan nokta ifade değerlendirme sırası

Farklı fp: precise, FP: Fast derleyicinin daha hızlı kod üretmek için kayan nokta işlemlerini yeniden sıralayabilir ve sağlar. Bu nedenle, bazı iyileştirmeler FP: Fast altında ifadeleri hedeflenen sıralamasını korumak değil. Örneğin, n-boyutlu iki vektörün nokta çarpımını hesaplar aşağıdaki işlevi göz önünde bulundurun.

```cpp
float dotProduct( float x[], float y[],
                  int n )
{
   float p=0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

FP: Fast altında skalar bir azalma iyileştirici gerçekleştirebilir `dotProduct` etkili bir şekilde işlev gibi dönüştürme işlevi:

```cpp
float dotProduct( float x[], float y[],int n )
{
    int n4= n/4*4; // or n4=n&(~3);
    float p=0, p2=0, p3=0, p4=0;
    int i;

    for (i=0; i<n4; i+=4)
    {
        p+=x[i]*y[i];
        p2+=x[i+1]*y[i+1];
        p3+=x[i+2]*y[i+2];
        p4+=x[i+3]*y[i+3];
    }
    p+=p2+p3+p4;

    // last n%4 elements
    for (; i<n; i++)
    p+=x[i]*y[i];

    return p;
}
```

İşlev iyileştirilmiş sürümünde dört ayrı ürün matematiksel aynı anda gerçekleştirilen ve birlikte eklenir. Bu iyileştirme, hesaplama hızlandırabilirsiniz `dotProduct` kadar tarafından bir faktör dört hedef işlemci ancak nihai sonuca bağlı olarak gereksiz işlemek için farklı şekilde yanlış olabilir. Bu iyileştirmeler tek bir işlev veya çeviri birimi için özellikle sorunludur, kayan nokta modu yerel olarak fp için değiştirilebilir: kesin kullanarak `float_control` derleyici pragması.

## <a name="the-fpstrict-mode-for-floating-point-semantics"></a>Fp: strict modu için kayan nokta semantiklerini

Zaman fp: strict modu etkin olduğunda, aynı kuralları için bu fp derleyici uyar: kayan nokta işlemlerini iyileştirmek, kesin kullanır. Bu mod Ayrıca, kayan nokta özel durum anlamsalları ve FPU ortam hassasiyet etkinleştirir ve kısaltmalar gibi bazı iyileştirmeler devre dışı bırakır. Bu işlem en katı modudur.

Fp: katı kayan nokta modu kullanarak etkin [/FP: strict](fp-specify-floating-point-behavior.md) aşağıdaki gibi derleyici komut satırı anahtarı:

> cl/FP: strict source.cpp

Bu örnekte fp kullanılacağını derleyiciye: source.cpp dosyası için kodu oluşturulurken katı semantiklerini. Fp: strict modeli da çağrılabilir bir işlev tarafından işlevi kullanarak `float_control` derleyici pragması.

Daha fazla bilgi için bkz. [float_control pragması](#the-float-control-pragma).

Fp altında: katı mod, derleyici hiçbir zaman kayan nokta hesaplamalar doğruluğunu perturb tüm iyileştirmeler gerçekleştirir. Derleyici atamaları her zaman doğru yuvarlar, yuvarlamasını ve işlev çağrıları ve FPU kaydeder gibi ara yuvarlama tutarlı bir şekilde aynı duyarlık gerçekleştirilir. Kayan nokta özel durum anlamsalları ve FPU ortam duyarlılık varsayılan olarak etkindir. Derleyici her durumda doğruluğu garanti edemediğinden, kısaltmalar gibi bazı iyileştirmeler devre dışı bırakıldı.

|FP: strict semantiği|Açıklama|
|-|-|
|Semantik yuvarlama|Açık atamaları yuvarlama yuvarlamasını ve işlev çağrıları<br/>Ara ifadelerin kayıt duyarlık olarak değerlendirilir.<br/>Aynı fp: precise|
|Cebirsel dönüşümleri|Katı kayan nokta Cebir ilişkilendirilemez, dağılma olmayan kıldığı bir dönüştürme her zaman kesin olan sürece, aynı sonuçları üretir.<br/>Aynı fp: precise|
|Kısaltmalar|Her zaman devre dışı|
|Kayan nokta değerlendirme sırası|Derleyici, kayan nokta ifadelerinin değerlendirme düzenlemez|
|FPU ortam erişimi|Her zaman etkindir.|
|Kayan nokta özel durum anlamsalları|Varsayılan olarak etkindir.|

### <a name="floating-point-exception-semantics-under-fpstrict"></a>Kayan nokta özel durum anlamsalları altında fp: strict

Varsayılan olarak, kayan nokta özel durum anlamsalları altında fp etkinleştirilir: katı modeli. Bu semantiği devre dışı bırakmak için kullanın **/FP: dışında-** geçin veya tanıtan bir `float_control(except, off)` pragması.

Daha fazla bilgi için bölümlere bakın [kayan nokta özel durum anlamsalları etkinleştirme](#enabling-floating-point-exception-semantics) ve [float_control Pragması](#the-float-control-pragma).

## <a name="the-fenvaccess-pragma"></a>Fenv_access pragması

Kullanım:

```cpp
#pragma fenv_access( [ on  | off ] )
```

[Fenv_access](../../preprocessor/fenv-access.md) pragma FPU bayrağı testleri ve FPU modu değişiklikleri bozmaya bazı iyileştirmeler yapmak için derleyici sağlar. Zaman durumunu `fenv_access` devre dışı, derleyici varsayabilirsiniz varsayılan FPU modları etkindir ve FPU bayrakları olmayan test edilir. Varsayılan olarak, ortam erişim fp için devre dışıdır: kesin modu, ancak bu pragma kullanılarak açıkça etkinleştirilebilir. Altında fp: strict, `fenv_access` her zaman etkindir ve devre dışı bırakılamaz. FP: Fast altında `fenv_access` her zaman devre dışı bırakılır ve etkinleştirilemez.

Fp içinde anlatıldığı gibi: kesin bölümünde bazı programcılar kullanarak kayan nokta yuvarlama yönünü değiştirebilir `_controlfp` işlevi. Örneğin, hata üst ve alt sınırları aritmetik işlemler üzerinde işlem için bazı programlar, iki kez aynı hesaplama eksi sonsuza doğru yuvarlama sırasında ilk'a ve ardından artı sonsuza doğru yuvarlama çalışırken gerçekleştirin. FPU yuvarlama denetlemek için kullanışlı bir yol sağlar. bu yana, programcı FPU ortam değiştirerek yuvarlama modunu değiştirmek tercih edebilirsiniz. Aşağıdaki kod, bir hatanın tam olarak bir kayan nokta çarpımı FPU ortam değiştirerek bağlı hesaplar.

```cpp
double a, b, cLower, cUpper;
// . . .
_controlfp( _RC_DOWN, _MCW_RC );    // round to -infinity
cLower = a*b;
_controlfp( _RC_UP, _MCW_RC );       // round to +infinity
cUpper = a*b;
_controlfp( _RC_NEAR, _MCW_RC );    // restore rounding mode
```

Devre dışı bırakıldığında `fenv_access` pragma varsayılan FPU ortam varsaymasını sağlar; böylece iyileştirici çağrıları yoksay ücretsiz olarak kullanılabilir `_controlfp` ve azaltmak için yukarıdaki atamaları `cUpper = cLower = a*b`. Ancak, etkinleştirildiğinde, `fenv_access` gibi iyileştirmeler engeller.

Programlar belirli kayan nokta hataları algılamak için FPU durum sözcüğünü de göz atabilirsiniz. Örneğin, aşağıdaki kod sıfırla bölme ve filtresinin koşullarını denetler

```cpp
double a, b, c, r;
float x;
// . . .
_clearfp();
r = (a*b + sqrt(b*b-4*a*c))/(2*a);
if (_statusfp() & _SW_ZERODIVIDE)
   handle divide by zero as a special case
_clearfp();
x = (a*b + sqrt(b*b-4*a*c))/(2*a);
if (_statusfp() & _SW_INEXACT)
   handle inexact error as a special case
etc...
```

Zaman `fenv_access` olduğundan devre dışı, derleyicinin yürütme sırasında bu nedenle büyük olasılıkla FPU durumu denetimleri subverting kayan nokta ifadelerinin düzenleyebilir. Etkinleştirme `fenv_access` gibi iyileştirmeler engeller.

## <a name="the-fpcontract-pragma"></a>Fp_contract pragması

Kullanım:

```cpp
#pragma fp_contract( [ on | off ] )
```

Fp içinde anlatıldığı gibi: precise, daraltmaya bölümdür birçok modern kayan nokta birimi için temel bir mimari özelliği. Kısaltmalar Ara yuvarlama hata ile tek bir işlem olarak bir toplama arkasından bir çarpma gerçekleştirmenize olanak sağlar. Bu tek yönergeleri ayrı yürütme daha hızlı çarpın ve yönergeler ekleyin ve Ara çarpımını yuvarlama olduğundan daha doğru. Bir sözleşme işlem değerini hesaplar `(a*b+c)` iki işlem sonsuz duyarlık için hesaplanır ve ardından yuvarlanır gibi kayan noktalı sayı en yakın. Bu iyileştirme, önemli ölçüde işlevlerini içeren birkaç birden çok kez aralıklı hızlandırmak ve işlemleri ekleyin. Örneğin, n-boyutlu iki vektörün nokta çarpımını hesaplar aşağıdaki algoritmasını göz önünde bulundurun.

```cpp
float dotProduct( float x[], float y[], int n )
{
   float p=0.0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

Bu hesaplama gerçekleştirilen bir dizi Çarp-Ekle formun yönergeleri `p = p + x[i]*y[i]`.

[Fp_contract](../../preprocessor/fp-contract.md) pragması, kayan nokta ifadelerinin sözleşmeleri yapılır olup olmadığını belirtir. Varsayılan olarak, fp: precise modu doğruluğu hem hızı artırmak bu yana kısaltmalar için sağlar. Kısaltmalar FP: Fast modu için her zaman etkindir. Ancak, hata durumlarını, açık olan algılama kısaltmalar bozmaya çünkü `fp_contract` pragma fp altında her zaman devre dışı: katı mod. Olabilecek örnekleri ne zaman sözleşmeleri yapılır `fp_contract` pragma etkin:

```cpp
float a, b, c, d, e, t;
...
d = a*b + c;         // may be contracted
d += a*b;            // may be contracted
d = a*b + e*d;       // may be contracted into a mult followed by a mult-add etc...

d = (float)a*b + c;  // won't be contracted because of explicit rounding

t = a*b;             // (this assignment rounds a*b to float)
d = t + c;           // won't be contracted because of rounding of a*b
```

## <a name="the-floatcontrol-pragma"></a>Float_control pragması

**/FP: precise**, **Fast**, **/FP: katı** ve **/FP: dışında** anahtarları bir dosyayı dosya çubuğunda kayan nokta semantiklerini denetimi temel. [Float_control](../../preprocessor/float-control.md) pragma, işlev tarafından işlevi olarak böyle bir denetim sağlar.

Kullanım:

```cpp
#pragma float_control(push)
#pragma float_control(pop)
#pragma float_control( precise, on | off [, push] )
#pragma float_control( except, on | off [, push] )
```

Pragmalar `float_control(push)` ve `float_control(pop)` sırasıyla gönderin ve kayan nokta modu ve özel durum seçeneği bir yığın üzerine geçerli durumunu açılır. Dikkat durumu `fenv_access` ve `fp_contract` pragması tarafından etkilenmez `pragma float_control(push/pop)`.

Pragma çağırma `float_control(precise, on)` etkinleştirir ve `float_control(precise, off)` modu kesin semantiği devre dışı bırakır. Benzer şekilde, pragma `float_control(except, on)` etkinleştirir ve `float_control(except, off)` özel durum anlamsalları devre dışı bırakır. Özel durum anlamsalları yalnızca kesin semantiği de etkin olduğunda etkinleştirilebilir. Olduğunda isteğe bağlı `push` bağımsız değişkeni varsa durumlarını `float_control` seçenekleri semantiği değiştirme önce itilir.

### <a name="setting-the-floating-point-semantic-mode-on-a-function-by-function-basis"></a>Kayan nokta anlam modunu işlev tarafından işlevi olarak ayarlama

Komut satırı anahtarları aslında dört farklı kayan nokta pragmaları ayarlamak için Toplu özellik var. Belirli bir kayan nokta anlam modu işlevi tarafından işlevi temelinde açıkça seçmek için her biri aşağıdaki tabloda açıklandığı gibi dört seçeneği kayan nokta pragmaları seçin:

||||||
|-|-|-|-|-|
||float_control(Precise)|float_control(except)|fp_contract|fenv_access|
|/ FP: strict|on|on|Kapalı|on|
|/ FP: strict/FP: except-|on|Kapalı|Kapalı|on|
|/ FP: precise|on|Kapalı|on|Kapalı|
|/ FP: precise/FP: except|on|on|on|Kapalı|
|Fast|Kapalı|Kapalı|on|Kapalı|

Örneğin, aşağıdaki açıkça FP: Fast semantiği sağlar.

```cpp
#pragma float_control( except, off )   // disable exception semantics
#pragma float_control( precise, off )  // disable precise semantics
#pragma fp_contract(on)                // enable contractions
#pragma fenv_access(off)               // disable fpu environment sensitivity
```

> [!Note]
> Özel durum anlamsalları "precise" semantiklerini kapatmadan önce kapatılmalıdır.

## <a name="enabling-floating-point-exception-semantics"></a>Kayan nokta özel durum anlamsalları etkinleştirme

Sıfıra bölme gibi olağanüstü belirli kayan nokta koşullar, bir donanım özel durumu sinyal FPU neden olabilir. Kayan nokta özel durumları varsayılan olarak devre dışıdır. Kayan nokta özel durumlarını FPU denetim sözcüğü değiştirerek etkin `_controlfp` işlevi. Örneğin, aşağıdaki kod sıfırla bölme kayan nokta özel durum sağlar:

```cpp
_clearfp(); // always call _clearfp before
            // enabling/unmasking a FPU exception
_controlfp( _EM_ZERODIVIDE, _MCW_EM );
```

Sıfırla bölme özel durum etkin olduğunda, herhangi bir bölme işlemi ile payda değeri sıfıra eşit bir sinyal FPU özel neden olur.

FPU denetim sözcüğü için varsayılan modu geri yüklemek için çağrı `_controlfp(_CW_DEFAULT, ~0)`.

Kayan nokta özel durum anlamsalları ile etkinleştirme **/FP: except** bayrağı kayan nokta özel durumlarını etkinleştirmekle aynı değildir. Kayan nokta özel durum anlamsalları etkinleştirildiğinde, derleyicinin kayan noktalı bir işlemin herhangi bir özel durum oluşturabilecek bulundurmalıdır. FPU ayrı işlemci birim olduğundan, FPU üzerinde çalıştırma yönergeleri, diğer birimleri yönergeler eşzamanlı gerçekleştirilebilir.

Bir kayan nokta özel durumu etkinleştirildiğinde, FPU izin verilmeyen bir yönerge yürütmeyi durdurmak ve ardından olağanüstü bir koşul FPU durum sözcüğünü ayarlayarak sinyal. CPU sonraki kayan nokta yönergeye ulaştığında bekleyen FPU özel durumlar için ilk denetler. Bekleyen bir özel durum ise, işlemci, işletim sistemi tarafından sağlanan bir özel durum işleyicisini çağırarak yakalar. Bu, kayan noktalı bir işlemin olağanüstü bir koşul karşılaştığında, sonraki kayan nokta işlemi yürütülene kadar karşılık gelen bir özel durum algılanmaz, anlamına gelir. Örneğin, aşağıdaki kod bir sıfırla bölme özel durumu yakalar:

```cpp
double a, b, c;
// . . .
// ...unmasking of FPU exceptions omitted...
__try
{
   b/c; // assume c==0.0
   printf("This line shouldn't be reached when c==0.0\n");
   c = 2.0*b;
}
__except( EXCEPTION_EXECUTE_HANDLER )
{
   printf("SEH Exception Detected\n");
}
// . . .
```

Sıfırla bölme koşul ifadesinde oluşursa bir/c, b = FPU yakalama / özel durum 2.0 ifadede sonraki kayan nokta işlemi kadar artırma olmaz * b. Bu, aşağıdaki çıktı olur:

```Output
This line shouldn't be reached when c==0.0
SEH Exception Detected
```

Çıkış ilk satırına karşılık gelen printf ulaşıldıysa değil; yürütme 2.0 ulaşılana kadar ifade b/c tarafından neden kayan nokta özel durum harekete geçirilen değildi çünkü ulaşıldı * b. B/c yürütmeden sonra özel durum yükseltmek için derleyici bir "wait" yönergesi girmeniz gerekir:

```cpp
// . . .
   __try
   {
      b/c; // assume this expression will cause a "divide-by-zero" exception
      __asm fwait;
      printf("This line shouldn't be reached when c==0.0\n");
      c = 2.0*b;
   }
// . . .
```

Bu "bekle" yönerge işlemcisi FPU durumuyla eşitlemek ve bekleyen tüm özel durumları işlemek için zorlar. Derleyicinin yalnızca bu oluşturacak "kayan nokta semantiklerini etkinleştirildiğinde yönergeleri bekle". Bu semantiği bırakıldığında varsayılan olarak, program synchronicity hataları, yukarıdaki gibi kayan nokta özel durumlarını kullanırken karşılaşabilirsiniz.

Kayan nokta semantiklerini etkinleştirildiğinde, derleyicinin yalnızca "wait" yönergeleri neden olmaz, kayan nokta kodu olası özel durumları saklanacaktır yasadışı en iyi duruma getirmesini, derleyici de engeller. Bu, özel ve durumlar noktaları değiştiren herhangi bir dönüştürme içerir. Bu etkenler nedeniyle kayan nokta semantiklerini etkinleştirme böylece uygulama performansının düşmesinde oluşturulan makine kodu verimliliğini önemli ölçüde düşürebilir.

Kayan nokta özel durum anlamsalları fp varsayılan olarak etkinleştirilir: katı mod. Bu semantiği fp içinde etkinleştirmek için: kesin modu ekleme **/FP: dışında** geçiş derleyici komut satırı. Kayan nokta özel durum anlamsalları da etkinleştirilebilir ve bir işlev tarafından işlevi kullanarak devre dışı `float_control` pragması.

### <a name="floating-point-exceptions-as-c-exceptions"></a>Kayan nokta özel durumları C++ özel durumlarını olarak

Olarak tüm donanım özel durumları, kayan nokta özel durumlarını doğası gereği bir C++ özel durum neden olmaz, ancak bunun yerine bir yapılandırılmış özel durum tetikleyin. Kayan nokta yapılandırılmış özel durumları C++ özel durumlarına eşlemek için kullanıcıların özel bir SEH özel durum Çeviricisi ortaya çıkarabilir. İlk olarak, her bir kayan nokta özel durum için karşılık gelen bir C++ özel durum tanıtmaktadır:

```cpp
class float_exception : public std::exception {};

class fe_denormal_operand : public float_exception {};
class fe_divide_by_zero : public float_exception {};
class fe_inexact_result : public float_exception {};
class fe_invalid_operation : public float_exception {};
class fe_overflow : public float_exception {};
class fe_stack_check : public float_exception {};
class fe_underflow : public float_exception {};
```

Ardından, bir kayan nokta SEH özel durumu algılar ve karşılık gelen bir C++ özel durum çevirisi işlev sunar. Bu işlevi kullanmak için yapılandırılmış özel durum işleyicisi translator geçerli işlem iş parçacığına ayarlamak [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md) çalışma zamanı kitaplığı işlevi.

```cpp
void se_fe_trans_func( unsigned int u, EXCEPTION_POINTERS* pExp )
{
    switch (u)
    {
    case STATUS_FLOAT_DENORMAL_OPERAND:   throw fe_denormal_operand();
    case STATUS_FLOAT_DIVIDE_BY_ZERO:     throw fe_divide_by_zero();
   etc...
    };
}
// . . .
_set_se_translator(se_fe_trans_func);
```

Bu eşleme başlatıldıktan sonra kayan nokta özel durumları C++ özel durumlarını olsa gibi davranır. Örneğin:

```cpp
try
{
   // floating-point code that might throw divide-by-zero
   // or other floating-point exception
}
catch(fe_divide_by_zero)
{
    cout << "fe_divide_by_zero exception detected" << endl;
}
catch(float_exception)
{
    cout << "float_exception exception detected" << endl;
}
```

## <a name="references"></a>Referanslar

[Her bilgisayar bilimi insanı kayan nokta aritmetiği hakkında neler bilmeniz gereken](http://pages.cs.wisc.edu/~david/courses/cs552/S12/handouts/goldberg-floating-point.pdf) David Goldberg tarafından.

## <a name="see-also"></a>Ayrıca bkz.

[Kodunuzu İyileştirme](optimizing-your-code.md)<br/>
