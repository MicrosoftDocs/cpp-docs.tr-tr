---
title: Microsoft Visual C++ kayan nokta en iyi duruma getirme | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 35c9263fa6252469124eefb0dfd575ef5bd2ac34
ms.sourcegitcommit: 5e932a0e110e80bc241e5f69e3a1a7504bfab1f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/21/2018
ms.locfileid: "34422749"
---
# <a name="microsoft-visual-c-floating-point-optimization"></a>Microsoft Visual C++ kayan nokta en iyi duruma getirme

Kayan nokta kodu, kayan nokta semantiği yönetmek için Microsoft C++ derleyicinin yöntem kullanarak en iyi duruma getirme hakkında tanıtıcı alın. Hızlı programları, yalnızca güvenli iyileştirmeler kayan nokta kodu üzerinde gerçekleştirilen sağlarken oluşturun.

## <a name="optimization-of-floating-point-code-in-c"></a>C++'ta kayan nokta kodunun en iyi duruma getirme

Bir en iyi duruma getirme C++ derleyicisi makine koda yalnızca kaynak kodu çevirir, makine yönergeleri verimliliğini artırmak ve/veya boyutunu azaltmak için farklı şekilde düzenler. Ne yazık ki, birçok ortak iyileştirmeler için kayan nokta hesaplamaları uygulandığında mutlaka güvenli değildir. Bu iyi bir örneği, "Ne her bilgisayar Bilimcisi gerektiğini biliyor hakkında Floating-Point aritmetik", David Goldberg alınan aşağıdaki toplam algoritması kullanılarak görülebilir. *bilgi işlem anketler*, Mart 1991, pg. 203:

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

Bu işlev n ekler **float** dizi vektör değerleri `A`. Döngü gövdesinde algoritma toplamayı bir sonraki adıma sonra uygulanan bir "düzeltme" değeri hesaplar. Bu yöntem toplu yuvarlama hataları O(n) zaman karmaşıklık korurken basit bir toplama kıyasla önemli ölçüde azaltır.

Kayan nokta aritmetik gerçek sayı aritmetik olarak aynı cebirsel kurallarını izlediğini naïve C++ derleyicisi varsayabilirsiniz. Bu tür bir derleyici sonra yanlışlıkla, duymanıza neden olabilir

> C = T - sum - Y == > (sum + Y) - sum - Y == > 0;

Diğer bir deyişle, C algılanan değeri her zaman sıfır sabitine olduğunu. Bu sabit değer ardından sonraki ifadelere yayılır, döngü gövdesine için basit bir toplama azalır. Kesin olarak için

> Y = bir [i] - C == > Y = [i]<br/>T = sum + Y == > T = sum + [i]<br/>Sum T = == > toplam = sum + [i]

Bu nedenle, mantıksal bir dönüştürme naïve derleyici için `KahanSum` işlevi olacaktır:

```cpp
float KahanSum( const float A[], int n )
{
   float sum=0; // C, Y & T are now unused
   for (int i=0; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

Dönüştürülmüş algoritması hızlıdır ancak *hiç Programcı amacınıza doğru bir gösterimi olan*. Dikkatle hazırlanmış hata düzeltme tamamen kaldırılmıştır ve biz basit, doğrudan toplam algoritma tüm ilişkili hata ile birlikte sol.

Kuşkusuz karmaşık bir C++ derleyicisi bu cebirsel bilecektir kuralları gerçek aritmetik genellikle geçerli kayan nokta aritmetik. Ancak, daha karmaşık bir C++ derleyicisi hala yanlış Programcı amacınıza yorumlayabilir.

Yazmaçları (çağrılan "enregistering" bir değer) mümkün olduğunca çok değerle tutacak çalışır ortak bir iyileştirme göz önünde bulundurun. İçinde `KahanSum` örneği, bu en iyi duruma getirme için enregister değişkenler çalışabilir `C`, `Y` ve `T` yalnızca döngü gövdesinde kullanıldıktan sonra. YAZMAÇ duyarlık 23bits (tek) yerine (çift) 52bits ise, bu en iyi duruma getirme türü etkili bir şekilde yükseltir. `C`, `Y` ve `T` yazmak için **çift**. Toplam değişken benzer şekilde işlemiyor değilse tek duyarlıklı kodlanmış kalır. Bu semantiği dönüştüren `KahanSum` şu

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

Ancak `Y`, `T` ve `C` şimdi hesaplanan yüksek kesinliği, bu yeni kodlama değerlere bağlı olarak daha az doğru bir sonuç oluşturabilir `A[]`. Bu nedenle bile görünen zararsız iyileştirmeler negatif sonuçları olabilir.

Bu en iyi duruma getirme sorun türlerini "hassas" kayan nokta kodu sınırlı değildir. Kayan nokta bile basit algoritmaları hatalı iyileştirilmiş zaman başarısız olabilir. Basit, doğrudan toplam algoritma göz önünde bulundurun:

```cpp
float Sum( const float A[], int n )
{
   float sum=0;
   for (int i=0; i<n; i++)
      sum = sum + A[i];
   return sum;
}
```

Kayan nokta bazı birimleri aynı anda birden çok işlemi gerçekleştirmeye yeterli olduğundan, bir derleyici skaler azaltma iyileştirme bulunmaya seçebilirsiniz. Bu iyileştirme etkili bir şekilde üstten basit Sum işlevi aşağıdaki dönüştürür:

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

İşlevi, şimdi her adımda aynı anda işlenebilir dört ayrı matematiksel tutar. En iyi duruma getirilmiş işlevi artık çok daha hızlı olsa da, en iyi duruma getirilmiş sonuçları iyileştirilmemiş sonuçlarından oldukça farklı olabilir. Bu değişiklik yaparken, derleyicinin ilişkilendirilebilir kayan nokta toplama olduğu varsayılır; diğer bir deyişle, bu iki ifadeye eşdeğerdir: `(a + b) + c == a + (b + c)`. Ancak, birleşim her zaman için kayan nokta sayıları doğru tutmaz. Toplam olarak bilgi işlem yerine:

```cpp
sum = A[0]+A[1]+A[2]+...+A[n-1];
```

Dönüştürülmüş işlevi artık sonucu olarak hesaplar

```cpp
sum = (A[0]+A[4]+A[8]+...)
    + (A[1]+A[5]+A[9]+...)
    + (A[2]+A[6]+A[10]+...)
    + (A[3]+A[7]+A[11]+...);
```

Bazı değerler için `A[]`, bu farklı toplama işlemlerini sıralama beklenmeyen sonuçlara neden olabilir. Daha da karmaşık hale, bazı programcıları gibi en iyi duruma getirme düşündüğünüz ve bunları uygun şekilde dengelemek tercih edebilirsiniz. Bu durumda, bir program dizi oluşturabileceğiniz `A` farklı bir düzende böylece en iyi duruma getirilmiş toplamı beklenen sonuçlar üretir. Ayrıca, çoğu durumda en iyi duruma getirilmiş sonuç doğruluğunu "yeteri" olabilir. Bu, özellikle en iyi duruma getirme ilgi çekici hızı avantajları sağladığında geçerlidir. Video oyunlar, örneğin, mümkün olduğunca çok hızlandırmak ancak genellikle yüksek oranda doğru kayan nokta hesaplamaları gerektirmeyen gerektirir. Derleyici alıcılar, bu nedenle hız ve doğruluk, genellikle farklı hedeflerini denetlemek programcıları için bir mekanizma sağlamanız gerekir.

Bazı derleyicileri en iyi duruma getirme her tür için ayrı bir anahtar sağlayarak hız ve doğruluk karşılaştırmasını çözümleyin. Bu, geliştiricilerin kendi belirli uygulama için kayan nokta doğruluğu değişiklikleri neden olan en iyi duruma getirme devre dışı olanak tanır. Bu çözüm derleyici denetime yüksek derecede sunabilir olsa da, bazı ek sorunlar sunar:

- Genellikle, etkinleştirme veya devre dışı geçer belirsiz olur.
- Tek bir iyileştirme devre dışı bırakma olmayan kayan nokta kodu performansını olumsuz etkileyebilir.
- Her bir ek anahtar birçok yeni geçiş birleşimleri doğurur; kombinasyon sayısını hızla yönetilmeleri olur.

Her iyileştirme için ayrı anahtar sağlama çekici görünebilir, bu nedenle böyle derleyicileri kullanarak sıkıcı ve güvenilir olmayan olabilir.

Birçok C++ Derleyicileri sunan bir *tutarlılık* kayan nokta modeli (aracılığıyla bir **/Op** veya **/fltconsistency** geçiş) programları uyumlu oluşturmak için geliştirici sağlar kayan nokta semantiği ile sıkı. Bağlı olduğunda, bu model çoğu iyileştirmeler üzerinde kayan nokta hesaplamaları kullanarak bu iyileştirmeler kayan olmayan noktası kodu için izin verirken derleyici engeller. Tutarlılık modeli, ancak koyu tarafı vardır. Neredeyse tüm uygulamaları farklı FPU mimariyi üzerinde tahmin edilebilir sonuçları döndürmek için **/Op** kullanıcıya yuvarlak Ara ifadeleri duyarlık belirtilen; Örneğin, aşağıdaki ifade göz önünde bulundurun:

```cpp
float a, b, c, d, e;
// . . .
a = b * c + d * e;
```

Tutarlı ve tekrarlanabilir sonuçlar altında için **/Op**, aşağıdaki gibi uygulanan gibi bu ifadenin:

```cpp
float x = b  *c;
float y = d * e;
a = x + y;
```

Tek duyarlıklı yuvarlama hataları nihai sonucu şimdi yükselmesine *ifade hesaplama her adımında*. Bu yorum kesinlikle C++ semantiği kuralı herhangi bir ihlal değil de, bu neredeyse hiçbir zaman kayan nokta ifadeleri değerlendirmek için en iyi yoludur. Ara pratik duyarlık olabildiğince yüksek sonuçlanır işlem genellikle daha iyi bir şeydir. Örneğin, ifade işlem daha iyi olacaktır `a = b * c + d * e` gibi yüksek duyarlık içinde

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

Yüksek duyarlık Ara sonuçların hesaplanırken nihai sonucu önemli ölçüde daha doğru olur. Tam olarak kullanıcının güvenli iyileştirmeleri devre dışı bırakarak hata azaltmak çalışırken ironically, tutarlılık modeli kabul ederek, hata olasılığını artar. Bu nedenle tutarlılık modeli aynı anda artan doğruluğu garanti sağlarken verimliliği ciddi da azaltabilirsiniz. Ciddi sayısal programcıları için bu gibi çok iyi kolaylığını görünmemektedir ve model genellikle iyi alınmamışsa, birincil nedenidir.

Sürüm 8.0 (Visual C++® 2005), Microsoft C++ başlayan derleyici daha iyi bir kadar alternatif sağlar. Üç genel kayan nokta modlarından birini seçmek programcıları sağlar: fp: kesin, fp:fast ve fp: katı.

- Fp altında: kesin, yalnızca güvenli iyileştirmeler kayan nokta kodu ve farklı olarak gerçekleştirilen **/Op**, Ara hesaplamaları en yüksek pratik duyarlık tutarlı bir şekilde gerçekleştirilir.
- FP:Fast modu doğruluğu ödün verme pahasına daha agresif iyileştirme izin vermeyi kayan nokta kurallarını rahatlatır.
- FP: katı mod fp tüm genel doğruluk sağlar: kesin etkinleştirme fp özel durum semantiği ve FPU ortamı değişiklikler (örneğin yönü vb. yuvarlama kayıt duyarlık) varlığında geçersiz dönüşümleri engelliyor.

Kayan nokta özel durum semantiği bağımsız olarak bir komut satırı anahtarını veya derleyici pragma tarafından denetlenebilir; Varsayılan olarak, kayan nokta özel durum semantiği altında fp devre dışı bırakılır: kesin ve fp altında etkin: katı. Derleyici de FPU ortamı duyarlılık ve kısaltmalar gibi belirli kayan nokta özel iyileştirmeler üzerinde denetim sağlar. Bu düz İleri model geliştiricilere aşırı yükü çok fazla derleyici anahtarları veya istenmeyen yan etkileri aday olmadan kayan nokta kod derleme üzerinde denetim sağlar.

## <a name="the-fpprecise-mode-for-floating-point-semantics"></a>Fp: kayan nokta semantiği için kesin modu

Fp varsayılan kayan nokta semantiği moddur: kesin. Bu mod seçildiğinde, derleyici kayan nokta işlemleri iyileştirirken kesinlikle güvenliği kural kümesine eklenecek. Bu kurallar derleyicinin kayan nokta hesaplamaları doğruluğunu koruyarak verimli makine kodu oluşturmasına izin verir. Hızlı üretim kolaylaştırmak için programlar, fp: kesin modelini devre dışı bırakır kayan nokta özel durum semantiği (bunlar açıkça etkin hale getirilebilir rağmen). Microsoft, fp seçildi: hızlı ve doğru programlar oluşturduğundan kesin varsayılan kayan nokta modu.

Fp istemenin: kullanım komut satırı derleyicisini kullanarak kesin modu [/fp: kesin](fp-specify-floating-point-behavior.md) geçin:

> cl /fp: kesin source.cpp

Bu dp kullanılacak derleyiciye: source.cpp dosyasının kodu oluştururken kesin semantiği. Fp: kesin model de çağrılabilir bir işlev tarafından işlevi olarak kullanarak [float_control derleyici pragma](#the-float-control-pragma).

Fp altında: kesin modu derleyici hiçbir zaman kayan nokta hesaplamaları doğruluğunu perturb iyileştirmeler gerçekleştirir. Derleyici atamaları olarak her zaman doğru yuvarlar, işaretçisine tür olarak atar ve işlev çağrıları ve FPU kaydeder gibi ara yuvarlama tutarlı olarak aynı duyarlık gerçekleştirilir. Kısaltmalar gibi güvenli iyileştirmeler varsayılan olarak etkinleştirilir. Özel durum semantik ve FPU ortamı duyarlılık varsayılan olarak devre dışıdır.

|FP: kesin semantiği|Açıklama|
|-|-|
|Semantiği yuvarlama|Açık atamaları olarak yuvarlama işaretçisine tür olarak atar ve işlevini çağırır. Ara ifadeleri kayıt duyarlık değerlendirilir.|
|Cebirsel dönüşümleri|Kayan nokta cebiri ilişkilendirilemez, dağıtarak olmayan katı bağlılığı dönüştürme her zaman sağlanır sürece aynı sonuçları üretir.|
|Kısaltmalar|Varsayılan olarak izin verilir. Daha fazla bilgi için bkz [fp_contract pragması](#the-fp-contract-pragma).|
|Kayan nokta değerlendirme sırası|Son sonuçları değiştirilmemesi koşuluyla derleyici kayan noktalı bir ifade değerlendirme yeniden.|
|FPU ortam erişim|Varsayılan olarak devre dışıdır. Daha fazla bilgi için bkz [fenv_access pragması](#the-fenv-access-pragma). Varsayılan duyarlık ve yuvarlama modu varsayılır.|
|Kayan nokta özel durum semantiği|Varsayılan olarak devre dışıdır. Daha fazla bilgi için bkz: [/fp: dışında](fp-specify-floating-point-behavior.md).|

### <a name="rounding-semantics-for-floating-point-expressions-under-fpprecise"></a>Kayan nokta ifadeleri fp altında anlamları yuvarlama: kesin

Fp: kesin modeli her zaman ifade değerlendirme belirli noktalarında yalnızca açıkça yuvarlama yüksek pratik duyarlık adresindeki Ara hesaplamalar gerçekleştirir. Kullanıcı tarafından belirtilen duyarlık için her zaman yuvarlama dört yerlerde oluşur: bir typecast (b) gerçekleştirildiğinde atama, (a) yapıldığında, (c) ne zaman bir kayan nokta değer geçirilir bağımsız değişken olarak bir işlev ve (d) bir kayan nokta değer işleminden döndürüldüğünde bir işlev. Ara hesaplamalar her zaman kayıt duyarlık gerçekleştirildiğinden, Ara sonuçların doğruluğunu platform bağlıdır (duyarlık her zaman en az belirtilen kullanıcı olarak doğru olur ancak duyarlık).

Aşağıdaki kodda atama ifadesi göz önünde bulundurun. Atama işleci '=' ifadesi sağ taraftaki kayıt duyarlık hesaplanan ve atama sol tarafında türünü açıkça yuvarlanır.

```cpp
float a, b, c, d;
double x;
...
x = a*b + c*d;
```

olarak hesaplanır

```cpp
float a, b, c, d;
double x;
...
register tmp1 = a*b;
register tmp2 = c*d;
register tmp3 = tmp1+tmp2;
x = (double) tmp3;
```

Açıkça bir ara sonuç yuvarlak bir typecast dağıtır. Örneğin, önceki kod ekleyerek değiştirilirse açık bir typecast, Ara deyimi (c * d) türüne typecast yuvarlanır.

```cpp
float a, b, c, d;
double x;
// . . .
x = a*b + (float)(c*d);
```

olarak hesaplanır

```cpp
float a, b, c, d;
double x;
// . . .
register tmp1 = a*b;
float tmp2 = c*d;
register tmp3 = tmp1+tmp2;
x = (double) tmp3;
```

Yuvarlama bu yöntemin bir uygulanır bazı görünen eşdeğer dönüşümleri aslında aynı semantiği gerekmemesidir. Örneğin, aşağıdaki dönüştürme iki atama ifadeleri tek atama ifadesine böler.

```cpp
float a, b, c, d;
// . . .
a = b*(c+d);
```

değil eşdeğer

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

değil eşdeğer

```cpp
a = b*(a=c+d);
```

İkinci kodlamalarının her bir ek atama işlemi sunulmuştur ve bu nedenle bir ek yuvarlama noktası bu Kodlamalar eşdeğer semantiği gerekmez.

Bir işlevin bir kayan nokta değer geri döndüğünde, değer işlev türü için yuvarlanır. Kayan nokta değeri işlevi için parametre olarak geçirildiğinde değer parametresinin türü için yuvarlanır. Örneğin:

```cpp
float sumsqr(float a, float b)
{
   return a*a + b*b;
}
```

olarak hesaplanır

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

olarak hesaplanır

```cpp
float x, y, z;
double c;
...
register tmp1 = w*x;
register tmp2 = tmp1+y;
float tmp3 = tmp2;
c = symsqr( tmp3, z);
```

### <a name="architecture-specific-rounding-under-fpprecise"></a>Fp altında mimarisi özgü yuvarlama: kesin

|İşlemci|Duyarlık Ara ifadeler için yuvarlama|
|-|-|
|x86|Ara ifadeleri 16 bit üs tarafından sağlanan genişletilmiş aralığı olan varsayılan 53 bit duyarlık hesaplanır. Bu 53:16 değerleri "(bir işlev çağrısı sırasında olabileceği gibi) belleğe geçmiş"olduğunda, genişletilmiş üs aralık 11 bit daraltıldığı. Diğer bir deyişle, geçmiş değerleri yalnızca 11 bit üs standart çift duyarlıklı biçimiyle cast.<br/>Bir kullanıcı ara kayan nokta denetimini kullanarak word değiştirilerek yuvarlama genişletilmiş 64-bit duyarlık geçmek `_controlfp` ve FPU ortam erişim sağlayarak (bkz [fenv_access pragması](#the-fenv-access-pragma)). Ancak, genişletilmiş duyarlılık register-değerleri bellek geçmiş, Ara sonuçların hala çift duyarlıklı yuvarlanır.<br/>Bu belirli anlamsal değiştirilebilir ' dir.|
|amd64|FP semantiği amd64 üzerindeki diğer platformlarından biraz farklıdır. Performans nedenleriyle Ara işlemleri ya da işleneni yerine kullanılabilir geniş duyarlık en geniş kesinliğini adresindeki hesaplanır.  İşlenen daha geniş bir duyarlılığı kullanılarak hesaplanan değer hesaplamalar zorlamak için bir alt ifadesinde en az bir işlenen üzerinde bir cast işlemi tanıtmak için kullanıcıların gerekir.<br/>Bu belirli anlamsal değiştirilebilir ' dir.|

### <a name="algebraic-transformations-under-fpprecise"></a>Fp altında cebirsel dönüşümleri: kesin

Zaman fp: kesin modu etkinleştirildiğinde, derleyici hiçbir zaman cebirsel dönüşümleri gerçekleştirir *nihai sonucu kanıtlanabilir aynı olmadığı sürece*. Gerçek sayı aritmetik için tanıdık cebirsel kuralları birçoğu için kayan nokta aritmetik her zaman tutmayın. Örneğin, aşağıdaki ifadeler eşdeğer Reals, ancak mutlaka float.

|Form|Açıklama|
|-|-|
|`(a+b)+c = a+(b+c)`|İlişkilendirilebilir kuralı ekleme|
|`(a*b)*c = a*(b*c)`|Çarpma ilişkilendirilebilir kuralı|
|`a*(b+c) = a*b + b*c`|Çarpma toplama üzerinden dağıtılması|
|`(a+b)(a-b) = a*a-b*b`|Cebirsel Finansman|
|`a/b = a*(1/b)`|Multiplicative ters bölme|
|`a*1.0 = a`|Çarpma kimliği|

İşlevi ile giriş örnekte gösterildiği gibi `KahanSum`, önemli ölçüde daha hızlı programlar üretmek üzere çeşitli cebirsel dönüşümleri gerçekleştirmeniz derleyici tempted. En iyi duruma getirme böyle cebirsel dönüşümler bağımlı neredeyse her zaman yanlış olsa da, mükemmel güvenli oldukları durumlar vardır. Örneğin, bunu bazen bölme değiştirmek için tercih edilir bir *sabit* sabiti çarpma-ters tarafından çarpma değerle:

```cpp
const double four = 4.0;
double a, b;
...

a = b/four;
```

İçine dönüştürülmüş

```cpp
const double four = 4.0;
const double tmp0 = 1/4.0;
double a, b;
...
a = b*tmp0;
```

İyileştirici derleme zamanında x'in belirleyebilirsiniz güvenli bir dönüşüm olmasıdır / 4.0 x, sonsuz ve NaN dahil olmak üzere tüm kayan nokta değerlerinin x*(1/4.0) ==. Bölme işlemi çarpma ile değiştirerek derleyici birkaç döngü kaydedebilirsiniz — özellikle bölme doğrudan uygulayan yoktur, ancak devrik yaklaşık bileşimini oluşturmak ve çarpma eklemek için derleyici gerektiren FPUs üzerinde yönergeler. Bu tür bir en iyi duruma getirme altında fp derleyici gerçekleştirebilir: yalnızca değiştirme çarpma tam vermediğinde kesin aynı bölme sonucu. Derleyici Önemsiz dönüşümleri dp altında gerçekleştirmek: kesin sonuçlar özdeş sağlanan. Bu güncelleştirmeler şunlardır:

|Form|Açıklama
|-|-|
|`(a+b) == (b+a)`|Yer değiştirebilme kuralı ekleme|
|`(a*b) == (b*a)`|Çarpma için yer değiştirebilme kuralı|
|`1.0*x*y == x*1.0*y == x*y*1.0 == x*y`|Çarpma 1.0 tarafından|
|`x/1.0*y == x*y/1.0 == x*y`|1.0 bölme|
|`2.0*x == x+x`|Çarpma 2.0|

### <a name="contractions-under-fpprecise"></a>Fp altında kısaltmalar: kesin

Bir anahtar mimari birçok modern kayan nokta birimleri ek ara yuvarlama hata ile tek bir işlem olarak arkasından bir çarpma gerçekleştirme yeteneğini özelliğidir. Örneğin, Intel Itanium mimarisi Üçlü bu işlemlerin her biri birleştirmek için yönergeler sağlar (bir*b + c), (bir*b-c) ve (c-a * b), tek bir kayan nokta yönergesi içine (fma, fms ve fnma sırasıyla). Tek bu yönergeleri ayrı yürütme daha hızlı çarpma ve yönergeler ekleyin ve Ara çarpımını yuvarlama olduğundan daha doğru olduğundan. Bu iyileştirme önemli ölçüde birkaç Çarp araya eklemeli içeren işlevlerini hızlandırmak ve işlemleri ekleyin. Örneğin, iki n boyutlu vektör nokta çarpımını hesaplar aşağıdaki algoritmayı göz önünde bulundurun.

```cpp
float dotProduct( float x[], float y[], int n )
{
   float p=0.0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

Bu hesaplama gerçekleştirilen bir dizi Çarp-add-p formunun yönergeleri p + x = [i] * [i] y.

Daraltmaya iyileştirme bağımsız olarak kullanılarak denetlenebilir `fp_contract` derleyici pragması. Varsayılan olarak, fp: kesin modeli doğruluk ve hız artırmak bu yana kısaltmalar için olanak sağlar. Fp altında: kesin, derleyici hiçbir zaman açık yuvarlama ile bir ifade sözleşme.
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

### <a name="order-of-floating-point-expression-evaluation-under-fpprecise"></a>Kayan nokta ifade değerlendirme fp altında sırasını: kesin

Kayan nokta ifade Değerlendirme sırasını korumak iyileştirmeleri her zaman güvenli ve bu nedenle altında fp izin verilen: kesin modu. Tek duyarlıklı içinde iki n boyutlu vektör nokta çarpımını hesaplar aşağıdaki işlevi göz önünde bulundurun. Programcı tarafından kodlanmış olarak ilk kod bloğu özgün işlevi bir kısmi döngü unrolling en iyi duruma getirme sonra aynı işlevi tarafından izlenir.

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

Bu en iyi duruma getirme birincil avantajı, % 75 koşullu döngü-dallanma sayısını azaltan ' dir. Ayrıca, döngü gövdesine işlemlerini sayısını artırarak derleyici artık daha fazla iyileştirmek için daha fazla fırsatı olabilir. Örneğin, bazı FPUs gerçekleştirmek mümkün olabilir Çarp-add-p += x [i] * [i + 1] x değerleri aynı anda alınırken [i] y ve y [i + 1] bir sonraki adımda kullanmak için. En iyi duruma getirme bu tür kayan nokta hesaplamaları için mükemmel güvenli olduğundan işlem sırası korur.

Genellikle, derleyicinin tüm işlemleri daha hızlı kod üretmek için yeniden sıralamak de yararlıdır. Aşağıdaki kod göz önünde bulundurun:

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

C++ anlamsal kuralları belirtmek ilk hesaplanan sanki program sonuçlar üretmesi gerekir x, ardından y ve son olarak z. Yalnızca dört kullanılabilir kayan nokta yazmaçlar derleyici olduğunu varsayalım. Derleyici işlem zorlanır ise x, y ve z sırada, kod aşağıdaki semantiği ile oluşturmak tercih edebilirsiniz:

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

Birkaç açıkça gereksiz işlemleri olduğundan bu kodlama vardır. Derleyici kesinlikle C++ anlamsal kurallara, program her atama ortası FPU ortam erişim çünkü bu sıralama gereklidir. Ancak, fp için varsayılan ayarları: kesin program ortamı değil olarak erişmelerini en iyi duruma getirme derleyici izin Bu deyimler yeniden sıralamak etkinleştirilebilir. Ardından, üç değerden bilgi işlem tarafından ters sırada, aşağıdaki gibi açarken kaldırmak ücretsizdir:

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

Bu dp yönerge sayısını % 40'neredeyse azaltılmış açıkça üstün kodlamadır. Sonuçlar için x, y ve z aynıdır eskisi, ancak daha az yükü ile hesaplanır.

Fp altında: kesin, derleyici de olabilir *titreşimli görüntü* daha hızlı kod oluşturmak amacıyla Genel alt ifade. Örneğin, ikinci derece eşitlik kökleri işlem kodu gibi yazılı olabilir:

```cpp
double a, b, c, root0, root1;
...
root0 = (-b + sqrt(b*b-4*a*c))/(2*a);
root1 = (-b - sqrt(b*b-4*a*c))/(2*a);
```

Bu ifadeler yalnızca tek bir işlem tarafından farklı rağmen Programcı her kök değeri en yüksek pratik kesinlik hesaplanan güvence altına almak için bu şekilde yazılmış. Fp altında: kesin, derleyici root0 ve ortak alt ifadelerin duyarlık kaybetmeden kaldırmak için root1 hesaplama titreşimli görüntü ücretsizdir. Örneğin, aşağıdaki çeşitli yedekli adımları tam aynı yanıt üretilirken kaldırdı.

```cpp
double a, b, c, root0, root1;
...
register tmp0 = -b;
register tmp1 = sqrt(b*b-4*a*c);
register tmp2 = 2*a;
root0 = (tmp0+tmp1)/tmp2;
root1 = (tmp0-tmp1)/tmp2;
```

Diğer en iyi duruma getirme belirli bağımsız bir ifade değerlendirme taşımak deneyebilir. Koşullu dal döngü gövdesine içinde içeren aşağıdaki algoritmadan göz önünde bulundurun.

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

Derleyici, algılayabilir ifadesinin değerini (abs(d) > 1) döngü gövdesinde değişmez olduğu. Bu "IF vinç için" derleyicisi tanır deyimi yukarıdaki kod aşağıdaki dönüştürme döngü gövdesine dışında:

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

Dönüştürme işleminin ardından yoktur artık koşullu dal böylece döngü genel performansını önemli ölçüde iyileştirme döngü gövdelerini birini. Bu tür bir en iyi duruma getirme mükemmel güvenlidir çünkü ifadesi değerlendirmesi (abs(d) > 1.0) diğer ifadelerin bağımsızdır.

Anlam akış değiştiğinden bu tür bir en iyi duruma getirme FPU ortam erişim veya kayan nokta özel durumları varlığında contraindicated. Bu tür iyileştirmesi yalnızca altında fp kullanılamaz: kesin modu FPU ortam erişim ve kayan nokta özel durum semantiği varsayılan olarak devre dışı bırakıldığı için. FPU ortam erişim işlevleri açıkça devre dışı bırakabilir Böyle iyileştirmeler kullanarak `fenv_access` derleyici pragması. Kayan nokta özel durumlar kullanma işlevleri benzer şekilde, kullanması gereken `float_control(except ... )` derleyici pragma (veya **/fp: dışında** komut satırı anahtarı).

Özet olarak, fp: son sonuçları değiştirilmemesi koşuluyla kayan noktalı bir ifade değerlendirme yeniden sıralamak için derleyici ve sonuçları bağımlı FPU ortamı veya kayan nokta özel durumları olmayan kesin modu sağlar.

### <a name="fpu-environment-access-under-fpprecise"></a>Fp altında FPU ortam erişim: kesin

Zaman fp: kesin modu etkinleştirildiğinde, derleyici bir program değil erişmek veya FPU ortamı alter olduğunu varsayar. Daha önce belirtildiği gibi bu varsayım yeniden sıralamak veya fp altında verimliliğini artırmak için kayan nokta işlemleri taşımak derleyici sağlar: kesin.

Bazı programlar kullanarak kayan nokta yuvarlama yönünü değiştirebilir `_controlfp` işlevi. Örneği için bazı programları üst işlem ve iki kez aynı hesaplama gerçekleştirerek alt hata sınır aritmetik işlemler ilk negatif sonsuz yuvarlama sırasında sonra doğru pozitif sonsuzluk yuvarlama while. FPU yuvarlama denetlemek için kullanışlı bir yol sağlayan beri Programcı FPU ortamı değiştirilerek yuvarlama modu değiştirmek seçebilirsiniz. Aşağıdaki kod FPU ortamı değiştirerek bir kayan nokta çarpımı tam hatayla bağlı hesaplar.

```cpp
double a, b, cLower, cUpper;
// . . .
_controlfp( _RC_DOWN, _MCW_RC );    // round to -&infin;
cLower = a*b;
_controlfp( _RC_UP, _MCW_RC );    // round to +&infin;
cUpper = a*b;
_controlfp( _RC_NEAR, _MCW_RC );    // restore rounding mode
```

Fp altında: iyileştirici çağrıları yoksaymak ücretsiz olacak şekilde kesin, derleyicinin her zaman varsayılan FPU ortamı varsayar `_controlfp` ve cUpper için yukarıdaki atamaları azaltmak cLower = = bir * b; Bu açıkça hatalı sonuçlar verir. Böyle iyileştirmeler önlemek için FPU ortamı kullanarak erişmesini `fenv_access` derleyici pragması.

Kayan nokta belirli hataları FPU'ın durum sözcüğünü denetleyerek algılamak diğer programları deneyebilir. Örneğin, aşağıdaki kodu sıfırla bölme ve filtresinin koşullarını denetler

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

Fp altında: kesin, ifade değerlendirme yeniden sıralamak en iyi duruma getirme belirli hataları meydana geldiği noktaları da değiştirebilirsiniz. Durum sözcüğünü erişme programlar kullanarak FPU ortam erişim etkinleştirmelisiniz `fenv_access` derleyici pragması.

Daha fazla bilgi için bkz [fenv_access pragması](#the-fenv-access-pragma).

### <a name="floating-point-exception-semantics-under-fpprecise"></a>Kayan nokta özel durum semantiği fp altında: kesin

Varsayılan olarak, kayan nokta özel durum semantiği altında fp devre dışı bırakılır: kesin. Çoğu C++ programcıları sistem ya da C++ özel durumlarını kullanmadan kayan nokta özel durumları işlemek tercih edilir. Ayrıca, daha önce belirtildiği gibi kayan nokta özel durum semantiği devre dışı bırakma derleyici esneklik kayan nokta işlemleri iyileştirirken sağlar. Kullanın ya da **/fp: dışında** geçiş veya `float_control` kayan nokta özel durum semantiği fp kullanırken etkinleştirmek için pragma: kesin modeli.

Daha fazla bilgi için bkz [kayan nokta özel durum semantiği etkinleştirme](#enabling-floating-point-exception-semantics).

## <a name="the-fpfast-mode-for-floating-point-semantics"></a>Kayan nokta semantiği fp:fast modu

Derleyici fp:fast modu etkinleştirildiğinde, bu dp kuralları rahatlatır: kayan nokta işlemleri iyileştirirken kesin kullanır. Bu modu daha fazla kayan nokta kod için kayan nokta doğruluğunu ve doğruluk ödün verme pahasına hızı en iyi duruma getirme derleyici sağlar. Yüksek oranda doğru kayan nokta hesaplamaları üzerinde güvenmeyin programlar önemli hızlı geliştirme fp:fast modunu etkinleştirerek karşılaşabilirsiniz.

Kullanarak fp:fast kayan nokta modu etkin [/fp:fast](fp-specify-floating-point-behavior.md) aşağıdaki gibi komut satırı derleyicisi anahtarı:

> cl /fp:fast source.cpp

Bu örnek fp:fast semantiği source.cpp dosyası için kod oluşturma sırasında kullanmak için derleyiciye. Fp:fast modeli kullanarak bir işlev tarafından işlevi olarak da çağrılabilir `float_control` derleyici pragması.

Daha fazla bilgi için bkz [float_control pragması](#the-float-control-pragma).

Fp:fast modunda kayan nokta hesaplamaları doğruluğunu alter iyileştirmeler derleyici gerçekleştirebilir. Derleyici doğru atamaları olarak yuvarlamak değil, işaretçisine tür olarak atar veya işlev çağrıları ve Ara yuvarlama işlemi her zaman gerçekleştirilmez. Kayan nokta özel en iyi duruma getirme, kısaltmalar gibi her zaman etkindir. Kayan nokta özel durum semantik ve FPU ortamı duyarlılık devre dışı bırakılmış ve kullanılamaz.

|FP:Fast semantiği|Açıklama
|-|-|
|Semantiği yuvarlama|Açık atamaları olarak yuvarlama işaretçisine tür olarak atar ve işlev çağrıları yoksayılabilir.<br/>En az duyarlık performans gereksinimlerine göre kaydetmek Ara ifadeleri yuvarlanmasını.|
|Cebirsel dönüşümleri|Derleyici gerçek sayı ilişkilendirilebilir, dağıtarak cebiri göre ifadeler dönüştürme; Bu dönüşümleri doğru ya da doğru olması garanti edilmez.|
|Kısaltmalar|Her zaman etkin; pragma tarafından devre dışı bırakılamaz `fp_contract`|
|Kayan nokta değerlendirme sırası|Bu değişiklikleri son sonuçları bile değiştirebilir, derleyici kayan noktalı bir ifade değerlendirme yeniden.|
|FPU ortam erişim|Devre dışı. Yok|
|Kayan nokta özel durum semantiği|Devre dışı. Yok|

### <a name="rounding-semantics-for-floating-point-expressions-under-fpfast"></a>Kayan nokta ifadeleri fp:fast altında anlamları yuvarlama

Fp aksine: kesin modeli, fp:fast modeli en kullanışlı duyarlık Ara hesaplamalar gerçekleştirir. Atamaları olarak yuvarlama işaretçisine tür olarak atar ve işlev çağrıları her zaman gerçekleşmeyebilir. Örneğin, üç tek duyarlıklı değişkenleri aşağıdaki ilk işlevi sunar (`C`, `Y` ve `T`). Derleyici enregister için yürürlükte türü yükseltmek, bu değişkenleri seçebilirsiniz `C`, `Y` ve `T` çift duyarlıklı için.

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

Değişkenleri işlemiyor:

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

Bu örnekte, özgün işlevi amacı fp:fast subverted. En son en iyi duruma getirilmiş değişkende tutulan sonuç `sum`, doğru sonuç oldukça perturbed olabilir.

FP:Fast altında derleyici genellikle en az kaynak kodu tarafından belirtilen duyarlık korumak dener. Ancak, bazı durumlarda derleyici Ara ifadeleri gerçekleştirmeyi tercih edebilirsiniz bir *alt duyarlık* kaynak kodunda belirtilenden. Örneğin, ilk kod bloğu bir çift duyarlıklı sürümü kare kökünü işlevi çağırır. Zaman işlevi işlenenleri ve sonuç açıkça tek duyarlıklı için cast gibi bazı durumlarda, fp:fast altında derleyici çift duyarlıklı çağrısı değiştirmeyi seçebilirsiniz `sqrt` tek duyarlıklı çağrısıyla`sqrtf`işlevi. Atamalar girmeden değeri emin olun çünkü `sqrt` ve yakında değeri tek duyarlıklı yuvarlanır, bu yalnızca Yuvarlamanın yer değiştirir. Sqrt gelen değer bir çift duyarlıklı değer bu dönüşüm derleyici gerçekleştirilen oluştuysa, duyarlık BITS kadar yarısı yanlış olabilir.

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

Ancak daha az doğru bu en iyi duruma getirme tek duyarlıklı, iç işlevler sürümleri sağlayın işlemciler hedeflerken özellikle yararlı olabilir `sqrt`. Yalnızca tam olarak derleyici gibi en iyi duruma getirme zaman kullanacağı platform ve içerik bağlıdır.

Ayrıca, hiçbir garanti edilen tutarlılık derleyiciye kullanılabilir tüm duyarlılık düzeyinde gerçekleştirilebilir Ara hesaplamalar kesinlik yoktur. En az kod tarafından belirtilen duyarlık düzeyini korumak derleyici deneyecek rağmen fp:fast iyileştirici alta Ara hesaplamalar için daha hızlı veya daha küçük makine kodu üretmek için sağlar. Örneğin, derleyici daha fazla kodu yukarıda tek duyarlıklı için Ara multiplications bazıları yuvarlanacak en iyi duruma.

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

Bu tür ek yuvarlama SSE2 gibi daha düşük duyarlılık bir kayan nokta birim kullanarak bazı Ara hesaplamalar gerçekleştirmek için neden olabilir. Fp:fast yuvarlama doğruluğunu bu nedenle platform bağlıdır; iyi bir işlemci için derleme kodu için de başka bir işlemci çalışmayabilir. Doğruluk sorunları hızı ağır basıyor varsa belirlemek için kullanıcıya bırakılır.

FP:Fast iyileştirme için belirli bir işlev özellikle sorunlu ise, kayan nokta modu yerel olarak fp için değiştirilebilir: kesin kullanarak `float_control` derleyici pragması.


### <a name="algebraic-transformations-under-fpfast"></a>Fp:fast altında cebirsel dönüşümleri

Belirli ve gerçekleştirmek derleyici fp:fast modunu etkinleştirir kayan için güvensiz cebirsel dönüşümleri ifadeleri gelin. Örneğin, aşağıdaki güvensiz iyileştirmeler fp:fast altında işe.

||||
|-|-|-|
|Özgün kod|#1. adım|#2. adım
|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = y – a – b;`<br/><br/>`c = x – z;`<br/><br/>`c = x * z;`<br/><br/>`c = x - z;`<br/><br/>`c = x + z;`<br/><br/>`c = z-x;`|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = 0;`<br/><br/>`c = x – 0;`<br/><br/>`c = x * 0;`<br/><br/>`c = x - 0;`<br/><br/>`c = x + 0;`<br/><br/>`c = 0 - x;`|`double a, b, c;`<br/>`double x, y, z;`<br/><br/>`y = (a + b);`<br/>`z = 0;`<br/><br/>`c = x;`<br/><br/>`c = 0;`<br/><br/>`c = x;`<br/><br/>`c = x;`<br/><br/>`c = -x;`|

1. adımda derleyici, gözlemleyen `z = y – a – b` her zaman sıfıra eşittir. Bu teknik olarak geçersiz bir gözlem olsa da, fp:fast altında izin verilir. Derleyici sonra z değişkenin sonraki her kullanılacak sabit değer sıfır yayar. 2. adımda, izlenerek derleyici daha fazla iyileştirir `x - 0 == x`, `x * 0 == 0`vb. Yeniden, bu gözlemleri kesinlikle geçerli olmasa da, bunlar fp:fast altında izin verilir. İyileştirilmiş kod artık çok daha hızlıdır, ancak Ayrıca önemli ölçüde daha az kesin veya hatta yanlış olabilir.

Fp:fast modu etkinleştirildiğinde aşağıdaki (güvenli olmayan) cebirsel kurallardan herhangi birinin iyileştiricisi tarafından işe:

|||
|-|-|
|Form|Açıklama|
|`(a + b) + c = a + (b + c)`|İlişkilendirilebilir kuralı ekleme|
|`(a * b) * c = a * (b * c)`|Çarpma ilişkilendirilebilir kuralı|
|`a * (b + c) = a * b + b * c`|Çarpma toplama üzerinden dağıtılması|
|`(a + b)(a - b) = a * a - b * b`|Cebirsel Finansman|
|`a / b = a * (1 / b)`|Multiplicative ters bölme|
|`a * 1.0 = a, a / 1.0 = a`|Çarpma kimliği|
|`a ± 0.0 = a, 0.0 - a = -a`|ADDITIVE kimliği|
|`a / a = 1.0, a - a = 0.0`|İptal Etme|

FP:Fast iyileştirme için belirli bir işlev özellikle sorunlu ise, kayan nokta modu yerel olarak fp için değiştirilebilir: kesin kullanarak `float_control` derleyici pragması.

### <a name="order-of-floating-point-expression-evaluation-under-fpfast"></a>Kayan nokta ifade değerlendirme fp:fast altında sırası

Fp aksine: kesin, fp:fast daha hızlı kod üretmek için kayan nokta işlemlerini yeniden sıralamak derleyici sağlar. Bu nedenle, bazı en iyi duruma getirme fp:fast altında ifadeleri hedeflenen sırasını korumak değil. Örneğin, iki n boyutlu vektör nokta çarpımını hesaplar aşağıdaki işlevi göz önünde bulundurun.

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

FP:Fast altında bir skaler küçültülmesine iyileştirici gerçekleştirebilir `dotProduct` etkili bir şekilde işlevi aşağıdaki gibi dönüştürme işlev:

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

İşlev'in en iyi duruma getirilmiş sürümünde dört ayrı ürün matematiksel aynı anda alınır ve birlikte eklenir. Bu en iyi duruma getirme hesaplama hızlandırabilir `dotProduct` kadar tarafından bir faktör dört hedef işlemci ancak nihai sonucu bağlı olarak gereksiz işlemek için bu nedenle yanlış olabilir. Bu tür iyileştirmeler tek işlevi veya çeviri birimi için özellikle sorunlu varsa, kayan nokta modu yerel olarak fp için değiştirilebilir: kesin kullanarak `float_control` derleyici pragması.

## <a name="the-fpstrict-mode-for-floating-point-semantics"></a>Fp: kayan nokta semantiği için katı mod

Zaman fp: katı mod etkinse, hepsi aynı kuralları için bu fp derleyici aynılarını: kayan nokta işlemleri iyileştirirken kesin kullanır. Bu mod ayrıca kayan nokta özel durum semantik ve duyarlılık FPU ortamına sağlar ve kısaltmalar gibi belirli iyileştirmeleri devre dışı bırakır. Bu işlem, sıkı modudur.

Fp: kayan nokta katı mod kullanılarak etkin [/fp: katı](fp-specify-floating-point-behavior.md) aşağıdaki gibi komut satırı derleyicisi anahtarı:

> cl /fp: katı source.cpp

Bu örnek fp kullanılacak derleyiciye: source.cpp dosyasının kodu oluştururken katı semantiği. Fp: katı model de çağrılabilir bir işlev tarafından işlevi olarak kullanarak `float_control` derleyici pragması.

Daha fazla bilgi için bkz [float_control pragması](#the-float-control-pragma).

Fp altında: katı mod derleyici hiçbir zaman kayan nokta hesaplamaları doğruluğunu perturb iyileştirmeler gerçekleştirir. Derleyici atamaları olarak her zaman doğru yuvarlar, işaretçisine tür olarak atar ve işlev çağrıları ve FPU kaydeder gibi ara yuvarlama tutarlı olarak aynı duyarlık gerçekleştirilir. Kayan nokta özel durum semantik ve FPU ortamı duyarlılık varsayılan olarak etkinleştirilir. Derleyici her durumda doğruluğu garanti edemez çünkü kısaltmalar gibi belirli iyileştirmeler devre dışı bırakılır.

|FP: katı semantiği|Açıklama|
|-|-|
|Semantiği yuvarlama|Açık atamaları olarak yuvarlama işaretçisine tür olarak atar ve işlevini çağırır<br/>Ara ifadeleri kayıt duyarlık değerlendirilir.<br/>Fp aynı: kesin|
|Cebirsel dönüşümleri|Kayan nokta cebiri ilişkilendirilemez, dağıtarak olmayan katı bağlılığı dönüştürme her zaman sağlanır sürece aynı sonuçları üretir.<br/>Fp aynı: kesin|
|Kısaltmalar|Her zaman devre dışı|
|Kayan nokta değerlendirme sırası|Derleyici kayan noktalı bir ifade değerlendirme yeniden değil|
|FPU ortam erişim|Her zaman etkindir.|
|Kayan nokta özel durum semantiği|Varsayılan olarak etkindir.|

### <a name="floating-point-exception-semantics-under-fpstrict"></a>Kayan nokta özel durum semantiği fp altında: katı

Varsayılan olarak, kayan nokta özel durum semantiği altında fp etkinleştirilir: katı modeli. Bu semantiği devre dışı bırakmak için kullanın ya da **/fp: dışında-** geçiş veya oluşabileceğini bir `float_control(except, off)` pragması.

Daha fazla bilgi için bölümlere bakın [kayan nokta özel durum semantiği etkinleştirme](#enabling-floating-point-exception-semantics) ve [float_control Pragması](#the-float-control-pragma).

## <a name="the-fenvaccess-pragma"></a>Fenv_access pragması

Kullanım:

```cpp
#pragma fenv_access( [ on  | off ] )
```

[Fenv_access](../../preprocessor/fenv-access.md) pragma FPU bayrağı testleri ve FPU modu değişiklikleri bozmaya bazı iyileştirmeler yapmak için derleyici sağlar. Zaman durumunu `fenv_access` derleyici varsayabilirsiniz devre dışı olduğundan, varsayılan FPU modları etkindir ve FPU bayrakları değil sınanır. Varsayılan olarak, ortam erişim için fp devre dışıdır: kesin modu, ancak bu pragma kullanarak açıkça etkinleştirilebilir. Fp altında: katı, `fenv_access` her zaman etkin ve devre dışı bırakılamaz. Fp:fast altında `fenv_access` her zaman devre dışı bırakılır ve etkinleştirilemez.

Fp açıklandığı gibi: kesin bölümünde, bazı programcıları yuvarlama yönünü kayan nokta kullanarak değiştirebilir `_controlfp` işlevi. Örneğin, hata üst ve alt sınırları aritmetik işlemler üzerinde işlem için bazı programlar, iki kez aynı hesaplama negatif sonsuz yuvarlama sırasında ilk sonra doğru pozitif sonsuzluk yuvarlama sırasında gerçekleştirin. FPU yuvarlama denetlemek için kullanışlı bir yol sağlayan beri Programcı FPU ortamı değiştirilerek yuvarlama modu değiştirmek seçebilirsiniz. Aşağıdaki kod FPU ortamı değiştirerek bir kayan nokta çarpımı tam hatayla bağlı hesaplar.

```cpp
double a, b, cLower, cUpper;
// . . .
_controlfp( _RC_DOWN, _MCW_RC );    // round to -infinity
cLower = a*b;
_controlfp( _RC_UP, _MCW_RC );       // round to +infinity
cUpper = a*b;
_controlfp( _RC_NEAR, _MCW_RC );    // restore rounding mode
```

Devre dışı bırakıldığında, `fenv_access` pragma varsayılan FPU ortamı varsaymak derleyici sağlar; böylece iyileştirici çağrıları yoksaymak ücretsiz `_controlfp` ve yukarıdaki atamaları azaltmak `cUpper = cLower = a*b`. Ancak, etkinleştirildiğinde, `fenv_access` gibi en iyi duruma getirme engeller.

Programlar, ayrıca belirli kayan nokta hataları algılamak için FPU durum sözcüğünü kontrol edebilirsiniz. Örneğin, aşağıdaki kodu sıfırla bölme ve filtresinin koşullarını denetler

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

Zaman `fenv_access` olan devre dışı, derleyici yürütme böylece FPU durum denetimi büyük olasılıkla subverting kayan nokta ifadeleri sırasını. Etkinleştirme `fenv_access` gibi en iyi duruma getirme engeller.

## <a name="the-fpcontract-pragma"></a>Fp_contract pragması

Kullanım:

```cpp
#pragma fp_contract( [ on | off ] )
```

Fp açıklandığı gibi: kesin, daraltmaya bölümdür birçok modern kayan nokta birimler için temel bir mimari özelliği. Kısaltmalar ek ara yuvarlama hata ile tek bir işlem olarak arkasından bir çarpma gerçekleştirmenize olanak sağlar. Tek bu yönergeleri ayrı yürütme daha hızlı çarpma ve yönergeler ekleyin ve Ara çarpımını yuvarlama olduğundan daha doğru olduğundan. Bir sözleşme işlemi değerini hesaplar `(a*b+c)` sanki iki işlem sırasında sonsuz duyarlık hesaplanan ve ardından yuvarlanır kayan noktalı sayı en yakın. Bu iyileştirme önemli ölçüde birkaç Çarp araya eklemeli içeren işlevlerini hızlandırmak ve işlemleri ekleyin. Örneğin, iki n boyutlu vektör nokta çarpımını hesaplar aşağıdaki algoritmayı göz önünde bulundurun.

```cpp
float dotProduct( float x[], float y[], int n )
{
   float p=0.0;
   for (int i=0; i<n; i++)
      p += x[i]*y[i];
   return p;
}
```

Bu hesaplama gerçekleştirilen bir dizi Çarp ekleme yönergeleri biçiminde `p = p + x[i]*y[i]`.

[Fp_contract](../../preprocessor/fp-contract.md) pragma kayan nokta ifadeleri sözleşme yapılan olup olmadığını belirtir. Varsayılan olarak, fp: kesin mod, doğruluk ve hız artırmak bu yana kısaltmalar için sağlar. Kısaltmalar fp:fast modu için her zaman etkindir. Ancak, hata koşullarını açık algılanması kısaltmalar bozmaya çünkü `fp_contract` pragma her zaman altında fp devre dışı: katı mod. Olabilir ifadeleri örnekleri ne zaman sözleşme yapılan `fp_contract` pragma etkinleştirildi:

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

**/Fp: kesin**, **/fp:fast**, **/fp: katı** ve **/fp: dışında** anahtarları denetleyen bir tarafından-dosya üzerinde kayan nokta semantiği temel. [Float_control](../../preprocessor/float-control.md) pragma işlevi tarafından işlevi temelinde böyle bir denetim sağlar.

Kullanım:

```cpp
#pragma float_control(push)
#pragma float_control(pop)
#pragma float_control( precise, on | off [, push] )
#pragma float_control( except, on | off [, push] )
```

Pragmaları `float_control(push)` ve `float_control(pop)` sırasıyla itme ve kayan nokta modu ve özel durum seçeneği bir yığın üzerine geçerli durumunu açılır. Unutmayın durumunu `fenv_access` ve `fp_contract` pragma etkilenmez `pragma float_control(push/pop)`.

Pragma çağırma `float_control(precise, on)` etkinleştirir ve `float_control(precise, off)` modu kesin semantiği devre dışı bırakır. Benzer şekilde, pragma `float_control(except, on)` etkinleştirir ve `float_control(except, off)` özel durum semantiği devre dışı bırakır. Özel durum semantiği, yalnızca kesin semantiği de etkinleştirilir etkinleştirilebilir. Olduğunda isteğe bağlı `push` bağımsız değişkeni varsa, durumlarını `float_control` seçenekleri semantiği değiştirmeden önce kalan.

### <a name="setting-the-floating-point-semantic-mode-on-a-function-by-function-basis"></a>Bir işlev tarafından işlevi temelinde kayan nokta anlamsal modunu ayarlama

Komut satırı anahtarları aslında dört farklı kayan nokta pragmaları ayarlamak için toplu var. Belirli bir kayan nokta anlamsal modu işlevi tarafından işlevi temelinde açıkça seçmek için her biri aşağıdaki tabloda açıklandığı gibi dört kayan nokta seçeneği pragmaları seçin:

||||||
|-|-|-|-|-|
||float_control(Precise)|float_control(except)|fp_contract|fenv_access|
|/FP: katı|on|on|Kapalı|on|
|/FP: katı /fp: dışında-|on|Kapalı|Kapalı|on|
|/FP: kesin|on|Kapalı|on|Kapalı|
|/FP: kesin /fp: dışında|on|on|on|Kapalı|
|/FP:Fast|Kapalı|Kapalı|on|Kapalı|

Örneğin, aşağıdaki açıkça fp:fast semantiği sağlar.

```cpp
#pragma float_control( except, off )   // disable exception semantics
#pragma float_control( precise, off )  // disable precise semantics
#pragma fp_contract(on)                // enable contractions
#pragma fenv_access(off)               // disable fpu environment sensitivity
```

> [!Note]
> Özel durum semantiği devre dışı "tam" semantiği kapatmadan önce kapatılması gerekir.

## <a name="enabling-floating-point-exception-semantics"></a>Kayan nokta özel durum semantiği etkinleştirme

Sıfıra bölme gibi olağanüstü belirli kayan nokta koşullar, bir donanım özel durumu sinyal FPU neden olabilir. Kayan nokta özel durumlar, varsayılan olarak devre dışıdır. Kayan nokta özel durumlar FPU denetim sözcüğü ile değiştirerek etkin `_controlfp` işlevi. Örneğin, aşağıdaki kod sıfırla bölme kayan nokta özel durum etkinleştirir:

```cpp
_clearfp(); // always call _clearfp before
            // enabling/unmasking a FPU exception
_controlfp( _EM_ZERODIVIDE, _MCW_EM );
```

Sıfırla bölme özel durumu etkinleştirildiğinde, sıfıra payda eşit olan herhangi bir bölme işlemi bildirilmesini FPU özel duruma neden olur.

Varsayılan mod FPU denetim sözcüğü geri yüklemek için arama `_controlfp(_CW_DEFAULT, ~0)`.

Kayan nokta özel durum semantiği ile etkinleştirme **/fp: dışında** bayrağı kayan nokta özel durumlar etkinleştirme ile aynı değil. Kayan nokta özel durum semantiği etkinleştirildiğinde, derleyici herhangi bir kayan nokta işlemi bir özel durum yaratabilir bulundurmalıdır. FPU ayrı işlemci birim olduğundan, diğer birimleri yönergeler eşzamanlı FPU üzerinde yürütme yönergeleri gerçekleştirilebilir.

Bir kayan nokta özel durumu etkinleştirildiğinde, FPU sorunlu yönerge yürütülmesini durdurmak ve ardından bir olağanüstü durum FPU durum sözcüğünü ayarlayarak sinyal. CPU sonraki kayan nokta yönergesi ulaştığında, önce bekleyen FPU özel durumlar için denetler. Bekleyen bir özel durum ise, işlemci, işletim sistemi tarafından sağlanan bir özel durum işleyici çağırarak yakalar. Bu, bir kayan noktalı işlem bir olağanüstü durum karşılaştığında, sonraki kayan nokta işlemi yürütülene dek karşılık gelen özel durum algılanmaz, anlamına gelir. Örneğin, aşağıdaki kod bir bölme sıfıra özel yakalar:

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

Sıfırla bölme koşul ifade oluşursa bir = b/c FPU yakalama/2.0 ifadesindeki sonraki kayan nokta işlemi kadar özel durum olursa olmaz * b. Bu durum şunlara sebep olur:

```Output
This line shouldn't be reached when c==0.0
SEH Exception Detected
```

Çıktı ilk satırına karşılık gelen printf henüz gelmemiş; yürütme 2.0 sınırına kadar tarafından ifade b/c neden kayan nokta özel durumu değildi çünkü ulaşıldı * b. B/c yürütme hemen sonra özel durum yükseltmek için derleme "bekleme" yönerge girmeniz gerekir:

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

Bu "bekleyin" yönerge işlemcisi FPU durumuyla eşitlemek ve bekleyen tüm özel durumları işleme zorlar. Derleyici yalnızca bunlar oluşturacak "kayan nokta semantiği etkinleştirildiğinde yönergeleri bekleyin". Varsayılan olarak bu semantiği, devre dışı bırakıldığında, programlar kayan nokta özel durumlar kullanırken yukarıdaki benzer synchronicity hatalarla karşılaşabilir.

Kayan nokta semantiği etkinleştirildiğinde, derleyicinin yalnızca "bekleme" yönergeleri tanıtılacaktır değil, olası özel durumlar varlığında kayan nokta kodu yasadışı iyileştirme onu derleyici de engeller. Bu, özel durumlar noktaları alter herhangi bir dönüştürme içerir. Bu etkenler nedeniyle kayan nokta semantiği etkinleştirme böylece uygulamanın performansını düşürmesini oluşturulan makine kod verimliliğini önemli ölçüde düşürebilir.

Kayan nokta özel durum semantiği fp altında varsayılan olarak etkindir: katı mod. Bu semantiği fp içinde etkinleştirmek için: kesin modu eklemek **/fp: dışında** geçiş komut satırı derleyicisi. Kayan nokta özel durum semantiği de etkinleştirilebilir ve bir işlev tarafından işlevi olarak kullanarak devre dışı `float_control` pragması.

### <a name="floating-point-exceptions-as-c-exceptions"></a>C++ özel durum olarak kayan nokta özel durumlar

Olarak tüm donanım istisnalar kayan nokta özel durumlar doğası gereği C++ özel durum neden, ancak bunun yerine yapılandırılmış özel durum tetikler. C++ özel durumlarını kayan nokta yapılandırılmış özel durum eşlemek için kullanıcıların özel SEH özel durum Çevirmen ortaya çıkarabilir. İlk olarak, her kayan nokta özel durumu için karşılık gelen bir C++ özel durum tanıtmaktadır:

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

Ardından, bir kayan nokta SEH özel algılar ve karşılık gelen C++ özel durum bir çeviri işlev tanıtır. Bu işlevi kullanmak için geçerli işlem iş parçacığı ile yapılandırılmış özel durum işleyici Çeviricisi ayarlamak [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md) Çalışma Zamanı Kitaplığı'ndan işlevi.

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

Bu eşleme başlatıldıktan sonra kayan nokta özel durumlar C++ özel durumlarını olsa gibi davranır. Örneğin:

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

[Ne her bilgisayar Bilimcisi kayan nokta aritmetik hakkında bilmeniz gereken](http://pages.cs.wisc.edu/~david/courses/cs552/S12/handouts/goldberg-floating-point.pdf) David Goldberg tarafından.

## <a name="see-also"></a>Ayrıca bkz.

[Kodunuzu İyileştirme](optimizing-your-code.md)<br/>
