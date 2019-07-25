---
title: Ekleme İşleçlerini Kullanma ve Biçimi Denetleme
ms.date: 11/04/2016
helpviewer_keywords:
- insertion operators
ms.assetid: cdefe986-6548-4cd1-8a67-b431d7d36a1c
ms.openlocfilehash: 2cf399501c0eab32e8bee80dfcb98d870c0193cb
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458017"
---
# <a name="using-insertion-operators-and-controlling-format"></a>Ekleme İşleçlerini Kullanma ve Biçimi Denetleme

Bu konu, biçimin nasıl kontrol ve kendi sınıflarınız için ekleme işleçleri nasıl oluşturulacağını gösterir. Tüm standart **<<** C++ veri türleri için önceden programlanan ekleme () işleci, bir çıkış akışı nesnesine bayt gönderir. Ekleme işleçleri, varsayılan tamsayı bağımsız değişkenlerinin biçimini değiştiren öğeler olan önceden tanımlanmış "düzenlemeler" ile çalışır.

Aşağıdaki seçeneklerle biçimi denetleyebilirsiniz:

- [Çıkış genişliği](#vclrfoutputwidthanchor3)

- [Hizalar](#vclrfalignmentanchor4)

- [Duyarlılık](#vclrfprecisionanchor5)

- [Taban](#vclrfradixanchor6)

## <a name="vclrfoutputwidthanchor3"></a>Çıkış genişliği

Çıktıyı hizalamak için, her bir öğe için çıkış genişliğini, akışı akışa yerleştirerek `setw` veya `width` üye işlevini çağırarak belirlersiniz. Bu örnek, bir sütundaki değerleri en az 10 karakter genişliğinde sağa hizalar:

```cpp
// output_width.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   double values[] = { 1.23, 35.36, 653.7, 4358.24 };
   for( int i = 0; i < 4; i++ )
   {
      cout.width(10);
      cout << values[i] << '\n';
   }
}
```

```Output
      1.23
     35.36
     653.7
   4358.24
```

Baştaki boşluklar 10 karakterden daha kısa bir değere eklenir.

Bir alanı doldurma için, belirtilen genişliğe `fill` sahip alanlar için doldurma karakterinin değerini ayarlayan member işlevini kullanın. Varsayılan değer boş bir değer. Sayıların sütununu yıldız işaretiyle birlikte bırakmak için, önceki **for** döngüsünü aşağıdaki gibi değiştirin:

```cpp
for (int i = 0; i <4; i++)
{
    cout.width(10);
    cout.fill('*');
    cout << values[i] << endl;
}
```

İşleici, yeni satır karakterinin (`'\n'`) yerini alır. `endl` Çıktı şöyle görünür:

```Output
******1.23
*****35.36
*****653.7
***4358.24
```

Aynı satırdaki veri öğelerinin genişliğini belirtmek için, şu öğeyi kullanın `setw` :

```cpp
// setw.cpp
// compile with: /EHsc
#include <iostream>
#include <iomanip>
using namespace std;

int main( )
{
   double values[] = { 1.23, 35.36, 653.7, 4358.24 };
   char *names[] = { "Zoot", "Jimmy", "Al", "Stan" };
   for( int i = 0; i < 4; i++ )
      cout << setw( 7 )  << names[i]
           << setw( 10 ) << values[i] << endl;
}
```

Üye işlevi iostream > içinde \<bildirilmiştir. `width` Ya da bağımsız `setw` değişkenlerle başka bir işleyici kullanırsanız, iomanıp > dahil \<etmeniz gerekir. Çıktıda dizeler, genişlik 6 ve tamsayı 10 ' un bulunduğu bir alanda yazdırılır:

```Output
   Zoot      1.23
  Jimmy     35.36
     Al     653.7
   Stan   4358.24
```

Değerleri `setw` ne `width` de keser. Biçimlendirilen çıktı genişliği aşarsa, akışın duyarlık ayarına bağlı olarak tüm değer yazdırılır. Her ikisi de `setw` yalnızca aşağıdaki alanı etkiler.`width` Alan genişliği, bir alan yazdırıldıktan sonra varsayılan davranışına (gerekli genişlik) geri döner. Ancak, diğer akış biçimi seçenekleri değiştirilene kadar yürürlükte kalır.

## <a name="vclrfalignmentanchor4"></a>Hizalar

Çıkış akışları varsayılan olarak sağa hizalanmış metne sahiptir. Önceki örnekteki adları Sola hizalamak ve sayıları sağa hizalamak için, **for** döngüsünü aşağıdaki gibi değiştirin:

```cpp
for (int i = 0; i <4; i++)
    cout << setiosflags(ios::left)
         << setw(6) << names[i]
         << resetiosflags(ios::left)
         << setw(10) << values[i] << endl;
```

Çıktı şöyle görünür:

```Output
Zoot        1.23
Jimmy      35.36
Al         653.7
Stan     4358.24
```

Sol hizalama bayrağı, `left` Numaralandırıcı ile [setiosflags](../standard-library/iomanip-functions.md#setiosflags) işleici kullanılarak ayarlanır. Bu Numaralandırıcı [iOS](../standard-library/basic-ios-class.md) sınıfında tanımlanmıştır, bu nedenle başvurusu **iOS::** prefix içermelidir. [Resetiosflags](../standard-library/iomanip-functions.md#resetiosflags) işleici, Sola Hizala bayrağını kapatır. Ve `width` `setiosflags` öğelerinden farklı olarak, ve`resetiosflags` etkileri kalıcı olur. `setw`

## <a name="vclrfprecisionanchor5"></a>Duyarlılık

Kayan nokta duyarlılığı için varsayılan değer altıdır. Örneğin 3466,9768 sayısı 3466,98 olarak yazdırılır. Bu değerin yazdırma şeklini değiştirmek için [setprecision](../standard-library/iomanip-functions.md#setprecision) işleici ' ı kullanın. İşleici için iki bayrak vardır: [fixed](../standard-library/ios-functions.md#fixed) ve [bilimsel](../standard-library/ios-functions.md#scientific). [Sabit](../standard-library/ios-functions.md#fixed) ayarlandıysa, sayı 3466,976800 olarak yazdırılır. `scientific` Ayarlanırsa, 3.4669773 + 003 olarak yazdırır.

[Hizalama](#vclrfalignmentanchor4) halinde gösterilen kayan nokta numaralarını tek bir anlamlı sayıyla göstermek için, **for** döngüsünü aşağıdaki gibi değiştirin:

```cpp
for (int i = 0; i <4; i++)
    cout << setiosflags(ios::left)
         << setw(6)
         << names[i]
         << resetiosflags(ios::left)
         << setw(10)
         << setprecision(1)
         << values[i]
         << endl;
```

Program bu listeyi yazdırır:

```Output
Zoot          1
Jimmy     4e+01
Al        7e+02
Stan      4e+03
```

Bilimsel gösterimi ortadan kaldırmak için, **for** döngüsünden önce bu ifadeyi ekleyin:

```cpp
cout << setiosflags(ios::fixed);
```

Sabit gösterim ile program, ondalık ayırıcıdan sonra bir basamakla yazdırılır.

```Output
Zoot         1.2
Jimmy       35.4
Al         653.7
Stan      4358.2
```

`ios::fixed` Bayrağını olarak`ios::scientific`değiştirirseniz program şunu yazdırır:

```cpp
Zoot    1.2e+00
Jimmy   3.5e+01
Al      6.5e+02
Stan    4.4e+03
```

Yine, program ondalık noktadan sonra bir basamak yazdırır. Ya da `ios::fixed` `ios::scientific` ayarlanmışsa duyarlık değeri, ondalık ayırıcıdan sonraki basamak sayısını belirler. Bayrak ayarlanmazsa duyarlık değeri, toplam önemli basamak sayısını belirler. `resetiosflags` İşleici bu bayrakları temizler.

## <a name="vclrfradixanchor6"></a>Taban

`dec`, Ve `oct` işleçörler,girişve`hex` çıkış için varsayılan taban 'i ayarlar. Örneğin, bir işleyiciyi çıkış akışına eklerseniz `hex` , nesne tamsayıların iç veri gösterimini onaltılık çıkış biçimine doğru bir şekilde çevirir. [Büyük harfli](../standard-library/ios-functions.md#uppercase) bayrak açık ise (varsayılan), sayılar a ile f arasındaki rakamlarla birlikte görüntülenir. Aksi takdirde, büyük harfle görüntülenir. Varsayılan taban `dec` (Decimal).

## <a name="quoted-strings-c14"></a>Alıntılanmış dizeler (C++ 14)

Bir akışa bir dize eklediğinizde, stringstream:: Str () üye işlevini çağırarak aynı dizeyi kolayca geri alabilirsiniz. Ancak, akışı sonraki bir noktada yeni bir dizeye eklemek için ayıklama işlecini kullanmak istiyorsanız, varsayılan olarak > > işleci ilk boşluk karakteriyle karşılaştığında durabileceğinden, beklenmeyen bir sonuç alabilirsiniz.

```cpp
std::stringstream ss;
std::string inserted = "This is a sentence.";
std::string extracted;

ss << inserted;
ss >> extracted;

std::cout << inserted;     //  This is a sentence.
std::cout << extracted;    //  This
```

Bu davranış el ile aşılır, ancak dizeyi yuvarlak bir şekilde daha kullanışlı hale getirmek için, c++ 14, ıomanıp > `std::quoted` içindeki \<akış işletörü ekler. Ekleme sırasında, `quoted()` dizeyi bir sınırlayıcı ile çevreler (' "' çift tırnak işareti) ve ayıklama işlemi son sınırlayıcıyla karşılaşana kadar tüm karakterleri ayıklamak için akışı yönetir. Herhangi bir katıştırılmış tırnak işareti kaçış karakteriyle (varsayılan olarak '\\\\') atlanmalıdır.

Sınırlayıcılar yalnızca Stream nesnesinde mevcuttur; Bunlar ayıklanan dizede mevcut değildir, ancak [basic_stringstream:: Str](../standard-library/basic-stringstream-class.md#str)tarafından döndürülen dizede bulunur.

Ekleme ve ayıklama işlemlerinin boşluk davranışı, bir dizenin kodda nasıl temsil edildiğine bağlıdır, bu nedenle, giriş dizesinin bir ham dize sabit değeri veya normal bir dize olmasına bakılmaksızın tırnak içine alınmış operatör yararlı olur. Bir giriş dizesinin biçimi ne olursa olsun, gömülü tırnak, satır sonları, sekmeler vb. olabilir ve bunların hepsi, tırnak işaretleri () işleküleyici tarafından korunur.

Daha fazla bilgi ve tam kod örnekleri için bkz. [alıntı](../standard-library/iomanip-functions.md#quoted).

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış Akışları](../standard-library/output-streams.md)
